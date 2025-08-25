# C++ Expert Course: From Fundamentals to Professional Development

## Part I: Foundations and Core Language

### Chapter 1: Development Environment and Toolchain

- 1.1 Setting up development environments (Visual Studio, VS Code, CLion, Vim/Emacs)
- 1.2 Compilers: GCC, Clang, MSVC differences and flags
- 1.3 Build systems: Make, CMake, Bazel, Ninja
- 1.4 Debuggers: GDB, LLDB, Visual Studio Debugger
- 1.5 Static analyzers and sanitizers (AddressSanitizer, ThreadSanitizer, Valgrind)
- 1.6 Version control integration with Git
- 1.7 Continuous Integration basics for C++

### Chapter 2: C++ Fundamentals and Type System

- 2.1 Program structure: main function, compilation units, headers vs implementation
- 2.2 Fundamental types
    - Integer types: char, short, int, long, long long
    - Unsigned variants and size guarantees
    - Floating-point: float, double, long double
    - Boolean type and nullptr
    - void type and void pointers
    - auto and decltype
- 2.3 Type qualifiers
    - const correctness and const propagation
    - volatile keyword and use cases
    - mutable members
    - constexpr and compile-time computation
- 2.4 References vs Pointers
    - Lvalue references
    - Rvalue references (C++11)
    - Reference collapsing rules
    - Pointer arithmetic and array decay
- 2.5 Type conversions
    - Implicit conversions and conversion rank
    - static_cast, dynamic_cast, const_cast, reinterpret_cast
    - C-style casts and why to avoid them

### Chapter 3: Control Flow and Functions

- 3.1 Conditional statements: if, switch, ternary operator
- 3.2 Loops: for, while, do-while, range-based for (C++11)
- 3.3 Function fundamentals
    - Function overloading and name mangling
    - Default arguments
    - Inline functions and inline variables (C++17)
    - Function pointers and std::function
- 3.4 Parameter passing strategies
    - Pass by value, reference, const reference
    - Perfect forwarding (C++11)
    - Return value optimization (RVO/NRVO)
- 3.5 Lambda expressions (C++11/14/17/20)
    - Capture modes: by value, by reference, generalized capture
    - Generic lambdas (C++14)
    - constexpr lambdas (C++17)
    - Template lambdas (C++20)

### Chapter 4: Object-Oriented Programming

- 4.1 Classes and structs
    - Member variables and member functions
    - Access specifiers: public, private, protected
    - Friend functions and classes
    - Nested classes and local classes
- 4.2 Constructors and destructors
    - Default constructor
    - Parameterized constructors
    - Copy constructor and copy assignment
    - Move constructor and move assignment (C++11)
    - Delegating constructors (C++11)
    - Explicit constructors
    - Virtual destructors
- 4.3 The Rule of Three/Five/Zero
- 4.4 Operator overloading
    - Arithmetic, comparison, and logical operators
    - Stream operators
    - Function call operator
    - Conversion operators
    - Spaceship operator (C++20)
- 4.5 Inheritance
    - Single and multiple inheritance
    - Virtual inheritance and the diamond problem
    - Public, protected, private inheritance
    - Using declarations and access changes
- 4.6 Polymorphism
    - Virtual functions and vtables
    - Pure virtual functions and abstract classes
    - Override and final specifiers (C++11)
    - Virtual function overhead and alternatives

## Part II: Memory Management and Performance

### Chapter 5: Memory Management

- 5.1 Stack vs Heap memory
    - Stack allocation and automatic storage duration
    - Heap allocation and dynamic storage duration
    - Memory layout of a C++ program
- 5.2 Dynamic memory allocation
    - new and delete operators
    - Array new[] and delete[]
    - Placement new
    - nothrow new
- 5.3 Smart pointers (C++11/14/17)
    - unique_ptr: ownership and move semantics
    - shared_ptr: reference counting
    - weak_ptr: breaking circular references
    - make_unique and make_shared
    - Custom deleters
- 5.4 Memory leaks and common pitfalls
    - RAII (Resource Acquisition Is Initialization)
    - Exception safety guarantees
    - Memory fragmentation
