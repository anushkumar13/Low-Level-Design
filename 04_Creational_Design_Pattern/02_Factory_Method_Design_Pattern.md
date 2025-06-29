## Factory Method Pattern - My Understanding

### What is the Factory Method Pattern?

Factory Method Pattern is a creational design pattern. It says that we should not create objects directly using `new` keyword. Instead, we should give that responsibility to a separate method called factory method.

This means the object creation logic is not written in the main code. It is handled by a separate method or class.

### Simple Meaning

Suppose you want to create an object. But you want to decide which object to create during runtime. Then you should give that responsibility to a factory method. It will create the correct object and return it to you.

---

### Real Life Example - Ice Cream Shop

Imagine going to an ice cream shop. There are many flavors like vanilla, chocolate and strawberry.

You just say, "I want chocolate."

You don’t care from which bucket it is coming, which freezer is used or who is scooping.

Shopkeeper handles all that. You only tell the type.

Same happens in factory method pattern. You tell the type. The factory method handles the rest and gives the object.

---

### Software Example - Notification System

Suppose I am making a notification system which sends:

* Email
* SMS
* Push Notification

If I write like this:

```java
new EmailNotification()
new SMSNotification()
```

Then I am tightly connecting my code to these classes. If I add new class like WhatsAppNotification, I have to change my existing code. That breaks Open-Closed Principle.

So, instead of directly creating objects, I will create a `NotificationFactory` class.
In that, I will write a method like:

```java
getNotification(String type)
```

This method will decide which object to create and return.
Now client will just call this method and factory will do the object creation work.

---

### Benefits of Factory Method Pattern

* Code becomes flexible
* Easy to add new types
* Code is not tightly coupled
* Follows Single Responsibility Principle

---

### One Line Summary

Let the factory method handle object creation, so your code stays clean and flexible.

---

### Design Pattern Category

* It is a Creational Design Pattern
* It is used for Object Creation

---

## Factory Method Pattern with Subclassing - Ice Cream Store Example

### Definition Recap

Factory method pattern gives interface for creating objects but allows the subclass to decide which class to create.

This helps in writing code which is flexible and loosely coupled.

---

### Explanation Using Story

Suppose there is a generic class called `IceCreamStore`. This is the superclass.

It has a method:

```java
makeIceCream(String flavor)
```

But `IceCreamStore` does not create the ice cream object by itself.

It calls another method:

```java
createIceCream(String flavor)
```

This method is abstract or can be overridden.

Now we create subclasses like `DelhiIceCreamStore`, `MumbaiIceCreamStore`.

Each subclass implements `createIceCream()` method differently. They decide how to create different `IceCream` objects.

---

### So What is Happening?

* Superclass `IceCreamStore` provides common structure
* Subclasses like `DelhiIceCreamStore` decide which object to create and return

So,

> Factory method is written in superclass but the decision of which class to instantiate is taken by subclass.

---

### One Line Summary

Factory Method Pattern means: Define a method for creating object, but let subclasses decide which object to create.

---

### Benefits

* Loose coupling
* Easy to extend
* Follows Open-Closed Principle
* Creation logic is hidden inside subclasses

This makes our system better and scalable.

---

## "Always Code to an Interface, Not an Implementation"

### What Does It Mean?

This is a famous design principle.
It means: Do not depend on specific classes. Depend on abstraction like interface or abstract class.

---

### Simple Explanation

Suppose I have a class `TravelService`

If I write like:

```java
Car car = new Car();
car.start();
```

Then I am tightly coupled with Car. If I want to change to Bike or Bus, I have to change `TravelService` code.

Better way is:

```java
Vehicle v = new Car();
v.start();
```

Now `TravelService` only knows about `Vehicle` interface. Changing from Car to Bike or Bus is easy now.

---

### Real Life Analogy - TV Remote

Remote has buttons like Power, Volume.
Remote doesn't care which TV you are using - LG, Sony or Samsung.
You use the remote (interface), not the actual TV internal parts (implementation).

Remote = Interface
TV = Implementation

We are using abstraction to control things.

---

### Why This is Useful

* Code is loosely coupled
* Easy to extend with new classes
* Easy for testing (mock interfaces)
* Easy to maintain and update in future

---

### One Line Summary

Interface is like a promise. Code should depend on the promise, not who or how it is fulfilled.

Always code to interface so that your code is flexible and easy to maintain.

---

## Understanding Tight vs Loose Coupling (My Notes)

### Statement:

```java
ScorpioN obj = new ScorpioN();
```

This line is not totally wrong but from design point of view it can make problems later. Let me try to explain in my own words.

---

### Tight Coupling (Why it can be bad)

If I write:

```java
ScorpioN obj = new ScorpioN();
```

It means my code is directly dependent on class `ScorpioN`.

If later I want to use `Thar` or `XUV`, then I have to change this line. Maybe also other lines in same class. This creates tight connection.

This is called tight coupling. It makes our code hard to change and not flexible.

---

### Loose Coupling using Interface

Better way is to use abstraction. Like create an interface:

```java
interface Car {
    void drive();
}

class ScorpioN implements Car {
    public void drive() {
        // driving logic
    }
}
```

Now write:

```java
Car obj = new ScorpioN();
obj.drive();
```

Now my code depends on `Car` interface not actual class. If I want to change to Thar, I only change the object creation:

```java
Car obj = new Thar();
```

No other changes.

This is called loose coupling. It makes our code better and easy to manage.

---

### Summary Table

| Code                             | Coupling Type    |
| -------------------------------- | ---------------- |
| `ScorpioN obj = new ScorpioN();` | Tight Coupling ❌ |
| `Car obj = new ScorpioN();`      | Loose Coupling ✅ |

---

### One Line Summary

`ScorpioN obj = new ScorpioN();` is fine for small codes but for large scalable code it creates tight coupling. Better is to use `Car obj = new ScorpioN();` to keep code flexible.

---

## When Should I Use Factory Method Pattern (My Notes)

I am learning when to use Factory Method Pattern. It is not just for fancy design, there are real situations where it helps.

---

### What mindset to have?

Use Factory Method when:

* I want to create object but not sure which class to create at compile time.
* I want that object creation decision should happen during runtime.
* I want to keep object creation code separate from main business logic.

---

### Signal 1: Too many new keywords

If my code looks like:

```java
if(type.equals("Email")) {
   new EmailNotification();
} else if(type.equals("SMS")) {
   new SMSNotification();
}
```

Then I am doing bad design. Too much tight coupling. I should move this to a factory method.

---

### Signal 2: Code is not flexible

If I write `new ScorpioN()` everywhere and then need to change to `new Thar()`, I have to change in many places.

With factory method, I just write one factory method that returns object. Main code stays untouched. So better flexibility.

---

### Signal 3: Object creation is complex

If to create object I need to:

* read from config
* do validations
* inject dependencies

Then it's better to move all this into a factory method and keep my main code clean.

---

### Signal 4: I want to add new object types later

Suppose today I support `EmailNotification`. Later I want `WhatsAppNotification` or `TelegramNotification`.

With factory method:

* I just update factory class.
* My main code is same.
* Open-Closed Principle is followed.

---

### Real Life Decision Table

| Situation                                          | Should Use Factory Method? |
| -------------------------------------------------- | -------------------------- |
| I want to create object but class is not fixed     | Yes ✅                      |
| I am using many if-else for object creation        | Yes ✅                      |
| Object creation is becoming complex                | Yes ✅                      |
| I want to add new types without changing main code | Yes ✅                      |

---

### One Line Summary

Use Factory Method Pattern when object creation needs to be flexible, changeable, and you want main code to be clean and decoupled from which class is being created.

---