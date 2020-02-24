---
title: "Agile - Little Rambling"
date: 2020-02-24T23:46:41+01:00
draft: false
---

# Agile - Little Rambling

> WIP - v0.0.1

The state of things in this industry is a bit ... "complicated". Maybe having an entry point could help.

## What is Software Development?

Lots of metaphors have been used to describe or define Software Development. Maybe because it has no definition yet, as of 2020.

### Software Development as Manufacturing

Yeah, no. When a factory manufactures a car, it can be used only by one client - unless we could send that one single car into parallel universes.

### Software Development as Gardening

Yeah, no. A plant does most of the job of growing by itself. You just provide some support, like fertilizers. The code does not grow by itself no matter how much fertilizer you provide.

### Software Development as Law Making

Yeah, possibly. You write the law once and every person has to comply. Except that there is no feedback mechanism to evaluate what you have made. And nobody cares these days. But software needs to work and we need a way to prove it's working properly - or at least that's the assumption.

So, what is Software Development?

## Code vs Artifact (Product)

Code vs Artifact (Product) dichotomy is all wrong. We are not actually selling a product - in a 19th  Industrial Revolution sense. We are selling functionality.

It's Code vs Execution.

## Code vs Execution

If your code is running 1000 times per second, it is providing value to the business - or damaging the business - 1000 times per second, 3'600'000 times per hour, 86'400'000 times per day.

That is a super simplified picture. There are other aspects to it that are even more "interesting".

Imagine that the code is written in a way that makes any sort of changes - from fixing a but to adding a new feature - very hard.

Your rival can grow in your target market 86'400'000 times per day, faster than you - if hers/his code has a better design.

It's not just about a code that just works.

_Nothing justifies putting bad code into production - a “temporary hack” or whatever_. And we can come up with all sorts of colorful and creative excuses - some of them are even “professional” terms, from all departments. And yes; we can push programmers - to an extent that they don’t care anymore. Kind of like an I-am-just-following-the-orders situation, you know. To make people in charge happy. Somehow like charts and diagrams which make people happy!

Except: You are not deploying those charts and diagrams. You are deploying the code.

## Iron Triangle

It’s rather a Golden Tetrahedron when it comes to Software Development. There is also **Quality**. How does it work? When _Quality_ degrades, for the same amount of money, you get less scope. It’s not possible to have a stream of features to compete in the market. Every "temporary" hack; every piece of entangled code, disrupts that steam of features. Those things are out of _scope_ now.

## Technical Excellence and Value

Technical Excellence _is_ value, you are deploying technical excellence (or lack of it) to your production environment. It lives all over your code. Or it is absent altogether. Now, what does it mean "Technical Excellence"?

A Civil Engineer knows how to build buildings, right? Houses, apartments, villas and all sorts of accommodations.

How about Nuclear Plants? That's new! Of-course they are shutting down those - most of them at least.

How about a cattle barn? A cattle barn should provide some very specific functionality. And some of that functionality does have any predefined framework to be measured and understood in. What if we want to build a cattle barn in a country without any subsides on energy to keep it warm during winter? Oh! We did not think of that before! There are lots of things that we have to talk about to our engineer and there are lots of things that he has to learn in order to build us a cattle barn.

We need to communicate very clearly and continuously because the cost of making mistakes will be too high.

## Communication

We need to communicate and we need to communicate on many levels - the business and the team.

### Team Communication

Having daily standups are nice. Everybody will know what everybody is doing and the Product Owner is also there to talk on behalf of the business (or Backlog Owner some call him).

It could be a nice thing if developers were working together on stuff. I mean when someone says I worked on X and I have never seen that code how the hell should I know what is he doing? Why do we even have to know each other if all of us are working on stuff alone? Just to report back to the Product Owner?

And BTW where is the Product Owner is getting his stories from? And where hers/his choice of words and concepts are coming from?

### Cross-Domain Communication

