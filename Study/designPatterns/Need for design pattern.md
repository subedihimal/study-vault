Design patterns solve maintainability & readability issues, NOT performance/scalability

**The Problem**

Creating objects with multiple attributes (firstName, lastName, age, email, password) and complex validations across 2+ attributes while keeping code clean and maintainable.

**Evolution of Solutions**

**Attempt 1: Public Fields**
```java
public class User {
    String firstName;
    String lastName;
    int age;
}
```
Issue: Anyone can set invalid values
```java
User u = new User();
u.firstName = ""; // No validation!
```

**Attempt 2: Getters/Setters**

Issues:
- Object exists with empty values between creation and setter calls
- Violates validation requirements
- Doesn't work for immutable types

**Attempt 3: Constructor with Validation**

Issues:
- Hard to remember parameter order
- Adding new parameters breaks existing code
- Must pass null for optional fields
- Need hundreds of constructors for different combinations
- Client code becomes unreadable and error-prone

**Attempt 4: HashMap/Dictionary**

Pass unordered key-value pairs: HashMap (Java), unordered_map (C++), dict (Python), object (JavaScript)

Still not ideal for type safety

**Solution: Builder Pattern**

Key Principles:
- Builder class handles object construction
- Setter-based validation in builder (not constructor)
- Builder is temporary so validation failures acceptable before final build
- User constructor stays simple (no validation code)
- Static nested class for access control

Structure:
```java
public class User {
    // Private constructor
    private User(Builder builder) {
        this.firstName = builder.firstName;
        // ...
    }
    
    // Static Builder class
    public static class Builder {
        private String firstName;
        
        public Builder setFirstName(String name) {
            if (name.isEmpty()) throw new Error();
            this.firstName = name;
            return this;
        }
        
        public User build() {
            return new User(this);
        }
    }
}
```

Why It Works:
- Readable: `new User.Builder().setFirstName("John").setAge(25).build()`
- Flexible: Optional parameters easily omitted
- Validated: Each setter checks constraints
- Maintainable: Easy to add new fields
- Type-safe: Unlike HashMap approach