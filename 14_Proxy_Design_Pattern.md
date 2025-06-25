# Proxy Design Pattern (Structural Design Pattern)

## 🔥 What is the Proxy Design Pattern?

"The Proxy pattern creates a representative or placeholder object (proxy) that controls access to another object (real subject)."

It allows you to create an interface to control, delay, or enhance the access to the original object.

---

## 🔐 Real-Life Example 1: ATM Card (Proxy for Bank Account)

* **Bank Account** = Real Object
* **ATM Card** = Proxy Object

You do not go to the bank vault directly to withdraw money. Instead:

* You use your **ATM card**, which acts as a **representative**
* It **authenticates**, **validates**, and **communicates** with the bank on your behalf

✅ **Controlled access** to your sensitive asset — that's a Proxy!

---

## 🧍 Real-Life Example 2: Celebrity Bodyguard

* **Celebrity** = Real Object
* **Bodyguard** = Proxy

If you want to meet the celebrity, you cannot go directly. The bodyguard:

* Screens you
* Grants or denies access
* Controls how and when you meet

➡️ The bodyguard acts as a **proxy**, protecting and managing access to the real subject.

---

## 💻 Types of Proxy in Programming

| Type             | Description                                                                                  |
| ---------------- | -------------------------------------------------------------------------------------------- |
| Virtual Proxy    | Controls access to objects that are expensive to create (e.g., large images)                 |
| Protection Proxy | Controls access rights based on roles (e.g., admin vs user)                                  |
| Remote Proxy     | Represents an object that exists in a different address space or machine (e.g., RMI in Java) |
| Smart Proxy      | Adds extra functionality like logging, reference counting, etc.                              |

---

## 🧾 Real-World Software Examples

| Real-World Case | Proxy Role                                 |
| --------------- | ------------------------------------------ |
| ATM Card        | Acts as a proxy for your Bank Account      |
| VPN             | Proxy between your system and the internet |
| Java RMI        | Remote proxy object for remote services    |
| Hibernate ORM   | Lazy-loaded database objects via proxy     |
| Image Viewer    | Loads image on demand using proxy          |

---

## 🎯 Final Summary (Bhai-Style 😄)

> Whenever you don’t want to give direct access to an object — for performance, security, or convenience reasons — you use a **Proxy Pattern**.

✅ Proxy object **stands in place** of the real object
✅ Controls how and when the real object is accessed
✅ Keeps the real object secure, optimized, or lazily initialized

---

## 📦 Java Analogy

* `RealSubject` = BankAccount
* `Proxy` = ATMCard
* `Client` = You

Proxy lets the client interact safely, smartly, and efficiently with the real subject.

---

# Proxy Design Pattern Explained

## Real-Life Example: Internet Cafe and Admin

Imagine you're in an internet cafe and you say:

> "I want to open YouTube."

But — you can't directly open YouTube on your own.

There's an admin computer installed in the cafe.
The admin monitors which sites are being accessed.

If YouTube is allowed → you get access.
If not → you see a message: "Access Denied."

### Mapping to Proxy Pattern:

* **You (Client)** → Wants to use the service
* **YouTube Server (Real Subject)** → The actual resource
* **Admin (Proxy)** → Acts as a gatekeeper between you and the YouTube server

The admin:

* Decides whether you can access the real server
* Can log your activity
* May show a fake page (like a "Blocked" notice)

This is exactly what the **Proxy Design Pattern** does.

---

## What is the Proxy Pattern?

In the Proxy Pattern, we create a class that acts as a substitute or placeholder for another object. This proxy class controls access to the actual object, and may also perform additional tasks such as logging, access control, lazy loading, etc.

---

## Roles in Proxy Pattern:

| Character      | Pattern Role |
| -------------- | ------------ |
| YouTube Server | Real Object  |
| Admin Guy      | Proxy        |
| You (User)     | Client       |

The **client does not interact directly** with the real object.
Instead, all requests go through the proxy, which may allow, deny, or modify the request.

---

## When to Use the Proxy Pattern?

* **Access Control / Security**
  E.g., Admin allows or blocks certain websites

* **Lazy Initialization (Virtual Proxy)**
  E.g., Loading large images only when needed

* **Remote Proxy**
  E.g., Accessing objects on another machine (like RMI in Java)

* **Logging / Monitoring**
  E.g., Keeping track of which services are being accessed

---

## Summary

The Proxy Pattern is a design pattern where you don't directly use the real object.
Instead, you go through a **proxy** that can:

* Control access
* Log actions
* Delay operations (lazy loading)
* Provide additional behavior

In short:

> A proxy acts on behalf of the real object — like a smart gatekeeper between the client and the service.

---

# Virtual Proxy Design Pattern Explained

## What is Virtual Proxy?

Virtual Proxy is a type of Proxy Design Pattern where the creation of an actual object is delayed until it's really needed. This is also known as **Lazy Loading**.

> "When creating the actual object is expensive in terms of time or memory, we create a proxy that defers its creation until it is truly required."

---

## Real-Life Analogy: Online Food Menu App

Imagine you're using a food delivery app that shows a list of 100 dishes.

Each dish has a high-resolution image of **5MB**.

