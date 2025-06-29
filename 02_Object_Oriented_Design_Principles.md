# What is SOLID?

**SOLID** is a set of 5 design principles that helps in writing better object-oriented code. Basically it makes your code more easy to understand, maintain, reuse, and scale.

I used to think yeh sab sirf theory hai, but after learning with examples it actually makes sense.

## S.O.L.I.D Breakdown (Simple Style)

### 1. S – Single Responsibility Principle (SRP)

A class should have only one kaam. Like, ek class ka sirf ek hi reason hona chahiye to change.

**Wrong Way:**

```java
class User {
    void saveToDB() { }
    void generatePDFReport() { }
}
```

Here, class is doing too much. Saving to DB and also creating report.

**Better Way:**

```java
class User { }

class UserRepository {
    void saveToDB(User u) { }
}

class ReportGenerator {
    void generatePDFReport(User u) { }
}
```

Now the work is divided properly. Har class ka apna kaam.

---

### 2. O – Open/Closed Principle (OCP)

Your class should be open for adding new features but closed for changing existing code.

This means, agar mujhe new functionality add karni hai, toh I shouldn't touch old code.

**Example:**

```java
abstract class Shape {
    abstract double area();
}

class Circle extends Shape { }
class Rectangle extends Shape { }
```

Now if I want to add Triangle, I can just extend Shape without changing old classes. That’s OCP.

---

### 3. L – Liskov Substitution Principle (LSP)

Subclasses should be able to replace the parent class without breaking the program.

Like, if class B extends class A, then I should be able to use B wherever A is expected — and things should still work.

**Wrong Example:**

If I make a class `Bird` with `fly()` method and then create `Penguin extends Bird` — it breaks because penguin can’t fly. So penguin is not a proper substitute of bird in this case.

---

### 4. I – Interface Segregation Principle (ISP)

Don’t force your class to implement things it doesn’t need.

**Bad Example:**

```java
interface Animal {
    void fly();  // But what if it’s a dog?
}
```

**Better Design:**

```java
interface Flyable {
    void fly();
}

interface Runnable {
    void run();
}
```

Now we only give methods to classes which they actually need. Smaller, useful interfaces.

---

### 5. D – Dependency Inversion Principle (DIP)

High-level code (like business logic) should not depend on low-level code (like database or engine). Both should depend on **interfaces**.

**Example:**

```java
interface Engine {
    void start();
}

class PetrolEngine implements Engine { }
class DieselEngine implements Engine { }

class Car {
    Engine engine;

    Car(Engine engine) {
        this.engine = engine;
    }
}
```

Now Car doesn’t care which engine it is. Petrol or diesel — it just works. That's DIP.

---

## SOLID Summary in Simple Table

| Letter | Name                  | Easy Explanation                       |
| ------ | --------------------- | -------------------------------------- |
| S      | Single Responsibility | One class = one job only               |
| O      | Open/Closed           | Add new stuff without changing old one |
| L      | Liskov Substitution   | Subclass should work same as parent    |
| I      | Interface Segregation | Only use interfaces you really need    |
| D      | Dependency Inversion  | Depend on interface, not details       |

---

## Final Thoughts

At first I thought SOLID is boring theory, but now I feel like it’s actually super useful. It helps keep code clean and easy to handle, especially in big projects. And haan — it also makes code more testable and modular.

---

## What is Single Responsibility Principle (SRP)?

### My Notes:

Okay, so today I learned about something called **SRP** in software design. Full form is **Single Responsibility Principle**.

At first, I was like, okay… what does this even mean? But after going through a few examples and videos, I understood it like this:

> *"A class should only have one reason to change. It should do one thing and do it properly."*

So let’s break this down.

---

### Real-Life Example I Came Up With:

There’s this guy Ravi. He’s doing everything:

* Going to college
* Cooking at home
* Doing a bank job
* Delivering food for Zomato too 😵‍💫

Now, imagine his college schedule changes — it affects his entire routine! That's because he’s managing too many responsibilities.

But if Ravi was just a student, only the college changes would affect him. Simple.

So SRP basically says — just like people, classes in code should also do one thing only.

---

### Software Example I Understood:

There’s a class called `ReportManager`. And guess what — it’s doing all these things:

