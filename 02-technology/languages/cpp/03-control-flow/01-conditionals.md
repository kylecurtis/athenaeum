# Conditional Statements

Conditional statements allow a program to execute different blocks of code depending on whether a specified condition is true or false.

<br>

---

<br>

## If Statement Syntax

**`if`**: Executes a block of code if its condition is true.
 
```cpp
if (condition) {
    // Execute if condition is true
}
```

<br>

#### Key points:

- `condition` must evaluate to a boolean or be convertible to bool
- Braces are optional for single statements but always recommended
- Zero, null pointers, and empty containers evaluate to false

<br>

---

<br>

## Else If Syntax

- **`else if`**: If the preceding `if` (or `else if`) condition is false, this next condition is tested. 
- You can chain multiple `else if` blocks.

- **`else`**: If all preceding conditions are false, the `else` block is executed. It's a catch-all and is optional.

```cpp
if (condition1) {
    // Execute if condition1 is true
} else if (condition2) {
    // Execute if condition1 is false and condition2 is true
} else {
    // Execute if all previous conditions are false
}
```

<br>

---

<br>

## Initialization If Statements (C++17)

```cpp
if (int result = expensive_calculation(); result > threshold) {
    // Use result here
    std::cout << "Result: " << result << std::endl;
}
// result is out of scope here
```

<br>

---

<br>

#### Full Example

```cpp
int score = 85;

if (score >= 90) {
    std::cout << "Grade: A" << std::endl;
} else if (score >= 80) {
    std::cout << "Grade: B" << std::endl; // This block will execute
} else if (score >= 70) {
    std::cout << "Grade: C" << std::endl;
} else {
    std::cout << "Grade: D or F" << std::endl;
}
```

<br>

---

<br>

## The Switch Statement

A `switch` statement is a specialized conditional that compares a single variable against a list of constant integer-type values (`int`, `char`, `enum`, etc.). It's often cleaner than a long chain of `if-else if` statements.


#### Switch Limitations and Requirements

- **Expression must be integral**: `int`, `char`, `enum`, not `float` or `string`
- **Case labels must be compile-time constants**
- **No duplicate case values**
- **Fall-through requires explicit `break`**

<br>

---

<br>

## Switch Statement Syntax

```cpp
switch (expression) {
    case constant1:
        // Execute for constant1
        break;
    case constant2:
        // Execute for constant2
        break;
    default:
        // Execute if no case matches
        break;
}
```

<br>

#### Key Points:

- **`case`**: Each `case` label represents a value to compare against.
- **`break`**: This is crucial. It exits the `switch` block. Without it, execution "falls through" to the next `case`.
- **`default`**: Similar to `else`, this block runs if no other `case` matches. It is optional.

<br>

---

<br>

####  Full Example

```cpp
int day_code = 3;
std::string day_name;

switch (day_code) {
    case 1:
        day_name = "Monday";
        break;
    case 2:
        day_name = "Tuesday";
        break;
    case 3:
        day_name = "Wednesday"; // This case matches
        break; // Execution stops here
    case 4:
        day_name = "Thursday";
        break;
    // ... cases for 5, 6, 7
    default:
        day_name = "Invalid day";
        break;
}
// day_name is now "Wednesday"
```

<br>

---

<br>

## Fallthrough Behavior 

Omitting `break` is sometimes done intentionally.

```cpp
char letter = 'b';
switch (letter) {
    case 'a':
    case 'e':
    case 'i':
    case 'o':
    case 'u':
        std::cout << "Vowel" << std::endl;
        break;
    default:
        std::cout << "Consonant" << std::endl;
}
```

<br>

---

<br>


## Switch with initialization

Since C++17

```cpp
switch (int value = get_value(); value) {
    case 1:
        process_one(value);
        break;
    case 2:
        process_two(value);
        break;
}
```

<br>

---

<br>

## The Ternary Operator (?:)

The conditional (or ternary) operator is a compact, one-line expression that functions like a simple `if-else` statement. It's used to decide which of two values a single expression should evaluate to.

<br>

**Syntax**: 

```cpp
condition ? expression_if_true : expression_if_false;
```

<br>

#### Example

```cpp
int a = 10;
int b = 20;

// Using if-else
int max_val;
if (a > b) {
    max_val = a;
} else {
    max_val = b;
}

// Using the ternary operator (more concise)
int max_val_ternary = (a > b) ? a : b; // max_val_ternary will be 20
```