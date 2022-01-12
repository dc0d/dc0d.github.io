---
title: 'Disposable Ideas'
date: 2022-01-07T15:27:59+01:00
draft: false
comment: false
tags: ['programming']
categories: ['journals']
keywords:
  [
    'tdd',
    'ddd',
    'domain driven design',
    'clean architecture',
    'ports and adapters',
    'hexagonal architecture'
  ]
---

![disposable-ideas](/images/2022/disposable-ideas.jpg 'https://commons.wikimedia.org/wiki/File:BrokenConcretion22.jpg')

## Key Takeaways

- Here a style of thinking - and some questions - about software development is put forward. It is a personal practice in note-taking and communicating thoughts.
- The first step in software development is to run the application, not design or write the code. It was like this, since before Smalltalk. The code is just a representation of the running application.
- There are two major decisions to make in software development, deciding what to keep, deciding what things to leave out. One is incomplete without the other[^1].
- The main focus in software development is the running application - not the code. Fixing the bugs is fixing the executions - thousands of them, running per second. The bug is not _happening_ in the code, once, in one place. At each moment, the bug is happening in a system in numerous instances of executions.
- Running application is an asset and must be reliable. Code is a liability and must be disposable.

## Prelude

As humans, we live inside the language. If the language is removed from a human being, the remaining entity will be a mammal, a primate driven by instincts. Many pieces of research show how language shapes our minds. In one such research, a small community was found on the western edge of Cape York, in northern Australia, the Kuuk Thaayorre. While talking about space "instead of words like "right," "left," "forward," and "back," which, as commonly used in English, define space relative to an observer, the Kuuk Thaayorre, use cardinal-direction terms - north, south, east, and west - to define space.” That property in their language, helps them to be more aware of their surroundings and stay coordinated all the time[^2] - their minds work that way because their language works that way.

Through language, humans conduct business. From a high-level point of view, a business is a group of humans, as intelligent actors, with a certain level of autonomy, who can understand, process, and execute the language inside a context and make confident choices and decisions. Software development is the process of incorporating an artificial, intelligent agent into the current business workflow, which can process and execute textual instructions, with a certain level of autonomy, and make choices and decisions in the context of those instructions, which is a subset of the context of the business.

This has some interesting implications. For example, it shows the importance of Ethical AI. Currently, probably for the first time in human history, an autonomous system is created that operates outside of the boundaries of the human language - it operates outside of the human world: the language[^3]. Is there an AI shutdown button? It would be very difficult to even define a predicate that could trigger such a shutdown process. How to describe something outside the language?

The other implication that is closer to the purpose of this text is the need for having a reliable conversation for humans to be able to move the business forward. The idea of structured conversations is pretty well known in many domains and fields. For example, In the field of law, all participants in a courtroom are familiar with a particular vocabulary and understand the mechanics of the interconnections between the concepts defined in that vocabulary. Same stands for different fields of healthcare. All members of a surgical team are fluent in the language, through which they cooperate in moving forward the operation and at the same time keep the vital signs of the patient stable. The smallest sloppiness in interpreting any of the conversations inside the operating room, which are going on between humans, or between humans and devices, can end in the death of the patient. Another domain, in which structured conversations are well known, is the world of tabletop role-playing games, which is very different from the other two[^4]. The purpose of a structured conversation is for a group of cooperating agents to achieve a collective understanding and come to an agreement about a choice and make a decision.

It is an interesting observation to see that a structured conversation is readily available to all participants in such different fields, but not in software development. Why? One reason could come from the fact that in software development, we need to work with more than one set of vocabulary from different fields simultaneously. The first conversation framework is for having a structured conversation about the business. The second framework is for having a structured conversation about the technical side. Also, a third framework must be maintained, which maps the vocabulary and the mechanics of the first group of conversations to the second one. DDD paints a detailed landscape in which these areas are pictured in detail through mapping the first conversation framework (problem space) to the second conversation framework (solution space)[^5]. And practical practices like Event Storming can be employed to execute such structured conversations.

