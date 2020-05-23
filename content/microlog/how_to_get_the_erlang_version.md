---
title: "How to get the Erlang version?"
date: 2020-05-24T00:17:36+02:00
draft: false
---

```
$ erl -eval 'erlang:display(erlang:system_info(otp_release)), halt().'  -noshell
```
