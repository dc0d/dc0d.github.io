---
title: "Dialogue II"
date: 2020-03-07T04:58:23+01:00
draft: false
tags: ["Agile", "TDD"]
cover:
    image: /images/agile-in-practice.png
    alternate: Agile In Practice
---

> ![wip](https://progress-bar.dev/1/?title=wip)
>   - This is a work in progress.
>   - It is picturing how one could think about Software Development - one of many possible ways.

{{<convo sep=":">}}

Niklas :: Something feels broken about all that code we have.

Edmond :: Maybe. But aren't you making money?

Niklas :: We do. But doing anything new is hard, changing or fixing stuff is hard, everything feels so slow, so ineffective. We have to constantly put too much lipstick on the pig, so the customer continues to like it. I wonder if we are also constantly lying to ourselves.

Edmond :: How so?

Niklas :: It is a constant battle. It's a 24/7 firefighting. Yes, there are all sorts of alarms, monitoring and automated stuff there. To be honest it feels like we are automating shit! Everything is red all the time. Nobody actually cares anymore. We all just want to be done with office hours and we pray on the _"standby"_.

Edmond :: Have you come up with any ideas about the whole thing? I mean, what's the cause of this?

Niklas :: Came up with lots of ideas! Lots of them! Even tried some of them. None worked. I ran out of ideas. What _is_ Software Development anyway?

Edmond :: Indeed. Let's have at it.

{{</convo>}}

## What is Software Development?

{{<convo sep=":">}}

Edmond :: So, what do _you_ think Software Development is?

Niklas :: I am not going to say _writing code_. And I'm sure it's different than _manufacturing_, right?

Edmond :: Yes. When a factory manufactures a car, it can be used only by one client - unless we could send that one single car into parallel universes.

Niklas :: I've heard it's been compared to gardening. You can find _similarities_ for sure. But it doesn't make that much sense.

Edmond :: Yeah, no. A plant does most of the job of growing by itself. You just provide some support, like fertilizers. The code does not grow by itself no matter how much fertilizer you provide.

Niklas :: OK, in Software Development we define and introduce something once and use it in many different places. Can we say that?

Edmond :: You mean something like _Law-Making_? Well; possibly; close enough. You write the law once and every person has to comply. Except that there is no feedback mechanism to evaluate what you have made. And nobody cares these days - politics I mean. But software needs to work and we need a way to prove it's working properly - or at least that's the assumption. So, _what is Software Development_? Let's come back to this question later.

{{</convo>}}

## Code vs Artifact (Product)

Code vs Artifact (Product) dichotomy is all wrong. We are not actually selling a product - in a conventional industrial sense. We are selling functionality.

It's Code vs Execution.

A Software Product is just a packaging and delivery mechanism to provide that functionality to the customer. And the customer has access to that functionality at any time she/he has a need for that functionality.

That's how we should think about Software Development: It's _Code vs Execution_. That should be _the base for all the judgments that we make about each step in Software Development_.

A software product is like parallel mirrors. Each reflection is an execution. When the code gets inside a product, between those mirrors, you get an infinite number of _what you have: the code_. You get that's in the code and you benefit from it everywhere - or get hurt everywhere.

## Code vs Execution

{{<convo sep=":">}}

Niklas :: But we sell a product - as an app or a service - to the customer. Isn't that obvious?

Edmond :: Yes, we do. But it is not the actual end to _Software Development Process_. In that process, the primary focus should be on _each execution_ of that code - each time that product is being used. We make our decisions based on that.

{{</convo>}}

If your code is running 1000 times per second, it is providing value to the business - or damaging the business - 1000 times per second, 3'600'000 times per hour, 86'400'000 times per day.

That is a super simplified picture. There are other aspects to it that are even more "interesting".

Imagine that the code is written in a way that makes any sort of changes - from fixing a bug to adding a new feature - very hard.

Your rival can grow in your target market 86'400'000 times per day, faster than you - if her/his code has a better design and can react to changes in business requirements faster.

It's not just about a code that just works.

_Nothing justifies putting bad code into production - a “temporary hack” or whatever_. And we can come up with all sorts of colorful and creative excuses - some of them are even “professional” terms, from all departments. And yes; we can push programmers - to an extent that they don’t care anymore. Kind of like an I-am-just-following-the-orders situation, you know. To make people in charge happy. Somehow like charts and diagrams which make people happy!

Except: You are not deploying those charts and diagrams. You are deploying the code.

## Iron Triangle

{{<convo sep=":">}}

Niklas :: I have never thought of that. I mean for sure we were focusing on customer experience and happiness. But this is different.

Edmond :: Customer experience comes from her/his experience, every time she/he uses the product - each execution of the code. And you are making profit from each execution of that code.

Niklas :: Makes sense. Except that I do not see where it sits inside the Iron Triangle: _time_, _money_, _scope_.

Edmond :: It’s rather a _Golden Tetrahedron_ when it comes to Software Development. There is also **Quality**.

Niklas :: Quality? Is it even objective when it comes to code?

Edmond :: It certainly does have many objective aspects - based on which, many principles and practices are based. It is a long story. We will come back to that.

Niklas :: You say it in a way that sounds there are that many things to learn about Software Development!

Edmond :: Do you have a car?

Niklas :: Yes. An old BMW.

Edmond :: Do you think if you can build me a BMW? I mean building every bit of it?

Niklas :: That needs far more than one specialty! Let alone one man!

Edmond :: Can you build me an Amazon? Or a Google? Or just a Notepad clone? Notepad is a pretty simple piece of software, right?

Niklas :: These are totally different questions and I am not getting a nice vibe from you right now.

Edmond :: Indeed they are different questions. Now my question is why in the world should someone think there is nothing to learn about Software Development? Why do you think being able to use a laptop and entering some code into it and get something on the screen is Software Development? I mean; where this assumption comes from that there is nothing there to learn when it comes to Software Development? Why do you think it's all about coding and being a "tool-expert"?

Niklas :: How _Quality_ works anyway? In that _Golden Tetrahedron_ of yours.

Edmond :: When _Quality_ degrades, for the same amount of money, you get less scope. It’s not possible to have a stream of features to compete in the market. Every "temporary" hack; every piece of entangled code, disrupts that steam of features. Those things that we strive for - reacting to changes in business requirements, as fast and as reliable as possible - are out of _scope_ now.

{{</convo>}}

Niklas thinking to himself; "I want to hear his answer".

## Write Quality Into Code

{{<convo sep=":">}}

Niklas :: OK, how can we write high quality code?

Edmond :: What is the essence of the code? I mean in its simplest sense.

Niklas :: It's some form of text, I guess.

Edmond :: True. And being text is an important aspect of code. But for now, let's go one level up. In all programming languages, we have two sets of constructs. One set for arranging and structuring the code - like functions, classes, packages, modules, interfaces, etc - which are not performing any actions. And there is this another set of constructs that act; like assignments, conditionals, calculations, function calls, etc - the part that runs.

Niklas :: Now that I think about it, indeed I can recognize those sets of constructs in a bunch of programming languages.

Edmond :: Imagine this ocean of programming language constructs, the definitions, and implementations. And we want to write them down. What should we write down?

Niklas :: We write down something that produces the expected output.

Edmond :: If I had asked you "How do you cook?" would you answer me "We will chop things up and scramble things until we have something that we can eat"? Please pay attention more closely.

Niklas :: OK, please elaborate.

Edmond :: What are the things that you will put inside a file as code? How do you name them? Where do you get those names from? Where do you get the ideas for how they should look like? How do you know what is the purpose of each definition? Where that purpose comes from? Is it based on what it does? Or is it based on what it is for? How do you describe the behavior? And from where do you get the specifications for that behavior?

Niklas :: I am not sure. Something comes into the system and something goes out and the code should convert the first to the second somehow.

Edmond :: Somehow? Sounds like you are programming by accident! Pretty much like how you cook.

Niklas :: I mean for sure when there is a concept, I will use that. For example, I might need a class named Customer.

Edmond :: What is a concept? Where have you found it? What is a Customer?

Niklas :: A concept is an abstraction of something. And I find it when I talk about the business.

Edmond :: That's not a wrong answer. Is equality a concept?

Niklas :: It certainly is!

Edmond :: Would you please define equality?

Niklas :: I find it pretty obvious. For example, if two variables have value 5 then they are equal.

Edmond :: So, five meters is equal to five gallons, right?

Niklas :: No.

Edmond :: What about two points in a three-dimension space? How can they be considered equal?

Niklas :: OK, equality is a concept that can have different meanings.

Edmond :: True. And where that meaning is coming from? From the _context_ in which we are having a conversation. Now, what is a Customer?

Niklas :: It depends I guess.

Edmond :: Depends on what?

Niklas :: On the context that we are having a conversation inside it.

Edmond :: How do you describe that context for the concept _Customer_?

Niklas :: It is obviously a customer of our business.

Edmond :: Assuming that your business is an e-commerce website, how do you define a _Customer_ in your system? For sure your business has different parts/departments/contexts, right? Is the meaning of _Customer_ the same in Sales and Billing and Shipping and Warehouse?

Niklas :: So, a single thing can have different meanings in different parts of the same business!

Edmond :: To be more specific, different _bounded contexts_ of the business. But we will defer explaining it to later. You ask about how to write good quality code. The first step is to decide what to write down and for that, you need a clear understanding of the _concepts_ of the business, alongside the business _contexts_ that give meaning to those _concepts_.

Niklas :: Sounds right. Yet I imagine it will be a constant battle between Software Developers and Business Experts, long, unmaintainable documents and such. I understand now that just writing down some code inside a file is insane, and having a shared understanding of our business domain is essential, yet this fact that we need to have a clear understanding of the business makes me just more disappointed in ever reducing the degree of the messiness.

Edmond :: You are not the first person discovering these facts. There are practices and techniques that are out there and have been invented and improved over the years, long before us, having our conversation.

{{</convo>}}

## Context, Concept, Behavior

{{<convo sep=":">}}

Niklas :: And now that I think about it we need also to describe the behavior of each concept in each context! And how those context islands should communicate! It's impossible to model all that details! That's insane!

Edmond :: That's not how we do it. Industrial Engineers faced similar problems long before Software Industry even comes to exist. They faced the same problems while they were trying to model systems - for example for project management. They learned that instead of focusing on describing everything in detail, the real focus should be only on action points, like commands and events. And also things that affect those, like policies.

Niklas :: Nice! I can imagine that might work.

Edmond :: We do the same thing. Instead of thinking about the details of a behavior in terms of _steps_, basically, we only care about the _commands_ - that trigger that action path - and the _events_ that are generated as the result of that.

Niklas :: Now, I guess we can have a very precise model of our business domain!

Edmond :: Except in Software Development we are not looking for precise models of the business domain!

Niklas :: OK ... Please elaborate.

Edmond :: The goal is to have a two-way communication channel between business on one hand, and all the way down to the code-base on the other hand. Business requirements change rather very fast at our time. Having a precise model is next to useless. Instead, so far, we established a _language_ that describes the different _entities_ and their _behavior_ in our domain. It's far less often for something technical to affect this language. But now everyone - both business and technical people - talk in the same language. They use same concepts that have a _clear_ (not static) meaning inside a specific context and they react to different _commands_ in our domain by triggering different _events_.

Niklas :: And it's a live thing!

Edmond :: Indeed! Which of-course gets mature over time, yet stays vigilant in face of any changes in business side. And also the technical side - we will come to this part later. Now, we have a clear language for describing our intent and a nice model that specifies the expected behavior in different parts of the system; how a specific bounded contaxt collaborates with the rest of the system, which commands it will handle, how it will react to those commands by trigering different events and what pilicies and business rules it will apply, based on which, those events will be decided.

{{</convo>}}

## Planned Programming

{{<convo sep=":">}}

Niklas :: Having a clear language through which everyone can communicate clearly, plus a nice model of our business domain, I can say we are ready to write some code!

Edmond :: Not quite.

Niklas :: But we achived our goal, right? To have a two-way communication channel between business and all the way down to the code.

Edmond :: The question still stays: What do you write down? What do you put inside those files as code?

Niklas :: I create an application for each bounded context and name my classes after things we find in the shared language for that context.

Edmond :: It is possible to write all sort of code in source files. How do you make sure that you actually need it? How do you make sure that you are not making something up that has no actual usage or has no actual equivalent in your business? As you have learned from your current system before, you already know that writing code can mean many things. But getting it right on first try, is not one of them. So, I guess to you, it looks like a bit of try and error.

Niklas :: It _is_ try and error. How can we write code any other way?

Edmond :: You didn't answer my question.

Niklas :: It sounds a bit confusing to me right now. What do I need more

{{</convo>}}

---

# TODO
