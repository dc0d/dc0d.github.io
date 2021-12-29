---
title: "What is Software Development?"
date: 2020-03-07T04:58:23+01:00
draft: false
tags: ["agile", "tdd"]
---

![alt text](/images/agile-in-practice.png "Agile In Practice")

>   - This is a work-in-progress - and will be so for some time.
>   - It is picturing how one could think about Software Development - one of many possible ways.
>   - Tradeoffs are made - the main goal here was/is to communicate.

**_Niklas:_** Something feels broken about all that code we have.

**Edmond:** Maybe. But aren't you making money?

**_Niklas:_** We do. But doing anything new is hard, changing or fixing stuff is hard, everything feels so slow, so ineffective. We have to constantly put too much lipstick on the pig, so the customer continues to like it. I wonder if we are also constantly lying to ourselves.

**Edmond:** How so?

**_Niklas:_** It is a constant battle. It's a 24/7 firefighting. Yes, there are all sorts of alarms, monitoring and automated stuff there. To be honest it feels like we are automating shit! Everything is red all the time. Nobody actually cares anymore. We all just want to be done with office hours and we pray on the _"standby"_.

**Edmond:** Have you come up with any ideas about the whole thing? I mean, what's the cause of this?

**_Niklas:_** Came up with lots of ideas! Lots of them! Even tried some of them. None worked. I ran out of ideas. I wonder, what am I doing? What am I trying to achieve? What in the world is this _Software Development_ thing?

**Edmond:** Indeed. Let's have at it.


## What is Software Development?


**Edmond:** So, what do _you_ think Software Development is?

**_Niklas:_** I am not going to say _writing code_. And I'm sure it's different from _manufacturing_, right?

**Edmond:** Yes. When a factory manufactures a car, it can be used only by one client - unless we could send that one single car into parallel universes.

**_Niklas:_** I've heard it's been compared to gardening. You can find _similarities_ for sure. But it doesn't make that much sense.

**Edmond:** Yeah, no. A plant does most of the job of growing by itself. You just provide some support, like fertilizers. The code does not grow by itself no matter how much fertilizer you provide.

**_Niklas:_** OK, in Software Development we define and introduce something once and use it in many different places. Can we say that?

**Edmond:** You mean something like _Law-Making_? Well; possibly; close enough. You write the law once and every person has to comply. Except that there is no feedback mechanism to evaluate what you have made. And nobody cares these days - politics I mean. But software needs to work and we need a way to prove it's working properly - or at least that's the assumption. So, _what is Software Development_? Let's come back to this question later.


## Code vs Artifact (Product)


Code vs Artifact (Product) dichotomy is all wrong. We are not actually selling a product - in a conventional industrial sense. We are selling functionality.

It's Code vs _Execution_. We sell _Executions_. We make money from each and every _Execution_ of the code.

A Software Product is just a packaging and delivery mechanism to provide that functionality to the customer. And the customer has access to that functionality at any time she/he has a need for that functionality.

Each Execution of the code is a demonstration of that functionality.

That's how we should think about Software Development: It's _Code vs Execution_. That should be _the base for all the judgments that we make about each step in Software Development_.

Each proper Execution means money. Failure to improve the Execution, in an acceptable cost-window, means the money is not coming to you - which will go to your competitor. Each bad Execution means loss of money.


## Code vs Execution


**_Niklas:_** But we sell a product - as an app or a service - to the customer. Isn't that obvious?

**Edmond:** Yes, we do. But it is not the actual end to the _Software Development Process_. In that process, the primary focus should be on _each execution_ of that code - each time that product is being used. We make our decisions based on that.



If your code is running 1000 times per second, it is providing value to the business - or damaging the business - 1000 times per second, 3'600'000 times per hour, 86'400'000 times per day.

That is a super simplified picture. There are other aspects to it that are even more interesting.

Imagine that the code is written in a way that makes any sort of changes - from fixing a bug to adding a new feature - very hard.

Your rival can grow in your target market far faster than you - if her/his code has a better design and can react to changes in business requirements faster.

