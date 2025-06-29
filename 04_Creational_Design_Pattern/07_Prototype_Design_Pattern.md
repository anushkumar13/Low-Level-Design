## prototype design pattern - what i understood

### main idea:

prototype pattern means making new object by copying a existing object instead of creating it again from zero using new keyword. so we copy from a pre-made object which we call prototype. it's faster and saves time also.

---

### doubts i cleared:

**does it really create new object?**
yes. but not by constructor. it clone the old object and give us new one.

**prototype is the original object?**
yes exactly. prototype is like a base object which we already setup once. after that we use it to make more objects like it by just cloning.

---

### real life example that clicked for me:

resume template - in college, we all take same resume template and just put our own name, photo, skills etc. nobody make resume from scratch.
template = prototype
our final resume = clone

---

### fast recap:

* prototype pattern = copy object from existing one
* avoid using "new" again and again
* helpful when object creation is slow or has many setup steps

---

### why this pattern is needed:

creating objects again and again from scratch takes time, memory, and effort. in big software like games or tools, making 100 similar objects can be slow if we use constructor every time. so we just make one prototype and clone it.

---

### example from photoshop:

i made a nice shape with border, text, shadow etc. now i need 20 more like that. i won’t make all from zero. i’ll just copy the first one and change things. that first one is my prototype.

---

### example from gaming:

a game has a zombie character with model, sound, animation etc. making this every time is too much work. so game devs just create one base zombie and clone it whenever new zombie is needed. saves time and performance.

---

### prototype vs new object:

| thing      | clone (prototype)              | new (constructor)                    |
| ---------- | ------------------------------ | ------------------------------------ |
| speed      | fast, just a copy              | slow, has to create fresh            |
| memory     | less usage, reuse same stuff   | more usage, everything from start    |
| setup time | very less, already configured  | more, need to setup again            |
| use when   | when need many similar objects | when need totally new and unique one |

---

### last thoughts:

i liked this pattern bcoz it’s easy to understand. instead of repeating object creation, we just copy one that’s already setup. saves lot of time. very useful when we deal with complex objects or when same type of object is needed again and again.

so ya, prototype pattern = clone and go 😄

---

## Shallow Copy vs Deep Copy

Understanding the difference between Shallow Copy and Deep Copy is very important specially when working with complex objects in programming. This note is my understanding of these two concepts in a student style.

---

### Basic Difference

| Copy Type    | What Gets Copied?                                                                 |
| ------------ | --------------------------------------------------------------------------------- |
| Shallow Copy | Only the outer object is copied. Inner objects are still shared (same reference). |
| Deep Copy    | Outer object and all inner objects are copied fully and separately.               |

---

### Real-Life Analogy: Student Bag

Imagine a situation from college life:

* Bag = Outer Object
* Books inside the bag = Inner Objects

#### Shallow Copy:

I copy my friend's bag, but the books inside are not copied. We both have different bags but we are using the same books. If I write something in one book, my friend can also see it in his bag because it's the same book.

This means both outer objects (bags) are different but inner objects (books) are same.

#### Deep Copy:

Now suppose I copy both the bag and I also buy the same set of books, then both of us have completely different things. If I write something in my book, my friend can't see it because his book is different.

This means both outer and inner objects are different.

---

### Programming Visualization

```java
class Person {
   String name;
   Address address;
}
```

#### Shallow Copy Example:

```java
Person copy = original.clone();
// name is copied
// but address is the same reference
```

So in this case:

* copy.address == original.address → true
* if I change the address in copy, it changes for original also

#### Deep Copy Example:

```java
Person copy = new Person();
copy.name = original.name;
copy.address = new Address(original.address); // deep copy
```

In this case:

* copy.address == original.address → false
* both objects are fully separate

---

### When to Use?

| Situation                                           | Use This Copy Type |
| --------------------------------------------------- | ------------------ |
| You only need the outer object, inner can be shared | Shallow Copy       |
| You need a complete independent duplicate           | Deep Copy          |

---

### Final Summary

Shallow Copy is when you copy the outer object but inner objects are still the same. So changes in one will reflect in another. There is risk of unwanted changes.

Deep Copy is when you copy everything. Outer object and all inner objects also. So both objects are completely independent.

Use shallow copy when you don't care about inner changes. Use deep copy when you want full separation and no risk.

This is how I understood the topic and I think it's very useful when working with clone operations or object copying.

---

## When to Use Prototype Design Pattern

### Purpose:

Prototype Pattern is useful when creating a new object takes too much time or memory or processing. So instead of creating objects again and again, we just make one object and then clone it.

---

### Story-Style Real-World Example:

Suppose I am a game developer. I made a very detailed monster:

* It has 3D animation
* A sound engine
* High quality textures
* AI behavior and weapons etc.

Now I need 50 more monsters like this in my game.
If I do this:

```java
new Monster();
```

every time,

Then it will:

* take too much time
* use a lot of memory
* make my game slow

So instead what I do is:

* create one base monster
* then just clone it using prototype pattern
* after cloning, I can change little things like name, health, etc.

This saves time and improves performance.

---

### When Should We Use Prototype Pattern?

We should use this pattern when:

1. Object creation is expensive (like DB calls, API calls, 3D loading etc.)
2. You want to make many similar objects
3. Constructor logic is complex or not public
4. You want to skip calling constructor again and again
5. Your class allows cloning (like `clone()` or copy constructor)
6. The application needs high performance (like games, graphics, simulators)

---

### Real-World Use Cases:

| Scenario                         | Why Use Prototype?                             |
| -------------------------------- | ---------------------------------------------- |
| Game (monsters, enemies)         | Same monster again and again with changes      |
| UI tools (shapes, buttons)       | Same UI component with different labels etc.   |
| Document templates (resume etc.) | One base layout cloned with new content        |
| Simulations (bots, robots)       | Copy and run same bot logic in parallel        |
| Networking setup or DB configs   | Reuse and clone same setup without repeat code |

---

### Final Summary:

If you are creating objects again and again which are mostly same, and creating them is costly, then Prototype Pattern is the best.

Just create one prototype object and keep cloning it.

This way you save memory, time and make the app faster.

Important words to remember: clone, copy, avoid constructor, fast object creation, save resources.

That's how I understood when to use Prototype Pattern.

---

