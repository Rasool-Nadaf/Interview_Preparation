# ⚡ Swift Interview Prep — Functions

---

### 1️⃣ What is a function in Swift?
A function is a **block of code** that performs a specific task and can be reused.

```swift
func greet() {
    print("Hello Swift!")
}
greet()
```

---

### 2️⃣ What are the types of functions in Swift?
✅ No parameter, no return  
✅ With parameter  
✅ With return type  
✅ Multiple return values (tuples)  
✅ Nested functions  
✅ Functions with default or variadic parameters  

---

### 3️⃣ How to define and call a function?
```swift
func add(a: Int, b: Int) -> Int {
    return a + b
}
print(add(a: 2, b: 3)) // 5
```

---

### 4️⃣ What is function signature?
It’s the **function name + parameter types + return type**.

---

### 5️⃣ What is a return type?
The data type a function returns after execution.  
If nothing is returned → `Void` or `()`.

---

### 6️⃣ What is a parameter vs argument?
- **Parameter** → variable inside function.  
- **Argument** → actual value passed.

```swift
func square(of number: Int) -> Int { number * number }
square(of: 4) // 4 is argument
```

---

### 7️⃣ What are external and internal parameter names?
External names used when calling, internal names used inside.

```swift
func multiply(_ a: Int, by b: Int) -> Int {
    return a * b
}
multiply(5, by: 2)
```

`_` hides external name.

---

### 8️⃣ What is default parameter?
You can assign default values to parameters.

```swift
func greet(name: String = "User") {
    print("Hello, \(name)")
}
greet() // Hello, User
```

---

### 9️⃣ What is variadic parameter?
It accepts multiple values of the same type.

```swift
func sum(_ numbers: Int...) -> Int {
    numbers.reduce(0, +)
}
sum(1,2,3,4) // 10
```

---

### 🔟 What is an inout parameter?
Allows a function to modify the argument’s actual value.

```swift
func swapValues(a: inout Int, b: inout Int) {
    let temp = a; a = b; b = temp
}
var x = 10, y = 20
swapValues(a: &x, b: &y)
```

---

### 11️⃣ What are nested functions?
Functions defined inside another function.  
Used to hide logic and improve readability.

```swift
func outer() {
    func inner() { print("Inner") }
    inner()
}
outer()
```

---

### 12️⃣ What are function types?
A function can be treated as a **value** and assigned to variables.

```swift
func add(a: Int, b: Int) -> Int { a + b }
let mathOperation: (Int, Int) -> Int = add
print(mathOperation(3,4)) // 7
```

---

### 13️⃣ What are higher-order functions?
Functions that **take functions as parameters** or **return functions**.  
Examples: `map`, `filter`, `reduce`.

---

### 14️⃣ What is recursion?
When a function **calls itself**.  
Must have a base case to stop.

```swift
func factorial(_ n: Int) -> Int {
    n == 0 ? 1 : n * factorial(n - 1)
}
```

---

### 15️⃣ What are closures in relation to functions?
Closures are **unnamed (anonymous) functions** — lightweight, can capture values.

---

### 16️⃣ What’s the difference between function and closure?
| Function | Closure |
|-----------|----------|
| Has name | Anonymous |
| Uses `func` keyword | Uses `{}` syntax |
| Doesn’t capture values | Captures from surrounding scope |

---

### 17️⃣ What is function overloading?
Multiple functions with **same name** but **different parameter types/count**.

```swift
func display(_ n: Int) { print("Int") }
func display(_ s: String) { print("String") }
display(5) // Int
```

---

### 18️⃣ Can we return multiple values from a function?
✅ Yes, using **tuples**.

```swift
func minMax(numbers: [Int]) -> (min: Int, max: Int) {
    (numbers.min()!, numbers.max()!)
}
```

---

### 19️⃣ What is function composition?
Combining multiple functions to form new behavior.

---

### 20️⃣ Why are functions important in Swift?
They make code:  
✅ Reusable  
✅ Organized  
✅ Testable  
✅ Easier to maintain  
