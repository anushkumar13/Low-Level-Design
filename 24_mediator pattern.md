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
