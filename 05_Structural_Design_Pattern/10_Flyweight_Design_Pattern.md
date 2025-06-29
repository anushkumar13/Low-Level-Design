# Flyweight Pattern - My Learning Notes

## What is Flyweight Pattern?

The Flyweight Pattern is used when there are thousands or even lakhs of objects which share some common data. Instead of creating separate objects for each instance, we share the common parts to save memory.

## Real-Life Example - Text Editor

Suppose I am building a text editor like MS Word and someone types:

```
AAAAAAABBBBBBBBBCCCCCCDDDDD
```

* A appears 7 times
* B appears 9 times
* C appears 6 times
* D appears 5 times

If I create a new object for each character, it will waste a lot of memory because all the A’s are exactly the same in terms of font, size, style etc. So, instead of making 7 different objects for A, I can create a single object and reuse it. The only thing that changes is its position on the screen, which I can pass externally.

This way, a single object is reused many times, which saves memory and improves performance.

## Key Concept

Flyweight pattern splits the state of the object into two parts:

| State Type      | Description             | Shared |
| --------------- | ----------------------- | ------ |
| Intrinsic State | Constant, internal data | Yes    |
| Extrinsic State | Variable, external data | No     |

For example, in a text editor:

* Intrinsic: character `A`, font = Arial
* Extrinsic: position (x, y), color

## Where to Use

| Use Case     | Reason                                    |
| ------------ | ----------------------------------------- |
| Text Editors | Characters repeat a lot                   |
| Games        | Many bullets, trees, or repeating sprites |
| Maps         | Same icons shown in multiple locations    |
| Chess        | Limited piece types reused on the board   |

## Pattern Structure

| Component         | Role                                                                 |
| ----------------- | -------------------------------------------------------------------- |
| Flyweight         | Interface with common methods                                        |
| ConcreteFlyweight | Implements Flyweight and actually stores shared data                 |
| FlyweightFactory  | Creates and returns shared Flyweight objects                         |
| Client            | Uses Flyweight objects and supplies the extrinsic data like position |

## My Summary

The Flyweight Pattern is very useful when there are many similar objects and memory is an issue. By splitting the shared data (intrinsic) and the varying data (extrinsic), I can reuse the same objects multiple times and make my code more efficient. It is very helpful in applications like text editors, games, map systems, or any other place where the same type of object repeats many times. This improves performance and reduces memory usage.

---