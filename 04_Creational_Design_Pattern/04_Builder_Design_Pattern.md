## Builder Pattern 

### What is Builder Pattern?

Builder pattern is used when object is too complex and have many parts. It helps to build the object step by step instead of putting everything in constructor.

---

### What I understood simply:

When object has too many options, constructor becomes messy. So we use Builder.
It allows us to do:

```java
BurgerBuilder()
  .addCheese()
  .addPatty("chicken")
  .addSauce("mayo")
  .addPickles()
  .build();
```

We just add one thing at a time and then finally call build().

---

### Real Life Example - Burger 🍔

Making burger:

* patty (veg or chicken)
* sauce (mayo, mustard etc)
* cheese
* pickles
* lettuce
* bun type

If we try to handle all in constructor, it becomes too much.
Better to use builder and add things step by step.

---

### When should we use Builder Pattern?

* when constructor has too many parameters
* when we want to build object step by step
* when we need many variations of same object
* when we want immutability (final object can’t change after built)

---

### How it’s Different from Factory Pattern?

| Pattern | Use For                   |
| ------- | ------------------------- |
| Factory | hide object creation      |
| Builder | build object step by step |

---

### My Final Line:

Builder Pattern is useful when object has many optional and required parts, and we want to create it in clear and safe way step-by-step.

---

## Aggregation vs Composition - My Notes

### Basic Idea:

Both are about objects containing other objects.
But:

* Aggregation = loose connection
* Composition = tight connection

---

### Aggregation - Loose Relationship

Example:

* University has students and teachers.
  Even if university is deleted, students and teachers can exist.

Real Life: Playlist has songs. Songs can exist without playlist.

Important Points:

* "has-a" relation
* part can live without whole
* loosely connected
* UML symbol: hollow diamond (◇)

---

### Composition - Tight Relationship

Example:

* House has rooms, doors, windows.
  If house is gone, all are gone.

Real Life: Human has heart, brain, lungs. They can’t live without human.

Important Points:

* "owns-a" relation
* part can’t live without whole
* strongly connected
* UML symbol: filled diamond (◆)

---

### Aggregation vs Composition Table

| Feature    | Aggregation         | Composition       |
| ---------- | ------------------- | ----------------- |
| Relation   | has-a               | owns-a            |
| Dependency | part is independent | part depends      |
| Lifetime   | not connected       | same as container |
| UML Symbol | hollow diamond      | filled diamond    |
| Example    | Playlist - Songs    | House - Rooms     |

---

### One Line Summary:

* Aggregation: object uses other objects but doesn’t own them
* Composition: object owns other objects and they can’t live separately

---

### My Builder Pattern One Line:

If object is complex and needs many parts, use builder pattern to build it step-by-step and finally make the full object.

---

### Real-Life Example: Burger Order at a Restaurant

Imagine you go to a restaurant and say:

> I want a customized burger.

The waiter who is like a Builder says:

> Sir, please tell me what you want.

Then you start telling step by step:

* Bread: Multigrain
* Patty: Chicken
* Cheese: Yes, double cheese
* Sauce: Only mayo
* Pickles: No, skip it

Now:

* Each step is done separately
* You can choose which things to include and skip
* After you complete all steps, you say:

> Done, make it

Now waiter makes your full customized burger just like the `build()` method in Builder Pattern. You get a final burger object which is made just for your order.

---

### Key Point:

* You are adding one-one ingredient step by step
* You are not giving everything at once like we do in constructor
* You can clearly see what things are added
* Final burger will not change after made — it is fixed now

---

### Another Example: Online Resume Builder

If you use a website to make resume:

* Add your name
* Add your photo
* Add your skills
* Add projects
* Add achievements
* Add social links

Then you click: Generate Resume

So here also:

* Resume is not simple object, it's a complex object
* You build it part by part
* After you done, final resume is generated
* You can't edit it after, it is fixed

This is also Builder Pattern.

---

### One More Quick Example: Making Juice

You say:

* Base: Orange
* Add: Sugar
* Add: Ice
* Add: Lemon
* Mix it
* Serve (like build method)

Juice is only served after all steps complete. So this is also Builder.

---

### Summary in Simple Words:

Builder Pattern means:

> When you want to create a object that needs many steps, where some steps are optional, and you want clarity and control — use Builder Pattern to build it step by step and then call build().

It is best when you want to make complex objects in clear and easy way.

---

### Understanding the Flow of Builder Pattern

#### Question 1: Does Client give Builder to Director?

Yes, Client chooses which builder to use like VegBurgerBuilder, ResumeBuilder etc. Then gives that builder to Director.

Director's job is to guide how to make the object step by step.

#### Question 2: Does Director give instructions to Builder?

Yes, Director tells Builder like:

* Add bun
* Add cheese
* Add lettuce
* Add sauce
* Put top bun

Like this, Director gives the plan, and Builder follows it.

#### Question 3: Does Builder return the final object to Client?

Yes, after following all steps, Builder calls build() and gives final object to Client.

---

### Real-Life Analogy Again: Custom Burger Order

**Client**: Says I want a custom burger and chooses VegBurgerBuilder

**Director**: Says step by step what to do — like add bun, add patty, add cheese...

**Builder**: Follows these steps and finally builds the burger using build()

---

### One-Line Summary:

* Client chooses Builder and gives to Director
* Director tells the steps
* Builder makes the object and gives final product to Client

This is the Builder Pattern real flow.

---