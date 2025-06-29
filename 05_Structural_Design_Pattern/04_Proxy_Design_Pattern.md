## Proxy Design Pattern (Structural Design Pattern)

### What is the Proxy Design Pattern?

The Proxy Pattern creates a representative or placeholder object (proxy) that controls access to another object (real subject). This pattern allows us to control, delay, or enhance how the original object is accessed.

---

### Real-Life Example 1: ATM Card (Proxy for Bank Account)

* Bank Account = Real Object
* ATM Card = Proxy Object

You don't go directly to the bank to withdraw cash. Instead, you use your ATM card.

* The ATM card acts on your behalf
* It checks your credentials and communicates with the bank
* Access is granted only after validation

This is controlled access — and that’s what a Proxy does.

---

### Real-Life Example 2: Celebrity Bodyguard

* Celebrity = Real Object
* Bodyguard = Proxy

You can’t directly meet the celebrity. The bodyguard:

* Screens who gets access
* Decides when and how someone meets the celebrity

Again, this is a proxy in action.

---

### Types of Proxy in Programming

| Type             | Description                                                                 |
| ---------------- | --------------------------------------------------------------------------- |
| Virtual Proxy    | Controls access to costly-to-create objects like large images               |
| Protection Proxy | Grants access based on permissions (like user roles)                        |
| Remote Proxy     | Represents objects on different machines or address spaces (e.g., Java RMI) |
| Smart Proxy      | Adds extra features like logging, counting references, etc.                 |

---

### Real-World Software Examples

| Real-World Use | What the Proxy Does                          |
| -------------- | -------------------------------------------- |
| ATM Card       | Acts as proxy to access your bank account    |
| VPN            | Sits between your system and the internet    |
| Java RMI       | Proxy to access remote objects               |
| Hibernate ORM  | Lazy loads database objects using proxy      |
| Image Viewer   | Uses proxy to load images only when required |

---

### Final Summary

Whenever you don’t want to give direct access to an object — either for performance, security, or convenience — you can use the Proxy Pattern.

* The proxy object replaces the real object temporarily or conditionally
* It decides how and when the real object should be accessed
* The actual object stays protected or optimized behind the proxy

---

### Java Analogy

* RealSubject = BankAccount
* Proxy = ATMCard
* Client = You

The proxy (ATMCard) lets the client (You) access the real object (BankAccount) in a safe and managed way.

---

### Real-Life Example: Internet Cafe and Admin

In an internet cafe, you might say:
"I want to open YouTube."

But you can’t open it directly.

There’s an admin computer in between. The admin:

* Monitors which sites can be accessed
* Allows or blocks access depending on policy

### Mapping to Proxy Pattern:

* You (Client) want to use a service
* YouTube Server = Real Object
* Admin = Proxy

The admin decides:

* Whether your request reaches the real server
* Logs your activity
* May show a block page instead of the real site

That’s exactly how a Proxy works in programming.

---

### Roles in the Proxy Pattern

| Role        | Who or What It Represents |
| ----------- | ------------------------- |
| Real Object | YouTube Server            |
| Proxy       | Admin                     |
| Client      | You (User)                |

The client never deals directly with the real object. Everything goes through the proxy.

---

### When to Use the Proxy Pattern

* **Access Control / Security** — Admin blocks or grants website access
* **Lazy Initialization** — Large files or images are loaded only when needed
* **Remote Proxy** — Communicate with objects on a remote system
* **Logging / Monitoring** — Record what services are being accessed and how often

---

### Summary

The Proxy Pattern is used when we want to avoid direct access to a real object. This can be because:

* The object is costly to create
* The object needs to be protected
* The object is on a remote machine
* We want to add extra features like logging

In simple words:

A proxy sits between the client and the real object — like a smart middle layer that manages, secures, or enhances the interaction.

---

## Virtual Proxy Design Pattern Explained

### What is Virtual Proxy?

Virtual Proxy is like a type of Proxy Design Pattern where we delay the creation of actual object until it's really needed. This is also called Lazy Loading.

In simple words:

> If creating the actual object is costly or slow, we make a proxy and use it. Then when we really need the object, we create it.

---

### Real-Life Analogy: Online Food Menu App

