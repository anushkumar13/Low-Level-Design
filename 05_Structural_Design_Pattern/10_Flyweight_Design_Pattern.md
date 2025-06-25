# Flyweight Pattern Explained — Real-Life Memory Saver Story

## 💡 One-Liner Definition:

**"Flyweight Pattern is used when we have thousands or lakhs of objects that share common data — so we share that common part to save memory."**

---

## 🍃 Real-Life Example: Text Editor Characters

Imagine you're building a text editor like MS Word.
Someone writes:

```
AAAAAAABBBBBBBBBCCCCCCDDDDD
```

* A appears 7 times
* B appears 9 times
* C appears 6 times
* D appears 5 times

If you create a new object for each character instance:

* It would consume a lot of memory
* But all A’s have same style, font, size, etc.

### ✅ Solution — Flyweight:

* Create only **1 object** for `A`
* Reuse it wherever needed
* Just pass external info like **position** (x, y)

➡️ Same object reused repeatedly = memory saved = performance boosted 🚀

---

## 🔥 Key Concept:

Flyweight pattern separates **object state** into two parts:

| State Type      | Description             | Shared? |
| --------------- | ----------------------- | ------- |
| Intrinsic State | Constant, internal data | ✅ Yes   |
| Extrinsic State | Changing, external data | ❌ No    |

**Example:**

* Intrinsic: `'A'`, font = Arial
* Extrinsic: (x, y) position, color

---

## 🧠 Programming Use Cases

| Use Case         | Why Flyweight Works             |
| ---------------- | ------------------------------- |
| Text Editor      | Characters repeat often         |
| Game Development | Thousands of bullets/trees/etc. |
| Maps             | Same icon used in many places   |
| Chess Game       | Limited piece types             |

---

## 📦 Flyweight Pattern Structure

| Component           | Role                                                                  |
| ------------------- | --------------------------------------------------------------------- |
| `Flyweight`         | Interface defining common methods                                     |
| `ConcreteFlyweight` | Implements Flyweight; shared object reused                            |
| `FlyweightFactory`  | Manages and returns shared Flyweight objects                          |
| `Client`            | Uses Flyweight objects and provides extrinsic data like position etc. |

---

## ✅ Bhai-Style Summary:

Flyweight Pattern is perfect when:

* You need **lots of similar objects**
* And want to **save memory** by reusing common internal data

### ➕ Intrinsic State = Shared data

### ➕ Extrinsic State = Provided by client (e.g., position)

**Examples:** Characters, Trees, Map Pins, Chess Pieces etc.

**Result:**

* Less memory usage
* Cleaner, more optimized code
* High performance in systems like editors, games, UI frameworks

---