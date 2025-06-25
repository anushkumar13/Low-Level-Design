# Adapter Design Pattern (Structural Pattern)

## One-Line Definition

"Adapter Pattern converts one interface into another interface clients expect. It bridges the gap between incompatible interfaces without modifying their source code."

## Real-Life Analogy: Charger Adapter

Imagine you have a US laptop charger with flat pins ⚡ but you're in India where sockets are round.

* The US charger doesn't fit Indian sockets directly
* Instead of changing the charger or the socket (which is impossible), you use an **adapter**

### Result:

* US charger plugs into the adapter
* Adapter plugs into Indian socket
* ✅ Compatibility achieved without modifying charger or socket

## Software Analogy

### Problem:

You have an existing class `OldLogger`:

```java
class OldLogger {
    void log(String msg) {
        // Old logging logic
    }
}
```

Your new system uses an interface `ILogger`:

```java
interface ILogger {
    void writeLog(String msg);
}
```

### Incompatibility:

`OldLogger` uses `log()` but the new system expects `writeLog()` from `ILogger`

### Solution: Use Adapter Pattern

Create an adapter that implements `ILogger` and internally uses `OldLogger`:

```java
class LoggerAdapter implements ILogger {
    private OldLogger oldLogger = new OldLogger();

    public void writeLog(String msg) {
        oldLogger.log(msg); // Adapting the method call
    }
}
```

### Result:

* The new system uses `ILogger` and calls `writeLog()`
* Internally, `log()` is called from `OldLogger`
* ✅ Old class reused without changing its code

## When to Use Adapter Pattern

* You have legacy code (old classes) with a different interface
* You want to reuse old code in a new system
* You can't (or shouldn't) modify the existing code
* You need to connect incompatible interfaces

## Real-World Examples

| Real World Use        | Description                                        |
| --------------------- | -------------------------------------------------- |
| Mobile Charger        | Adapts charger plug to fit socket                  |
| Card Reader           | SD card plugs into USB port using reader (adapter) |
| `Arrays.asList()`     | Converts array to List in Java                     |
| Spring HandlerAdapter | Adapts controllers to work with Spring Dispatcher  |

## Summary

**Adapter Pattern** helps two incompatible classes work together by wrapping one class with an adapter that translates calls into the expected format. It's like a smart bridge or jugaad system that enables code reuse and compatibility without rewriting original code.

---

## Adapter Design Pattern: Real-Life & Code Analogies

### ✨ Easy Real-Life Example: Mobile Charger Adapter

Imagine you're on a trip to Europe.

You have:

* ✅ An Indian mobile charger (with 2 round pins)
* ❌ But the European wall socket only accepts 3 flat pins

**Problem:** Your charger doesn't fit.

**Solution:** You use a charger adapter:

* It converts your Indian charger's plug to fit into the European socket
* ✅ Same charger
* ✅ Same socket
* ✅ No change to the actual charger or socket
* ✅ Adapter just *bridged* the compatibility gap

**➡️ This is the Adapter Pattern in action!**

---

### 🧠 Programming Imagination:

You have an `OldCharger` class with a method:

```java
chargeWithRoundPins()
```

But the new system only accepts:

```java
chargeWithFlatPins()
```

**Mismatch!** Their interfaces are different, even if their functionality is the same.

**✅ Adapter Pattern to the Rescue:**
You create a `ChargerAdapter` class that:

* Implements `chargeWithFlatPins()`
* Internally calls `chargeWithRoundPins()` from the `OldCharger`

Result:

* System sees the correct interface
* Old charger works without being modified
* Everything functions seamlessly

---

### 📦 Another Easy Analogy: Headphone Jack 🎧

You have a 3.5mm headphone

* But your new phone only has a USB-C port

**Solution:** Use a 3.5mm-to-USB-C adapter

* ✅ Headphone stays the same
* ✅ Phone stays the same
* ✅ No code or design change
* ✅ Adapter enables compatibility

---

### 🔥 Final Bhai-Style Summary:

**Adapter Pattern** is used when:

* Two existing systems/classes/interfaces are not directly compatible
* But you want them to work together without modifying their original code

You create an **Adapter class** that:

* Acts as a *bridge* between the two
* Converts one interface to another

> Adapter Pattern = Compatibility jugaad between incompatible interfaces — without touching their code. ✅

---