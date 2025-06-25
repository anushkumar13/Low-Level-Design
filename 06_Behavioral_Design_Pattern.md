# Behavioral Design Patterns (Gang of Four)

## What Are Behavioral Design Patterns?

Behavioral design patterns are used to define **how objects interact with each other**, how responsibilities are distributed among them, and how the **flow of behavior** is managed in the system.

These patterns help achieve:

* **Loose coupling** between objects
* **Better communication flow**
* **Improved flexibility and maintainability**

They focus on:

* Who does what
* How requests or events are handled
* How behavior flows through the system

---

## List of Behavioral Design Patterns (with Real-World Style Explanation)

| Pattern Name                | Bhai-Style Explanation                                                                 |
| --------------------------- | -------------------------------------------------------------------------------------- |
| **Strategy**                | When the algorithm is interchangeable — like choosing Paytm, UPI, or Cash at checkout  |
| **Observer**                | When one change updates many others — like YouTube notifications after you subscribe   |
| **Command**                 | When you turn a request into an object — like RemoteControl with undo/redo buttons     |
| **Iterator**                | When you need to go through items one by one — like using `next()` and `hasNext()`     |
| **Mediator**                | When multiple objects talk via one middleman — like Air Traffic Control                |
| **Memento**                 | When you need to save/restore object state — like Undo in MS Word                      |
| **State**                   | When object behavior depends on internal state — like Fan speed (Low/Med/High)         |
| **Template Method**         | When structure is fixed but steps are flexible — like making Tea or Coffee             |
| **Chain of Responsibility** | When a request goes through multiple handlers — like Customer Care IVR                 |
| **Visitor**                 | When you want to add operations without changing classes — like Tax visiting Employees |
| **Interpreter**             | When you need to parse or interpret a language — like Regex or SQL parser              |

---

## Summary

Behavioral Design Patterns are all about:

* Structuring **how objects communicate**
* Assigning **responsibility clearly**
* Keeping **interaction loosely coupled**

They help create software where:

* Behavior is more flexible
* Code is easier to maintain
* Communication is clean and well-managed

---

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

# Command Design Pattern

## What Is It?

The **Command Design Pattern** turns a request into an object. This lets you parameterize clients with commands, queue them for execution, log them for auditing, or support undoable operations.

---

## 🎯 One-Line Definition:

"Command Pattern converts a request into an object so it can be stored, queued, undone, or executed later."

---

## 🕹️ Real-Life Example: Remote Control

Imagine you have a **remote control**:

* Each button does something: Turn TV On, Turn TV Off, Increase Volume, etc.
* The **remote itself doesn’t know how to perform** the action — it just calls `command.execute()`.
* The **command object** knows which **receiver** to talk to and what to tell it to do.

So:

* You press a button → Remote calls `command.execute()` → Command tells TV what to do

---

## 🧠 Command Pattern Roles

| Role                | Description                                                   |
| ------------------- | ------------------------------------------------------------- |
| **Command**         | Interface with a method like `execute()`                      |
| **ConcreteCommand** | Class that implements Command and works with a Receiver       |
| **Receiver**        | The actual object that performs the action (e.g., TV, Light)  |
| **Invoker**         | The object that triggers the command (e.g., RemoteControl)    |
| **Client**          | The one who creates the command and assigns it to the Invoker |

---

## 📦 Where Is It Used?

* Remote control systems: `LightOnCommand`, `FanOffCommand`
* Undo/Redo functionality: Every action is a Command object
* Job scheduling systems: Queue up command objects for later execution
* GUI buttons: Pressing a button triggers a Command
* Macro recording: Record a list of commands for later replay

---

## 💡 Bhai-Friendly Story Style Summary:

Imagine:

* `Light` = **Receiver** (knows how to turn on/off)
* `LightOnCommand` = **Command** (knows what to ask the receiver to do)
* `RemoteControl` = **Invoker** (only calls `command.execute()`)
* **You (Client)** set the command in the remote button

Now:

* You press the button → `RemoteControl` calls the command → command turns on the light

✅ This provides:

* **Loose coupling** (Invoker doesn’t know the internal logic)
* **Flexibility** (commands can be swapped at runtime)
* **Undo/Redo support** (store command history)

---

## 📦 Final Summary:

Use the Command Pattern when you want to:

* Wrap a request into an object
* Parameterize or schedule actions
* Support undo/redo
* Decouple sender from receiver

