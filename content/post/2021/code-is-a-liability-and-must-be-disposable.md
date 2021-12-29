---
title: 'Code Is a Liability and Must Be Disposable'
date: 2021-11-22T21:00:00+01:00
draft: false
comment: false
tags: ['programming']
---

All the reduction in revenue comes from the code. All the lost opportunities and overdue time-to-market come from the code. The code causes long lead times. All the bugs come from the code. And for developers all the beautiful weekends, that you could be spent with your kids and your family, but weren't so, come from the code.

Code is a liability, not an asset. The functionality of it could be an asset, assuming you're building something that someone is willing to pay for it. If it was possible to have the functionality, without the code, that would be Nirvana! Unfortunately, that's not possible.

We know that if we want the functionality, we can not avoid the code. Yet, maybe we can try to make the code disposable. The presence of disposable code is less intrusive and you can get on more easily with your life.

There are two aspects to the code production process. First, it is possible to focus on the process of code generation, which nobody likes to talk about because it is about people, and the people part is hard - and we will follow the majority here. The second one is to focus on the design and make the code as disposable as possible.

We will discover things about the second aspect and will make the code disposable.

Of course, there could be a step even before making the code disposable, which is to try to write the least amount of code possible - which we will put aside for now.

# break it down, break it down, break it down

But how?

If we cut a pile of code in half, we will get two piles of code. That's not helping.

Let's try something else first. What if we break apart and decompose this very room that we are sitting inside? What would we get?

We would get a bunch of girders, some bricks, maybe some lumber, maybe not, possibly some pipes, metal, or plastic. OK, Let's stop there. That's far enough for our purpose.

So, even as people, not necessarily well versed in construction building, we can recognize these parts. Because they are different. They have different shapes, different textures, different weights. Those are not just piles of things. They are separate, recognizable things.

Unlike a pile of code.

So, what should we do? Can we decompose a pile of code based on functionality? But that's always changing. Based on language constructs? Like types and functions and constants? But even if we want to do that, we can't, because we never know all the types and functions that we might need. If we could do a big upfront design, it would be great. If we could know all the possible features that we need to implement in any possible feature, that would be great. And lot's of other IFantasies that we could be fantasizing about. But, that's not the case.

# break it down, a bit

Maybe we could break it down based on the nature of the code. That part we can do upfront, right? That part needs the least amount of knowledge about the future and its never-ending stream of changes. We can break down the codebase on its nature, its purpose. Based on how business-specific it is, how application-specific it is, or how technology-specific it is. This is a good enough first step in making the code disposable. If we manage to have these kinds of codes in separate baskets, we can throw away the baskets and dispose of them more easily. In other words, change it more easily.

But which depends on which? Two-way dependencies are the same bad as spaghetti code. The whole history of programming is about making things go in one direction, Structured Programming, one-way structured branching (avoid `goto`), React, one-way data flow (avoid two-way data binding, which is like `goto`, but for data), Ports & Adapters, one-way code dependency, Functional programming, one-way changes in value, in time (avoid assignments), OOP, single-way messaging, (avoid branching, by using polymorphism).

And two-way dependency will be circular anyway, which makes it useless.

# break it down, and wire

So, we can tell how business-specific, or how application-specific, or, how technology-specific some code can be. But how should we wire those?

Let's look at our building once more. Maybe we can find something useful, that helps us with this.

Every building is made from five essential components. The site, on which, the whole building sits. The structure, which sits over the site and holds everything else together. The skin, which covers the structure, protects it from things like rain and also makes it look beautiful. The services, like water and perhaps gas pipes, electricity, air conditioning and such. And, finally, the stuff, which we put in there, like the TV and the sofa. These five components are designed and built in a way, for the parts that change more frequently, to be more accessible, to change more easily. There should be no need for tearing apart the services, or the structure, while we are trying to change the TV. That's why we build doors in the walls. So, core parts, which serve our daily lives, should be easily replaceable, and more structural parts should provide the interface to make this possible.

It is the same for us. The business-specific code, should not care about in what application it is being run, or what technology provides the required underlying infrastructure components. The business-specific code should be disposable immediately. That's a good reason for it to depend on nothing but itself. We can put the business-specific code, at the core. That would be the model of our business. The next part that should be easily disposable is the application-specific code. Of course, it should take care of the business-specific code, and coordinate its different components. So, the application-specific part, which triggers our business use-cases, depends on the business-specific code, but nothing else. And at last comes the technology-specific code, which talks to the infrastructure and brings our application to life. The technology-specific code only cares about, well, technology, obviously, and it talks most of the time, only in terms of DTOs and low-level APIs.

