# Swift Closures 

## 🧠 Closure in Swift

A **closure** is a self-contained block of code that can be passed and
used in your code. It can capture and store references to variables and
constants from its surrounding context.

### Example

``` swift
let greet = { (name: String) -> String in
    return "Hello, \(name)!"
}
print(greet("Rasool"))  // Output: Hello, Rasool!
```

------------------------------------------------------------------------

## ⚙️ Types of Closures

1.  Global Closures -- defined outside any function, don't capture
    values.
2.  Nested Closures -- inside a function, can capture values.
3.  Closure Expressions -- short, inline closures (most common).

------------------------------------------------------------------------

## 🧩 Closure Syntax

``` swift
{ (parameters) -> returnType in
    // code
}
```

### Example

``` swift
let add = { (a: Int, b: Int) -> Int in
    return a + b
}
print(add(3, 4))  // Output: 7
```

------------------------------------------------------------------------

## 🪄 Shortened Syntax

  Version                    Example                                         Notes
  -------------------------- ----------------------------------------------- -----------------------
  Full syntax                `{ (a: Int, b: Int) -> Int in return a + b }`   Normal
  Type inferred              `{ a, b in return a + b }`                      Type auto-detected
  Implicit return            `{ a, b in a + b }`                             For single expression
  Shorthand argument names   `{ $0 + $1 }`                                   Shortest form

------------------------------------------------------------------------

## 🔁 Closures as Function Parameters

``` swift
let numbers = [5, 2, 8, 1]
let sorted = numbers.sorted { $0 < $1 }
print(sorted)  // [1, 2, 5, 8]
```

------------------------------------------------------------------------

## 🧠 Capturing Values

``` swift
func makeCounter() -> () -> Int {
    var count = 0
    return {
        count += 1
        return count
    }
}
let counter = makeCounter()
print(counter())  // 1
print(counter())  // 2
```

------------------------------------------------------------------------

## 🚫 Escaping Closures

``` swift
var handlers: [() -> Void] = []

func storeHandler(_ handler: @escaping () -> Void) {
    handlers.append(handler)
}
```

------------------------------------------------------------------------

## 🧱 Autoclosures

``` swift
func log(_ message: @autoclosure () -> String) {
    print("Log:", message())
}
log("Error found!")
```

------------------------------------------------------------------------

### 1. What is a closure in Swift?

A closure is a block of code that can be passed, stored, and executed
later. It can capture values from its surrounding context.

### 2. How is a closure different from a function?

-   Functions have names; closures can be anonymous.
-   Functions don't capture variables; closures can.
-   Closures are short and inline.

### 3. What does "capturing values" mean?

Closures can remember and modify variables from their environment.

### 4. What are escaping and non-escaping closures?

-   **Non-escaping:** Runs within the function call.
-   **Escaping:** Stored and called after the function ends
    (`@escaping`).

### 5. When do you use `@escaping`?

When the closure is stored or used asynchronously.

### 6. What is a trailing closure?

When a closure is the last argument, written outside parentheses.

### 7. What is an autoclosure?

Automatically created closure that delays evaluation.

### 8. Example of closure capturing

``` swift
func makeIncrementer() -> () -> Int {
    var value = 0
    return {
        value += 1
        return value
    }
}
```

### 9. Can closures cause memory leaks?

Yes, if a closure captures `self` strongly. Use `[weak self]` or
`[unowned self]`.

### 10. What are shorthand argument names?

Swift provides `$0`, `$1`, etc. for arguments.

### 11. When should you use closures?

-   For callbacks or completion handlers
-   For async tasks or data processing

### 12. Can you store closures?

Yes, closures are reference types and can be stored in arrays or
properties.

### 13. Are closures reference or value types?

Closures are **reference types**.

### 14. What happens if you capture a variable?

Swift keeps a reference --- changes inside the closure affect the
variable.

### 15. Difference in performance between escaping and non-escaping closures?

Non-escaping closures are faster since they don't escape the function's
scope.

------------------------------------------------------------------------


