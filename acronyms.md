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

## O - Open/Closed Princple

## L - Liskov Substitution Principle

## I - Interface Segregation Principle

## D - Dependency Inversion Principle

# Y.A.G.N.I.
**Y**ou **A**ren't **G**onna **N**eed **I**t

This principle is meant to combat the clever developer's tendency to implement
far more functionality than they actually need to get the job done.