Something that has a special place in this graph of conversations is having an idea about the costs and consequences of the choices made.

## Disposable Decisions

If the decisions made are disposable, we can undo them without regret. New decisions are made at each iteration of the whole business conversation cycle, and new requirements and bugs are discovered. These decisions and discoveries will be mapped and translated into a technical conversation. And those technical conversations are transcribed as code and fed into the application. The most brittle link in the chain of a business conversation is the code because it needs to reflect both the business and the technical decisions - all the vocabulary, rules, policies, and predicates that trigger the success or determine the failure in each step. The code contains the history of all conversations that happened in the business. From the business conversation to mapping to technical conversation, including the code, and to the next iteration of the business conversation, an ongoing process of refinement is needed to keep the deviation in vocabulary and mechanics to a minimum - based on the feedback from the previous cycle and the current discoveries and decisions. Since the code is the most inflexible element in the business context, it should be readily disposable without slowing down other business activities.

## Rigid Code & Disposable Code

Rigid code is hard to change. It is slow in reacting to the natural stream of changes and bugs. It does not have clear boundaries, and any changes cause never-ending ripples that bounce back to other conversations and affect all aspects of the business. It is full of mysterious patches that no one dares to approach. It sticks, and it is persistent. Disposable code has clear boundaries that make it simpler to unplug an unhealthy component and redirect the flow to a healthy substitute at the same time. It is reusable by design. But not all reusable codes are disposable.

Here are some causes - choices & decisions - that can make a business conversation end in rigid code or disposable code.

### Decompose Using Procedural Calls & Decompose Using Messages

Coupling appears at both design time and runtime. Design time coupling happens when the technical conversation has not resulted from a well-mapped business conversation. The result is a collection of code artifacts that have multiple natures at the same time. The business-specific code, the application-specific code, and the technology-specific code can be found throughout the whole code-base and inside each other.

In disposable code, the business-specific parts do not rely on any other kinds of code (application-specific code or technology-specific code). This is the core model of an application. Suppose a business policy ends in sending an email. The technology-specific code sends a message (in OOP terms) to some downstream interactor, behind a protocol, without having any knowledge about it. The interactors are application-specific. They react to the incoming signals and trigger the business-specific code model with a translated signal. Also, they can be triggered by a signal from the core model. In turn, the driven interactors will signal some technology-specific code - which might persist some data inside a database or make a call to a telemetry service[^6].

The runtime-coupling is created when the availability of one service or resource in the system affects the other ones. This happens when the technical conversation has incorporated some vocabulary and mechanics that are not well mapped/translated from/to the business conversation. One typical decision pattern that ends in runtime-coupling is when a local message sending or a local procedure call is converted to a synchronous remote call. If there are any problems in the local procedure calls, now a new set of the issues is added on top of that, like cases of unavailable services and resources, timeouts, complex retry policies for the remote calls (not the retries for the business logic, which is different) and the like. Synchronous remote procedure calls are helpful mainly for CRUD-base stateless actions when scalability is a concern. They do not address availability because the two services are still tightly coupled.

For making the different parts of the system loosely-coupled, the same central concept from OOP can be applied, messaging. By hiding implementation behind a message[^7], that part becomes disposable. These two parts can react to changes independently because instead of depending on each other, they depend on a set of shared abstractions: the messages.

In both cases, disposable code is decomposed using messaging, making polymorphism possible, reducing execution paths. Because the disposable code holds no knowledge about its collaborators, other than the messages they understand, their interface. So it will not decide who will receive that message, the actual collaborator or a double that takes its place and mimics its role (not its implementation), which makes testing the disposable code much faster.

## Move Fast & Change Fast

