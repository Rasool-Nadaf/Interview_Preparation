# Swift Interview Prep – Class, Struct, Actor
---

## 🔹 General Questions
1. **What is a class in Swift?**
   - A **reference type** that supports inheritance, ARC, and shared instances.

2. **What is a struct in Swift?**
   - A **value type** that copies data when assigned, lightweight, no inheritance.

3. **What is an actor in Swift?**
   - A **reference type** designed for **safe concurrency** (thread-safe by default).

4. **Difference between class and struct?**
   - Class = reference type, inheritance, ARC, deinit.
   - Struct = value type, no inheritance, faster.

5. **Difference between class and actor?**
   - Both are reference types.
   - Class → not thread-safe, Actor → thread-safe by default.

6. **Difference between struct and actor?**
   - Struct = value type (copied).
   - Actor = reference type (shared, but safe in concurrency).

7. **When to choose struct over class?**
   - When modeling small, immutable data → safer & faster.

8. **When to choose class over struct?**
   - When you need inheritance, shared instances, or ARC cleanup.

9. **When to choose actor?**
   - When data is accessed by multiple concurrent tasks.

10. **Can struct inherit from another struct or class? Why not?**
   - ❌ No. Structs don’t support inheritance → to keep them lightweight.

11. **Can a class inherit from another class?**
   - ✅ Yes. Classes support single inheritance.

12. **Can actors inherit?**
   - ❌ No, only conform to protocols.

13. **What is meant by reference type vs value type?**
   - Reference → shared instance (class/actor).
   - Value → copied on assignment (struct/enum).

14. **What happens when you assign one struct to another?**
   - A new copy is made.

15. **What happens when you assign one class instance to another?**
   - Both point to the same object.

16. **Do actors behave like reference type or value type?**
   - Reference type.

17. **Can you use deinit in class? Struct? Actor?**
   - Class ✅, Actor ✅, Struct ❌.

18. **Do structs have initializers by default?**
   - ✅ Yes (memberwise initializer).

19. **Why are structs considered lightweight?**
   - Stored in stack, no ARC overhead, copied easily.

20. **What is copy-on-write in structs?**
   - Optimization → actual copy is made **only when modified**.

---

## 🔹 Class-specific
21. **What is reference semantics?**
   - Multiple vars point to same instance.

22. **How memory is managed for classes?**
   - Using ARC (Automatic Reference Counting).

23. **Do classes support inheritance?**
   - ✅ Yes.

24. **Can classes conform to protocols?**
   - ✅ Yes.

25. **Do classes have deinitializers? Why?**
   - ✅ Yes, to clean up resources when instance is deallocated.

26. **Can classes be used with ARC?**
   - ✅ Yes, ARC tracks class instances.

27. **What is strong, weak, and unowned reference?**
   - Strong → increases ARC count.
   - Weak → no ownership, optional.
   - Unowned → no ownership, non-optional.

28. **What is retain cycle? How to avoid it?**
   - Two objects strongly reference each other → memory leak.
   - Fix with `weak` or `unowned`.

29. **Why are classes slower than structs sometimes?**
   - Heap allocation + ARC overhead.

30. **Example where class is better than struct?**
   - `UIViewController`, `DatabaseManager` (shared, lifecycle management).

---

## 🔹 Struct-specific
31. **What is value semantics?**
   - Each variable owns its own copy.

32. **How memory is managed for structs?**
   - Usually on stack, copied when passed/assigned.

33. **Why structs are preferred in Swift?**
   - Safer, faster, no ARC overhead.

34. **Can structs conform to protocols?**
   - ✅ Yes.

35. **Can structs have methods?**
   - ✅ Yes.

36. **Can structs have mutating functions? Why?**
   - ✅ Yes, needed because structs are immutable by default.

37. **Do structs have inheritance?**
   - ❌ No.

38. **Can you extend a struct?**
   - ✅ Yes, with extensions.

39. **Can structs have computed properties?**
   - ✅ Yes.

40. **Example where struct is better than class?**
   - `Point`, `Rectangle`, `User` data model.

---

## 🔹 Actor-specific
41. **What is concurrency in Swift?**
   - Running multiple tasks without blocking main thread.

42. **Why were actors introduced in Swift 5.5?**
   - To provide built-in thread-safe shared state.

43. **What problem do actors solve?**
   - Race conditions, data corruption in multi-threading.

44. **How are actors different from classes?**
   - Actor = safe for concurrent access, Class = not safe by default.

45. **Can actors conform to protocols?**
   - ✅ Yes.

46. **How do you call an actor method?**
   - Using `await` → `await actor.method()`.

47. **What is actor isolation?**
   - Only one task can access actor’s mutable state at a time.

48. **Can actors share state across tasks safely?**
   - ✅ Yes.

49. **Do actors support inheritance?**
   - ❌ No.

50. **Example where actor is better than class?**
   - `ChatManager`, `BankAccount` (shared across threads).

---

## 🔹 Scenario / Trick
51. **If you copy a struct and change the copy, will the original change?**
   - ❌ No.

52. **If you copy a class reference and change the copy, will the original change?**
   - ✅ Yes.

53. **If multiple tasks call an actor’s method at the same time, what happens?**
   - They are executed **one at a time** safely.

54. **Can actors cause deadlocks?**
   - Rare, only if tasks await each other incorrectly.

55. **Can you make a struct thread-safe without actors?**
   - ✅ Yes, using locks/queues (but manual effort).

56. **Is `String` a class or struct in Swift? Why?**
   - Struct (value type, copy-on-write, fast).

57. **Why does Swift standard library prefer structs (like Array, Dictionary)?**
   - Safer (no shared mutation), copy-on-write optimization.

58. **If performance is a concern, which is better: struct or class?**
   - Struct (most of the time), unless large shared state is needed.

59. **Can you store a struct inside a class? Vice versa?**
   - ✅ Yes, both ways possible.

60. **How does ARC differ for class and actor?**
   - Both use ARC, but actor also has task isolation for concurrency.

---