So, tell me:

- How many times are you going to write/update the code each day?
- How many times are you going to read the code each day?
- How many times are you going to run that code each day?

The number go up, in each step, exponentially. Because of that, it's more important to write code that is easy to maintain, change and fix. Not a code that is easy to write.

It's not just about a code that just works.

_Nothing justifies putting bad code into production - a “temporary hack” or whatever_. And we can come up with all sorts of colorful and creative excuses - some of them are even “professional” terms, from all departments. And yes; we can push programmers - to an extent that they don’t care anymore. Kind of like an I-am-just-following-the-orders situation, you know. To make people in charge happy. Like charts and diagrams which make people happy!

Except: You are not deploying those charts and diagrams. You are deploying the code.

Code is a manifestation of your business intentions. Imagine if your intention is to succeed, but what you have written down in the code is “I want to fail” by accident. Maybe because you were thinking that you are in a hurry and you made that mistake. You can move slowly toward your goal and eventually reach it. Or you can move very fast in any other direction - it wouldn't matter anymore.


## Iron Triangle


**_Niklas:_** I have never thought of that. I mean for sure we were focusing on customer experience and happiness. But this is different.

**Edmond:** Customer experience comes from her/his experience, every time she/he uses the product - each execution of the code. And you are making profit from each execution of that code.

**_Niklas:_** Makes sense. Except that I do not see where it sits inside the Iron Triangle: _time_, _money_, _scope_.

**Edmond:** It’s rather a _Golden Tetrahedron_ when it comes to Software Development. There is also **Quality**.

**_Niklas:_** Quality? Is it even something objective when it comes to code?

**Edmond:** It certainly does have many objective aspects - based on which many principles and practices are based. It is a long story. We will come back to that.

**_Niklas:_** How does _Quality_ work anyway, in that _Golden Tetrahedron_ of yours?

**Edmond:** When _Quality_ degrades, for the same amount of money, you get less scope. It’s not possible to have a stream of features to compete in the market. Every temporary hack; every piece of entangled code, disrupts that stream of features. Those things that we strive for - reacting to changes in business requirements, as fast and as reliable as possible - are out of _scope_ now.


## Write Quality Into Code


**_Niklas:_** OK, how can we write high-quality code?

**Edmond:** What is the essence of the code? I mean, in its simplest sense.

**_Niklas:_** It's some form of text, I guess.

**Edmond:** True. And being text is an important aspect of code. But for now, let's go one level up. In all programming languages, we have two sets of constructs. One set for arranging and structuring the code - like functions, classes, packages, modules, interfaces, etc - which are not performing any actions. And there is this another set of constructs that act; like assignments, conditionals, calculations, function calls, etc - the part that runs.

Imagine this ocean of programming language constructs, definitions, and implementations. And we want to write them down. What should we write down?

**_Niklas:_** We write down something that produces the expected output.

**Edmond:** If I had asked you "How do you cook ratatouille?" would you answer me "We will chop things up and scramble things until we have something that we can eat"?

**_Niklas:_** OK, please elaborate.

**Edmond:** What are the things that you will put inside a file as code? How do you name them? Where do you get those names from? Where do you get the ideas for what they should look like? How do you know what is the purpose of each definition? Where does that purpose come from? Is it based on what it does? Or is it based on what it is for? How do you describe the behavior? And from where do you get the specifications for that behavior?

**_Niklas:_** I am not sure. Something comes into the system and something goes out and the code should convert the first to the second somehow.

**Edmond:** Somehow? Sounds like you would be programming by accident! Pretty much like how you would cook.

**_Niklas:_** I mean for sure when there is a concept, I will use that. For example, I might need a class named Customer.

**Edmond:** What is a concept? Where have you found it? What is a Customer?

**_Niklas:_** A concept is an abstraction of something. And I find it when I talk about the business.

**Edmond:** That's not a wrong answer. Is equality a concept?

**_Niklas:_** It certainly is!

**Edmond:** Would you please define equality?

