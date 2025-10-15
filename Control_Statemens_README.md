# 🧠 Swift Control Statements 

## 🔹 1. What are control statements in Swift?
Control statements manage the flow of program execution based on conditions and loops.

**Types:**
- Conditional: `if`, `if-else`, `switch`
- Looping: `for-in`, `while`, `repeat-while`
- Transfer: `break`, `continue`, `fallthrough`, `guard`, `return`

---

## 🔹 2. Explain if, else if, and else with example.
```swift
let marks = 85
if marks >= 90 {
    print("Grade A+")
} else if marks >= 75 {
    print("Grade A")
} else {
    print("Needs Improvement")
}
```

---

## 🔹 3. Explain switch statement with example.
```swift
let day = 3
switch day {
case 1: print("Monday")
case 2: print("Tuesday")
case 3: print("Wednesday")
default: print("Invalid Day")
}
```

✅ `switch` must be exhaustive (cover all cases or include `default`).

---

## 🔹 4. What is fallthrough in Swift?
It continues execution to the next case explicitly.

```swift
let num = 2
switch num {
case 1:
    print("One")
case 2:
    print("Two")
    fallthrough
case 3:
    print("Three")
default:
    print("Other")
}
```
🧠 Output:
```
Two
Three
```

---

## 🔹 5. Difference between while and repeat-while loops
| Feature | while | repeat-while |
|----------|--------|--------------|
| Condition Check | Before loop | After loop |
| Executes | 0 or more times | At least once |

```swift
var count = 1
while count <= 3 {
    print(count)
    count += 1
}

var n = 1
repeat {
    print(n)
    n += 1
} while n <= 3
```

---

## 🔹 6. Explain break and continue with example.
```swift
for i in 1...5 {
    if i == 3 { continue }
    if i == 5 { break }
    print(i)
}
```
🧠 Output: 1, 2, 4

---

## 🔹 7. What is guard statement?
Used for early exit when condition fails.

```swift
func login(user: String?) {
    guard let name = user else {
        print("No username provided")
        return
    }
    print("Welcome, \(name)")
}
login(user: nil)
```

🧠 Output: `No username provided`

---

## 🔹 8. Difference between if-let and guard-let
| Feature | if-let | guard-let |
|----------|---------|-----------|
| Purpose | Optional binding | Early exit |
| Scope | Inside block | Outside block |
| Readability | Nested | Clean |

```swift
// if-let
if let name = userName {
    print("Hello, \(name)")
}

// guard-let
guard let name = userName else { return }
print("Hello, \(name)")
```

---

## 🔹 10. Why switch doesn’t fall through by default?
To prevent unintentional execution of multiple cases and improve code safety.