* Making the report
* Printing it
* Saving it to the database
* Emailing it to someone

If tomorrow we want to change how the email looks, we’ll have to touch this class. Even though we just wanted to update the email format, not the report.

That’s bad. That’s why it breaks SRP.

---

### How To Fix It (What I Noted):

Break things down:

* `ReportCreator` – Only makes the report
* `ReportPrinter` – Only handles printing
* `ReportStorage` – Just saves to DB
* `EmailService` – Sends the email

Now if we wanna change the email logic, we only touch `EmailService`. That's much better.

---

### Why I Think SRP Is Useful:

* Code becomes much easier to read and fix
* Features don’t get messed up just because you made a small change
* Looks cleaner
* Less bugs
* You only touch the class that’s related to the change you want

---

### One Line I’ll Remember:

> **One class = One job. And it should change only if that job changes.**

---

### Example That Breaks SRP:

```java
public class Student {
    private String name;
    private int rollNo;

    public Student(String name, int rollNo) {
        this.name = name;
        this.rollNo = rollNo;
    }

    public void printDetails() {
        System.out.println("Name: " + name);
        System.out.println("Roll No: " + rollNo);
    }

    public void saveToDatabase() {
        System.out.println("Saving " + name + " to database...");
    }

    public void sendEmail() {
        System.out.println("Sending email to " + name);
    }
}
```

This class is literally doing 3 jobs — printing, saving, and emailing. Clearly not SRP-friendly.

---

### SRP-Friendly Version I Noted Down:

```java
// Class 1 - Just holds student info
public class Student {
    private String name;
    private int rollNo;

    public Student(String name, int rollNo) {
        this.name = name;
        this.rollNo = rollNo;
    }

    public String getName() {
        return name;
    }

    public int getRollNo() {
        return rollNo;
    }
}

// Class 2 - Just prints details
public class StudentPrinter {
    public void printDetails(Student student) {
        System.out.println("Name: " + student.getName());
        System.out.println("Roll No: " + student.getRollNo());
    }
}

// Class 3 - Saves to DB
public class StudentRepository {
    public void save(Student student) {
        System.out.println("Saving " + student.getName() + " to database...");
    }
}

// Class 4 - Sends email
public class StudentEmailService {
    public void sendEmail(Student student) {
        System.out.println("Sending email to " + student.getName());
    }
}
```

Now each class is doing its own job. Feels more organized and follows SRP.

---

### "One Reason to Change" – What It Really Means:

If your class is doing just one thing, it’ll only change when that one thing changes.

But if it’s doing multiple jobs, even a small change could force us to touch that entire class. Which is super risky.

So it’s better to have small, focused classes. That’s what SRP is all about.

---

### Final Thoughts (My Takeaway):

* ✅ If a class has one job and one reason to change → SRP is followed
* ❌ If a class has too many jobs → SRP is broken and code can become messy

This principle makes our code easier to manage in the long run. Glad I understood it clearly today!

---

## What is the Open-Closed Principle (OCP)?

### My Notes:

Today I studied the second principle of SOLID design – Open-Closed Principle (OCP).

At first it sounded very technical, but when I understood the basic idea, it was pretty simple. Here's how I noted it:

> "Software entities like classes, functions, modules should be open for extension but closed for modification."

Matlab – hum naye features add kar sakte hai (open for extension), but existing code ko modify nahi karna chahiye (closed for modification).

---

### Simple Example That Helped Me:

Suppose I am making a music player app. Right now it only plays **MP3** files.

Then client says, "Can you add support for **WAV** files?"

Wrong way: I go back and modify the `AudioPlayer` class to handle WAV along with MP3.

Right way: I keep the existing MP3 code untouched, and just create a new class for WAV files.

That’s how we apply Open-Closed Principle. Don’t break the working stuff, just add new things separately.

---

### Real-Life Analogy I Thought Of:

Think of a switchboard with 2 switches: 1 for fan, 1 for light.

Now if I want to add an AC switch, should I break the whole board? No!

I’ll just add one more socket. I’m extending it, not modifying the existing one.

That’s exactly what OCP means in real life.

---

### Why I Think OCP Is Useful:

