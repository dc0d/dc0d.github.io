---
title: "OOP and FP"
date: 2020-05-31T01:38:54+02:00
draft: false
---

Let's assume that we can question everything that is assumed to be a fact (or ask stupid questions - your take).

# OOP _was_ about message passing

Apparently, the language that is most close to the original idea of OOP, is ... Erlang! According to Alan Kay (mentioned this on [different](https://news.ycombinator.com/item?id=14337970) [occassions](https://www.quora.com/What-does-Alan-Kay-think-about-Joe-Armstrong-claiming-that-Erlang-might-be-the-only-object-oriented-language-and-also-his-thesis-supervisor-s-claim-that-Erlang-is-extremely-object-oriented)).

# Closures & Functional Programming

> Here we are cheating a bit, just to communicate better. We can blame things after.

```go
const (
	factor = 10
)

func add10(n int) int      { return n + factor }
func multiply10(n int) int { return n * factor }
```

Here, only functions are used. The `factor` constant, is a closure, accessed inside `add10` and `multiply10` functions. Very Functional so far.

# Factor Out The Shared Closure

An idea: let's factor out the shared closure and put it inside something (we will call it an object later).

```go
type factor struct {
	value int
}

func newFactor() factor {
	return factor{value: 10}
}

func (f factor) add10(n int) int      { return n + f.value }
func (f factor) multiply10(n int) int { return n * f.value }
```

Wow! An Object is very much like a bunch of functions with a shared closure!

# Last Bit, Mutation

```go
type factor struct {
	value int
}

func newFactor() factor {
	return factor{value: 10}
}

func (f factor) add10(n int) int                           { return n + f.value }
func (f factor) multiply10(n int) int                      { return n * f.value }
func (f *factor) makeOtheMethodsMeaningless(newFactor int) { f.value = newFactor }
```

Now we have a mutable closure, shared between a bunch of functions (now called _methods_).

# OOP and Functional Duality

OOP and Functional Programming "can" be seen as a dual. They represent the same thing, to a great extent and they try to provide tools to solve the same problem: composition.

# What about message passing?

We simply forgot about that - in time. OOP - in its original form - was about message-passing and behavior. And was trying to organize state and transformation through composing behaviors. While the OOP that we have tries to solve the composition problem, through data structures/type - same as Functional Programming.

The Behavior has been forgotten.

> This was a quick sketch for drafting out these ideas and get them written. Maybe it can be improved, maybe not.
