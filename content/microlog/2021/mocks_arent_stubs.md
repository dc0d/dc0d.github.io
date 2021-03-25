---
title: "Mocks aren't Stubs"
date: 2021-03-25T09:09:09+02:00
draft: false
---

[Mocks are not Stubs - Martin Fowler](https://martinfowler.com/articles/mocksArentStubs.html#ClassicalAndMockistTesting)

> In this article I've explained a pair of differences: _state_ or _behavior_ verification / classic or mockist TDD.

- If it's an easy collaboration then the choice is simple. If I'm a classic TDDer I don't use a mock, stub or any kind of double. I use a real object and state verification. If I'm a mockist TDDer I use a mock and behavior verification. No decisions at all.

- If it's an awkward collaboration, then there's no decision if I'm a mockist - I just use mocks and behavior verification. If I'm a classicist then I do have a choice, but it's not a big deal which one to use. Usually classicists will decide on a case by case basis, using the easiest route for each situation.

> In essence classic xunit tests are not just unit tests, but also mini-integration tests.

- It's at this point that I should stress that whichever style of test you use, you must combine it with coarser grained acceptance tests that operate across the system as a whole.

- I've always felt I'd be more comfortable with the Law of Demeter if it were called the Suggestion of Demeter.

- An acknowledged issue with state-based verification is that it can lead to creating query methods only to support verification. It's never comfortable to add methods to the API of an object purely for testing, using behavior verification avoids that problem. The counter-argument to this is that such modifications are usually minor in practice.
