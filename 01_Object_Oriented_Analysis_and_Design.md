# Object-Oriented Analysis and Design (OOAD)

Object-Oriented Analysis and Design (OOAD) is a software development process in which real-world problems are analyzed and designed using object-oriented principles. In this approach, every part of the system is broken down into classes, objects, and their relationships.

## Simple Definition

OOAD means:
"Thinking, modeling, and designing software in an object-oriented style."
In other words, it involves converting real-world entities (like student, bank account, order) into classes and objects.

## OOAD 2-Part Process

### 1. Object-Oriented Analysis (OOA)

* Focuses on "What is the problem?"
* It understands the real-world problem and identifies objects, attributes, and their relationships.
* **Output**: Requirements + Conceptual Model

### 2. Object-Oriented Design (OOD)

* Focuses on "How will the solution be built?"
* It involves creating software class diagrams, defining methods, using inheritance, and applying polymorphism.
* **Output**: Blueprint of code (UML diagrams, design specifications)

## Example: School Management System

**OOA:**

* Identify objects: Student, Teacher, Course, Classroom
* Find relationships: A Student enrolls in a Course, a Teacher teaches a Course

**OOD:**

* Create classes: Student, Course
* Add attributes: name, id, courseList
* Add behaviors: enrollInCourse(), assignTeacher()
* Use inheritance: Person → Student, Teacher

## OOAD Concepts

* **Class**: Blueprint of an object (e.g. Car)
* **Object**: Real instance of a class (e.g. myCar)
* **Encapsulation**: Combining data and methods together
* **Abstraction**: Showing only necessary information
* **Inheritance**: Reusing code by extending classes
* **Polymorphism**: Same method can behave differently in different contexts

## OOAD Tools

* UML Diagrams (Class Diagram, Sequence Diagram, etc.)

* Use Case Diagrams
* Design Patterns (Singleton, Factory, etc.)

## Purpose of OOAD

* To make code modular and reusable
* To break a complex system into manageable parts
* To build software that mirrors real-world thinking