**_Niklas:_** I find it pretty obvious. For example, if two variables have value 5 then they are equal.

**Edmond:** So, five meters is equal to five gallons, right?

**_Niklas:_** No.

**Edmond:** What about two points in a three-dimensional space? How can they be considered equal?

**_Niklas:_** OK, equality is a concept that can have different meanings.

**Edmond:** True. And where is that meaning coming from? From the _context_ in which we are having a conversation. Now, what is a Customer?

**_Niklas:_** It depends, I guess.

**Edmond:** Depends on what?

**_Niklas:_** It depends on the context in which we are having a conversation.

**Edmond:** How do you describe that context for the concept _Customer_?

**_Niklas:_** It is obviously a customer of our business.

**Edmond:** Assuming that your business is an e-commerce website, how do you define a _Customer_ in your system? For sure your business has different parts/departments/contexts, right? Is the meaning of _Customer_ the same in Sales and Billing and Shipping and Warehouse?

**_Niklas:_** Right, a single thing can have different meanings in different parts of the same business!

**Edmond:** To be more specific, different _bounded contexts_ of the business. But we will defer explaining it to later. You ask about how to write high quality code. The first step is to decide what to write down and for that, you need a clear understanding of the _concepts_ of the business, alongside the business _contexts_ that give meaning to those _concepts_.

**_Niklas:_** Sounds right. Yet I imagine it will be a constant battle between Software Developers and Business Experts using long and unmaintainable documents. I understand now that just writing down some code inside a file is illogical, and having a shared understanding of our business domain is essential. Yet the fact that we need to have a clear understanding of the business makes me doubtful that we could ever reduce the level of mess.

**Edmond:** You are not the first person discovering these facts. There are practices and techniques that are out there that have been invented and improved over the years, long before our having our conversation.


## Context, Concept, Behavior


**_Niklas:_** And now that I think about it, we need to also describe the behavior of each concept in each context! And how those context islands should communicate! It's impossible to model all those details! That's impractical!

**Edmond:** That's not how we do it. Industrial Engineers faced similar problems long before the Software Industry even came to exist. They faced the same problems while they were trying to model systems - for example for project management. They learned that instead of focusing on describing everything in detail, the real focus should be only on action points, like commands and events. And also things that affect those, like policies.

**_Niklas:_** Nice! I can imagine that might work.

**Edmond:** We do the same thing. Instead of thinking about the details of behavior in terms of _steps_, basically, we only care about the _commands_ - that trigger that action path - and the _events_ that are generated as the result of that.

**_Niklas:_** Now, I guess we can have a very precise model of our business domain!

**Edmond:** Except in Software Development we are not looking for precise models of the business domain!

**_Niklas:_** OK ... Please elaborate.

**Edmond:** The goal is to have a two-way communication channel between business on one hand, and all the way down to the code-base on the other hand. Business requirements change rather fast nowaday. Having a precise model is next to useless. Instead, so far, we established a _language_ that describes the different _entities_ and their _behavior_ in our domain. It's far less often for something technical to affect this language. But now everyone - both business and technical people - speak the same language. They use the same concepts that have a _clear_ (not static) meaning inside a specific context and they react to different _commands_ in our domain by triggering different _events_.

**_Niklas:_** It sounds like this shared language or shared understanding is less like a static model and more like a control panel which not only drives the business but also drives and guides the technical side - the implementation.

**Edmond:** Indeed! Which of course gets mature over time, yet stays vigilant in face of any changes on the business side. And also the technical side - we will come to this part later. Now, we have a clear language for describing our intent and a nice model that specifies the expected behavior in different parts of the system; how a specific bounded context (you could say a sub-system) collaborates with the rest of the system, which commands it will handle, how it will react to those commands by triggering different events and what policies and business rules it will apply, based on which, those events will be decided.


## Planned Programming


**_Niklas:_** Having a clear language through which everyone can communicate clearly, plus a nice model of our business domain, I can say we are ready to write some code!

**Edmond:** Not quite.

