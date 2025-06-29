## Abstract Factory Pattern (Factory of Factories) 

### What is Abstract Factory Pattern?

So this pattern is like a factory... but a factory that gives other factories. Sounds weird first time, but it makes sense.

Simple idea:

> If I want to create a full group of related things that should match (like theme items), then I use Abstract Factory Pattern.

---

### What I understood:

* Factory Method is good when we need to create one object.
* Abstract Factory is for when we want to create a group of related objects together.

---

### Real Life Example: Restaurant Meal Combo

If I go to a restaurant and ask for a combo meal,

**Meal Combo A - Indian Thali** has:

* sabzi
* roti
* daal
* rice

**Meal Combo B - Italian Meal** has:

* pasta
* garlic bread
* soup
* dessert

So if I order Indian, the kitchen uses IndianMealFactory which creates all items like sabzi, roti etc.

If I order Italian, then ItalianMealFactory handles everything.

I just say what combo I want, and I get the full matching set of items. That’s what abstract factory does in code.

---

### Software Example I imagine:

Suppose I'm making a UI with themes (dark and light).

**DarkThemeFactory** creates:

* DarkButton
* DarkTextBox
* DarkCheckbox

**LightThemeFactory** creates:

* LightButton
* LightTextBox
* LightCheckbox

Now my main code just does:

```java
factory.createButton()
```

It doesn't care which theme is used. That decision is handled inside the factory.

---

### When to Use Abstract Factory?

* When I need to create matching groups of things
* When I want object creation to be organized in one place
* When I already use Factory Method and want to scale to more related objects

---

### Difference I Noted:

| Factory Method | Abstract Factory                  |
| -------------- | --------------------------------- |
| Makes 1 object | Makes full group of objects       |
| Simple         | More powerful and flexible        |
| One method     | Multiple methods (one per object) |

---

### My One Line Summary:

Abstract Factory is like a super-factory that gives me a complete matching set of objects without me worrying about which class is used.

---

## Abstract Factory - Why it’s Useful (my notes)

This line is 100% true:

> abstract factory pattern solves the problem of creating families of related products that must be used together.

Let me explain it my way.

---

### Story to Understand:

I am building a GUI app. There are 2 themes:

1. Dark Theme

   * Dark Button
   * Dark TextBox
   * Dark Checkbox

2. Light Theme

   * Light Button
   * Light TextBox
   * Light Checkbox

Now I want the full UI to match. If user picks dark theme, everything should be dark. Same for light theme.

---

### Without Abstract Factory - Big Mess

If I do like:

```java
new DarkButton()
new LightTextBox()
new DarkCheckbox()
```

Then it's a total mix. My UI looks weird.

Also, code becomes very messy.

* Logic is repeated everywhere
* Hard to change later
* Adding new theme is pain

---

### With Abstract Factory - So Simple

With abstract factory, I just do:

```java
UIComponentFactory factory = new DarkThemeFactory();

Button b = factory.createButton();
TextBox t = factory.createTextBox();
Checkbox c = factory.createCheckbox();
```

Now:

* I don’t need to worry about how these are made
* I don’t need to know which class is used
* I get full matching set of objects based on theme

---

### Why This is So Useful:

Because I get a full set of related things, that always go together. Like theme UI components.

* Everything stays consistent
* Code is clean
* Easy to switch themes

---

### Final One Line:

Abstract Factory Pattern is used when I want to create a group of related things (like buttons, textboxes, checkboxes) that all match a certain style, theme, or platform. It helps keep code clean and easy to update later.

---

## When Should I Use Abstract Factory Pattern?

So I learned that if I ever think:

> "I need to create a group of related objects, and I want to change them at runtime"
> Then it's time to use **Abstract Factory Pattern**.

Here are few clear signs I wrote down when we should use abstract factory.

---

### Signal 1: I need to make a group of related objects

Like I'm building:

* DarkButton, DarkTextBox, DarkCheckbox
* LightButton, LightTextBox, LightCheckbox

These are related items, they come as a family. This is perfect place to use abstract factory.

---

### Signal 2: I want to switch whole object groups at runtime

User selects theme:

* If Dark theme selected, everything becomes dark
* If Light selected, everything becomes light

This means I need to switch full group of objects based on runtime choice. Abstract factory helps me do that cleanly.

---

### Signal 3: My object creation is getting messy or repeated

If I see this type of code again and again:

```java
new DarkButton()
new DarkTextBox()
new DarkCheckbox()
```

Then it’s becoming duplicate and messy. I should just say:

```java
factory.createButton()
```

And let the factory do the rest.

---

### Signal 4: I want to add more object groups in future

Today I have:

* DarkThemeFactory
* LightThemeFactory

Tomorrow I may want:

* HighContrastThemeFactory
* ColorBlindFriendlyThemeFactory

Abstract factory makes it easy to add more without touching old code. It follows open/closed principle.

---

### Signal 5: I want more power than factory method

Factory method gives one object only. Abstract factory gives me a full group of objects.

If I was using factory method and now I need multiple related items, I should upgrade to abstract factory.

---

### Final One Line I wrote:

> If I need to make a group of related things, switch them at runtime, and want to keep code clean and scalable, then I should use abstract factory pattern.

---

## Understanding the 3 Types of Factory Design Patterns (in easy way)

When I studied factory patterns, I saw 3 types that sound similar but do different things. So I made notes to understand better.

---

### 1. Simple Factory (not official GoF pattern but used a lot)

This is just a class that creates object based on input.
No subclassing or anything.

Example:

```java
Shape shape = ShapeFactory.getShape("CIRCLE");
```

Factory has if-else or switch to return correct object.

* Who creates object? The factory class
* Flexibility: low (basic)
* Subclassing? No

---

### 2. Factory Method (official GoF pattern)

This one moves the creation to subclasses.
Base class has method like create(), but subclasses actually create the object.

Example:

```java
NotificationFactory factory = new SMSNotificationFactory();
Notification n = factory.createNotification();
```

* Superclass: NotificationFactory

* Subclasses: SMSNotificationFactory, EmailNotificationFactory

* Who creates object? The subclass

* Flexibility: medium

* Subclassing? Yes

---

### 3. Abstract Factory (advanced GoF pattern)

This one is for creating full family of related things like whole theme components.

Example:

```java
UIFactory factory = new DarkThemeFactory();
Button b = factory.createButton();
TextBox t = factory.createTextBox();
```

* Factory creates group of related things
* Who creates? Specific family factory
* Flexibility: high
* Subclassing? Yes, multiple products

---

### One Line Summary I wrote:

| Pattern          | What it creates                | Flexibility |
| ---------------- | ------------------------------ | ----------- |
| Simple Factory   | one object based on input      | low         |
| Factory Method   | one object created by subclass | medium      |
| Abstract Factory | full group of related objects  | high        |

---

### My Final Thoughts:

* Simple Factory is okay when project is small
* Factory Method helps when object creation depends on type
* Abstract Factory is best when we want multiple related objects like themes, and want clean and scalable code

---