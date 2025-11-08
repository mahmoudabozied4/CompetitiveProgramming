# Competitive Programming Solutions

This repository contains C++ implementations of competitive programming problems from [Codeforces](https://codeforces.com/), [AtCoder](https://atcoder.jp/), and [CSES](https://cses.fi/problemset/).  
It focuses on performance, clarity, and reusable templates suitable for high-speed problem-solving environments such as online contests.

---

## 📘 Description

Each file implements a standalone solution for a single problem.  
The core utilities—input/output optimizations, type aliases, macros, and helper templates—are reused across all solutions to minimize overhead during contests.

The code follows a consistent structure:
- `Zied()` for setting up fast I/O and conditional local debugging.
- `Solve()` as the main logic entry point.
- Optional `Stress()` functions for local stress testing.
- Reusable templates for vectors and pairs to simplify input/output.
- Preprocessor macros for common tasks like modulo operations, loop bounds, and precision formatting.

---

## ⚙️ Interesting Techniques

1. **Fast I/O Setup**  
   Uses `ios_base::sync_with_stdio(false)` and `cin.tie(nullptr)` for fast I/O ([cppreference](https://en.cppreference.com/w/cpp/io/ios_base/sync_with_stdio)).

2. **Template-Based Stream Operators**  
   Overloaded `>>` and `<<` operators for vectors and pairs reduce repetitive code and make the logic more expressive.

3. **Custom Type Aliases and Macros**  
   Common idioms like `#define all(vec) vec.begin(), vec.end()` and `#define sz(s) int32_t(s.size())` speed up both writing and reading the code.

4. **Use of `std::function` for Lambdas**  
   Recursive lambdas using `std::function` enable inline DFS and BFS implementations without global helpers.

5. **Graph Traversal Abstractions**  
   Graph problems (like in [`CSES/Building_Roads.cpp`](CSES/Building_Roads.cpp)) use clean DFS/BFS patterns with reusable adjacency lists and minimal global state.

6. **Policy-Based Data Structures**  
   The [`ordered_set`](https://gcc.gnu.org/onlinedocs/libstdc++/ext/pb_ds.html) from `ext/pb_ds` enables efficient order-statistics operations and unique value lookups beyond STL capabilities.

7. **Enumerated Directions for Grid Traversal**  
   The global `dx` and `dy` arrays, along with an `enum dir`, make multidirectional grid traversal clean and readable—useful for problems like [`CSES/Counting_Rooms.cpp`](CSES/Counting_Rooms.cpp).

8. **Preprocessor Tricks**  
   Techniques like `#define Ceil(n, m) (((n)/(m)) + ((n) % (m) ? 1 : 0))` encapsulate common arithmetic routines.

9. **Functional Macros for Early Returns**  
   The custom `#define endd(s)` allows concise early exits from void-returning functions.

10. **Conditional Debugging Blocks**  
    Conditional compilation using `#ifndef ONLINE_JUDGE` automatically toggles between local file I/O and standard input/output.

---

## 🧩 Non-Obvious Technologies and Libraries

- **GNU PBDS (Policy-Based Data Structures)**  
  Included via `<ext/pb_ds/assoc_container.hpp>` and used to implement an `ordered_set`.  
  Reference: [GCC libstdc++ documentation](https://gcc.gnu.org/onlinedocs/libstdc++/ext/pb_ds.html)

- **I/O Redirection for Local Testing**  
  The `#ifndef ONLINE_JUDGE` block allows redirecting `stdin` and `stdout` to `input.txt` and `output.txt` for local debugging.

- **Precomputation Placeholders**  
  The `preprocessing()` function serves as a hook for memoization or sieve-like precomputations when scaling to larger datasets.

- **Bit Manipulation and Modular Arithmetic**  
  Utility macros like `mul_mod`, `add_mod`, and `sub_mod` ensure safe modular arithmetic operations (useful for problems with modulus constraints such as `1e9+7`).

Directory structure:
```
└── mahmoudabozied4-competitiveprogramming/
    ├── AtCoder/
    │   ├── abc061b.cpp
    │   ├── abc166c.cpp
    │   ├── abc169a.cpp
    │   └── abc220a.cpp
    ├── CodeForces/
    │   ├── 2060A.cpp
    │   ├── 2060B.cpp
    │   ├── 2164A.cpp
    │   ├── 2164B.cpp
    │   ├── 2164C.cpp
    │   ├── 219158B.cpp
    │   ├── 377A.cpp
    │   ├── 500A.cpp
    │   ├── 574B.cpp
    │   ├── 630A.cpp
    │   ├── 633A.cpp
    │   ├── 977C.cpp
    │   └── 990D.cpp
    └── CSES/
        ├── Bit_Strings.cpp
        ├── Building_Roads.cpp
        ├── Building_Teams.cpp
        └── Counting_Rooms.cpp
```

### Directory Descriptions

- **AtCoder/** — Implementations of selected AtCoder Beginner Contest problems.  
- **CodeForces/** — Contains Codeforces round problem solutions, typically grouped by round number.  
- **CSES/** — Contains structured problem solutions from the CSES Problem Set, including graph and bit manipulation exercises.

---

## 🧠 Notes for Developers

- All code uses 64-bit integers (`#define int long long`) for consistency and to avoid overflow in mathematical problems.  
- Files are intentionally self-contained, ensuring they can compile independently in online judges.
- Each solution follows a consistent entry-point design (`main()` → `Zied()` → `Solve()`).

---
