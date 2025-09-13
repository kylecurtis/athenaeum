# Integer Types

Integer types in C++ are fundamental data types that represent whole numbers.

<br>

---

<br>

## The Basic Signed Integer Types

These are the standard integer types whose exact sizes can vary slightly by platform.

<br>

### Integer Range Formulas

Where $n$ is the number of bits.

**Signed Integer**:  $-2^{n -1}$  to $2^{n - 1} - 1$
**Unsigned Integer**: $0$ to $2^{n} -1$

<br>

### short (short int)

- **Purpose**: Smallest integer type, optimized for memory conservation
- **Size**: At least 16 bits (2 bytes)
- **Typical range**: -32,768 to 32,767 (assuming 16-bit)

### int

- **Purpose**: The "natural" integer size for the target architecture, offering optimal performance
- **Size**: At least 16 bits, typically 32 bits on modern systems
- **Typical range**: -2,147,483,648 to 2,147,483,647 (assuming 32-bit)
- **Key point**: Usually matches the processor's word size for optimal performance

### long (long int)

- **Purpose**: An integer with an extended range
- **Size**: At least 32 bits
**Platform Variation**: Famously inconsistent. It's 32 bits on 64-bit Windows but 64 bits on 64-bit Linux and macOS. This ambiguity is why fixed-width integers are often preferred
- **Typical ranges**:
    - 32-bit: -2,147,483,648 to 2,147,483,647
    - 64-bit: -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807

### long long (long long int)

- **Purpose**: Maximum standard integer precision, introduced in C++11 to guarantee a large integer type
- **Size**: At least 64 bits
- **Range**: -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807

<br>

---

<br>

## Unsigned Variants

Each integer type has an `unsigned` counterpart. By removing the sign bit, the entire range of bits is used for positive values, doubling the maximum value

- `unsigned short` → 0 to 65,535 (16-bit)
- `unsigned int` → 0 to 4,294,967,295 (32-bit)
- `unsigned long` → Platform dependent
- `unsigned long long` → 0 to 18,446,744,073,709,551,615 (64-bit)

<br>

---

<br>

## Binary Representation and Two's Complement

Computers use a system called **two's complement** to represent signed integers. The most significant bit (MSB) acts as the sign bit (0 for positive, 1 for negative). This design simplifies the CPU's hardware because addition and subtraction algorithms work uniformly for both positive and negative numbers.

**Signed Integers** use two's complement representation:

- Most significant bit (MSB) is the sign bit
- **Positive numbers**: standard binary
- **Negative numbers**: invert all bits and add 1

