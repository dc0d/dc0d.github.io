---
title: "A Study In Reliable Messaging Without Distributed Transactions"
date: 2021-03-05T22:09:21+01:00
draft: false
tags: ["aws", "golang"]
---

In a Microservice Architecture, some services update an entity. A service that updates an entity, might need to send an event to a down-stream service, to inform it about the update. The problem is, these two actions - updating a database and sending a message to a queue - can not be guaranteed to be completed transactionally. What if updating the database fails, but a message be sent to the queue? What if the database is updated, but sending the message to the queue fails?

This description of the problem is for the purpose of demonstration. An example implementation is also provided. The first property of our service - and also the down-stream service - is idempotency[^1].


# Idempotency

To achieve idempotency, the service needs to keep track of the incoming events. When the service receives a new message from the queue, the first step is to look up in the list of the incoming messages that are already processed. If the incoming message is already processed, the service will ignore the message and delete it from the queue. This way, in case the service receives a message twice, it will process it only once.

![idempotency](/images/2021/idempotency.png "idempotency")

If the incoming message is a new one, the service will proceed to the next step.

# Processing The Incoming Message

After making sure that the incoming message is new and not processed yet, the service will process the incoming message and update the entity. It will load the previous state of the entity and changed it based on the new update that it received and the related logic. The data object that persists in the entity, needs to have a special field that will be used for optimistic concurrency which helps to avoid any conflicts while updating an entity. This way, if the entity is being updated by another process in the service, they will not overwrite the changes that are made and one of these two updates will fail.

But, the entity must be updated in a transaction. Two other tables will change within this transaction.

The first table is a table for keeping track of incoming messages. Which helps with achieving idempotency.

The second table contains the outgoing notification messages that the service needs to send out to down-stream listeners.

![transactional-process](/images/2021/transactional-process.png "transactional-process")

After this transaction is completed, the process will delete the incoming message that is successfully processed.

# Outgoing Notification

A notifier process in the service will poll the outgoing notification messages table. When an outgoing notification appears in the table, the notifier process, will read that message, sends it to a queue, and then delete the record from the queue. To have a smoother stream of notifications, optionally, the main process can trigger the notifier process to wake up and take care of outgoing messages.

![outgoing-notification](/images/2021/outgoing-notification.png "outgoing-notification")

In the provided example, the notification part is implemented using dynamodb streams, which triggers a lambda function that acts as the notifier. In this example, the notifier does not poll the outgoing notification messages table and relies on this feature that is provided by the infrastructure.

# Example Implementation

The service is implemented using Go Programming Language. The deployment to AWS Cloud is implemented using AWS CDK, which contains three stacks for data, messaging, and the service. The delivery code can be found inside `cmd` directory and the core model for the application is inside `core` directory[^2]. There are rooms for improvement in the code but the goal was to put forward a demonstration on how these ideas could be put into practice. It can be found in this [repository](https://github.com/dc0d/reliable-messaging).

[^1]: [Reliable Messaging Without Distributed Transactions](https://vimeo.com/111998645)
[^2]: [IDD](https://www.youtube.com/watch?v=dYvSaajboEs)
