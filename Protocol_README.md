# 🧩 Swift Protocols 

## 🔹 What is a Protocol?
A **blueprint** that defines methods and properties a type must implement.  
Used for **abstraction and flexibility**.  
```swift
protocol Animal {
    func sound()
}
```

---

## 🔹 Why use Protocols?
✅ Defines **common behavior** for classes, structs, and enums  
✅ Enables **multiple conformance**  
✅ Promotes **code reusability** and **loose coupling**

---

## 🔹 Protocol vs Class Inheritance

| Feature | Protocol | Class Inheritance |
|----------|-----------|------------------|
| Inheritance | Multiple | Single |
| Purpose | Defines behavior | Shares implementation |
| Relationship | “Can do” | “Is a” |

---

## 🔹 Protocol Extension
Add **default implementations** or shared behavior.  
```swift
protocol Greet { func sayHello() }
extension Greet { func sayHello() { print("Hello!") } }
```

---

## 🔹 Delegation Pattern
Used for **communication between objects**.  
Example: UITableViewDelegate, UITextFieldDelegate  
```swift
protocol TaskDelegate { func didFinish() }
```

---

## 🔹 AnyObject
Restricts protocol conformance to **class types only**.  
```swift
protocol MyDelegate: AnyObject {}
```

---

## 🔹 Protocol Composition
Combine multiple protocols into one type.  
```swift
func operate(_ v: Flyable & Drivable) { }
```

---

## 🔹 Stored Properties in Protocols
❌ Not allowed.  
Protocols can only have **get/set property requirements**.

---

## 🔹 Associated Types
Used for **generic protocols**.  
```swift
protocol Container {
    associatedtype Item
    func add(_ item: Item)
}
```

---

## 🔹 Protocol-Oriented Programming (POP)
Swift’s design approach focusing on:
- **Protocols + Extensions**
- **Value types (Structs)**
- **Code reuse without inheritance**