If the app loads all 100 images at once:

* The app will become **slow**
* **Memory usage** will shoot up
* **Load time** will increase drastically

### Solution: Use Virtual Proxy

Instead of loading the real images immediately:

* Show a lightweight placeholder using an **ImageProxy**
* Only when the user clicks **"View Image"**:

  * The proxy then creates and loads the **actual image object**
  * Displays the real image

The proxy acts like a real image but loads the heavy object **only when needed**

---

## In Programming Terms (e.g., Java Style)

```java
Image img = new ImageProxy("dish.jpg");
img.display(); // Image is loaded only at this moment
```

In this example:

* Initially, the `ImageProxy` holds a `null` reference to the real image
* When `display()` is called, the real image is created and shown

---

## When to Use Virtual Proxy?

| Situation                              | Why Use Virtual Proxy?              |
| -------------------------------------- | ----------------------------------- |
| Heavy object creation (e.g., images)   | To save memory and reduce load time |
| Expensive DB calls / report generation | Avoid unnecessary computation       |
| Lazy loading UI components             | Don’t load UI elements until needed |
| Network-heavy objects                  | Load only when required             |

---

## Summary

✅ Virtual Proxy delays the creation of real objects until absolutely necessary.

This leads to:

* **Better performance**
* **Efficient memory usage**
* **Fast and responsive applications**

> "Don't create what you don't need — until you need it." That’s the power of **Virtual Proxy**.

---

# Security Proxy Design Pattern Explained

## What is a Security Proxy?

A **Security Proxy** is a type of Proxy Design Pattern that controls access to an object based on the user's identity, role, or permissions.

> "A Security Proxy determines whether a client is authorized to access the real object or not."

It acts like a **bouncer** who only lets in the VIPs.

---

## Real-Life Analogy: Office Building with Security Guard

Imagine there's a **VIP floor** in an office building — like a **Server Room**.

Not every employee can go there.

When someone tries to enter:

* A **Security Guard** scans their ID card
* If they have permission → Access is granted
* If not → The guard says: "Access Denied"

### Mapping:

* **Employee (Client)** → Wants access to the server room
* **Security Guard (Security Proxy)** → Controls who gets in
* **Server Room (Real Object)** → The resource being protected

---

## Programming Analogy

Suppose there's a class: `SensitiveData`

You don’t want every user to access it.

So, you create: `SensitiveDataProxy`

* When a method is called, the proxy checks the **user's role**
* If the role is `admin` → it forwards the call to the real object
* If not → it throws `AccessDeniedException`

---

## When to Use Security Proxy?

| Situation                | What the Proxy Does                          |
| ------------------------ | -------------------------------------------- |
| Admin dashboards         | Checks if the user has admin privileges      |
| Banking systems          | Allows only authorized users to transact     |
| File access control      | Ensures only valid users can view/edit files |
| API Gateways (JWT/OAuth) | Verifies tokens before allowing access       |

---

## Summary

✅ A **Security Proxy** is used when access to a resource must be restricted based on user identity or role.

It:

* Prevents unauthorized access
* Adds a security layer without modifying the real object
* Keeps sensitive operations safe from untrusted clients

> Just like a VIP bouncer, it makes sure **only the right people get in.**

---

# Why Proxy and Real Object Implement the Same Interface

## Core Idea

✅ Yes — the **Proxy Object** and the **Real Object** implement the **same interface**.

### But Why?

Because the **interface defines a contract** — a common set of behaviors that both the proxy and the real object agree to follow.

This ensures that the **client code** (which uses the object) does not need to care whether it's using a real object or a proxy — it just interacts with the **interface**.

---

## Real vs Proxy Object Responsibilities

| Type         | Responsibility                      |
| ------------ | ----------------------------------- |
| Real Object  | Provides the actual functionality   |
| Proxy Object | Controls access, adds logging, etc. |

The client doesn't need to know what's behind the interface — it just trusts that the object will behave as per the contract.

---

## Example in Java

```java
interface YouTube {
    void playVideo();
}
```

### Real Object:

```java
class RealYouTube implements YouTube {
    public void playVideo() {
        // Actual video plays here
    }
}
```

### Proxy Object:

```java
class ProxyYouTube implements YouTube {
    private RealYouTube realYouTube;
    private boolean isPremium;

    public void playVideo() {
        if (isPremium) {
            realYouTube = new RealYouTube();
            realYouTube.playVideo();
        } else {
            System.out.println("Access Denied. Upgrade to Premium!");
        }
    }
}
```

### Client Code:

```java
YouTube yt = new ProxyYouTube();
yt.playVideo(); // Client doesn't care if it's proxy or real
```

---

## Benefits

✅ **Loose Coupling**:
Client remains unaware of whether it’s interacting with the real object or the proxy.

✅ **Flexibility**:
You can add or swap out proxies without changing the client code.

✅ **Maintainability**:
Concerns like access control, logging, caching can be isolated in the proxy class.

---

## Summary

Yes — both the **proxy** and the **real object** implement the same interface so that:

* The client treats them interchangeably
* The system stays flexible and loosely coupled
* Proxies can seamlessly substitute the real object when needed

---