It's sad that we still need to write code (just thinking about all those bugs and painful on-call nights, caused by the code, gives me the shivers). But, at least we have made it a bit more disposable.

# decomposition achieved!

Yay! Our code become more disposable!

Are we done?

The short answer is, no.

There are invisible factors. There are invisible factors, that affect the design of this very room, that we are sitting at. One might think of the ergonomics of the stuff and the philosophical mindset behind a consumer-oriented world and things like that. Which are very important. Perhaps the most important ones (which again, no one cares about much).

But, no. There are invisible factors that are physical but have no actual body. I am not playing Yoda.

We are talking about forces, like tension and pressure. They are invisible. There is no physical body, that we can show to someone else and say "this is the tension in the room". If any mistakes are made in calculations of the tension and pressure, the room and the building will crumble upon our heads

Going back to programming, there are similar forces there, like coupling and cohesion, that if are neglected, they can make the code less disposable. It is said that the functionality that a system provides is bigger than the sum of its parts. In the same way, the problems that can occur in a system, are far more complex than the problems that occur in each part. The whole design part of software development is about what to keep and what to leave out. And, at any time, we just focus on the responsibilities, that are needed to be carried out, by the part that is changing. Summoning any out-of-context knowledge is the same as asking for trouble.

At this point, we will be tempted to think in terms of reusability and making reusable stuff to make things easier. But reusability is not about reusability. It is about how easily the code can be changed or replaced. For example, an http router is a "reusable" technology-specific code-pile - library, package, module. It abstracts talking to the network, using the http protocol. It is not reusable because we care about the underlying technology. It looks reusable because it _accepts_ change. It allows the http handlers to become disposable. It is _disposable-friendly_.

Decupling is a well-established technique for achieving disposable code. And one way to implement decoupling is to use messages. We should prefer hiding responsibilities that we want to put out, behind messages over implementing behavior.

# messages? what messages?

Let's implement a simple calculator. We send a command message to the calculator, with the next operand. For example `add 3` or `sub 4`. And based on the command message, we perform some calculations.

```go
package main

import "fmt"

func main() {
	calc := &calculator{}

	calc.do("add", 10)
	calc.do("sub", 4)
	calc.do("mul", 3)
	calc.do("div", 2)
	calc.do("add", 10)

	fmt.Println("result:", calc.result())
}

type calculator struct {
	value int
}

func (c *calculator) result() int { return c.value }

func (c *calculator) do(cmd string, n int) {
	switch cmd {
	case "add":
		c.value += n
	case "sub":
		c.value -= n
	case "mul":
		c.value *= n
	case "div":
		c.value /= n
	}
}
```

The `main()` function does not care how those calculations work. It only needs someone that understands `"add"`, `"sub"`, `"mul"` and `"div"` command messages. And `calculator` is capable of processing those command messages.

There is another way for `calculator` to tell us what messages it understands.

```go
package main

import "fmt"

func main() {
	calc := &calculator{}

	calc.add(10)
	calc.sub(4)
	calc.mul(3)
	calc.div(2)
	calc.add(10)

	fmt.Println("result:", calc.result())
}

type calculator struct {
	value int
}

func (c *calculator) result() int { return c.value }

func (c *calculator) add(v int) { c.value += v }
func (c *calculator) sub(v int) { c.value -= v }
func (c *calculator) mul(v int) { c.value *= v }
func (c *calculator) div(v int) { c.value /= v }
```

This looks much nicer! An object can tell us what messages it can process, by providing a set of methods. This program is the same as before. The only difference is that the `calculator` provides the set of messages that it can understand, explicitly.

But does the `main()` function care about who is performing the calculations? It does not care if the object that can process those command messages is `calculator` or another calculation engine or `darthVadar`, right? `main()` only care about the set of messages that it needs to send to get the calculations.