- 5.5 Custom memory allocators
    - Overloading operator new/delete
    - Memory pools
    - Arena allocators

### Chapter 6: Templates and Generic Programming

- 6.1 Function templates
    - Template parameters and instantiation
    - Template argument deduction
    - Explicit specialization
    - Overloading vs specialization
- 6.2 Class templates
    - Template class members
    - Partial specialization
    - Template template parameters
- 6.3 Variadic templates (C++11)
    - Parameter packs
    - Pack expansion
    - Fold expressions (C++17)
- 6.4 SFINAE and type traits
    - enable_if and conditional compilation
    - Type traits library
    - void_t and detection idiom (C++17)
- 6.5 Concepts (C++20)
    - Defining concepts
    - Constraining templates
    - Requires clauses and expressions
- 6.6 Template metaprogramming basics
    - Compile-time recursion
    - constexpr if (C++17)

## Part III: Data Structures and Algorithms

### Chapter 7: Standard Library Containers

- 7.1 Sequence containers
    - array: fixed-size arrays
    - vector: dynamic arrays, capacity vs size
    - deque: double-ended queue
    - list: doubly-linked list
    - forward_list: singly-linked list
- 7.2 Associative containers
    - set/multiset: ordered unique/non-unique elements
    - map/multimap: ordered key-value pairs
    - Implementation (usually Red-Black trees)
- 7.3 Unordered containers (C++11)
    - unordered_set/unordered_multiset
    - unordered_map/unordered_multimap
    - Hash functions and collision resolution
    - Load factor and rehashing
- 7.4 Container adaptors
    - stack: LIFO operations
    - queue: FIFO operations
    - priority_queue: heap implementation
- 7.5 Container selection criteria
    - Time complexity comparisons
    - Memory overhead
    - Iterator invalidation rules
    - Cache performance considerations

### Chapter 8: Algorithms and Complexity

- 8.1 Time and space complexity
    - Big O, Omega, Theta notation
    - Best, average, worst case analysis
    - Amortized analysis
    - Space-time tradeoffs
- 8.2 STL algorithms
    - Non-modifying sequence operations (find, count, search)
    - Modifying sequence operations (copy, transform, remove)
    - Partitioning and sorting algorithms
    - Set operations
    - Heap operations
    - Min/max operations
    - Numeric algorithms
- 8.3 Parallel algorithms (C++17)
    - Execution policies
    - Parallel STL algorithms
- 8.4 Ranges library (C++20)
    - Range concepts
    - Views and view adaptors
    - Range algorithms

### Chapter 9: Core Data Structures Implementation

- 9.1 Arrays and strings
    - Dynamic array implementation
    - String optimization (SSO - Small String Optimization)
    - String algorithms (KMP, Rabin-Karp)
- 9.2 Linked lists
    - Singly linked list implementation
    - Doubly linked list implementation
    - Circular linked lists
    - XOR linked lists
- 9.3 Trees
    - Binary search tree implementation
    - AVL tree balancing
    - Red-Black tree properties
    - B-trees and B+ trees
    - Trie (prefix tree)
    - Segment trees
    - Fenwick trees (Binary Indexed Trees)
- 9.4 Heaps
    - Binary heap implementation
    - Fibonacci heap
    - Binomial heap
- 9.5 Hash tables
    - Separate chaining
    - Open addressing (linear, quadratic probing)
    - Robin Hood hashing
    - Cuckoo hashing
- 9.6 Graphs representation
    - Adjacency matrix
    - Adjacency list
    - Edge list

### Chapter 10: Essential Algorithms

- 10.1 Sorting algorithms
    - Comparison sorts: QuickSort, MergeSort, HeapSort
    - Non-comparison sorts: Counting, Radix, Bucket sort
    - Hybrid algorithms: IntroSort, TimSort
- 10.2 Searching algorithms
    - Binary search and variations
    - Ternary search
    - Exponential search
    - Interpolation search
- 10.3 Graph algorithms
    - BFS and DFS traversal
    - Dijkstra's shortest path
    - Bellman-Ford algorithm
    - Floyd-Warshall algorithm
    - A* search algorithm
    - Minimum spanning tree (Kruskal's, Prim's)
    - Topological sorting
    - Strongly connected components
    - Cycle detection