It’s perfect for remote controls, GUI actions, job queues, and more!

---

# Is `execute()` Method Mandatory in Every Command Class?

## 🔥 The Question:

**"Should every Command class have an `execute()` method?"**

## ✅ The Answer:

**YES, absolutely!**

### Why?

Because the **core concept** of the Command pattern is:

* Every command must implement a **common interface or abstract class**
* This interface defines one method: `execute()`

Each concrete command class like:

* `LightOnCommand`
* `FanOffCommand`
* `VolumeUpCommand`

...must implement the `execute()` method. Without it, the pattern breaks.

---

## 🧠 Understand With Code:

```java
interface Command {
    void execute(); // 🔥 All command classes MUST implement this!
}

class LightOnCommand implements Command {
    public void execute() {
        light.turnOn(); // Performs the specific action
    }
}
```

### Why Is This Important?

The **Invoker** (like a RemoteControl or GUI button) doesn't care what the command does. It only knows:

```java
command.execute();
```

➡️ If a command class doesn't implement `execute()`, the code won't compile or will fail at runtime.

---

## 💡 Bonus Tip: Optional Methods

In advanced use cases, you may add methods like:

* `undo()`
* `redo()`
* `getName()`
* `canExecute()`

But `execute()` is **mandatory** in every Command class.

---

## 🎯 Bhai Style Final Summary:

✅ Yes bro! Every Command class **must** have an `execute()` method.
It’s the **core principle** of the pattern.

The `execute()` method defines what action the command performs.

Without it — there is no command!
No action, no trigger — the whole pattern collapses. 💣

---

# Does a Command Have a Has-a Relationship with the Receiver?

## 🔥 The Question:

**"Should a Command object have a has-a relationship with its Receiver?"**

## ✅ The Answer:

**YES — 100% it must!**

---

## 🔍 Why Is It Necessary?

The primary job of a **Command** object is:

* To **tell the Receiver what to do**

But it can’t do that unless it has a reference to the Receiver.
Without the Receiver, a Command has no way to perform any real action.

---

## 📦 Bhai Style Breakdown of Roles:

* **Invoker**: Only calls `command.execute()`
* **Command**: Knows *what* needs to be done
* **Receiver**: Knows *how* to do it (actual implementation)

So, the Command must have a reference to the Receiver — a **has-a** relationship.

---

## ✅ Java Example:

```java
class LightOnCommand implements Command {
    private Light light; // ✅ Has-a relationship with Receiver

    public LightOnCommand(Light light) {
        this.light = light;
    }

    public void execute() {
        light.turnOn(); // 💥 Performs the action on the Receiver
    }
}
```

➡️ `LightOnCommand` has a reference to `Light` — this is the **has-a relationship**

---

## ✅ UML Representation:

```
+--------------------+         +----------------+
| LightOnCommand     |<------->|   Light        |
|--------------------|   Has-a|----------------|
| - light: Light     |         | +turnOn()      |
| +execute()         |         +----------------+
+--------------------+
```

---

## 🎯 Final Bhai-Style Recap:

✅ Yes bro — every concrete Command class **must have a reference to the Receiver**
✅ This is called a **has-a relationship**
✅ Without the Receiver, the Command is just an empty shell — it can’t perform any action!

That Receiver is what gives the Command its actual power! ⚡

---

# Mediator Design Pattern

## What Is It?

The **Mediator Design Pattern** is used to reduce complex communication between multiple objects by introducing a **central mediator object** that handles the interactions.

---

## 🎯 One-Line Definition:

"The Mediator pattern avoids direct communication between objects and lets them interact through a central mediator."

---

## 🛫 Real-Life Example: Air Traffic Control (ATC)

Imagine:

* Multiple planes are approaching or leaving a runway.
* If each plane tries to communicate with every other plane directly → total chaos!

Instead:

* Every plane talks to one **Air Traffic Controller (ATC)**.
* The ATC decides:

  * Who lands
  * Who takes off
  * Who must wait

➡️ **Planes = Colleague objects**
➡️ **ATC = Mediator**

---

## 😨 Without Mediator:

* Each object needs to know about every other object
* Example: 100 planes = 100 x 99 = 9,900 connections!
* Highly coupled, hard to maintain

## 😎 With Mediator:

* Each object only communicates with the mediator
* Example: 100 planes = only 100 connections (to mediator)
* Clean, simple, loosely coupled

---