**_Niklas:_** But we achieved our goal, right? We have a two-way communication channel between business and all the way down to the code.

**Edmond:** The question still remains: What do you write down? What code do you put inside those files? We need a feedback loop which keeps us on track, to help us to avoid swaying away from our business domain, while we are happily busy building our LEGO towers. Without a feedback loop that proves the focus of the code is on business, and more importantly, proves its correctness according to the expected behavior, you would just be coding the same way that you cook!

**_Niklas:_** I do not cook that way. But I understand what you mean. So, please elaborate.

**Edmond:** We need some sort of planned programming. First, we devise a plan for the behavior that we expect from our code - most of the time from a business point of view. Obviously, our plans won’t work at first. Then we write just enough code to make those plans work. And then we stop right there. Because any code written beyond that line is unplanned code. And nobody in her/his right mind would place unplanned code into production.

**_Niklas:_** Sounds pragmatic. It's almost common sense. How exactly do we plan for what we expect our code to provide?

**Edmond:** This is another one of those solved problems out there. Let's come back to that later. Before getting there, let's get more familiar with the nature of the code at different parts of the system, the application, in our modules and packages and in all the other places.


## Three Dimensional Code


**_Niklas:_** Do you mean the nature of the code changes depending on where it sits?

**Edmond:** It is more precise to say that nature changes depending on the purpose of that code - what it is for. There are three dimensions of purpose for code: how _business-specific_ it is, how _application-specific_ it is, or, how _technology-specific_ it is.

**_Niklas:_** Arrrrg! That's almost obvious! Why haven't I thought of it? It explains a *lot* about our code-base. We have all of them present in all the places of our code-base! We are mixing unrelated stuff in all places.

**Edmond:** I figured that much. Just a heads up, mixing unrelated things can happen at higher conceptual levels which are also harder to recognize.

**_Niklas:_** So are there other aspects to the code?

**Edmond:** Yes, but not at the same space as these three, which we will study in more detail later. Now that we have a clear understanding of the business purpose of our activity, we reached the point where we actually start that activity.

**_Niklas:_** Writing some code?

**Edmond:** No. Please! Even now that we know that we have to plan, yet, we don't know _how_ to do the planning. Where should we start? How do we write down our plans? Do we need to have an image of how the whole thing should look like? How do we know that image is the right one?

**_Niklas:_** OK, how to do the planning?

**Edmond:** This is the part that we want to wrap our business language inside another language - the technical language. The technical language acts as a host for the business language, so it can communicate with the alien world of technology - the hardware, the network, the Matrix! There is no spoon! But we know the business is real and it is paying the bills.

**_Niklas:_** OK ... It was a descriptive picture. But how does that affect the planning?

**Edmond:** We want this layer to be as thin and as simple as possible. But what is simplicity in Software Development? If we try to answer this question, we will end up with the wrong answer - or an incomplete one. Because you have to define simplicity in terms of something you have beforehand - your assumptions. But, as we learned so far, the business decides the things that need to be done - our assumptions are next to meaningless. And the main activity in writing the software, the design, cannot benefit from out-of-thin-air assumptions. A better question is: How to avoid complexity?


## Complexity


**_Niklas:_** So, our main activity is design?

**Edmond:** Yes.

**_Niklas:_** And the purpose of planning is to help with the design?

**Edmond:** Yes.

**_Niklas:_** What is design in Software Development?

**Edmond:** What we have done so far, was part of the design. What we will do next, is part of the design as well. It is about choosing based on informed decisions. And the core part of this activity is far more human than what you might imagine. We will see more of it as we go.

**_Niklas:_** How to avoid complexity then?

**Edmond:** How do we imagine our system? As close as possible to the business, right? So, we want our system to be able to respond to changes in a reliable manner and adapt itself in an as-small-as-possible cost window. For that, we should be able to undo our decisions that are made over time - and piled up as the system was evolving. Being unable to do that, is complexity. When designing a system, complexity comes from the irreversibility of our decisions.

**_Niklas:_** Interesting! But, is such a design even possible?

