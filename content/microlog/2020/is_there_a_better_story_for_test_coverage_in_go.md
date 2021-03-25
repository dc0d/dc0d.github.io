---
title: "Is there a better story for test coverage in Go?"
date: 2020-05-23T20:19:15+02:00
draft: false
---

So far, using Go Modules, it is possible to:

```
$ go test -count=1 -coverprofile=./cover/profile.out -covermode=atomic -coverpkg ./...
$ go tool cover -html=./cover/profile.out -o ./cover/coverage.html
```

Still, stuff are missing - maybe a story for another time.
