## Adapter Design Pattern (Structural Pattern)

### One-Line Definition

The Adapter Pattern is all about converting one interface into another that a client expects. Basically, it helps two incompatible interfaces work together without changing their original code.

### Real-Life Analogy: Charger Adapter

Let’s say you have a US laptop charger with flat pins but you're in India where sockets are round. The charger doesn’t fit. Instead of replacing the charger or changing the socket, you simply use an adapter.

What happens is:

* Your US charger plugs into the adapter
* The adapter plugs into the Indian socket
* You don’t change anything in the charger or the socket, yet everything works fine

This is exactly what the Adapter Pattern does in software too.

### Software Analogy

#### Problem:

You already have a class called `OldLogger` like this:

```java
class OldLogger {
    void log(String msg) {
        // Old logging logic
    }
}
```

But in your new system, everything expects an interface like this:

```java
interface ILogger {
    void writeLog(String msg);
}
```

Here’s the issue: `OldLogger` has a method called `log()` but the new system needs `writeLog()`.

#### Solution:

You make an adapter class that implements the `ILogger` interface and uses `OldLogger` inside.

```java
class LoggerAdapter implements ILogger {
    private OldLogger oldLogger = new OldLogger();

    public void writeLog(String msg) {
        oldLogger.log(msg); // This is where the translation happens
    }
}
```

Now:

* Your system still uses `ILogger`
* The adapter translates that call to the old method
* You didn’t touch the old class at all, and everything just works

### When to Use Adapter Pattern

* You have some old legacy classes whose code you can’t or don’t want to change
* But you want to use those classes in your new system
* And the interfaces don’t match up
* So you build a small adapter to make them compatible

### Real-World Examples

| Real World Use        | What’s Happening                                  |
| --------------------- | ------------------------------------------------- |
| Mobile Charger        | Plug shape is changed to fit socket               |
| Card Reader           | SD card fits into a USB port using an adapter     |
| Arrays.asList()       | Converts an array to a List in Java               |
| Spring HandlerAdapter | Makes controllers work with the Spring Dispatcher |

### Summary

The Adapter Pattern is just a neat way to help two mismatched classes work together. You wrap one of them inside an adapter and translate calls so that everything flows smoothly. It’s like a smart workaround to make old and new code talk to each other.

---

### Adapter Pattern in Real Life and Code

#### Easy Real-Life Example: Mobile Charger Adapter

Imagine you’re traveling to Europe.
You have:

* An Indian charger (with round pins)
* But the socket only takes flat pins

Problem: You can’t plug it in.

Solution: Use an adapter.

* The adapter converts round pins to flat ones
* Your charger and the socket stay as they are
* No changes, but it all works

This is exactly what the Adapter Pattern does in code.

---

#### Code Example Style:

Let’s say you have this old charger class:

```java
chargeWithRoundPins()
```

But the system expects:

```java
chargeWithFlatPins()
```

There’s a mismatch. You make an adapter class:

* It implements `chargeWithFlatPins()`
* Internally it calls `chargeWithRoundPins()`

That’s how it works: you bridge the gap without touching old code.

---

#### Another Real-Life Example: Headphone Jack

You have normal headphones with a 3.5mm jack.
But your new phone only has a USB-C port.

You don’t throw away your headphones or your phone.
You just buy a 3.5mm-to-USB-C adapter.

It lets both things work without any modification.

---

### Final Summary

Adapter Pattern is super useful when:

* You already have some code but it doesn’t match the interface you now need
* You want to reuse that old code
* You can’t (or don’t want to) change the old code

So instead, you create an adapter class that:

* Acts like a bridge between the old and new
* Converts one interface into the other

In short, it’s a practical way to make two different systems work together without rewriting either of them.

---