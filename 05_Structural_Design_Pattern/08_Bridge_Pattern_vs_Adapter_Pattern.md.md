# Bridge Pattern vs Adapter Pattern

## Purpose

| Aspect          | Bridge Pattern                                                                    | Adapter Pattern                                             |
| --------------- | --------------------------------------------------------------------------------- | ----------------------------------------------------------- |
| Purpose         | To decouple abstraction from implementation                                       | To make incompatible classes work together                  |
| Use Case        | When you want both sides (abstraction and implementation) to evolve independently | When you need to use an existing class with a new interface |
| Designed During | Design time (used in new system design)                                           | Afterthought (used for existing code reuse)                 |
| Relationship    | Abstraction and Implementation (loose coupling)                                   | Client and Adaptee (fixing interface mismatch)              |
| Flexibility     | High – abstraction and implementation can grow separately                         | Low – adapts specific existing code                         |

## Real-Life Example

### Adapter Pattern: Charger Adapter

Suppose I have an Apple charger which doesn’t fit into an Indian plug socket. To solve this, I use an adapter.

* The Apple charger (old code) doesn’t change.
* The Indian socket (new interface) stays the same.
* I use an adapter in between to make them compatible.

This is similar to how the Adapter Pattern helps to reuse old code in a new environment by fixing interface mismatches.

### Bridge Pattern: Remote and TV

Now think of a remote control and a TV. The remote is the abstraction, and the TV is the implementation.

* The remote can control any TV through a common interface.
* I can add new remotes or TVs without changing existing classes.
* This was planned during design to allow flexibility.

This is how the Bridge Pattern separates abstraction and implementation from the beginning.

## Simple Analogy

| Situation                                                                             | Pattern         |
| ------------------------------------------------------------------------------------- | --------------- |
| You are building a new system where abstraction and implementation should be separate | Bridge Pattern  |
| You have old code that you want to use in a new system                                | Adapter Pattern |

## Final Summary

### Bridge Pattern:

* Useful when designing a new, scalable system.
* Helps to separate abstraction from implementation.
* Designed for long-term flexibility and maintainability.

### Adapter Pattern:

* Useful when trying to reuse existing code in a new system.
* Acts like a converter to make incompatible interfaces work together.
* Designed to make old code fit without modification.

Both Bridge and Adapter are structural design patterns, but they serve very different purposes. Bridge is about designing scalable systems from the beginning, while Adapter is about making old code usable in new scenarios.

---