# Part I — Orientation & Strategy

- Why C++ in 2025: where it shines (systems, low-latency backends, games, embedded, HPC)
    
- Learning path & milestones; building a portfolio; how to read standards & proposals
    
- The “modern C++” mindset: value semantics, RAII, zero-cost abstractions
    

# Part II — Toolchain & Workflow

- Compilers & standard libraries: GCC, Clang/LLVM, MSVC; libstdc++, libc++; picking versions
    
- Build systems: CMake (targets, presets, toolchains), brief Meson/Ninja
    
- Package managers: vcpkg, Conan; vendoring vs system packages
    
- Project layout & reproducible builds; Debug/Release/RelWithDebInfo
    
- IDEs & editors: Visual Studio, CLion, VS Code; formatting with clang-format
    
- Continuous Integration: CTest, GitHub Actions
    
- Sanitizers & static analysis: ASan/TSan/UBSan/MSan, clang-tidy, cppcheck
    
- Profilers & tracers: perf, VTune, Xcode Instruments, Windows WPA
    
- Benchmarking: Google Benchmark; avoiding benchmarking pitfalls
    
- Cross-compilation & containers: Docker toolchains, cross for ARM
    

# Part III — C++ Essentials (Syntax & Core Semantics)

- Translation units, linkage, ODR; headers, include guards, pragma once
    
- Namespaces; using-declarations vs using-directives; ADL
    
- Basic I/O: iostreams, `<format>` vs iostream formatting, sync_with_stdio
    

# Part IV — Types & Value Categories

- Fundamental types
    
    - `bool`
        
    - Character types: `char`, `signed/unsigned char`, `wchar_t`, `char8_t`, `char16_t`, `char32_t`
        
    - Integers: `short`, `int`, `long`, `long long` (`signed`/`unsigned`)
        
    - Floating point: `float`, `double`, `long double`
        
    - `std::byte`; enumerations (`enum`, `enum class`)
        
- Pointers & references
    
    - Raw pointers, pointer arithmetic, `nullptr`, `const` correctness
        
    - Lvalue/rvalue/xvalue/prvalue; references: `T&`, `const T&`, `T&&`
        
- Object model & storage durations: static, thread, automatic, dynamic
    
- Alignment & `alignas`, padding, strict aliasing
    

# Part V — Initialization, Assignment & Lifetime

- Initialization forms: default, value, direct, list (`{}`), aggregate; narrowing
    
- Copy/move/assignment; copy elision, NRVO
    
- Constructors/destructors; in-class member init; delegating constructors
    
- Rule of Zero/Three/Five; special member functions; `=default`, `=delete`
    

# Part VI — Expressions, Functions & Overload Resolution

- Operators, precedence, short-circuiting, `constexpr` evaluation
    
- Function declarations/definitions; default args; inline; `constexpr`/`consteval`
    
- Overloading vs templates; implicit conversions, user-defined conversions
    
- Operator overloading: when (and when not) to do it
    
- Lambdas: captures, generic lambdas, `mutable`, `constexpr` lambdas
    

# Part VII — Classes, Inheritance & Polymorphism (Modern View)

- Class layout; `struct` vs `class`; `friend`
    
- Inheritance: public/protected/private; virtual dispatch; vtables
    
- Dynamic polymorphism: `virtual`, `override`, `final`, pure virtual; RTTI, `dynamic_cast`
    
- Static polymorphism: CRTP; mixins; policy-based design
    
- Type erasure: `std::function`, DIY type erasure, small buffer optimization (SBO)
    
- Pimpl idiom; ABI stability; visibility & exporting symbols
    

# Part VIII — Templates & Generic Programming

- Function/class templates; partial/explicit specialization
    
- Template argument deduction; CTAD; deduction guides
    
- Variadic templates; fold expressions
    
- SFINAE & traits; building type traits with `<type_traits>`
    
- Concepts & `requires` (constraints, requires-clause vs requires-expr)
    
- `constexpr` metaprogramming vs classic TMP; non-type template params
    
- Compile-time data structures; string literals at compile time
    
- Patterns: tag dispatching, traits, `enable_if` vs concepts, customization points
    

# Part IX — The Standard Library: Containers, Views & Iterators

- Strings: `std::string`, `std::u8string`*, `string_view` (lifetimes!)
    
- Contiguous containers: `array`, `vector`, `span` (views over memory)
    
- Node-based: `list`, `forward_list`
    
- Associative (tree-based): `map`, `multimap`, `set`, `multiset` (hinting, heterogeneous lookup)
    
- Unordered (hash-based): `unordered_map`, `unordered_set`, multimaps/multisets; custom hash/equal; DOS-resistant hashing notes
    
- Adaptors: `stack`, `queue`, `priority_queue`, `deque`
    
- Other utilities: `bitset`, `optional`, `variant`, `any`, `pair`, `tuple`
    
- Iterators: categories, iterator invalidation rules, `std::iterator_traits`
    
