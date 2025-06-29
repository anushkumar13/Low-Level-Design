## Facade vs Proxy Design Pattern

### Overview

Okay so sometimes these patterns kinda look similar, but actually their purpose is not the same at all. So I thought I should just write it down in my own words, so that I don't get confused later.

---

### One-Line Definition

| Pattern | What It Does                                                    |
| ------- | --------------------------------------------------------------- |
| Proxy   | It acts like a middleman and controls access to the real thing  |
| Facade  | It gives one simple way to use a system that's actually complex |

---

### Story-Style Analogy

#### Proxy Pattern (Security Guard Example)

So imagine you wanna go inside a server room. But there's a security guard there.

The guard:

* Checks your ID
* Sees if you're allowed to go inside
* And then lets you in or stops you

So you are not directly talking to the server room. You're going through the guard. That guard is like a **proxy**. He is there to protect or manage access.

#### Facade Pattern (Receptionist Example)

Now imagine you walk into a hotel. There are so many services there:

* Kitchen
* Spa
* Billing
* Housekeeping

If you had to go to each one for every small thing, that would be annoying and messy.

But instead, you just go to the receptionist and say:

* "Can I get food please?"
* "Can you clean my room?"
* "I wanna checkout."

And the receptionist handles everything behind the scenes. That’s a **facade** — one simple person who makes your life easy.

---

### Comparison Table

| Point             | Proxy Pattern                             | Facade Pattern                            |
| ----------------- | ----------------------------------------- | ----------------------------------------- |
| Purpose           | Controls or restricts access              | Makes a complex system easier to use      |
| Behavior          | Pretends to be real object and adds logic | Gives a neat interface to many subsystems |
| Client Sees       | Just a proxy (feels like the real thing)  | A single, simple entry point              |
| Real Object       | Only one real object behind it            | Many different subsystems behind it       |
| Real-Life Example | Security guard, ATM card                  | Hotel receptionist, remote control        |
| Design Intent     | Used for control, protection, delay       | Used for simplicity and abstraction       |

---

### Final Summary

**Proxy Pattern** is like when you need a gatekeeper for an object. It helps in protecting it, adding logging, or delaying its usage.

**Facade Pattern** is for when you’re dealing with something too big or complex, and you just want an easy way to use it.

> So yeah... proxy protects, facade simplifies. That’s how I try to remember it.
