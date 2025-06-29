# Decorator Design Pattern

## What I Understood in One Line

Decorator pattern is a design pattern that helps me add new features or behaviors to an object while the program is running, and I don't need to change the original class for that.

---

## Pizza Example That Helped Me Understand

When I think about pizza, I start with a basic one. Then I add cheese, then maybe olives, then jalapenos. Every topping I add is like a decoration. But I never change the original pizza base, I just keep adding things on top of it. That’s how decorator pattern works too. We keep wrapping an object with more layers to add features.

---

## Coding Example That Made It Clear

In programming, I thought of a TextEditor class. Suppose I want to add bold, italic, and underline features.

But I don’t want to touch the TextEditor class again and again. So I create new classes like BoldDecorator, ItalicDecorator, and UnderlineDecorator. Each one of them takes the TextEditor object and adds its own feature. This way I don't change the original class.

---

## The Parts I Noted Down in This Pattern

* Component Interface: This is the base interface or abstract class which both the original object and all decorators implement.
* Concrete Component: The real object I want to add more behavior to.
* Decorator Class: An abstract class which stores a reference to the component and implements the interface.
* Concrete Decorators: These are the actual classes that add new behavior on top of the component.

---

## When I Think This Pattern Is Useful

* When I want to add new responsibilities to an object while the program is running.
* When making subclasses is not a good option because there are too many feature combinations.
* When I want to follow the open/closed principle, meaning I want to extend the object but not change the old code.

---

This is what I have understood so far about the decorator pattern. It's really helpful when I want to keep code clean and still add extra features on the go.

---

## Real-World Software Examples

### Java I/O Streams:

```java
InputStream in = new BufferedInputStream(new FileInputStream("file.txt"));
```

* FileInputStream = base component
* BufferedInputStream = decorator

### Pizza Order System:

* BasePizza + CheeseDecorator + OliveDecorator

### Text Formatting:

* Add styles (bold, italic, underline) to text objects

### GUI Components:

* Add scrollbars, borders, shadows without changing the base component

## Final Summary:

Decorator Pattern is perfect when you want to:

* Extend functionality without altering original code
* Compose behavior flexibly at runtime

Think: Pizza toppings, Java Streams, and dynamic UI layers — all achieved using the Decorator Pattern.

## Real-Life Example: Pizza Order System using Decorator Design Pattern

### Problem Statement:

In a pizza ordering system, customers want different combinations of toppings:

* Customer A: Cheese
* Customer B: Cheese + Mushroom
* Customer C: Cheese + Mushroom + Olive

If we create a separate class for each combination:

```java
CheesePizza {}
CheeseMushroomPizza {}
CheeseMushroomOlivePizza {}
```

It results in a class explosion. With 100 toppings, we may end up needing thousands of classes.

### Solution: Use Decorator Pattern

The Decorator Pattern allows features to be added to objects dynamically at runtime without altering the class structure.

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

### Order a Pizza:

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

### Key Takeaways:

* Each topping is a decorator
* Toppings are chained (wrapped) like layers
* Base pizza code is untouched
* Each decorator adds its own logic, making it modular and reusable

### Final Summary:

The Decorator Pattern is useful when we want to add features in a modular way without modifying the original code. The pizza toppings analogy clearly demonstrates how new features can be layered dynamically at runtime.

---