* Old code stays safe (less chances of bugs)
* We don’t break anything that already works
* New features can be added easily
* Multiple people can work on different features without clashing

---

### One Line That I’ll Try To Remember:

> "We should add new features by writing new code, not by changing old working code."

---

## Music Player Example I Learned

### Scenario:

I am building a music player app. Right now, it supports only MP3 files.

So I have one class `AudioPlayer` and a method called `playMp3()`.

---

### Then the client asks:

> "Can you also support WAV files?"

---

### ❌ Bad Approach (Breaks OCP):

* I go inside `AudioPlayer` and start adding `if else` blocks.
* `if mp3`, `if wav`, `if aac`... etc.

This is bad because:

* Every new format means we are touching old code
* Chances of breaking something increase
* Testing becomes hard
* Code becomes messy and unreadable

---

### ✅ Good Approach (Follows OCP):

* Keep `AudioPlayer` class as it is
* Make a new class called `WAVPlayer`
* Both `MP3Player` and `WAVPlayer` can implement some common interface or base class
* Let `AudioPlayer` use that abstraction

Now we’re not touching existing logic. We just plug in new features.

---

### Final Comparison Table I Made:

| Case              | OCP Broken ❌    | OCP Followed ✅        |
| ----------------- | --------------- | --------------------- |
| Add WAV support   | Change old code | Add new class only    |
| Add AAC in future | Change again    | Just extend via class |
| Risk of bugs      | High            | Low                   |
| Code structure    | Messy           | Clean and modular     |

---

### Java Code Examples I Practiced

#### ❌ OCP Violated Version:

```java
class AudioPlayer {
    public void play(String audioType) {
        if (audioType.equals("mp3")) {
            System.out.println("Playing mp3 file...");
        } else if (audioType.equals("wav")) {
            System.out.println("Playing wav file...");
        } else {
            System.out.println("Unsupported audio format: " + audioType);
        }
    }
}
```

#### ✅ OCP Followed Version:

```java
abstract class AudioFormat {
    public abstract void play();
}

class MP3Player extends AudioFormat {
    public void play() {
        System.out.println("Playing mp3 file...");
    }
}

class WAVPlayer extends AudioFormat {
    public void play() {
        System.out.println("Playing wav file...");
    }
}

class AudioPlayerOCP {
    public void play(AudioFormat format) {
        format.play();
    }
}

public class Main {
    public static void main(String[] args) {
        AudioPlayerOCP player = new AudioPlayerOCP();
        player.play(new MP3Player());
        player.play(new WAVPlayer());
    }
}
```

Here I didn’t touch the `AudioPlayerOCP` class at all. I just made new classes when needed.

---

### Final Thoughts:

OCP helps in making code safe and scalable. If I follow this, I won’t break my working code every time I add something new.

Today I really got why software people always say – "Don’t touch working code unless you have to." This principle makes that idea very clear.

Next, I’ll study the Liskov Substitution Principle!

---

## Understanding Downcasting & Cyclomatic Complexity – My Clean Code Notes

### Q1: Does Downcasting Break Open-Closed Principle (OCP)?

Okay so I was reading about OCP, and this term **downcasting** popped up a lot. I wanted to know if downcasting breaks OCP or not.

**Short answer I found:** Mostly yes. Downcasting is a red flag and often means you are breaking OCP.

---

### What is Downcasting?

So basically downcasting means you're forcefully converting a parent class reference into child class type.

```java
Shape s = new Circle();  
((Circle) s).drawCircleOnly();  // this is downcasting
```

Why this is risky?

* You are depending on a child class directly.
* If tomorrow a new class like `Square` is added, you might break something.
* You have to touch existing code = not closed for modification = OCP broken.

**Better way:**

* Use abstract classes and interfaces properly.
* Write code that works with abstractions.
* No need for instanceof or casting like this.

**One-liner I noted:**

> If you're using downcasting, chances are your design can be improved.

---

### Q2: What is Cyclomatic Complexity?

This was new for me, and thoda confusing at first. But here’s how I understood it:

Cyclomatic Complexity tells how many **decision paths** are there in your code. Basically, it counts all your `if`, `else`, `for`, `while`, etc.

