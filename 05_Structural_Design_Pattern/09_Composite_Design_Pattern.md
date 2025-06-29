# Composite Design Pattern Explained

## What Is the Composite Design Pattern?

The Composite Pattern allows you to treat a single object and a group of objects in the same way.

It is used to build tree-like structures where:

* Leaf = Single object
* Composite = Group of objects (including other groups or leaves)

## Real-Life Example: File System

Think about a file system on your laptop:

* You open the Downloads folder
* Inside, you have:

  * file1.txt
  * file2.jpg
  * A sub-folder called MyPhotos

When you delete or move the Downloads folder:

* All files and sub-folders inside it also get affected
* You are treating files and folders the same way

In this analogy:

* File = Leaf
* Folder = Composite
* Operations like delete() and move() work on both

This is an example of the Composite Pattern.

## Programming Perspective

To implement the Composite Pattern in code:

1. Create an interface called `Component` with a method like `display()`
2. Create a `File` class that implements `Component` and defines `display()`
3. Create a `Folder` class that also implements `Component`, but:

   * Holds a list of `Component` objects (can be files or folders)
   * Its `display()` method iterates over the list and calls `display()` on each

Example:

```java
Component file1 = new File("resume.pdf");
Component folder = new Folder("Documents");
folder.add(file1);
folder.display();
```

Whether you call `display()` on a File or Folder, it behaves the same way.

## Real-World Software Examples

| Real Concept  | Description                                     |
| ------------- | ----------------------------------------------- |
| File System   | Folders containing files or other folders       |
| UI Components | Panels containing buttons, sliders, text fields |
| Organization  | Managers as Composite, Employees as Leaf        |
| Menus         | MenuItems and Submenus treated uniformly        |

## Final Summary

Composite Pattern allows us to:

* Create tree-like structures
* Treat single objects and collections uniformly
* Apply operations like display(), delete(), or execute() in the same way

This makes the code cleaner and more maintainable and avoids the need for handling different cases separately.

## Company Structure Example

Imagine a company hierarchy:

```
CEO
 ├── Manager1
 │    ├── Employee1
 │    └── Employee2
 └── Manager2
      └── Employee3
```

Here:

* CEO is an employee
* Manager is also an employee
* Employee is obviously an employee

All of them share a common role, though their responsibilities differ. We can use a method like `showDetails()` on any of them, and it will work consistently.

This is exactly what the Composite Pattern enables in programming.

---

# Composite Design Pattern - Two Main Components

## 1. Leaf (Simple Object)

- Example: Employee
- Implements `showDetails()` method to show only its own details

## 2. Composite (Group Object)

- Example: Manager, CEO
- Also implements `showDetails()` method which:
  - Shows its own name/details
  - Calls `showDetails()` on all its subordinates

---

## What is the Composite Pattern?

This pattern allows both individual objects and groups of objects to be treated uniformly through a common interface.

- A Leaf performs only its own task.
- A Composite performs its task and delegates to its child components.

---

## Common Use Cases

| Scenario          | Leaf            | Composite    |
| ----------------- | --------------- | ------------ |
| File Explorer     | File            | Folder       |
| Menu Bar          | Menu Item       | Submenu      |
| Company Hierarchy | Employee        | Manager/CEO  |
| GUI Components    | Button, TextBox | Panel, Frame |

---

## When to Use Composite Pattern

Use Composite Pattern when you have a hierarchy of objects such as:

- Single items (like files or employees)
- Groups of items (like folders or managers)

And you want to perform the same operations on both, for example `delete()`, `showDetails()`, or `render()`.

---

## Example Java Implementation

```java
interface Employee {
    void showDetails();
}

class Developer implements Employee {
    private String name;
    public Developer(String name) {
        this.name = name;
    }
    public void showDetails() {
        System.out.println("Developer: " + name);
    }
}

class Manager implements Employee {
    private String name;
    private List<Employee> subordinates = new ArrayList<>();

    public Manager(String name) {
        this.name = name;
    }

    public void add(Employee emp) {
        subordinates.add(emp);
    }

    public void showDetails() {
        System.out.println("Manager: " + name);
        for (Employee emp : subordinates) {
            emp.showDetails();
        }
    }
}

Now, you can call showDetails() on any Employee type, whether it is a Developer or a Manager with a team.

---