## 🧠 Programming Structure

| Component                  | Description                                              |
| -------------------------- | -------------------------------------------------------- |
| **Mediator (interface)**   | Defines how objects communicate via the mediator         |
| **ConcreteMediator**       | Implements the coordination logic between colleagues     |
| **Colleague (components)** | Objects (like planes) that send/receive via the mediator |

---

## 📦 Real-World Use Cases

* **Chat Rooms**: Users send messages through a central ChatRoom
* **GUI Widgets**: Buttons, textboxes, checkboxes communicate via mediator
* **Games**: Players interact using a central game controller
* **Messaging Apps**: WhatsApp group messages go through a server (mediator)

---

## 🎯 Bhai Style Summary

✅ When you have multiple objects interacting directly and heavily
✅ And you want to centralize their communication via one object
✅ To make the system clean, maintainable, and loosely coupled

Then you use the **Mediator Pattern** 💡

---

## 💬 One Line To Remember:

"Colleagues should not talk to each other — they should all talk to the Mediator."

---

# Observer Design Pattern

## What Is It?

The **Observer Design Pattern** defines a one-to-many dependency between objects so that when one object changes state, all its dependents (observers) are automatically notified and updated.

---

## 🎯 One-Line Definition:

"When a Subject changes, all its Observers are automatically notified."

---

## 📱 Real-Life Example: YouTube Channel Subscription

Imagine:

* You subscribe to a YouTube channel
* You also press the bell icon 🔔

Now when the channel uploads a new video:

* It doesn’t send messages to every subscriber manually
* It just calls `notify()`

And instantly:

* All subscribed users (observers) receive the update

✅ **Channel** = Subject
✅ **Subscribers** = Observers
✅ **New video** = State change event
✅ **Notification** = Update sent to observers

---

## 🧠 Programming Structure

| Component            | Role                                              |
| -------------------- | ------------------------------------------------- |
| **Subject**          | The object being observed (e.g., YouTube channel) |
| **Observer**         | Listens for changes (e.g., subscribers)           |
| **ConcreteSubject**  | Implements the actual logic of the subject        |
| **ConcreteObserver** | Implements update behavior                        |

---

## 🔁 Real-World Examples

* **News App**: Weather updates sent to all subscribed widgets
* **Stock Market App**: Price change updates all chart views
* **GUI Buttons**: Clicking a button notifies all registered listeners
* **Social Media**: Following someone → get updates when they post

---

## 🔥 Benefits

| Benefit            | Explanation                                                |
| ------------------ | ---------------------------------------------------------- |
| **Loose Coupling** | Subject doesn’t need to know details of its observers      |
| **Dynamic**        | Observers can be added/removed at runtime                  |
| **Event-Driven**   | Makes reactive/event-driven programming easier and cleaner |

---

## 🎯 Bhai Style Summary

✅ Use the **Observer Pattern** when:

* One object changes
* And you want multiple other objects to automatically react to that change
* Without tightly coupling them

---

## 💬 One Line To Remember:

"Subject notifies → Observers react."

---

# Iterator Design Pattern

## What Is It?

The **Iterator Design Pattern** provides a way to access elements of a collection sequentially **without exposing its underlying representation**.

---

## 🎯 One-Line Definition:

"Iterator pattern allows sequential access to collection elements without revealing internal structure."

---

## 📺 Real-Life Example: TV Remote / Instagram Reels

### Scenario 1: TV Remote

* You have a remote with 100 channels.
* You just press **next** or **previous**.
* You don’t know **how channels are stored** internally (array, list, DB?)
* You can **scroll through them one by one** — that’s what Iterator does.

### Scenario 2: Instagram Reels / YouTube Shorts

* You swipe up for the next video
* Each swipe gives you the next item
* You’re **iterating over content**, one at a time

✅ That’s real-world Iterator behavior!

---

## 🧠 Programming Structure

| Component            | Role                                             |
| -------------------- | ------------------------------------------------ |
| **Iterable**         | The collection containing data (e.g., List, Set) |
| **Iterator**         | Provides the mechanism for sequential access     |
| **ConcreteIterator** | Implements the actual traversal logic            |
| **Client**           | Uses the iterator to loop through elements       |

---

## 🔁 Real Use Cases

* Java collections like **List**, **Set**, **Map** all have `.iterator()`
* **For-each loop** (`for(String s : list)`) internally uses Iterator
* **Database cursors**
* **Tree and Graph traversals**

