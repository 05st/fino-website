---
slug: /
sidebar_position: 1
---

# Introduction

Welcome to the Fino programming language documentation. If you believe any changes should be made on any page, please click the **Edit this page** button at the bottom and open a pull request.

Fino is a statically typed, general purpose, functional programming language. It primarily takes inspiration from Haskell and languages from the ML family.

Fino is designed with simplicity in mind. It offers an easy-to-read syntax and an expressive type system, all while maintaining a small set of features. Additionally, Fino aims to address some common issues / inconveniences presented by the programming languages it takes inspiration from (Haskell). For example: it is strictly evaluated and allows side effects, its records are not syntactic sugar, it uses a built-in data type for strings, and and the module system is very simple and intuitive (albeit lacking many planned features at the moment).

At the moment, Fino is not in a usable state (i.e. code generation is not completed yet). The compiler is planned to primarily target C, and additionally in the future, JavaScript.

Here is a rough outline of the progress so far:
- [X] Syntax, tokenization, parsing
- [X] Basic module system
- [X] Module verification (topological sorting, cycle detection)
- [X] Name resolution
- [ ] User-defined prefix, infix, and postfix operators
- [ ] Hindley-Milner type inference
- [ ] Algebraic data types
- [ ] Records with scoped labels
- [ ] Traits (i.e. Haskell typeclasses)
- [ ] Monomorphization
- [ ] Closure conversion / lambda lifting
- [ ] Code generation (to C)
- ...

