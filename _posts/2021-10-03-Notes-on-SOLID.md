---
layout: post
title: Notes on SOLID
excerpt_separator: <!--more-->
---

In preparation for looking for a [new job](https://twitter.com/lukestringer90/status/1432632589744066560?s=20) earlier this year I did some revision on the SOLID principles. These articles were helpful to refresh my understanding and ground it in Swift:

- [SOLID Principles Applied To Swift](https://www.marcosantadev.com/solid-principles-applied-swift/)
- [Open-Closed Principle in Swift](https://medium.com/movile-tech/open-closed-principle-in-swift-6d666270953d)

Below are the notes I took.

<!--more-->

---

The **SOLID** principles are as follows:

**Single Responsibility**

- Break down into smaller classes.
- There should be only 1 reason for a class to change.

**Open Closed (OSP)**

- Open: extend or change behaviours without effort.
- Closed: extend class without changing implementation.
- If class A uses class B, modifying class B should not also require class A to be modified. Class B is not closed if this is true.
- If a class depends on a global variable is it not closed.
- Encapsulation follows OCP.
    - Keep properties private.

**Liskov Substitution (LSP)**

- Derived class must be useable in place of base classes.
- Avoids problems when using inheritance _badly_.
- Examples:
    - Overriding a method and adding a precondition not present in the base class break LSP.
    - Post condition changes (for example setting a property to always be true) make a derived class different from a base class.
- Better to:
    - Move the changing logic into a interface function.
    - Or implement differently with two classes.
    - Rather than inheriting and changing the derivation

**Interface Segregation**

- Clients should not be forced to depend upon an interface that they do not use.
- Avoid implementing empty function from a "Fat Interface".
    - Break functions into smaller interfaces.
- Avoid "Fat Classes" that pass too much information to a function.
    - Define an interface for a subset of a class' functions
    - Those only needed for the client.
    - This makes is easier to sub the protocol for testing.

**Dependency Inversion**

- Important for reusable code.
- Reuse high level modules by removing tight coupling to low level modules.
- Abstract dependencies using protocols.
- Useful for testing.