---

## 📦 Java Example:

```java
Iterator<String> it = list.iterator();
while(it.hasNext()) {
    String item = it.next();
    System.out.println(item);
}
```

➡️ `hasNext()` = Checks if another element exists
➡️ `next()` = Returns the next element

---

## 🎯 Bhai Style Summary

✅ Use the **Iterator Pattern** when:

* You want to access elements **one-by-one**
* Without knowing **how** they’re stored internally
* And want the access logic **separate from the collection**

---

## 💬 One Line To Remember:

"Iterator = remote control of a collection."

---

# When to Use the Iterator Design Pattern

## 🔥 The Core Idea:

Use the **Iterator Pattern** when you want to access elements of a collection **one-by-one**, **without knowing** how the collection is structured internally, and **you want control over the traversal** process.

---

## ✅ Situations to Use Iterator Pattern

### 1️⃣ When You Want to Hide the Internal Structure

* Example: A bookshelf
* The client should not know **how books are arranged** internally
* Client just uses `nextBook()` to go through the books

### 2️⃣ When You Need Multiple Traversal Strategies

* Example: Iterate **left to right**, **right to left**, **skip 2 by 2**, etc.
* You can create **custom iterators** for each traversal

### 3️⃣ When You Are Working With Trees or Graphs

* For example:

  * Tree traversals: **Inorder**, **Preorder**, **Postorder**
  * Graph traversals: **BFS**, **DFS**
* Each traversal can be implemented using its own iterator

### 4️⃣ When Implementing Undo/Redo or History Features

* Example: Browser Back/Forward buttons
* Use iterators to move back and forth through the visited pages list

### 5️⃣ When You Want the Client to Control the Traversal

```java
while(iterator.hasNext()) {
    iterator.next();
}
```

* The client decides **when** to move forward, **when** to stop, and **how** to iterate

---

## 💬 Bhai Style 1-Line Summary:

"Use the Iterator Pattern when you want to access any complex or simple collection **one-by-one**, **without diving into its internal structure**!"

---

# Visitor Design Pattern

## What Is It?

The **Visitor Design Pattern** allows you to add new operations to existing object structures **without modifying their classes**.

---

## 🎯 One-Line Definition:

"Visitor pattern lets you define new operations on objects without changing their class definitions."

---

## 🏛 Real-Life Example: Museum Entry Check

Imagine:

* A museum has different types of visitors:

  * **Students**
  * **Teachers**
  * **Foreigners**

Each type behaves differently at the ticket counter:

* Students show student ID → ₹10 ticket
* Teachers show staff ID → Free entry
* Foreigners show passport → ₹100 ticket

But the logic of "what to do" is with the **ticket checker**, not the visitors.
Visitors simply **accept** the operation.

✅ Ticket checker = **Visitor**
✅ Student/Teacher/Foreigner = **Visitable Elements**

---

## 🧠 Structure of the Pattern

| Role                    | Description                                            |
| ----------------------- | ------------------------------------------------------ |
| **Element (Visitable)** | Object on which operations are performed               |
| **Visitor**             | Interface defining visit methods for each element type |
| **ConcreteVisitor**     | Implements actual operations (e.g., calculate fee)     |
| **accept(visitor)**     | Method in elements to accept a visitor                 |

---

## 🧪 When to Use It?

Use the Visitor Pattern when:

* You have **multiple types of objects** in a structure
* You want to **perform new operations** on them
* But you want to avoid **modifying their original classes**

---

## 👨‍💻 Code World Example:

You have:

* `Employee`, `Manager`, `Intern` classes

Now you want to perform new tasks like:

* `generateSalarySlip()`
* `calculateBonus()`

Instead of modifying every class, you:

* Create a `Visitor` interface with `visit(Employee)`, `visit(Manager)`, etc.
* Implement those methods in a `ConcreteVisitor`
* Add `accept(Visitor v)` method in each class → it calls `v.visit(this)`

---

## 🔥 Bhai Style Summary:

✅ When you have **different types of objects** (like `Book`, `Magazine`, `Newspaper`)
✅ And you want to perform **new tasks** on them (like `printSummary`, `exportToPDF`, `calculateGST`)
✅ **Without modifying their internal class structure**

Then you use the **Visitor Pattern** 💡

---

## 💬 Bhai Style One Liner:

"Instead of writing logic inside the object, write it outside in a visitor!"

---