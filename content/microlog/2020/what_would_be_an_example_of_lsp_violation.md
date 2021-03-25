---
title: "What would be an example of violation of LSP?"
date: 2020-08-27T21:21:23+02:00
draft: false
---

> An example of violation of Liskov Substitution Principle (LSP)

If Square inherits from Rectangle, the problem starts when the intention is to change the width. We expect the height of a rectangle remains the same. But that's not the behavior of a Square.

It is a behavioral violation of LSP.

To fix it:

- Make Rectangle immutable or,
- Break the inheritance chain