There are nice techniques for understanding the flow of behaviors in a system. The practice Event Storming can be used for understanding all sorts of things. From arranging the way one family with kids and lots of carriages want to go to the airport, to decyphering a very complicated business domain with lots of events and policies.

This allows all people from all departments to communicate and grow a shared understanding and crystalize the language that can be used clearly by all parties - business, sales, marketing, developers and even your tools: the forms your print, the datastore, and of-course: The Code.

This is the realm of DDD which creates a two-way bridge between Problem Space and Solution Space.

### Knowledge Building

The code is a tool to communicate. The main audience of the code are humans - computers just carry on the orders. Architecture is a means of communication. It's how developers write down the business language. They talk about the business language via architecture and code.

## Technical Excellence

How can we know that we are talking about the business language correctly? One side of it is to maintain a clear and always on the line of communication with the business. But how can we make sure that we are describing it properly? We need some sort of feedback loop to trigger us when we are swaying away from the shared understanding that holds all the business together - and it's not a static thing! The business grows, changes and adapts!

We need some sort of planned programming. First, we plan for the behavior that we want to have. Obviously, our plans won't work at first. Then we write enough code to make those plans work. And then we stop right there. Because any code written beyond that line is unplanned code. And nobody in hers/his right mind would place unplanned code into production - there is absolutely nothing in this world that justifies that.

### Planned Programming

How can we do that? Sound pragmatic. Where should we start?

Actually, there is a well-known practice that helps us to achieve this style: TDD. It is exactly as it sounds, it is a design technique and in this technique, tests are used to specify the design and provide the necessary feedback for evaluating the efficiency of our design.

We need to already know about designing software, some techniques, some experience on how to draw boundary lines and provide an architecture. And TDD acts as a negative feedback loop that keeps us on track by demanding to clearly explain our intent.

Our intent is to describe and the expected behavior based on the business language. Which in turn has its roots in the communication patterns in a company (they call it culture also - it's too poetic for my taste).

### TDD does nothing by itself

It's a technique for adopting our Solution Space language (Domain Model) to the Problem Space language.

It can be learned. There is nothing magical about it. First, we need to improve our sense of smell for code smells - those parts that stink. And we do that by getting to know about principles bit by bit. It takes time and that's fine. Everybody has to start somewhere. Getting familiar with S in SOLID and then D is a nice starting point.

You will figure out the rest on the way. Whenever in doubt to what to do, in front of some legacy code, ask some good questions like:

- What is this code for? (Not what does it do?)
- Why is it hard to test? (Not how to test it?)

And when designing a class you can ask:

- What is the thing that I want to have here?
- What are the things that I do not want to have here (they are not part of the responsibility of this class)?

You can even play with [CRC](https://en.wikipedia.org/wiki/Class-responsibility-collaboration_card) cards. This thought experience helps greatly to filter-out collaborators and distill the desired responsibilities of that code (it could be Component-Responsibility-Collaboration).

And we need an actual car body to put all those devices together. Here we look into Clean Architecture. Actually, we needed to have this in place before the previous step.

But it's fine as long as we are learning.

The civil engineer needed to learn a lot about cattle business when making a barn.

It's the same here. Software Development is mainly a learning process to learn and understand the business. The rest are just tools to achieve that end.

And remember, nothing justifies putting a bad code or a code that can not react to changes fast enough, into production. When that happened, all other teams will rely on it and your rivals will get ahead of you 86'400'000 times a day (most likely even faster).

> P.S. It's like for six months that I am trying to prepare this as a presentation or a blog or something - but could not make it. I have done some half-baked dry-runs and finally decided to dump it like this, just to empty my mind because the whole "Current State of Agile" was getting heavy on me. I have written lots of shit before - I confess. Yet the businesses are still asking for the same shit with a new name; "Agile" and there are some that have converted this "Agile"-thing to a business of its own. This is the original [Agile Manifesto](https://agilemanifesto.org/). It's quite different from what we have today. Why?


