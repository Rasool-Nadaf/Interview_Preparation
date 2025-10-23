# 🧠 Swift — Methods

---

## 1️⃣ What are methods in Swift?
Methods are **functions inside a class, struct, or enum**.  
They perform actions related to that type.

```swift
struct Car {
    func start() {
        print("Car started")
    }
}
Car().start()
```

---

## 2️⃣ Types of methods
1. **Instance methods** — Work on one object.  
2. **Type methods** — Belong to the type, not instance.  
3. **Mutating methods** — Modify struct/enum properties.

---

## 3️⃣ Instance method example
```swift
class Dog {
    func bark() {
        print("Woof!")
    }
}
let dog = Dog()
dog.bark()
```

---

## 4️⃣ Mutating method example
Used in structs/enums to modify properties.

```swift
struct Counter {
    var count = 0
    mutating func increment() {
        count += 1
    }
}
```

---

## 5️⃣ Why 'mutating'?
Because **structs/enums** are **value types**, any change modifies the whole instance.

---

## 6️⃣ Type methods (static / class)
Used for behavior shared by all instances.

```swift
struct Math {
    static func square(of number: Int) -> Int {
        number * number
    }
}
print(Math.square(of: 4))
```

---

## 7️⃣ Difference between static and class
| static | class |
|--------|--------|
| Can’t be overridden | Can be overridden (only in classes) |

---

## 8️⃣ Using 'self'
`self` refers to the current instance.

```swift
struct Student {
    var name: String
    func show() {
        print(self.name)
    }
}
```

---

## 9️⃣ Method parameters & return values
```swift
func add(a: Int, b: Int) -> Int {
    a + b
}
```

---

## 🔟 Default parameter values
```swift
func greet(name: String = "Guest") {
    print("Hello, \(name)")
}
greet() // Hello, Guest
```

---

## 11️⃣ Method overloading
Same name, different parameters.

```swift
func printData(_ value: Int) {}
func printData(_ value: String) {}
```

---

## 12️⃣ Internal vs External names
```swift
func greet(person name: String) {
    print("Hello \(name)")
}
greet(person: "Rasool")
```

---

## 13️⃣ Methods in enums
```swift
enum Light {
    case on, off
    func toggle() -> Light {
        self == .on ? .off : .on
    }
}
```

---

## 14️⃣ Real-world example
```swift
struct Account {
    var balance = 0.0
    mutating func deposit(_ amount: Double) { balance += amount }
    mutating func withdraw(_ amount: Double) { balance -= amount }
    func showBalance() { print(balance) }
}
```

---

## 15️⃣ Summary
| Type | Keyword | Used In | Purpose |
|------|----------|----------|----------|
| Instance | none | Class/Struct | Work on instance |
| Mutating | mutating | Struct/Enum | Modify value types |
| Type | static/class | Class/Struct | Work on the type itself |