Imagine you're using a food delivery app which shows 100 dishes.
Each dish has a high quality image around 5MB size.

If app loads all images at once:

* It becomes slow
* Uses lot of memory
* Not a good experience for user

So instead of loading all images:

* App show a placeholder using `ImageProxy`
* When user clicks on "View Image", only then the real image loads

Proxy acts like image but delays the actual loading till needed.

---

### Programming Analogy (Java Style)

```java
Image img = new ImageProxy("dish.jpg");
img.display(); // Image is only loaded now
```

Here:

* `ImageProxy` don’t load the image immediately
* Only when `display()` is called, real image gets created and shown

---

### When to Use Virtual Proxy?

| Situation                            | Why Use Virtual Proxy?          |
| ------------------------------------ | ------------------------------- |
| Heavy object creation (e.g., images) | Save memory and reduce time     |
| Expensive DB calls or reports        | Avoid doing them unless needed  |
| Lazy loading UI parts                | Load UI only when user need it  |
| Network-heavy stuff                  | Don’t fetch until really needed |

---

### Summary

Virtual Proxy is good when the real object is heavy or slow to make. It help us:

* Improve app speed
* Save memory
* Make user experience better

The idea is simple:

> Don’t create something until you actually need it.

---

## Security Proxy Design Pattern Explained

### What is a Security Proxy?

Security Proxy is another type of Proxy Design Pattern. It control the access to real object depending on who is trying to access it.

In easy words:

> Security Proxy checks who the client is and only allow if permission is there.

---

### Real-Life Analogy: Office Building with Security Guard

Think there is a secure floor in office like server room.
Not every employee can go there.

If someone try to enter:

* Security guard checks their ID
* If they are allowed → access given
* If not → they can’t enter

In pattern terms:

* Employee = Client
* Guard = Security Proxy
* Server Room = Real Object

---

### Programming Analogy

Say we have a class `SensitiveData`
We don’t want all users to access it

So we create a `SensitiveDataProxy`

* It checks user’s role
* If admin → allow access
* If not → throw error or deny

---

### When to Use Security Proxy?

| Situation           | What the Proxy Does                      |
| ------------------- | ---------------------------------------- |
| Admin panels        | Checks if user is admin                  |
| Banking systems     | Allow only valid user to do transactions |
| File systems        | Only right users can edit or view files  |
| APIs (JWT or OAuth) | Verify token before allowing request     |

---

### Summary

Security Proxy is used when only some people should use a resource. It works like protection.

It:

* Stops access to wrong users
* Keep real object safe
* Adds one extra layer without changing real object code

It’s like a gatekeeper who allow only trusted people inside.

---

## Why Proxy and Real Object Implement the Same Interface

### Core Idea

Yes, proxy and real object both use the same interface.

### But Why?

Because the interface give them a common set of rules or behaviours. So both of them must follow that.

This help the client code to not worry about who is doing the work. It just use the interface and it works.

---

### Real vs Proxy Object Responsibilities

| Type         | What It Does                      |
| ------------ | --------------------------------- |
| Real Object  | Do the actual task                |
| Proxy Object | Adds access control, logging, etc |

Client don’t need to care who is handling it. It just expect correct output as per the interface.

---

### Java Example

```java
interface YouTube {
    void playVideo();
}
```

#### Real Object:

```java
class RealYouTube implements YouTube {
    public void playVideo() {
        // Video is playing
    }
}
```

#### Proxy Object:

```java
class ProxyYouTube implements YouTube {
    private RealYouTube realYouTube;
    private boolean isPremium;

    public void playVideo() {
        if (isPremium) {
            realYouTube = new RealYouTube();
            realYouTube.playVideo();
        } else {
            System.out.println("Access Denied. Please upgrade to premium");
        }
    }
}
```

#### Client Code:

```java
YouTube yt = new ProxyYouTube();
yt.playVideo(); // Client not cares if proxy or real
```

---

### Benefits

* Loose Coupling:
  Client is not depend on which object is used.

* Flexibility:
  We can change between proxy and real anytime without changing client code.

* Maintainability:
  All extra stuff like logging or security can go in proxy only.

---

### Summary

Both real object and proxy use the same interface so that:

* Client can use both without any problem
* Code stays easy to manage
* We can replace real with proxy when ever needed

---
