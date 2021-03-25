---
title: "Where to implement Ports in Ports and Adapters?"
date: 2020-06-05T06:25:27+02:00
draft: false
---

Ports on driver side, are implemented inside the application. Ports on driven side are implemented inside the infrastructure (outside the application).

Application here can be seen as usecases, which cover the core vocabulary - two inner layers of the onion.

> [Ports and Adapters](http://www.dossier-andreas.net/software_architecture/ports_and_adapters.html) is an architecture also known as Hexagonal Architecture.

{{< figure src="/images/ports-and-adapters.png" title="Ports & Adapters - image found on Google" >}}
