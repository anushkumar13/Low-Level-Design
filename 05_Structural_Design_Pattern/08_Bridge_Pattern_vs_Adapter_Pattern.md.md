# Bridge Pattern vs Adapter Pattern

## 🎯 Purpose

| Aspect              | Bridge Pattern                                                                    | Adapter Pattern                                             |
| ------------------- | --------------------------------------------------------------------------------- | ----------------------------------------------------------- |
| 🔧 Purpose          | To decouple abstraction from implementation                                       | To make incompatible classes work together                  |
| 📦 Use Case         | When you want both sides (abstraction and implementation) to evolve independently | When you need to use an existing class with a new interface |
| 🏗️ Designed During | Design time (used in new system design)                                           | Afterthought (used for existing code reuse)                 |
| 🔗 Relationship     | Abstraction ↔ Implementation (loose coupling)                                     | Client ↔ Adaptee (fixing interface mismatch)                |
| 🔄 Flexibility      | High – abstraction and implementation can grow separately                         | Low – adapts specific existing code                         |

## 💡 Real-Life Example

### 🔌 Adapter Pattern: Charger Adapter

Imagine you have an Apple charger (which doesn’t fit Indian plug sockets). You use an adapter to make the Apple charger work with the Indian socket.

* You don’t change the client code (you as a user).
* You just add an adapter in between to make the incompatible plug and socket work together.
* Adapter makes old code usable in a new environment.

### 🌉 Bridge Pattern: Remote & TV

Think of a TV remote. The remote is the **abstraction**, and the TV is the **implementation**.

* Both are connected via a bridge interface.
* You can add new remotes or new TVs without changing the other side.
* This was planned at **design time** for flexibility.

## 🤯 Super Simple Analogy

| Situation                                                                             | Pattern             |
| ------------------------------------------------------------------------------------- | ------------------- |
| You are building a new system where abstraction and implementation should be separate | **Bridge Pattern**  |
| You have old code that you want to use in a new system                                | **Adapter Pattern** |

## ✅ Final Summary

### 🧱 Bridge Pattern:

* Used when your system is complex.
* You want to **separate abstraction from implementation**.
* Gives **long-term flexibility and scalability**.

### 🔌 Adapter Pattern:

* Used when you have **existing code** that doesn't match the required interface.
* You create a **converter** (adapter) to reuse that code **without changing it**.

> Both are structural design patterns but solve **very different problems**. Bridge is proactive (for designing scalable systems), Adapter is reactive (for using old code in new systems).