- Ranges (C++20/23): views, actions, range adaptors (`views::filter`, `transform`, `take`, `zip`, etc.); iterator vs range algorithms; pipe style
    

# Part X — Algorithms & Numerics

- `<algorithm>` essentials: `sort`, `stable_sort`, `partial_sort`, `nth_element`, `lower_bound`/`upper_bound`, set ops
    
- Parallel algorithms (C++17/20): execution policies (`seq`, `par`, `par_unseq`)
    
- `<numeric>`: `accumulate`, `reduce`, `inner_product`, `exclusive_scan`/`inclusive_scan`
    
- Random: engines (mt19937, pcg*), distributions; seeding correctly
    
- Math: `<cmath>`, `<numbers>`; `complex`; `valarray` (when/why)
    

# Part XI — Memory Management & Resource Safety

- RAII idiom; `unique_ptr`, `shared_ptr`, `weak_ptr`; custom deleters
    
- Ownership patterns: passing by value/ref/pointer; `gsl::not_null`
    
- Allocation strategies: `new`/`delete`, placement new; arenas & pools
    
- Polymorphic allocators & `<memory_resource>`; per-component arenas
    
- Object lifetime pitfalls: dangling, double-free, use-after-free
    
- Small object optimization (SBO); EBO; alignment-aware containers
    

# Part XII — Error Handling & Contracts

- Exceptions: `throw`, `try`/`catch`, `noexcept`, exception specs
    
- Exception safety guarantees (basic/strong/nothrow); commit-or-rollback
    
- Alternatives: status codes, `std::expected<T,E>` (C++23), `tl::expected`
    
- Designing error hierarchies; logging & propagation; boundary decisions (turn off exceptions?)
    
- Assertions; defensive programming; GSL contracts style
    

# Part XIII — Concurrency, Parallelism & the Memory Model

- Threads & tasks: `std::thread`, `jthread`, `async`, futures/promises, packaged_task
    
- Synchronization: `mutex`, `shared_mutex`, `condition_variable`, `semaphore`, `latch`, `barrier`, `stop_token`
    
- Atomics: `std::atomic<T>`, memory orders (`relaxed`, `acquire/release`, `acq_rel`, `seq_cst`), fences; lock-free patterns
    
- The C++ memory model: happens-before, data races, tear-free types, false sharing
    
- Designing thread pools; work stealing; producer/consumer queues
    
- Parallel ranges/algorithms & pitfalls; NUMA notes
    

# Part XIV — I/O, Filesystems, Serialization & Networking

- Filesystem: `<filesystem>` paths, status, iteration, observers vs modifiers
    
- Text & formatting: `<format>` vs `fmt` vs `iostream`; `std::print` (C++23)
    
- Binary I/O: endianness, struct packing, `mmap`, memory-mapped files
    
- Networking (practical):
    
    - Boost.Asio / `std::asio`-style async model (timers, sockets, strands)
        
    - HTTP (Boost.Beast, cpp-httplib), WebSocket basics
        
    - TLS (OpenSSL/wolfSSL); certificate handling; ALPN
        
- Serialization: Protocol Buffers, FlatBuffers, Cap’n Proto, JSON (nlohmann/rapidjson), YAML
    
- IPC: pipes, shared memory, message queues
    

# Part XV — Modules, Coroutines & Advanced Language Features

- Modules: partitions, interfaces, BMI caching, migration from headers
    
- Coroutines: `co_await`, `co_yield`, `co_return`; awaitables/awaiters; event loops (Asio); generators & task types
    
- The spaceship operator `<=>`; three-way comparison
    
- `std::span`, `std::bit_cast`, designated initializers, `constexpr` on more constructs
    
- C++23 highlights & availability notes: `std::expected`, `std::print`, `mdspan`, more ranges algorithms/views
    

# Part XVI — Performance Engineering & Low-Level Details

- CPU basics for devs: caches, prefetch, branch prediction, pipelines
    
- Measuring correctly: warm-ups, variance, perf counters; flame graphs
    
- Data-oriented design & locality; AoS vs SoA; cache-aware algorithms
    
- Vectorization: autovectorization, compiler flags, intrinsics (SSE/AVX/NEON), libraries (Eigen, Blaze)
    
- Build flags: `-O2`/`-O3`, LTO, PGO; symbol visibility; exceptions/RTTI trade-offs
    
- Allocator tuning; custom allocators; small-buffer tricks
    
- Debugging heisenbugs: races, UAFs; sanitizers & Valgrind
    
- Latency engineering: avoiding syscalls, batching, lock contention, time sources (`chrono::steady_clock`)
    

# Part XVII — Testing, Debugging & Quality

- Unit testing frameworks: GoogleTest, Catch2, doctest
    
- BDD/property tests & fuzzing: RapidCheck, libFuzzer/AFL++
    
- Code coverage: gcov/lcov/llvm-cov; what coverage can/can’t tell you
    
- Debuggers: gdb/lldb/Visual Studio; core dumps, post-mortem debugging
    
- Logging: spdlog, Boost.Log; structured logging; rate limiting
    
