# Singleton Design Pattern - My Notes

## What is Singleton Pattern?

Singleton Pattern make sure that:

* Only one object of the class is created
* That one object is used everywhere in program
* No one can create more objects of that class again

## Simple Way to Understand:

Think like Wi-Fi router in your home. All people in home connect to same router. We don’t buy new router for everyone.

Same in Singleton Pattern — one object only, used by all.

## Real Life Examples I Learned:

### 1. Printer Spooler

* Only one print manager should exist
* All print commands go to same instance

### 2. Database Connection Manager

* Only one connection manager should be used
* If many are created, problems will come

### 3. Logger

* One logger should manage all log entries
* All classes use same logger object

## Why Singleton is Useful?

* Saves memory (only one object)
* Easy to use everywhere in app (globally accessible)
* Manages shared things like loggers, config etc.

## Problem Without Singleton:

If we do this:

```java
new PrinterSpooler();
new PrinterSpooler();
new PrinterSpooler();
```

Then:

* Many spoolers created
* Print jobs go here and there
* System become inconsistent

But with Singleton:

```java
PrinterSpooler.getInstance();
```

Then:

* Only one instance used
* All jobs handled from one place

## Summary:

Singleton Pattern = Only one object of class is made and same object used again and again. It gives control, saves memory, and works same everywhere.

---

## Real World Use Cases I Studied

### 1. Printer Spooler System

#### Problem:

* Many people print at same time
* If every one create new PrinterSpooler object:

  * Queue get messed
  * Printer get confused

#### Solution:

* Use Singleton PrinterSpooler
* Only one object handles all jobs
* It manage queue and print one by one

#### Why Singleton is Good Here:

* One physical printer only
* All print jobs go to same object
* No confusion or conflict

---

### 2. Logging System

#### Problem:

* Each class makes its own logger
* Logs go in different files
* Hard to debug

#### Solution:

* Use Singleton Logger
* One logger for all
* Logs stay in one place

---

### 3. Database Connection Pool

#### Why Singleton:

* Making new DB connection takes time and memory
* One pool of reusable connections is better
* Singleton manages all of them

---

### 4. Configuration Manager

#### Why Singleton:

* App settings like file paths, limits should come from same source
* Singleton give one common config object to everyone

---

### 5. Cache Manager

#### Why Singleton:

* Cache is in memory, shared by all
* Only one object should manage it
* So data stay same for all

---

## One-Line Summary:

Singleton Pattern is used when only one object should exist for whole application. It gives consistency, saves resources and control is better.

---

# Singleton Pattern Core Concepts - My Learning Notes

## Why Constructor is Private?

To stop others from creating new object using `new` keyword.
If constructor is public then:

```java
MySingleton obj = new MySingleton(); // This is wrong
```

Multiple objects will be created. This break Singleton Pattern.

### What Private Constructor Do:

* Only the class can make its object
* Outside classes can't use `new`

---

## Why We Use Static Method `getInstance()`?

This method create object only if it's not already created. Then return the same object every time.

### First Time:

```java
getInstance(); // It will create the object
```

### Later Calls:

```java
getInstance(); // Same object returned
```

So:

* Only one object is created
* All classes use same object

---

## Why `getInstance()` Must Be Static?

Yes, it must be static.
Because:

```java
MySingleton obj = MySingleton.getInstance();
```

If it's not static, then we need object to call it. But Singleton say we can't create object from outside. So we make method static.

---

## Summary Flow of Singleton:

| Step                 | What it do                                    |
| -------------------- | --------------------------------------------- |
| Private Constructor  | Stop others from using `new`                  |
| Static Variable      | Store the object in class                     |
| Static getInstance() | Make and give object if needed                |
| One-time creation    | Save memory and give same behavior every time |

---

## Bonus: Thread Safety (Advance Stuff)

In multi-thread system, if 2 threads call getInstance at same time, 2 objects can get created.

### How to Solve:

* Use synchronized block
* Use double-checked locking
* Use enum Singleton (Java recommended)

---

## Final Line:

To make Singleton work:

* constructor should be private
* one static object
* static method getInstance()

This way, only one object is created and used in whole app.

---

# Singleton vs Static - Confusion Solved

## Common Confusion:

People think if we use static, then it's Singleton. But it's not true.

## Truth:

Static just mean method or variable belongs to class, not object. It doesn’t stop object creation.

---

## Example:

```java
class MySingleton {
    static MySingleton obj = new MySingleton();
}
```

Yes, `obj` is static. But still someone can do:

```java
MySingleton obj1 = new MySingleton();
MySingleton obj2 = new MySingleton();
```

If constructor is public, then this code makes multiple objects. So static not stop it.

---

## What static Really Do?

* Belong to class, not objects
* Only one copy of static var exists
* Allow calling method without making object

---

## How To Make Sure Only One Object?

You have to write Singleton logic:

```java
if (instance == null) {
    instance = new MySingleton();
}
```

This create object only one time and return same object again and again.

---

## Final Summary:

| Concept        | Meaning                                                   |
| -------------- | --------------------------------------------------------- |
| `static`       | Class level thing, shared with all                        |
| Object control | Only possible by Singleton logic                          |
| Singleton      | Needs private constructor + static object + getInstance() |

> So static helps to share things, but to make one object only, you need to use full Singleton logic.

---

# Singleton Pattern in Multithreading 

## Problem: Singleton Fails in Multithreaded Case

### What Really Go Wrong?

If I write my singleton like this:

```java
if (instance == null) {
   instance = new MySingleton();
}
return instance;
```

And now two threads (Thread A and Thread B) both run this at same time.

* Both see instance is null
* Both make new object
* Now two objects created

So Singleton break here. This is called **Race Condition** — many threads try to use same resource without any lock.

---

## How To Fix This - Thread Safe Solutions

### 1. Synchronized Method

```java
public static synchronized MySingleton getInstance() {
   if (instance == null) {
      instance = new MySingleton();
   }
   return instance;
}
```

* Yes this is thread safe
* But it is slow because every time method get locked even if object is already created

### 2. Double Checked Locking

```java
if (instance == null) {
   synchronized(MySingleton.class) {
      if (instance == null) {
         instance = new MySingleton();
      }
   }
}
```

* First check is to avoid locking every time
* Second check inside lock makes sure only one object created
* Need to use `volatile` with instance variable

### 3. Bill Pugh Singleton (Inner Class)

```java
private static class Holder {
   private static final MySingleton instance = new MySingleton();
}

public static MySingleton getInstance() {
   return Holder.instance;
}
```

* This is lazy and fast
* Thread safe by Java class loader
* Class load only when getInstance called

### 4. Enum Singleton

```java
public enum MySingleton {
   INSTANCE;
}
```

* Fully thread safe
* Safe from serialization, reflection too
* Recommended by Java expert Joshua Bloch

---

## Summary Table

| Method                | Thread Safe | Fast | Good Choice?             |
| --------------------- | ----------- | ---- | ------------------------ |
| Normal Singleton      | No          | Yes  | Not good in multi-thread |
| Synchronized Method   | Yes         | No   | Okay for small projects  |
| Double Check Locking  | Yes         | Yes  | Better and common choice |
| Bill Pugh Inner Class | Yes         | Yes  | Very good and clean      |
| Enum Singleton        | Yes         | Yes  | Best and safest way      |

---

## My Final Understanding

In multithreaded programs, normal singleton code can fail. So we must write it carefully.

Depending on project size and need:

* For easy and fast way: use Bill Pugh method
* For full safety: use Enum Singleton

If not done properly, multiple objects get created and singleton fails.

I will always keep in mind now that Singleton in threads is tricky but fixable if written properly.

---