## What are Design Patterns

Okay so design patterns are like smart ways or tricks that experienced programmers already figured out to solve common coding problems. They are not full code but more like reusable ideas or blueprints that we can follow. This helps us write better and cleaner code.

---

### Simple Definition:

"Design patterns are like tried and tested solutions that help solve common design problems in programming."

---

### Real Life Example:

Like when someone builds a house, they don’t design it from zero every time. They use ready-made plans like 1BHK, 2BHK, duplex etc. These plans already work well, so they save time and effort.

Same way in coding, we use design patterns instead of inventing new ways for every problem.

---

### Why Use Design Patterns

* Helps write code that we can reuse later
* Makes our code easier to understand and maintain
* Saves time because we use existing solutions
* Good when working in teams, everyone follows same style

---

### Types of Design Patterns

There are 3 main types of design patterns:

---

### 1. Creational Design Patterns

These help us when we need to create objects in a better way. Instead of always using `new`, we can use different ways depending on the situation.

**Example from real life:**

If I want a pizza, I can make it from scratch step-by-step (builder), or I can order one from a shop (factory).

**Common Patterns:**

| Pattern Name     | What it does                                                      |
| ---------------- | ----------------------------------------------------------------- |
| Singleton        | Makes sure only one object of a class is ever created             |
| Factory Method   | Lets another class decide what object to create                   |
| Builder          | Helps make big complex objects step-by-step                       |
| Prototype        | Lets you copy an existing object                                  |
| Abstract Factory | Lets you create a group of related objects (factory of factories) |

---

### 2. Structural Design Patterns

These help with how to organize classes and objects in our code properly.

**Example from real life:**

Like in a house, fridge is in the kitchen, bed is in bedroom. Everything has a place. Same idea goes with objects in code.

**Common Patterns:**

| Pattern Name | What it does                                                   |
| ------------ | -------------------------------------------------------------- |
| Adapter      | Helps connect two things that don’t match directly             |
| Decorator    | Adds extra features to object without changing original object |
| Composite    | Lets you treat group of objects as just one object             |
| Proxy        | Uses another object to control access to something             |
| Facade       | Gives a simple interface to a big complicated system           |
| Flyweight    | Reuses common objects to save memory                           |
| Bridge       | Separates what an object does from how it does it              |

---

### 3. Behavioral Design Patterns

These are about how objects interact with each other and how they behave.

**Example from real life:**

In school, teacher gives orders and students follow. Or a manager assigns tasks to employees. Same idea in code.

**Common Patterns:**

| Pattern Name            | What it does                                                      |
| ----------------------- | ----------------------------------------------------------------- |
| Observer                | Notifies all related objects when one changes                     |
| Strategy                | Allows changing logic (algorithm) at runtime                      |
| Command                 | Wraps a request or action as an object                            |
| State                   | Changes object behavior based on current internal state           |
| Iterator                | Lets you go through a collection step by step                     |
| Mediator                | Controls how objects talk to each other using one central place   |
| Template Method         | Puts common steps in base class, and special steps in child class |
| Chain of Responsibility | Passes a request from one object to another till it's handled     |

---

### Final Summary:

| Type       | What it is for                          |
| ---------- | --------------------------------------- |
| Creational | Smart ways to create objects            |
| Structural | How to arrange or connect objects       |
| Behavioral | How objects talk and behave with others |

---