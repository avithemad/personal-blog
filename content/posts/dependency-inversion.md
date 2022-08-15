---
title: "Dependency Inversion"
date: 2022-08-15T19:10:06+05:30
categories: ["Programming"]
ShowToc: true
---

### Intro

Dependencies are common in programming. Any system you are programming with a medium to high complexity will have also have dependencies between modules.
Dependency inversion principle is one of the principle from SOLID (single responsibility, open-closed, liskov substitution, interface-segregation, dependency inversion). These were promoted by [Robert C. Martin](http://blog.cleancoder.com/).

### Definition

The definition of Dependency Inversion principle goes like this

- _High level modules should not depend on low-level modules. Both should depend on abstractions_
- _Abstractions should not depend upon details. Details should depend upon abstractions._

### Example

One of the best example is repository pattern. Here we have an abstraction of repository. The business/domail layer depends upon this abstraction for persisting data, but it does not need the details of whether data is persisted in SQL database or a spreadsheet. On the other hand the class implementing this abstration will depend upon the abstractions and implement these details in whichever persistence it can.

Here the high level module that is business layer does not depend on the low level module like SQL or spreadsheet, and both repository's implementation and business layer depend upon the abstraction of the repository. Also, the abstraction does not depend on the details, instead details i.e., class implementing the repository will depend on the abstraction of repository.

This is also a way to decouple high level modules from low level implementation.

### An analogy

Take the system of transportation. Suppose we want to get from place A to B, now this is an abstract concept. How do we get there is a low level detail, like we can use a public transportation or private or go by walk. A cab service and our intentions are loosely coupled. If you depended only on the same cab for you to get from place A to B, it would be very inconvinient in times, this cab is not available and you have to wait a long time for this. Instead you and the cab service only depends on the abstraction that you need to get from place A to B, and one of the cab is assigned to you based on availability.

Another analogy is of Food. If you relied solely on a single type of food for survival, you would not survive for long. Instead the body depends on nutrition for its nourishment, so here nutrition is like an abstract concept and each food has different composition of nutrients. Now the body depends on certain quantity of nutrition which can be derived from multiple sources.

### Declarative and imperative

These are just some of my thoughts. Declarative is a paradigm of describing **WHAT** a program does and imperative is paradigm of describing **HOW** a program should do something.

With imperative programming it is difficult to achieve complex things quickly, since most of your time is spent in implementing the details. On other hand declarative programming gives faster results this is why scripting languages make it easier to achieve complex tasks. With declarative programming you only depend on what your problem is at hand and you provide high level instructions to achieve this.

### Black boxing

A concept I recently came across that programmers use is that of a black box. Now suppose there is a concept you need to learn in order to solve a particular problem. You can black box this concept meaning you only need to know what the inputs to this algorithm would be and what would be the output. For example Kalman filter, you need not know the implementation details in order to use it for your signal processing. But knowing so helps in tweaking and just improve general knowledge on the subject.

Abstractions and decomposition are what the whole system of software would boil down to. Dependency inversion is one of the principle that makes your code much easier to maintain and test.