```java
if (x > 0) {   // 1
  ...
}
for (int i = 0; i < n; i++) {   // 1 more
  ...
}
```

So total = 1 base path + 2 decisions = **3**

**Formula (didn't go too deep):**

```
M = E - N + 2P
```

Where:

* M = Cyclomatic complexity
* E = edges, N = nodes, P = connected components (usually 1)

Why it's useful:

* Helps in measuring how complex your code is
* If too high, code becomes hard to test
* Lower complexity = cleaner code

### What’s a good score?

| Score | Meaning            |
| ----- | ------------------ |
| 1–10  | All good           |
| 11–20 | Medium complex     |
| 21+   | High complexity ⚠️ |

---

## If-Else or Switch and OCP – Are They Bad?

I always thought if-else and switch-case are fine. But ab pata chala – agar you keep adding conditions, then it’s not good.

**Short Answer:** Yes, growing if-else or switch blocks violate OCP.

---

### Example I Understood:

```java
if (type.equals("pdf")) {
  // handle pdf
} else if (type.equals("doc")) {
  // handle doc
} else if (type.equals("xls")) {
  // handle xls
}
```

Every time I add a new type like `ppt`, I have to touch this code. That’s a clear OCP violation.

---

### OCP-Friendly Way:

Instead of all these if-else, we can use an interface:

```java
interface DocumentHandler {
  void handle();
}

class PDFHandler implements DocumentHandler {
  public void handle() { }
}

class DOCHandler implements DocumentHandler {
  public void handle() { }
}
```

Now I don’t have to touch old code when a new type is added. Just create a new class = OCP followed.

### Summary Table:

| Code Style         | OCP Friendly? | Maintainability |
| ------------------ | ------------- | --------------- |
| If-else with types | ❌ No          | ❌ Poor          |
| Switch-case        | ❌ No          | ❌ Poor          |
| Polymorphism       | ✅ Yes         | ✅ Excellent     |

One thought I liked:

> If-else is not bad itself. It’s bad **when used for growing logic**. If logic is fixed, then it's fine.

---

## Type Checking & Anti-Abstraction vs OCP

Another topic I studied today — **type checking** and **anti-abstraction**. These are like design smells (warning signs).

### What is Type Checking?

When you write code like this:

```java
if (shape instanceof Circle) {
  // Circle stuff
} else if (shape instanceof Square) {
  // Square stuff
}
```

You are checking type directly instead of using polymorphism.

Why it’s bad:

* Breaks abstraction
* You’re again modifying code to support new types
* Clearly violates OCP

---

### Anti-Abstraction?

When you have a superclass or interface, but still use `instanceof` instead of proper polymorphism.

Example:

```java
void printDetails(Object obj) {
  if (obj instanceof Invoice) { ... }
  else if (obj instanceof Report) { ... }
}
```

Again same issue — for every new type like `Certificate`, I need to change the code.

Better:

```java
interface Document {
  void print();
}

class Invoice implements Document {
  public void print() { }
}
```

Now no need to check type, just call `print()`.

---

### Final Summary:

| Concept               | Problem                        |
| --------------------- | ------------------------------ |
| Downcasting           | Breaks abstraction, OCP        |
| Cyclomatic Complexity | Tells code complexity level    |
| Type Checking         | Violates OCP, bad design smell |
| Anti-Abstraction      | Ignoring polymorphism, risky   |

---

### Last Line I Noted:

> If you're adding if-else/switch/type checks whenever a new thing comes up, you are most likely breaking OCP. Better use interfaces and polymorphism instead.

This whole thing really changed the way I think about code structure now.

---

## Liskov Substitution Principle (LSP)

### What is LSP?

LSP means that if we use a child class in place of parent class, the program should still work properly. If something go wrong after replacing, then it means LSP is not followed.

### My Understanding:

I think LSP is telling us to not make child class which changes behaviour of parent. Like if parent has a method fly(), then child class also should do proper flying. If child do something else, code can behave wrongly.

### Real Life Example:

Let say we make a class Bird with method fly(). Then we make Parrot, Crow, Sparrow which are fine. But then we also make Penguin as child of Bird. Penguin can't fly.

```java
Bird bird = new Penguin();
bird.fly();
```

This line will not work as expected because Penguin can't fly. So Penguin is not proper child of Bird if Bird means all birds can fly.

### Golden Rule:

Child class should always follow the rules and expectations of its parent class.

### How to Fix:

Make a more common class like Animal. Then make interface Flyable for only those birds who can fly.

### One More Example:

There is a Rectangle class with setWidth() and setHeight(). Then we create Square class from it. But in Square, width and height should always be equal.

```java
Rectangle r = new Square();
r.setWidth(5);
r.setHeight(10);
System.out.println(r.getArea());
```

This gives wrong output because Square is changing Rectangle behaviour. So LSP is not followed.

### Final Thoughts:

I learned that we should be careful while using inheritance. If our child class can't do what parent class says, then we are breaking LSP. Always check if child can be used in place of parent safely.

---

## Liskov Substitution Principle (LSP) – Real-World Example: Payment System

### What is the Concept:

LSP says that child class should be used in place of parent class without breaking the code.

### Example I Studied:

Let’s say we have a parent class called Payment with method processPayment(). This method does the main payment work.

#### Good Subclasses:

We make classes like:

* CreditCardPayment
* DebitCardPayment
* UPIPayment

These all extend Payment and implement processPayment() properly. So when we do:

```java
Payment p = new CreditCardPayment();
p.processPayment();
```

It works fine. So LSP is followed.

#### Problem Subclass:

We also make:

* CashPayment extends Payment

But this class has no online logic. No server, no transaction ID. Maybe it does nothing or gives error.

```java
Payment p = new CashPayment();
p.processPayment();
```

Now this behaves differently and maybe incorrectly.

### Why this breaks LSP:

Because user expects processPayment() to do real payment. But CashPayment can't do that. So this class breaks the rule of parent Payment class.

### How to Fix:

Make a new abstract class called OnlinePayment which extends Payment. Then put CreditCard, UPI, etc. under OnlinePayment. CashPayment should go in different structure. It should not pretend to be same as online ones.

### Final Learning:

If child class do things different from parent and cause wrong result, then LSP is broken. We should design in a way that each child behaves as expected. Especially in interviews this type of example is useful to show good design understanding.

---

## Interface Segregation Principle (ISP)

### What is ISP?

Interface Segregation Principle means that we should not make a class to implement methods which it will never use. Classes should only get those methods which are useful for them.

### My Understanding:

I understood that sometimes we make a big interface with too many methods. But then some classes are forced to implement all of them even if they don't need all. This creates unnecessary work and confusion. ISP tells us to break big interface into small ones.

### College Example I Related With:

There are 3 students in college:

* Ram - only write notes
* Shyam - only record videos
* Geeta - only record audio

Now we create one interface like:

```java
interface ContentCreator {
    void writeNotes();
    void recordVideo();
    void recordAudio();
}
```

If Ram has to implement this, then he will be forced to write methods for video and audio which he don't use. Maybe he leave them blank or put some dummy code. This is wrong.

### What ISP Says:

Make small and focused interfaces:

```java
interface NoteTaker {
    void writeNotes();
}

interface VideoRecorder {
    void recordVideo();
}

interface AudioRecorder {
    void recordAudio();
}
```

Now Ram only implements NoteTaker. Shyam and Geeta implement only what they need. This is better and clean.

### Real Life Example I Understood:

There is a Printer interface like:

```java
interface Printer {
    void print();
    void scan();
    void fax();
}
```

We make a SimplePrinter class which only supports print(). But now because of the interface, we are forced to implement scan() and fax() also. Even if we don't need.

#### Better Solution:

Break the interface:

```java
interface Printable {
    void print();
}

interface Scannable {
    void scan();
}

interface Faxable {
    void fax();
}
```

Now SimplePrinter only use Printable. No extra work. This follows ISP.

### One More Example:

Suppose we have interface Shape with methods:

* calculateArea()
* calculatePerimeter()
* calculateVolume()

Now Square and Rectangle are 2D shapes. So volume don't make sense.
Cube is 3D, so maybe perimeter is not useful.

But still all of them have to implement all 3 methods. This is not good.

#### How to Fix:

Make 2 interfaces:

```java
interface TwoDShape {
    void calculateArea();
    void calculatePerimeter();
}

interface ThreeDShape {
    void calculateArea();
    void calculateVolume();
}
```

Now Square and Rectangle implement TwoDShape. Cube implements ThreeDShape.

### Final Thoughts:

I learned that we should not force classes to use methods they don't need. Instead break things into small parts and only give class what it really use. It makes code more clean and easy to understand.

---

## Difference Between Liskov Substitution Principle (LSP) and Interface Segregation Principle (ISP)

### My Understanding:

Both LSP and ISP are part of SOLID principles. At first they feel similar but they are different. I tried to write down what I learnt.

### 1. Liskov Substitution Principle (LSP)

This one is about parent and child class. If we make a child class from a parent class, then that child should be usable in place of the parent.

If parent class have some behaviour, the child should not change it or break it. If it breaks, then it is LSP violation.

#### Example I Remember:

There is a class Bird with a method fly(). Then we make Sparrow and Crow subclasses. They fly, so ok.

But then we make Penguin class also extend Bird. But Penguin can't fly. Now if we do:

```java
Bird b = new Penguin();
b.fly();
```

This will go wrong. So LSP is broken. Penguin is not a good subclass of Bird.

### 2. Interface Segregation Principle (ISP)

This one is about not giving too many methods to a class. When we create a big interface with too many methods, and make a class implement that, then that class might have to write some useless methods.

ISP says break interface into small pieces. Only give what is needed.

#### Example:

Suppose we make a Shape interface with area(), perimeter(), volume(). Now we create Square class. It only needs area and perimeter. But still we have to write volume() method. This is wrong.

We should instead make different interfaces like TwoDShape and ThreeDShape.

### Summary Table I Made:

| Principle | Focus Area           | When Problem Happens                      |
| --------- | -------------------- | ----------------------------------------- |
| LSP       | Parent-Child classes | When child break parent's promise         |
| ISP       | Interface design     | When class is forced to use extra methods |

### Final Line:

LSP is like - child class should behave like parent.
ISP is like - give class only that interface which it really need.

Both are useful to write clean and working code.

---

## Dependency Inversion Principle (DIP) - My Notes as a Student

### What is DIP?

So basically, from what I got, DIP means that the main part of your program (called the high-level module) should not directly depend on the small details (called low-level modules). Both of them should depend on something in between — like an interface or abstract class.

#### When DIP is NOT followed (bad design)

Imagine the placement cell only works with CSE students. Now if students from ECE, IT or MBA want to join placements, then we have to change the placement cell code. That means the main logic (placement cell) is depending too much on one specific thing (CSE students).

So this is bad because it's tightly coupled.

#### When DIP is Followed (good design)

Now instead of depending on only CSE students, we create an interface called `EligibleCandidate`.

Then all kinds of students (CSE, ECE, MBA) implement this interface.

Now the placement cell just needs to deal with `EligibleCandidate`, not with any specific student type. So even if we add new types of students later, we won’t touch the placement cell code.

This is what DIP says — depend on abstraction, not on details.

### Another Cool Example - Going to College

#### Wrong Way (DIP violated):

Let’s say a student always says: "I go to college only by scooter."

If the scooter breaks down, he can’t go. That means he is directly depending on scooter (a low-level thing), which is bad.

#### Correct Way (DIP followed):

Now instead we make an abstraction called `TransportMode`.

The student just says: "I need any TransportMode to go to college."

Now whether it’s scooter, bus, auto, cycle — anything can work.

Student only depends on `TransportMode`, and not on the actual transport.

So this is how DIP works — both student (high-level) and transport types (low-level) depend on the same abstraction.

### Why DIP is Actually Helpful

Because if later we want to add something new (like a cab, or new student category), we don’t have to change our main logic. Our code becomes clean, flexible and super easy to maintain.

### Final Thoughts

DIP doesn’t mean remove dependency totally. It just means don’t depend on real stuff (like scooter or CSE student), just depend on a common interface.

It helps to keep code reusable, future-ready and less messy.

---

### 💡 Interview Impact

If I tell this example in interview, the interviewer will quickly understand that:

> "I actually understood what Dependency Inversion Principle is — not just the bookish definition."

This is how I remembered DIP in simple and real way. ✅

---