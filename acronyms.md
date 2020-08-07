# Overview
This document contains software development principles that have an acronym for
remembering them.

- D.R.Y.
- S.O.L.I.D.
- Y.A.G.N.I.

# D.R.Y
**D**on't **R**epeat **Y**ourself

When you find yourself copying a chunk of code and changing some small part of
it, consider whether you can extract that chunk of code into a function in
which the part that changes becomes a parameter.

# S.O.L.I.D.
This acronym refers to 5 different principles meant to apply to object-oriented 
programming, but may be relevant otherwise.

A good explanation of each can be found [here](https://deviq.com/solid/).

## S - Single Responsibility Principle
> A class should have only one reason to change.

## O - Open/Closed Princple
> Software entities (classes, modules, methods, etc.) should be **open** for
> extension, but **closed** for modification.

## L - Liskov Substitution Principle
> Subtypes must be substitutable for their base types.

## I - Interface Segregation Principle
> Clients should not be forced to depend on interface methods that they do not
> use.

## D - Dependency Inversion Principle
> High level modules should not depend on low level modules; both should depend
> on abstractions. Abstractions should not depend on details. Details should
> depend on abstractions.

# Y.A.G.N.I.
**Y**ou **A**ren't **G**onna **N**eed **I**t

This principle is meant to combat the clever developer's tendency to implement
far more functionality than they actually need to get the job done.