- Diagnostics in production: perf events, eBPF basics, tracing
    

# Part XVIII — Secure & Robust C++

- SDL/CERT/SEI secure coding guidelines; C++ Core Guidelines
    
- Bounds, lifetime, and ownership checks; `span`, `string_view` safety
    
- Input validation, injection surfaces, format-string & UB hazards
    
- Time, time zones, clocks: `<chrono>` best practices; leap seconds
    
- Handling untrusted data; fuzz-driven development
    

# Part XIX — Algorithms & Data Structures for Interviews (with C++-Specific Tactics)

- Complexity analysis: Big-O/Ω/Θ; amortized; memory complexity; cache effects
    
- Arrays & strings
    
    - Two-pointers, sliding window, prefix/suffix sums
        
    - `string` vs `string_view`; Unicode & UTF-8 (`char8_t`)
        
- Hashing & sets/maps
    
    - `unordered_map`/`unordered_set`; custom hash for pairs/tuples; load factor & rehash
        
- Stacks/queues/deques; monotonic stacks/queues; heap/priority queue (`priority_queue`, custom comparators)
    
- Linked lists: singly/doubly; cycle detection; list vs vector trade-offs
    
- Trees
    
    - Binary trees, BSTs, segment/fenwick trees; tries; tree DP; LCA
        
    - STL maps as red-black trees (properties & complexity contracts)
        
- Graphs
    
    - Representations (adjacency list/matrix, CSR); BFS/DFS; topological sort
        
    - Shortest paths: Dijkstra, Bellman-Ford; Floyd-Warshall
        
    - MST: Kruskal (DSU), Prim; Union-Find with path compression & union by rank
        
- Dynamic programming patterns
    
    - Knapsack, LIS, LCS/ED, partition, digit DP; state compression with bitsets
        
- Greedy, divide & conquer, backtracking; pruning & ordering
    
- Number theory & bit tricks: gcd, sieve, modular arithmetic; bit masks & DP optimizations
    
- Practical coding patterns in C++
    
    - Fast I/O (`ios::sync_with_stdio(false); cin.tie(nullptr);`)
        
    - Avoiding TLE/MLE with views/iterators; avoiding needless copies; emplace vs push
        
    - Handling 64-bit overflow; `std::gcd`, `std::lcm`, `std::bit_ceil/floor`
        

# Part XX — Domain Tracks (Choose Your Adventure)

- Backend/Networked services
    
    - Asio-based servers, HTTP/REST, gRPC; structured concurrency; backpressure
        
    - Caching (LRU/LFU), rate limiting, serialization at scale
        
- Low-latency/Trading
    
    - Lock-free queues, ring buffers; kernel bypass basics; timestamping; pacing
        
- Game dev
    
    - Game loop, ECS pattern, real-time constraints; asset pipelines; physics libs
        
- Embedded/IoT
    
    - Cross-compiling for ARM; `-fno-exceptions`/`-fno-rtti` builds; RTOS basics; memory-mapped I/O
        
- HPC/Scientific
    
    - `mdspan`/BLAS; MPI intro; GPU offload options (CUDA, HIP, SYCL)
        

# Part XXI — Design, Architecture & APIs

- API design in modern C++: value types first; spans & views; error surfaces
    
- Dependency management & DI patterns (compile-time vs runtime)
    
- Layering & boundaries; pImpl for ABI; plugins & `extern "C"` interfaces
    
- Config, feature flags, and versioning; semantic versioning for libraries
    
- Documentation: Doxygen, Sphinx+Breathe, literate tests
    

# Part XXII — Capstones (Portfolio-Ready)

- Build a header-only algorithms library with ranges concepts
    
- A production-style thread pool + work-stealing scheduler
    
- HTTP/1.1 server with Asio + coroutines + `expected` for error flow
    
- A lock-free MPMC queue with benchmarks & TSan tests
    
- Memory arena/PMR allocator + microbenchmarks
    
- Mini game engine core (ECS + systems + deterministic update loop)
    
- Embedded project: sensor driver + ring buffer + log over UART
    

# Part XXIII — Job Prep & Interview Strategy

- Picking projects & writing great READMEs; reproducible builds
    
- Crafting a C++-focused resume; showcasing perf wins & sanitizer finds
    
- Whiteboard vs IDE strategy; templates under pressure; “explain this crash”
    
- Take-home assignment checklist; code review etiquette & expectations
    
- Study plan & spaced repetition; targeted LeetCode list by topic
    

# Appendices

- A. Modern C++ feature timeline (C++11 → C++23): what to use, when, and why
    
- B. Compiler flags cheat sheets (GCC/Clang/MSVC)
    
- C. Common UB traps & how to detect them
    
- D. STL complexity & invalidation tables
    
- E. Glossary: standardese to plain English
    
- F. Further reading: C++ Core Guidelines, authoritative books, key libraries
    

_Notes:_ Some C++23 library features (e.g., `mdspan`) may still be rolling out across compilers/standard libraries—treat them as “use if available.”