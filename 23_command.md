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