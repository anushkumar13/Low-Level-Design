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