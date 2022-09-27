---
author: Alo
categories:
- Software Architecture
- Clean Architecture
date: "2022-09-25"
description: clean architecture in under 5 minutes
tags:
- clean-architecture
- software-architecture
title: clean architecture in a nutshell
draft: true
---

# Clean architecture in a nutshell


## Why ?

As with anything, understanding the why of an idea is probably the best way to approach a problem.

Clean Architecture, is a software architecture proposed by Uncle Bob (Robert C. Martin).

If I was to resume the goal of CA: _**to write maintainable code that will resist the time.**_

## How ?

There's plenty of resources out there to really dig into it, but the idea is to _** Isolate our domain logic by implementing boundaries**_.

To do so, Uncle Bob propose to:
1. Slice our application into four layers with distincts responsibilities,
2. Enforce a single direction of dependence

We can represent the whole Clean Architecture in one simple diagram: 
Four concentric circles, in the middle is Domain layer, then the Application layer and finally the Infrastructure and Presentation layer.

Each layer can only depend on its inner layer.
This means that the Domain layer does not depend on anything, and the outer layer, the presentation for example, can (and will!) depend on the domain layer but also the application layer.

In other words, the domain does not know anything about the actual interface.
The application layer, in charge of communicating to the domain, does not know about the interface either.

For the sports enthuasts, think about the domain as the rule of the game and the referee. The application is the captain of the team, and the outer layer, the players.


It's seemingly simple but powerful idea.
Basically Uncle Bob state the obvious, he gives a priority order to each layer.
Which one should rely on which one.

In software, dependencies are tricky. When a piece of code depends on another and that code changes, then the dependant have to change as well.

Ideally, you wouldn't have any dependencies, but that's obiviously impossible.
So Uncle Bob says: 'Well, hang on, let's try to see what should depend on what, so we don't spend out time rewriting the software'.

Anything in the outer layer is susceptible to change frequently: a new interface, a different DB.
But the domain logic, rarely changes. And if it does, then everything changes.

If a bank decide to change their rules about borrowing money, then obviously the interface HAS to change.
But if the interface changes, why should the bank rules change? That doesn't make sense.


### The domain layer - Core

The domain layer is central to our application. It contains all the domain related code of our application.

The domain is the 'real world thing our software is about'. It's the context in which the software lives.

If we build a banking application, then the domain is the bank itself, account, money... 
Domain lives with our without software. I was to delete my application, the bank would still be there.

### Application layer - Core

The application layer is the glue between our Domain, and the outer layers, namely the infrastructure layer, presentation layer, testing layer.

The application layers translate the domain needs in the application.

It contains the use cases for our application.

### Infrastructure layer

The infrastructure layer (often shortened to infra) is sometimes refered to the data layer. It contains the interfaces to access external services, such as databases, files, third-party services, configration files ...

### Presentation layer

The presentation layer is quite easy to understand. It provides a way for the user to interact with the application. It can be a web page, a web page, a native application or even a CLI.


### Testing layer

Not much to say here! This is where the tests live!
This layer might contains the mock and stubs, and any other tests related resources, such as E2E tests.


## In practice?

See ITFUB for a detailed walk-through, I'm going to build it in public.
But basically, you rely heavily on dependency inversion using interfaces 

# Summary

As always, good ideas are stating the obvious.

I had a crack at it earlier and it was quite verbose, but I'm keen to try it again to learn more.

