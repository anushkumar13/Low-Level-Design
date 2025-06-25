# Chain of Responsibility Design Pattern

## What Is It?

The **Chain of Responsibility** design pattern allows a request to pass through a chain of handlers until one of them handles it. Each handler decides whether it can process the request — if not, it forwards it to the next handler in the chain.

---

## One-Line Definition:

"A request travels through a chain of objects, and the one capable of handling it takes responsibility."

---

## Real-Life Example: Customer Care IVR System

Imagine you call a customer care number:

1. An **automated bot** answers the call.
2. It says: “Press 1 for recharge, 2 for network issues, 3 to talk to a human...”
3. You press 2 → your call goes to the **network support team**.
4. If the network team can’t solve it, they escalate it to **senior support**.
5. Finally, someone handles your request.

Here:

* Each level (bot, network support, senior support) is a **handler**.
* Each handler checks: "Can I handle this?"

  * **If yes**, it processes the request.
  * **If no**, it forwards to the next handler.

This is exactly how the Chain of Responsibility pattern works.

---

## Where It’s Used in Programming?

### 🔹 Logging Systems:

```
DebugLogger → FileLogger → ErrorLogger
```

Each logger decides: "Is this my level?"
If yes → log the message. If not → pass it on.

### 🔹 GUI Event Bubbling:

```
Button → Panel → Window
```

If the button doesn’t handle the event, the panel tries, then the window.

### 🔹 Middleware Systems:

```
AuthMiddleware → LoggingMiddleware → ErrorHandlingMiddleware
```

Each middleware layer processes or passes the request.

---

## Benefits

| Benefit            | Why It’s Awesome                                            |
| ------------------ | ----------------------------------------------------------- |
| **Loose Coupling** | The sender doesn’t need to know who will handle the request |
| **Flexible Chain** | You can easily add/remove/reorder handlers                  |
| **Cleaner Code**   | Each handler has a single responsibility                    |

---

## Bhai Style Summary:

When you have a situation where **a request doesn’t go to just one object**, but instead **moves through a chain** — and **whichever object is capable takes care of it** — that’s when you use the:

💥 **Chain of Responsibility Pattern** 💥

Perfect for support systems, logging, event handling, and middleware architectures!

---

# Core Concepts of Chain of Responsibility Pattern

## ✅ Question 1:

**"Do all handler objects need to implement a common interface?"**

✔️ Yes, absolutely!
Every handler (object) in the chain must implement a **common interface** or extend an **abstract class** that defines a method like:

```java
void handleRequest(Request request);
```

### Why?

* To ensure all handlers can be treated **uniformly**
* Enables **polymorphism**, allowing the chain to work seamlessly

---

## ✅ Question 2:

**"Does each handler object hold a reference to the next one in the chain?"**

✔️ Yes — and that’s what makes it a **chain**!
Every handler holds a reference to the **next handler** in line. If it can't process the request, it simply passes it to the next:

```java
nextHandler.handleRequest(request);
```

➡️ This continues until:

* A handler processes the request
* Or the end of the chain is reached

---

## 🎯 Quick Story Style Explanation:

Each handler is like an employee in a team.

* Every employee knows who the **next employee** is.
* When a task (request) comes:

  * The employee checks: **"Can I handle it?"**

    * If yes → they handle it.
    * If no → they pass it to the **next employee**.

This continues down the chain until someone takes care of it.

---

## 📦 Bhai Style Final Summary:

✅ In the Chain of Responsibility pattern:

* All handler objects must implement a **common interface or abstract class**
* Each handler holds a reference to the **next handler**

These two are the **core foundations** of the pattern — without them, the chain can't function 💡

---