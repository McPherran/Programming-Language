# Memory Safe Programming Language
## Code Name: ccn

Copyright 2026 McPherran  
[License](https://github.com/McPherran/Programming-Language/edit/main/LICENSE)

---

## Language Overview

- **Type: C++-like**
- **Language code name: ccn**
- **File extension: cn (e.g. main.cn)**
- **Inspired By**
  - C and C++
  - Go and Rust
  - F#
  - Shell
  - Google code style

#### Origin of Name "ccn"

"ccn" is an acronym for Comp Code Net. "ccn" is general name that was used for the http server software and concept of software delivery via the internet. Serendipitously, "ccn" can also apply to C-related languages, e.g. "cc" is often associated with C compilation. Language name ideas for a permanent name are welcomed.  
[Language Name](https://github.com/McPherran/Programming-Language/discussions/2)

---

## Language Design/Concepts

---

### Language Features
- **Functional-OO (foo-oriented)**
- **OO: Extension classes**
- **Standard Function Syntax: Example()**
- **Automated imports** (no #include/import syntax)
- **Eases migration from both C and C++**
- **Memory Safety**
- **Syntax Fosters AI/Scanning**
- **High Performance**
- **Power Efficiency**
- **System V AMD64 ABI (Unix/Linux C-ABI)** (initial ABI)

### Details

#### OO Aspects
- https://github.com/McPherran/Programming-Language/blob/main/Classes.md
- Functional OO (foo-oriented): Extension classes
- Data acts as object
- Traditional OO Call Syntax
- Interfaces
- Non-Inheritance Overrides
- Data oriented
- Data accessibility syntax
- Mutability syntax
- No properties (unneeded)
  
#### Functions
- Pattern matching
- Imperative statements supported
- No return statements
- Pattern match or value as last statement is return value
- Function call acts as data/value
- Value of function uses struct member access syntax
- Boolean status optionally associated with function
- Syntax to access status and value
- Parentheses unused for functions without params

#### General Minimization of Declaration of Variables
- Function call syntax provides effective return value variable
- Return value is either primitive or struct
- Explicit declaration of variables is generally unnecessary
- Automatic sequence variables (loop, span, list, hash, array, ...)
- Types not implied, clear from context.

#### Code Organization
- Translation units based on hierarchies (e.g. namespaces, types)
- Directories define namespaces (under project root)

#### No Exceptions (clean, performant)
- E.g. no throw/catch
- See Functions (boolean status)
  
#### Memory Safety

- Memory Management: Entry/Exit Design
  - Software operations are partitioned as Memory IO boxes.
  - A Memory IO box has an Entry/Exit stage (analogous to In/Out)
  - Memory is Acquired at the box Entry and Released at the box Exit
  - Memory Acquisition/Release occurs only at box Entry/Exit
  - Mode: Acquisition/Release may be alloc/free or pool get/return
  - Attributes control mode and pool sizes
  - Memory management is part of the application design
  - No garbage collection (GC)
  - Boxes can contain smaller boxes with the same paradigm
  - Async operations supported, box memory generally thread-local
  - Fast compilation, high-performance runtime, deterministic

- Normal Context
  - No global variables (local and module-level only)
  - No pointers
  - No allocations
  - No garbage collection
  - Memory managed as part of language
  - Unsafe contexts allowed

- Unsafe Context
  - No pointers
  - Addresses and ranges (arrays, bounds)
  - Memory-mapped structs (e.g. for drivers)

- Why No Garbage Collection (GC)
  - Manage memory safety once at compile-time, not repeatedly at run-time
  - GC indulges haphazard coding; Reduces AI-compatibility
  - GC negatively impacts performance and determinism
  - GC unnecessary (e.g. Rust)
  - GC works for memory safety, but it's deprecated

- See Also:
  - [CISA - Memory Safety](https://www.cisa.gov/sites/default/files/2023-12/CSAC_TAC_Recommendations-Memory-Safety_Final_20231205_508.pdf)
  - [F# native compiler initiative](https://github.com/FidelityFramework/Firefly)

#### Reduce Unproductive Decision-Making (Code Clarity, AI)
- No referring to "operator precedence" 
- Parentheses required when needed, disallowed when not
- Syntax provides clarity when parentheses disallowed/unnecessary
- Prevent confusing math equations and boolean logic
- Functional approach to math/logic/operators
- FP/OO (foo) approach fosters data pattern recognition

#### Reduce Unproductive Debates
- Syntax minimizes need for conventions
- No "when are parens needed/better" debates
- Indentation uses tabs. Tab size of 2 spaces recommended.
- Builder enforces tabs of size 2 or 4.
- Most syntax lowercase only
- Line comments allowed, no comments on same line as code
- Self-documenting code is standard/convention

## Development Plan

### Initial development in C++ using Linux

### Builder
- Builds C++. Eliminates explicit #include/import syntax
- Source files and references (imports/#includes) are automated and mapped
- Builds and translates ccn 
- Translation Units are hierarchy-based as opposed to file-based

### Code/Text Editor