- 10.4 Dynamic programming
    - Memoization vs tabulation
    - Classic problems: Knapsack, LCS, Edit Distance
    - State space optimization
    - Bitmask DP
- 10.5 Greedy algorithms
    - Activity selection
    - Huffman coding
    - Interval scheduling
- 10.6 Divide and conquer
    - Master theorem
    - Closest pair of points
    - Karatsuba multiplication
- 10.7 String algorithms
    - Pattern matching: KMP, Z-algorithm
    - Suffix arrays and suffix trees
    - Longest common substring
    - String hashing and rolling hash

## Part IV: Modern C++ and Best Practices

### Chapter 11: Modern C++ Features

- 11.1 C++11 core features
    - Move semantics and rvalue references
    - Perfect forwarding
    - Uniform initialization
    - Range-based for loops
    - nullptr
    - Strongly-typed enums
    - Static assertions
- 11.2 C++14 enhancements
    - Generic lambdas
    - Return type deduction
    - Variable templates
    - Binary literals
- 11.3 C++17 additions
    - Structured bindings
    - If/switch with initializer
    - Inline variables
    - std::optional, std::variant, std::any
    - string_view
    - Parallel algorithms
    - Filesystem library
- 11.4 C++20 major features
    - Concepts
    - Modules
    - Coroutines basics
    - Ranges
    - Three-way comparison
    - Designated initializers
    - std::span
    - std::format
- 11.5 C++23 preview
    - std::expected
    - Multidimensional subscript operator
    - std::print

### Chapter 12: Concurrency and Multithreading

- 12.1 Thread basics
    - std::thread creation and joining
    - Thread local storage
    - std::this_thread utilities
- 12.2 Synchronization primitives
    - Mutex types: mutex, recursive_mutex, timed_mutex
    - Lock management: lock_guard, unique_lock, scoped_lock
    - Condition variables
    - Semaphores (C++20)
    - Barriers and latches (C++20)
- 12.3 Atomic operations
    - std::atomic and memory ordering
    - Lock-free programming basics
    - Compare-and-swap operations
- 12.4 High-level concurrency
    - std::async and futures
    - std::promise
    - std::packaged_task
    - Thread pools implementation
- 12.5 Parallel STL
    - Execution policies
    - Parallel algorithms
- 12.6 Common pitfalls
    - Data races
    - Deadlocks
    - Priority inversion
    - False sharing

### Chapter 13: Error Handling and Debugging

- 13.1 Exception handling
    - throw, try, catch blocks
    - Exception specifications and noexcept
    - Standard exception hierarchy
    - Exception safety guarantees
    - RAII and exception safety
- 13.2 Error codes vs exceptions
    - std::error_code and std::error_condition
    - std::expected (C++23)
    - Result types pattern
- 13.3 Assertions and contracts
    - assert macro
    - static_assert
    - Contracts proposal
- 13.4 Debugging techniques
    - Defensive programming
    - Logging strategies
    - Core dumps analysis
    - Memory debugging tools
    - Race condition detection

## Part V: Professional Development

### Chapter 14: Design Patterns and Architecture

- 14.1 Creational patterns
    - Singleton (and why to avoid it)
    - Factory Method and Abstract Factory
    - Builder
    - Prototype
- 14.2 Structural patterns
    - Adapter
    - Bridge
    - Composite
    - Decorator
    - Facade
    - Proxy
- 14.3 Behavioral patterns
    - Observer
    - Strategy
    - Command
    - Iterator
    - Template Method
    - Visitor
- 14.4 Modern C++ patterns
    - CRTP (Curiously Recurring Template Pattern)
    - Type erasure
    - Policy-based design
    - Expression templates
    - Pimpl idiom

### Chapter 15: Testing and Quality Assurance

- 15.1 Unit testing
    - Google Test framework
    - Catch2 framework
    - Test-driven development (TDD)
    - Mock objects and Google Mock
- 15.2 Integration and system testing
- 15.3 Performance testing
    - Microbenchmarking with Google Benchmark
    - Profiling tools: perf, VTune, gprof
- 15.4 Static analysis
    - Clang-Tidy
    - Cppcheck
    - PVS-Studio
