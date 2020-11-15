---
title: "What is the relationship between TDD and the half-life of the line of code?"
date: 2020-11-15T20:50:57+01:00
draft: false
---

> So there’s a variable that I didn’t know existed at that time, which is really important for the trade-off about when automated testing is valuable. It is the half-life of the line of code. If you’re in exploration mode and you’re just trying to figure out what a program might do, and most of your experiments are going to be failures and be deleted in a matter of hours or perhaps days, then most of the benefits of TDD don’t kick in, and it slows down the experimentation—a latency between "I wonder" and "I see".
>
> You want that time to be as short as possible. If tests help you make that time shorter, fine, but often, they make the latency longer. And if the latency matters and the half-life of the line of code is short, then you shouldn’t write tests.[^1]-[^2]-[^3]

### Other Interesting Parts

> Logging is all about being able to debug after something horrible goes wrong. In classic extreme programming style, you aren’t going to need it (YAGNI), so you don’t write it. Well, here you are going to need it, so you do write it. Even if you don’t end up ever needing it, you still need it.

> It’s always been my policy that nothing has to be tested. Lots of people write lots of code without any tests, and they make a bunch of money, and they serve the world. So clearly, nothing has to be tested.

> There are lots of forms of feedback, and one of the factors that goes into the trade-off equation for tests is: What’s the likelihood of a mistake? So if you have a getter, and it’s just a getter, it never changes. If you can mess that up, we have to have a different conversation. Tests are not going to fix that problem.

[^1]: [Kent Beck Interview](https://www.forbes.com/sites/oracle/2017/01/09/facebook-guru-and-agile-pioneer-kent-beck-reveals-the-mind-of-the-modern-programmer/?sh=14fd29d363d0#1dce857863d0)

[^2]: [Complete Interview - from Oracle](https://blogs.oracle.com/javamagazine/interview-with-kent-beck)

[^3]: IMO, it doesn't seem to be applicable while working on legacy code.