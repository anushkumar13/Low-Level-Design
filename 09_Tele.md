# Telescoping Constructor Pattern — The Problem That Builder Pattern Solves

## 🔭 What is the Telescoping Constructor Pattern?

The **Telescoping Constructor Pattern** occurs when a class has many parameters, and multiple overloaded constructors are used to provide different combinations of these parameters.

### Example:

```java
Burger(boolean cheese)
Burger(boolean cheese, boolean lettuce)
Burger(boolean cheese, boolean lettuce, boolean tomato)
Burger(boolean cheese, boolean lettuce, boolean tomato, boolean sauce)
...
```

As you add more optional parameters, you end up writing more and more constructors — they look like a telescoping tube, growing longer with each overload.

---

## 😩 Why is it a Problem?

* **Confusing to use**: When many constructors exist, it becomes unclear which one to use.
* **Hard to maintain**: Adding or removing a parameter breaks all constructors.
* **Unreadable code**: Passing multiple booleans or values gives no clue what they mean.

### Bad Example:

```java
Burger b = new Burger(true, false, true, false);
```

You have no idea what each parameter stands for — cheese? sauce? lettuce?

---

## 🍕 Real-Life Analogy: Pizza Order

Imagine building a pizza:

* Cheese (optional)
* Tomato (optional)
* Pepperoni (optional)
* CrustType (optional)
* ExtraToppings (optional)

If you make a constructor for every combination:

* You end up with 10-15 different overloaded constructors.
* It's a nightmare to read, use, and maintain.

---

## ✅ Solution: Builder Pattern

Instead of writing telescoping constructors, use the **Builder Pattern** for flexible and readable object construction.

### Builder Style Example:

```java
Pizza pizza = new PizzaBuilder()
                 .addCheese()
                 .addPepperoni()
                 .build();
```

* Much clearer than multiple constructors
* Easy to add/remove options
* Step-by-step construction with method chaining

---

## 🔁 In Summary:

> **Telescoping Constructor Pattern** = When you create multiple overloaded constructors to handle optional parameters. It becomes confusing, unreadable, and hard to maintain.

> ✅ **Builder Pattern** = A clean and modern solution that builds complex objects step-by-step, avoids confusion, and makes your code much more readable.

---

Use Builder Pattern when your class has:

* Many optional parameters
* Need for readable and maintainable object creation
* Avoidance of constructor explosion

Stay clean. Use Builders!

---

# Prototype Design Pattern

## 🔁 In One Line:

When you want to create a **copy (clone)** of an existing object instead of making a new one from scratch — use the **Prototype Design Pattern**.

---

## 🧠 Simple Understanding:

Prototype pattern is used for **object cloning**.
Rather than using `new` to create a fresh object every time, we **clone** an already existing object.

---

## 🍕 Real-Life Example: Pizza Template

Imagine a pizza shop 🍕

They create one **"Base Pizza"** object:

* Size: Medium
* Crust: Thin
* Sauce: Tomato
* Cheese: Yes

Now:
When customers place an order, instead of building from scratch, they:

* **Clone** the base pizza
* Customize it slightly (e.g., add toppings, change size)

➡️ The base pizza = **Prototype**
➡️ Customer-specific pizzas = **Clones**

---

## 🧠 Why Use It?

1. **Creating object is expensive**

   * Example: object involves a database call, API request, or heavy calculation

2. **Creation takes time**

   * Use a pre-built object → clone it → save time

3. **You already have a base object**

   * Just need many variations of it

---

## 🛠️ Real-World Software Examples

### 1. Resume Builder App

* You build a resume template once
* Users clone it to create their custom resumes

➡️ Template = **Prototype**
➡️ User resume = **Clone**

### 2. Graphic Design Apps (Photoshop, Figma)

* Designer creates a styled shape (red circle with shadow & text)
* Needs 10 similar shapes

➡️ Instead of redrawing, **clone the existing shape**
➡️ Make small tweaks

---

## 🔄 Shallow Copy vs Deep Copy

* **Shallow Copy**: Only top-level object is copied. Internal references are shared.
* **Deep Copy**: Everything is copied, including internal objects. No shared references.

In the Prototype Pattern:

* Choose the type of copy depending on your need.

---

## 🎯 Summary:

The **Prototype Design Pattern** is perfect when:

* You want to avoid costly object creation
* You already have a base (template) object
* You need multiple similar objects quickly

Instead of building new, you **clone existing** — efficiently and flexibly ✅

---