# 🧠 Swift — Properties 

---

## 1️⃣ What are properties in Swift?
Properties are **variables or constants** that store values inside a **class, struct, or enum**.

```swift
struct Person {
    var name: String
    let age: Int
}
```

---

## 2️⃣ Types of properties
1. **Stored properties** — store constant or variable values.  
2. **Computed properties** — calculate value instead of storing it.  
3. **Lazy stored properties** — created only when first accessed.  
4. **Type properties (static)** — belong to the type, not instance.  
5. **Property observers** — observe changes (willSet, didSet).

---

## 3️⃣ Stored property example
```swift
struct Car {
    var brand = "Tesla"
}
var myCar = Car()
myCar.brand = "BMW"
```

---

## 4️⃣ Computed property example
```swift
struct Circle {
    var radius: Double
    var area: Double {
        return 3.14 * radius * radius
    }
}
```

---

## 5️⃣ Lazy stored property example
Used when initialization is expensive or unnecessary until used.
```swift
class DataLoader {
    lazy var fileData = loadData()
    func loadData() -> String { "Data Loaded" }
}
```

---

## 6️⃣ Property observers (willSet & didSet)
Run code when a property value changes.

```swift
var temperature: Int = 25 {
    willSet { print("Will set to \(newValue)") }
    didSet { print("Changed from \(oldValue)") }
}
```

---

## 7️⃣ Type properties (static & class)
Used for values common to all instances.

```swift
struct Math {
    static let pi = 3.14159
}
print(Math.pi)
```

---

## 8️⃣ Difference between stored & computed
| Stored | Computed |
|--------|-----------|
| Stores actual data | Calculates on access |
| Has memory | No memory used for value |

---

## 9️⃣ Why use lazy properties?
- Delay costly initialization.  
- Used when property depends on external data.  

---

## 🔟 Difference between static & class properties
| static | class |
|--------|--------|
| Can’t be overridden | Can be overridden (only in classes) |

---

## 11️⃣ Can enums have properties?
✅ Yes, **computed** or **type**, but ❌ no stored properties.

---

## 12️⃣ Real-world example (computed + observer)
```swift
struct Account {
    var balance: Double {
        willSet { print("About to change balance") }
        didSet { print("Balance updated") }
    }
    var interest: Double {
        return balance * 0.05
    }
}
```
