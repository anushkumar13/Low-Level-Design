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