|Integer|Binary (Two's Complement)|Notes|
|:---:|:---:|:---|
|`127`|`01111111`|Max positive value. The sign bit is `0`.|
|`1`|`00000001`||
|`0`|`00000000`|A single, unambiguous representation for zero.|
|`-1`|`11111111`|To get -1 from 1: Invert `00000001` to `11111110`, then add 1.|
|`-128`|`10000000`|Min negative value. The sign bit is `1`.|

<br>

### Advantages of Two's Complement

- Single representation for zero
- Addition / Subtraction algorithms work uniformly
- Hardware implementation is simpler

<br>

---

<br>

## Memory Layout: Endianness

**Endianness** refers to the order in which bytes of a multi-byte data type are stored in computer memory. This is critical when transferring data between systems, such as over a network or through binary files.

- **Little-endian**: The least significant byte is stored first (at the lowest memory address). This is used by most common architectures, like x86/x64 (Intel, AMD).
    
- **Big-endian**: The most significant byte is stored first. This is common in networking (often called "network byte order") and older systems.

<br>

### Expanded Example

Storing `0x01020304` (a 32-bit integer)

Let's assume the memory address starts at `100`.

|Endianness|Address 100|Address 101|Address 102|Address 103|
|---|---|---|---|---|
|**Little-endian**|`04`|`03`|`02`|`01`|
|**Big-endian**|`01`|`02`|`03`|`04`|

A C++ programmer must be aware of this when, for example, reading a binary file created on a big-endian system while running code on a little-endian machine. You would need to reverse the byte order to interpret the number correctly.

<br>

---

<br>

## Size Guarantees and Platform Considerations

<br>

The C++ Standard guarantees:

```cpp
sizeof(char) <= sizeof(short) <= sizeof(int) <= sizeof(long) <= sizeof(long long)

// Minimum Sizes:
// char: 8 bits (1 byte)
// short: 16 bits (2 bytes)
// int: 16 bits (2 bytes)
// long: 32 bits (4 bytes)
// long long: 64 bits (8 bytes)
```

### Checking Sizes at Runtime
```cpp
#include <iostream>
#include <climits>

int main() {
    std::cout << "short: " << sizeof(short) << " bytes, "
              << "range: " << SHRT_MIN << " to " << SHRT_MAX << std::endl;
    
    std::cout << "int: " << sizeof(int) << " bytes, "
              << "range: " << INT_MIN << " to " << INT_MAX << std::endl;
    
    std::cout << "long: " << sizeof(long) << " bytes, "
              << "range: " << LONG_MIN << " to " << LONG_MAX << std::endl;
    
    std::cout << "long long: " << sizeof(long long) << " bytes, "
              << "range: " << LLONG_MIN << " to " << LLONG_MAX << std::endl;
}
```

<br>

---

<br>

## Overflow Behavior

<br>

### Signed Integer Overflow

- **Undefined behavior** in C++
- Common implementations wrap around, but not guaranteed
- Can lead to security vulnerabilities and unpredictable results

```cpp
int max_int = INT_MAX;
int overflow = max_int + 1; // undefined behavior
```

<br>

### Unsigned Integer Overflow

- **Well-defined behavior**: wraps around (modular arithmetic)
- Follows modulo 2^n arithmetic

```cpp
unsigned int max_uint = UINT_MAX;
unsigned int wrap = max_uint + 1; // Guaranteed to be 0
```

<br>

---

<br>

## Type Conversions and Integer Promotion

<br>

### Integer Promotion Rules

- `char` -> `int` (if int can represent all values)
- `short` -> `int` (if int can represent all values)
- Otherwise -> `unsigned int`

<br>

### Usual Arithmetic Conversions

When mixing signed and unsigned types:

- If both are signed or both unsigned -> promote to larger type
- If unsigned type rank >= signed type rank -> convert to unsigned
- Otherwise -> convert to signed (if it can represent all values)

```cpp
int a = -1;
unsigned int b = 1;

if (a < b) {  
	// False! a converts to large unsigned value
    std::cout << "This won't print" << std::endl;
}
```

<br>

---

<br>

## Hardware and Performance Considerations

Choosing the right integer type and organizing your data correctly can have a massive impact on performance. This is because modern CPUs use sophisticated hardware features like caching, vectorization, and branch prediction to execute code faster. Writing code that "plays nice" with these features is key to high performance.

<br>

### Cache Line Effects

**The Concept**: Modern CPUs do not read memory one byte at a time. To save time, they pull data from the slow main memory (RAM) into a small, extremely fast local memory called the **CPU cache**. They do this in fixed-size chunks called **cache lines**, which are typically 64 bytes on modern processors. Accessing data that is already in the cache is hundreds of times faster than fetching it from RAM.

**Relevance to Integers**: When you lay out your data in a contiguous block, like in an array or a `std::vector`, you maximize the chance of cache hits.

#### Cache-Friendly (Good)

```cpp
// A 16-integer array is 16 * 4 = 64 bytes.
int scores[16]; // It fits perfectly into one cache line.

long long total = 0;
for (int i = 0; i < 16; ++i) {
	total += scores[i]; // The first access pulls all 16 scores into the cache.
	                    // The next 15 accesses are lightning fast.
}
```

#### Cache-Unfriendly (Bad)

Data structures like linked lists, where each node can be in a completely different part of memory, often lead to a cache miss for every single element accessed, making them much slower for sequential iteration.

- Modern CPUs have 64-byte cache lines
- Accessing nearby memory locations is faster
- Consider data layout for performance-critical code

<br>

### SIMD and Vectorization

**SIMD** stands for **Single Instruction, Multiple Data**. It's a hardware feature that allows a single CPU instruction to perform the exact same operation on multiple pieces of data simultaneously. Modern CPUs have special wide registers (128, 256, or even 512 bits) for this purpose.

- Modern processors can operate on multiple integers simultaneously
- Compiler auto-vectorization works better with certain patterns
- Consider `int32_t` arrays for SIMD optimization

<br>

### Branch Prediction

- Conditional operations on integers affect CPU branch prediction
- Predictable patterns (like sorted data) perform better