- 15.5 Code coverage
    - Line, branch, and path coverage
    - Coverage tools: gcov, llvm-cov
- 15.6 Continuous integration for C++

### Chapter 16: Performance Optimization

- 16.1 Profiling and measurement
    - CPU profiling
    - Memory profiling
    - Cache profiling
- 16.2 Algorithmic optimizations
    - Choosing appropriate data structures
    - Algorithm complexity analysis
    - Space-time tradeoffs
- 16.3 Low-level optimizations
    - Cache-friendly code
    - Branch prediction
    - Loop optimizations
    - Vectorization and SIMD
    - Inlining strategies
- 16.4 Memory optimizations
    - Memory pooling
    - Custom allocators
    - Reducing allocations
    - Structure packing
- 16.5 Compiler optimizations
    - Optimization levels
    - Link-time optimization
    - Profile-guided optimization

### Chapter 17: Interview Preparation

- 17.1 Common C++ interview questions
    - Language fundamentals
    - Memory management
    - OOP concepts
    - STL usage
- 17.2 Coding interview patterns
    - Two pointers
    - Sliding window
    - Fast and slow pointers
    - Merge intervals
    - Cyclic sort
    - Tree and graph traversal patterns
    - Dynamic programming patterns
    - Backtracking patterns
    - Bit manipulation tricks
- 17.3 System design with C++
    - Scalability considerations
    - Memory-efficient designs
    - Thread-safe designs
    - API design principles
- 17.4 Behavioral questions
    - Discussing C++ projects
    - Problem-solving approach
    - Code review scenarios

### Chapter 18: Real-World Applications

- 18.1 Building libraries
    - Header-only vs compiled libraries
    - API design and ABI stability
    - Versioning strategies
    - Documentation with Doxygen
- 18.2 Cross-platform development
    - Platform-specific code
    - Conditional compilation
    - Build configuration
- 18.3 Interfacing with other languages
    - C interoperability
    - Python bindings (pybind11)
    - JNI for Java
- 18.4 Domain-specific topics
    - Game development considerations
    - Embedded systems constraints
    - High-frequency trading requirements
    - Scientific computing with C++

### Chapter 19: Code Quality and Best Practices

- 19.1 Coding standards
    - Google C++ Style Guide highlights
    - C++ Core Guidelines
    - MISRA C++ for safety-critical systems
- 19.2 Code organization
    - Header guards and pragma once
    - Forward declarations
    - Namespace organization
    - Module system (C++20)
- 19.3 Documentation
    - Self-documenting code
    - Comment strategies
    - API documentation
- 19.4 Code review practices
    - Common C++ code smells
    - Performance pitfalls
    - Security considerations
- 19.5 Refactoring techniques
    - Safe refactoring in C++
    - Dealing with legacy code
    - Incremental modernization

### Chapter 20: Capstone Projects

- 20.1 Implementation projects
    - Custom STL container
    - Thread pool library
    - Memory allocator
    - Simple database engine
    - Network server
    - Compiler frontend
- 20.2 Algorithm challenges
    - Competitive programming problems
    - LeetCode hard problems walkthrough
    - System design implementation
- 20.3 Performance challenges
    - Optimization case studies
    - Profiling and tuning exercises
- 20.4 Portfolio building
    - Open source contribution
    - Project documentation
    - GitHub best practices

## Appendices

### Appendix A: Quick Reference

- A.1 C++ keywords and operators
- A.2 STL container complexity reference
- A.3 Algorithm complexity cheat sheet
- A.4 Common compiler flags
- A.5 Debugging commands reference

### Appendix B: Resources

- B.1 Recommended books
- B.2 Online resources and communities
- B.3 Practice platforms
- B.4 C++ conferences and talks
- B.5 Notable C++ libraries

### Appendix C: Setting Up Development Environments

- C.1 Windows setup with Visual Studio
- C.2 Linux setup with GCC/Clang
- C.3 macOS setup
- C.4 WSL setup
- C.5 Docker for C++ development

### Appendix D: Migration Guides

- D.1 Migrating from C to C++
- D.2 Migrating from older C++ standards
- D.3 Common pitfalls when coming from other languages