**Edmond:** We have a history of fighting complexity in Software Development and we have learned a lot on how to manage the details in different parts of the system, in a way that they don't affect other parts. It is true that we have to stick to our plans and never have anything unplanned in our system. But, at the same time, we understand the nature of our three-dimensional code, so we can organize the responsibilities and collaborations between different parts of the system, in a way to keep the coupling between them to a minimum. These practices, techniques and principles help us in all aspects of our design, from the organization of our code in some files to higher-level abstractions that we might introduce and use, based on the feedback that we get from our plans and specifications, which in turn reflect our business language.

**_Niklas:_** Aren't we making some assumptions that way?

**Edmond:** Not about the business. And the goal of these techniques and practices is to make different parts of our system disposable/replaceable - to _easily undo our technical decisions_.


## The Samurai and The Katana


**_Niklas:_** How can we ... well, design the design?

**Edmond:** We don't. We can't.

**_Niklas:_** Then what do we do?

**Edmond:** We drive the design.

**_Niklas:_** How does that work?

**Edmond:** Everything flows through people, from business all the way to the implementation. We need to drive our design in that direction. We do this through planned programming, devised as specifications that drive our design. How else can we align the outcome with the business?

**_Niklas:_** Everything flows through people, true. But where do our tools and technology sit in this picture?

**Edmond:** The Katana - the samurai sword - has nine different types of blades. Imagine that you have the best Katana ever made. Can you run into a battle, having the best Katana ever made? Do you dare facing swordmasters on the battlefield?

**_Niklas:_** No way!

**Edmond:** Why?

**_Niklas:_** Because they are masters!

**Edmond:** Exactly. The best Kata ever made, is useless, if you have not mastered the forms, the techniques. It's useless if you have not practiced those forms and techniques to internalize them. Your tool is useless if you do not know how to use it best.

**_Niklas:_** So, that's where our tools and technology sits.

**Edmond:** Yes. And the same goes for the teams that do not practice to be a team, and also for the organizations. Any group of people that fails to practice communication on a daily basis will produce dysfunctional outcomes and products. Tools are passive in nature. We can automate them. And surely we need to learn about them. Yet we have to drive them through our design toward our goal. That's why having a feedback loop is essential.


## Onions


**_Niklas:_** So, we have to master the design.

**Edmond:** Yes.

**_Niklas:_** And we drive the design, through the specifications that are devised based on the business.

**Edmond:** Yes.

**_Niklas:_** How can we make sure that those specifications are describing every bit of behavior that we expect from every detail in the code?

**Edmond:** It doesn't work like that. We do not need to care about the details of the code. We focus only on the behavior of the code.

**_Niklas:_** Still, it's not easy for me to imagine that.

**Edmond:** The relationship between the specifications and the code is similar to the relationship between interfaces and classes. Interfaces describe behavior that a class needs to provide - without exposing anything about the implementation details. The specification for a specific behavior is similar. It is a protocol that the code must follow. It does not describe _how_ the code does that.

**_Niklas:_** Does the nature of the specifications also change? Based on the nature of the code.

**Edmond:** Yes. Remember that the technical language is meant to act as a host for the business language to make it able to communicate with the non-human, alien world of technology. This is our system. If we imagine it as an onion, the business language sits at its core. The closer a layer is to the core, the more business-specific it will be. As we move toward outer layers, the language - the code - becomes more application-specific. And at the outermost layers, it's mostly technology-specific. The inner layers do not care about the outer layers. Because it's the business that dictates what we have to do. That's why the outer layers depend on inner layers. But the inner layers do not know anything about outer layers.

**_Niklas:_** Interesting! That way the inner layers will remain intact, while we make all sorts of changes in the outer layers!

**Edmond:** Indeed. We can change the outermost layers which are basically technology-specific, without even touching the inner layers. That's the main way of controlling complexity: _to be able to undo our technical decisions easily_.


---

> TODO

---

> P.S. _I sincerely appreciate the help from all people who either helped with preparations or provided useful advice_.