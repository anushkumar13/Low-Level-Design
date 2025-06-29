# Telescoping Constructor Pattern - What It Is And Why It's Bad

## What Is Telescoping Constructor Pattern?

When a class has many parameters, and we create multiple constructor by overloading to cover different combinations of those parameters.

Example:

```java
Burger(boolean cheese)
Burger(boolean cheese, boolean lettuce)
Burger(boolean cheese, boolean lettuce, boolean tomato)
Burger(boolean cheese, boolean lettuce, boolean tomato, boolean sauce)
```

It keeps getting bigger and bigger — like a telescope — that's why the name.

---

## Why This Is Bad?

* Too confusing to understand which constructor to use
* If you add/remove something, all constructor changes
* Reading constructor call with many booleans is headache

### Bad Code Example:

```java
Burger b = new Burger(true, false, true, false);
```

I can't tell which is for cheese and which is for sauce etc. Totally unreadable.

---

## Real Life Example - Pizza Order

Suppose we want to order pizza with:

* Cheese (optional)
* Tomato (optional)
* CrustType (optional)
* Extra toppings (optional)

Now imagine writing constructor for all combinations. There will be like 10-15 constructors — so messy and hard to maintain.

---

## Solution - Use Builder Pattern Instead

With builder pattern we can do like this:

```java
Pizza pizza = new PizzaBuilder()
                .addCheese()
                .addTomato()
                .build();
```

* Looks clean
* Easy to read
* Easy to add or remove items
* Easy to maintain

---

## Summary:

**Telescoping Constructor** = using many overloaded constructors to handle options. Bad because too confusing and not clean.

**Builder Pattern** = solves this problem by step by step method chaining to make complex object.

Use builder when class has many optional fields and you want easy and clean code.

---

# Prototype Design Pattern - Cloning Objects

## What It Means?

Instead of making a brand new object every time using `new`, we just copy (clone) an existing object. This is called prototype pattern.

---

## Easy Example - Pizza Shop

The shop makes one base pizza:

* Size: Medium
* Sauce: Tomato
* Cheese: Yes

Now for each order:

* Clone the base pizza
* Add extra toppings or change size

So the base pizza is **prototype** And all custom pizzas are **clones**

---

## Why Use It?

1. Creating object is costly (like DB call or big calculation)
2. Creating takes time, so we clone to save time
3. We already have one base object, and we need similar ones

---

## Real App Example:

### Resume Builder

* You make one base template
* Users copy it and make their version

Base = prototype User version = clone

### Design Tools (like Figma)

* Make one circle with style
* Then just copy it again and again to make similar shapes

---

## Types of Copy:

* **Shallow Copy** = only top level is copied, inner things are same reference
* **Deep Copy** = everything is copied including inside parts

So we choose which type we need in prototype pattern

---

## Final Summary:

Prototype Pattern is good when:

* Object creation is expensive or slow
* You already have one ready object
* You want many similar objects fast

So instead of building from start, just clone and go.

---