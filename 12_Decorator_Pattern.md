# 💥 Decorator Design Pattern

## 🎯 Definition in One Line:

"A design pattern used to add new features or behaviors to an existing object at runtime without modifying its original code."

---

## 🍕 Real-Life Analogy: Pizza Toppings

Imagine you're making a pizza:

1. Start with a base pizza.
2. Add cheese.
3. Add olives.
4. Add jalapenos.

➡️ Each topping is a **decoration**.
➡️ You never modify the original base pizza — you simply **wrap** it with new features.

This is exactly how the **Decorator Pattern** works!

---

## 💻 Programming Analogy: Text Editor

Think of a `TextEditor` object. Now you want to add features like:

* Bold
* Italic
* Underline

Instead of changing the original `TextEditor` class, you:

* Create separate classes like `BoldDecorator`, `ItalicDecorator`, etc.
* Each of these wraps the base editor and adds its own behavior.

---

## 🔧 Technical Breakdown:

* **Component Interface:** The base interface (or abstract class) which all concrete components and decorators implement.

* **Concrete Component:** The original class whose behavior we want to extend.

* **Decorator Class:** An abstract wrapper class that implements the component interface and has a reference to a component object.

* **Concrete Decorators:** Extend the decorator class and override methods to add new behaviors.

---

## 🧠 When to Use Decorator Pattern?

* When you want to add new responsibilities to objects **dynamically at runtime**.
* When subclassing is impractical due to too many possible combinations of behaviors.
* When you want to avoid altering existing code (Open/Closed Principle).

---

## 🧾 Real-World Software Examples:

### ✅ Java I/O Streams:

```java
InputStream in = new BufferedInputStream(new FileInputStream("file.txt"));
```

* `FileInputStream` = base component
* `BufferedInputStream` = decorator

### ✅ Pizza Order System:

* BasePizza + CheeseDecorator + OliveDecorator

### ✅ Text Formatting:

* Add styles (bold, italic, underline) to text objects

### ✅ GUI Components:

* Add scrollbars, borders, shadows without changing the base component

---

## 🎯 Final Summary:

Decorator Pattern is perfect when you want to:

* Extend functionality without altering original code
* Compose behavior flexibly at runtime

**Think: Pizza toppings, Java Streams, and dynamic UI layers — all thanks to Decorator Pattern!**

---

## Real-Life Example: Pizza Order System using Decorator Design Pattern

### Problem Statement:

You have a pizza ordering system. Customers want different combinations of toppings:

* Customer A: Cheese
* Customer B: Cheese + Mushroom
* Customer C: Cheese + Mushroom + Olive

If you create a new class for each combination:

```java
CheesePizza {}
CheeseMushroomPizza {}
CheeseMushroomOlivePizza {}
```

➡️ This leads to **class explosion**!
100 toppings = 1000s of combinations = 1000s of classes ❌

### ✅ Solution: Use Decorator Pattern

The Decorator Pattern allows you to add features to objects **dynamically** at runtime without altering the existing class structure.

---

### Step 1: Base Interface

```java
interface Pizza {
    String getDescription();
    int getCost();
}
```

### Step 2: Base Class

```java
class PlainPizza implements Pizza {
    public String getDescription() {
        return "Plain Pizza";
    }
    public int getCost() {
        return 100;
    }
}
```

### Step 3: Topping Decorators (Cheese, Mushroom, Olive)

Each decorator:

* Implements the Pizza interface
* Accepts a Pizza object to wrap
* Enhances getDescription() and getCost()

#### CheeseDecorator

```java
class CheeseDecorator implements Pizza {
    private Pizza base;

    public CheeseDecorator(Pizza base) {
        this.base = base;
    }

    public String getDescription() {
        return base.getDescription() + ", Cheese";
    }

    public int getCost() {
        return base.getCost() + 30;
    }
}
```

#### MushroomDecorator

```java
class MushroomDecorator implements Pizza {
    private Pizza base;

    public MushroomDecorator(Pizza base) {
        this.base = base;
    }

    public String getDescription() {
        return base.getDescription() + ", Mushroom";
    }

    public int getCost() {
        return base.getCost() + 20;
    }
}
```

#### OliveDecorator

```java
class OliveDecorator implements Pizza {
    private Pizza base;

    public OliveDecorator(Pizza base) {
        this.base = base;
    }

    public String getDescription() {
        return base.getDescription() + ", Olive";
    }

    public int getCost() {
        return base.getCost() + 25;
    }
}
```

### 🍕 Order a Pizza:

```java
Pizza order = new OliveDecorator(
                    new MushroomDecorator(
                        new CheeseDecorator(
                            new PlainPizza()
                        )
                    )
                );
```

### Output:

```
Description: Plain Pizza, Cheese, Mushroom, Olive
Cost: ₹100 + ₹30 + ₹20 + ₹25 = ₹175
```

---

### 🔥 Key Takeaways:

* Each topping is a decorator.
* Toppings are chained (wrapped) like layers.
* Base pizza code is untouched.
* Each decorator adds its own logic → modular and reusable.

---

### 🎯 Final Summary:

The **Decorator Pattern** is used when you want to add features in a modular way **without touching the original code**.

Pizza toppings = Best real-life analogy for Decorator Pattern 💯

---