```go
package main

import "fmt"

func main() {
	var calc calculatorEngine
	calc = calculatorFactory()

	calc.add(10)
	calc.sub(4)
	calc.mul(3)
	calc.div(2)
	calc.add(10)

	fmt.Println("result:", calc.result())
}

type calculatorEngine interface {
	add(v int)
	sub(v int)
	mul(v int)
	div(v int)
	result() int
}

type calculator struct {
	value int
}

func calculatorFactory() calculatorEngine {
	// logic to choose the right calculator
	return &calculator{}
}

func (c *calculator) result() int { return c.value }
func (c *calculator) add(v int)   { c.value += v }
func (c *calculator) sub(v int)   { c.value -= v }
func (c *calculator) mul(v int)   { c.value *= v }
func (c *calculator) div(v int)   { c.value /= v }
```

Much better now! Now the `main()` function, can work with anyone that understands the set of messages, described in the `calculatorEngine` contract. And it is the responsibility of the factory to provide the right one.

Here, we hid everything about the calculations, behind a set of messages - _a set of methods_ - instead of trying to provide them directly inside the `main()` function.

Now, from the point of view of the `main()` function, `calculator` is completely disposable. The `main()` function knows nothing about the `calculator`. And it does not care a single bit.

![stranger](https://i.kym-cdn.com/entries/icons/original/000/028/648/loki.jpg)

I love how Go makes it possible to do these designs so neatly! The same thing in other statically typed "OO" programming languages would be unnecessarily longer - and uglier, needless to say.

# where to put the contract?

Maintaining a one-way code dependency between the three types of code, that we have - the business-specific code, the application-specific code, and the technology-specific code - seems complicated at times. We want the code dependencies (the `import` statements in case of Go) to go like: `technology-specific -> calls -> application-specific -> calls -> business-specific` . But sometimes the business-specific code needs to store some state in a storage or a database (usually through a repository object). But at the same time, the business-specific code can not depend on the technology-specific code (the database in this case).

What should we do?

There is a simple trick to this! We just put the abstractions inside the business-specific code - our core model! This way, two different types (usually of different nature) do not need to depend on each other, and instead, will depend on those abstractions (like interfaces and their inputs and outputs). Now, all types of code can depend on them and use them happily. We don't need to start with complex directory structures when we start a new project. Just keep in mind that the technology-specific code itself has two types, the part that triggers stuff, or the delivery - which is usually inside the `cmd` directory in Go projects, for REST API or CLI or whatever type of delivery we need to provide for the functionality that we want to expose - and the other part that is being triggered from the logic (like the database). So, the technology-specific code either triggers stuff or will be triggered.

We could start with some flat directories for each of these three kinds of code. And make it more structured as we discover new concepts in our domain.

The most important thing is to keep the code as disposable as possible at all times. This has another interesting side-effect. Now, we are almost always able to answer these questions when we look at a codebase:

- Where to put a behavior?
- How to trigger the behavior?
- What input is needed for that?

Because disposable code is isolated by design and easier to test. And it is also reusable by design. Unfortunately, we rush into writing code and we introduce new types liberally, instead of trying to discover them as we go through the course of implementing a system.

# every design decision is a tradeoff

We should allow the problem to guide us and as we go, types will be discovered. Disposable code makes it possible to undo our design decisions more easily. So, as we get more experienced with the domain, we can make better decisions. One of the reasons that Go prefers composition over inheritance, is this. To avoid making big design decisions, too early, and also change them more easily.

> I am not a fan of type-driven programming, type hierarchies, and classes, and inheritance. Although many hugely successful projects have been built that way, I feel the approach pushes important decisions too early into the design phase, before experience can influence them. In other words, I prefer composition to inheritance.
>
> - [Rob Pike](https://evrone.com/rob-pike-interview)

We can make those tradeoffs as cheap as possible, as disposable as possible. Go had put together the best parts of OOP in one beautiful package. And since [Go is object-oriented, even though it doesn't have the notion of a class](https://www.informit.com/articles/article.aspx?p=1623555), it is possible to use the good parts (and leave out the less useful parts) of OOP world.

Go is our tool. One of the best out there - if not the best. But, it is not the solution. A hammer is a tool. A chair is a solution. In software, the design is the solution. And Go makes it possible to change those design decisions at any stage of a project, through many different capabilities provided in the language and its amazing tool-chain. To write disposable code, and balance the tradeoffs.

And remember: _When we fix a bug, we do not fix the code. We fix the executions - hundreds, thousands, millions of them; per second. That's a common misunderstanding about bugs. It is not about the code. Changing the code is just a means to an end. If the code is disposable, bugs become disposable_.

> _also as a participation in 2021 [gopheradvent](https://gopheradvent.com/calendar/2021/code-is-a-liability-and-must-be-disposable/)_
