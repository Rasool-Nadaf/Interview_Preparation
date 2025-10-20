# 🧠 Extensions & Protocol Extensions

---

## 🚀 EXTENSIONS

### 1️⃣ What are extensions in Swift?
Extensions add new functionality to an existing **class, struct, enum, or protocol** without modifying original code.

```swift
extension Int {
    func square() -> Int { self * self }
}
print(5.square()) // 25
```

---

### 2️⃣ Why use extensions?
- Add features to existing types.  
- Organize code.  
- Adopt new protocols.  
- Extend system types (e.g., String, Int).  

---

### 3️⃣ What can extensions add?
✅ Methods  
✅ Computed properties  
✅ Subscripts  
✅ Convenience initializers  
✅ Protocol conformance  

❌ No stored properties  
❌ No method overrides  

---

### 4️⃣ Difference between extension and inheritance
| Extension | Inheritance |
|------------|--------------|
| Adds new behavior | Modifies behavior |
| Works on value & reference types | Only for classes |
| No subclassing | Uses subclassing |

---

### 5️⃣ Can extensions conform to protocols?
✅ Yes.
```swift
struct Student {}
extension Student: CustomStringConvertible {
    var description: String { "I am a student" }
}
```

---

## 🧩 PROTOCOL EXTENSIONS

### 6️⃣ What are protocol extensions?
They allow adding **default implementations** for methods or properties in protocols.

```swift
protocol Greetable {
    func greet()
}
extension Greetable {
    func greet() { print("Hello!") }
}
struct Person: Greetable {}
Person().greet() // Hello!
```

---

### 7️⃣ Why are protocol extensions powerful?
They make **protocol-oriented programming** possible — letting you share default behavior without inheritance.

---

### 8️⃣ Can you override default implementation from a protocol extension?
✅ Yes, just define your own implementation inside the conforming type.

---

### 9️⃣ What can’t protocol extensions do?
❌ No stored properties.  
❌ Cannot override existing methods directly like subclassing.  

---

### 🔟 Protocol vs Protocol Extension
| Protocol | Protocol Extension |
|-----------|--------------------|
| Defines rules (no body) | Provides default implementation |
| Adopted by types | Shared by all conforming types |
| No logic | Can have logic |

---

### 11️⃣ What happens if both protocol and extension have methods with same name?
- If conforming type provides its own → **type’s version wins**.  
- Else → **extension’s default** runs.  

---

### 12️⃣ What are constrained protocol extensions?
They apply default behavior only to certain conforming types.

```swift
extension Collection where Element: Equatable {
    func hasDuplicates() -> Bool {
        return Set(self).count != self.count
    }
}
```

---