The designing part of a technical conversation - in this context, the conversation between the human and the device - requires some additional decisions to be made. This technical side of the conversation has some operational costs. It has to be maintained for long periods in a sustainable way. Suppose decisions made on this side (the solution space) are not disposable. The increasing complexity of the interconnections between different parts[^8] will make the whole business conversation much slower, ending in longer iterations.

If the word fast is incorporated into the vocabulary of the business, we need to be aware of its implications. The goal usually is to deliver fast. But if the plan is to move fast, and drop the refinement process, then in the face of new changes or bugs, the system can not react quickly, because it is not made that way. These two families of design decisions - the move-fast and the change-fast design decisions - can not easily coexist in the history of all the business conversations: the code. A poetic analogy and parallel to move-fast/change-fast duality is Heisenberg's Uncertainty Principle. This principle indicates that it is not possible to measure both the momentum and position on a particle/wave simultaneously. Similarly, we cannot both move fast and change fast at the same time. Code that is created through focusing on moving fast through building concrete blocks can not be mended. Such code can not react to change and is not readily disposable. On the other hand, by focusing on reacting fast, any part of the system can change fast. Always choose a change-fast mindset over a move-fast mindset to be able to make disposable software artifacts.

The main focus should be the running application, not the code, to minimize the feedback time. The code is just a representation of the running application. Keeping this mindset is a proper approach for verifying if the code is disposable or not. Long feedback loops cause the code to lose its integrity, flexibility, and contact with the domain model.

## Summary

As the code ages, the design decisions made through all the business cycles descend deeper into the system’s structure, like the fossils in different geological layers. If those design decisions are not disposable, it is tough to make any changes, whether changes are coming from a new requirement or a bug. Because the older they are, the more parts depend on them. We should favor the change-fast decisions over move-fast decisions, disposable code vs layer of patches[^9].

[^1]: Making these decisions attentively, helps create focused units of artifacts, focused tests, and have focused error paths.
[^2]: "Follow me to Pormpuraaw, a small Aboriginal community on the western edge of Cape York, in northern Australia. I came here because of the way the locals, the Kuuk Thaayorre, talk about space. Instead of words like "right," "left," "forward," and "back," which, as commonly used in English, define space relative to an observer, the Kuuk Thaayorre, like many other Aboriginal groups, use cardinal-direction terms — north, south, east, and west — to define space.1 This is done at all scales, which means you have to say things like "There's an ant on your southeast leg" or "Move the cup to the north northwest a little bit." One obvious consequence of speaking such a language is that you have to stay oriented at all times, or else you cannot speak properly. The normal greeting in Kuuk Thaayorre is "Where are you going?" and the answer should be something like " Southsoutheast, in the middle distance." If you don't know which way you're facing, you can't even get past 'Hello.'" - [Source](https://www.edge.org/conversation/lera_boroditsky-how-does-our-language-shape-the-way-we-think).
[^3]: Human textual/verbal/pictorial language is a subset of a infinite set of textual/verbal/pictorial possibilities. Human language is about human things. An AI textual/verbal/pictorial language does not have that limitation/requirement - to be limited to humans. So, it can operate beyond human language.
[^4]: The players in a tabletop RPG use a conversation system for making a collective judgment about the fiction.
[^5]: The advantage of keeping the technical conversations (for example, through the specifications or the code) and business conversations is "Tightly relating the code to an underlying model gives the code meaning and makes the model relevant." - [Source](https://domainlanguage.com/wp-content/uploads/2016/05/DDD_Reference_2015-03.pdf)
[^6]: This design can be found in Hexagonal Architecture, Ports & Adapters, and similar designs.
[^7]: Objects react to messages (the stimulus) employing a certain method. The way the methods are implemented, can be hid behind a protocol (also called interface) which describes which set of messages (verbs plus arguments) an object can react to.
[^8]: the vocabulary and the mechanics of the model, the software artifacts that are made using that model, and the increasing deviation between the model and the software artifacts
[^9]: Polly want a message - Sandi Metz [Talk](https://youtu.be/XXi_FBrZQiU)