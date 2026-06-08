# New Memory Safe Programming Language (code name mach)
Copyright 2026 McPherran  
See LICENSE

---

## Language Design Overview
  - Type: C++-like
  - Supports automated imports -replaces C++20 modules
  - Language Code Name: mach

## Current Development Plan

### Initial development in C++17 (Linux, gcc 15.2)

### Builder
- Builds C++17 and eliminates use of explicit include files
- Builds and translates mach (new C++-like programming

### Code/Text Editor

### 
1. Compile optimal (commonly used) subset of C
2. Compile new language
3. Migration from C tool.

---

# Language Design Ideas

## Inspired By
- C and C++
- Go and Rust
- F#
- Shell scripts
- Google code style

## C++-Like

---

## Memory Management: Entry/Exit Design

### Software operations are partitioned as Memory IO boxes.
### A Memory IO box has an Entry/Exit stage (analogous to In/Out)
### Memory is Acquired at the box Entry and Released at the box Exit
### Memory Acquisition/Release occurs only at box Entry/Exit
### Compiler-controlled
### Mode: Acquisition/Release may be alloc/free or pool get/return
### Attributes control mode and pool sizes
### Memory management is part of the application design
### No garbage collection (GC)
### Boxes can contain smaller boxes with the same paradigm
### Async operations supported, box memory generally thread-local
### Fast compilation, high-performance runtime, deterministic


See Also:
- [CISA - Memory Safety](https://www.cisa.gov/sites/default/files/2023-12/CSAC_TAC_Recommendations-Memory-Safety_Final_20231205_508.pdf)
- [F# native compiler initiative](https://github.com/FidelityFramework/Firefly)

### Language Features
- **Functional-Programming Oriented**
- **OO: Extension classes**
- **Standard Function Syntax: Example()**
- **Memory Safety**
- **Syntax Fosters AI/Scanning**
- **High Performance**
- **Power Efficiency**
- **System V AMD64 ABI (C-ABI)**

##### Functions
- Pattern matching
- Imperative statements supported
- No return statements
- Pattern match or value as last statement is return value
- Function call acts as data/value
- Value of function uses struct member access syntax
- Boolean status optionally associated with function
- Syntax to access status and value
- Parentheses unused for functions without params

##### General Minimization of Declaration of Variables
- Function call syntax provides effective return value variable
- Return value is either primitive or struct
- Explicit declaration of variables is generally unnecessary
- Automatic sequence variables (loop, span, list, hash, array, ...)
- Types not merely implied, clear from context.

##### OO Aspects
- Interfaces
- Extension classes
- Non-Inheritance Overrides
- Data oriented
- Data accessibility syntax
- Mutability syntax
- No properties (unneeded)
- OO-like call syntax for functions with data as first arg

##### Data Accessibility Syntax
- Access control syntax, no getters/setters
- Public and private only
- Default: public
- Private access flag for functions

##### Mutability Syntax
- Immutable by default
- Mutability enable keyword/symbol

##### Generic Types (Interfaces)
- Interfaces
- Defined by data and/or functions
- Implementation functions are not members

##### Code Organization
- Single file translation units
- No separate include files, include the source file
- Exports precompiled to separate output file
- Include source uses precompiled exports file
- Directories define namespaces (under project root)

##### Traditional OO-Like Call Syntax
- Data acts as object
- Applies to functions with data as first arg
- Example function: Trim(string str)
- Example call: line.Trim

##### No Exceptions (clean, performant)
- E.g. no throw/catch
- See Functions (boolean status)

##### Reduce Unproductive Decisions (Code Clarity, AI)
- No referring to "operator precedence" 
- Parentheses required when needed, disallowed when not
- Syntax provides clarity when parentheses disallowed/unnecessary
- Prevent confusing math equations and boolean logic
- Functional approach to math/logic/operators
- FP approach not less concise, rather far more concise overall...
- FP and data approach fosters pattern recognition/capture.

##### Reduce Unproductive Debates
- No "when are parens needed/better" debates
- Indentation uses tabs. Tab size of 2 spaces recommended.
- Integrated editor (see IDE plan below) enforces tabs of size 2 or 4.
- Syntax minimizes need for conventions
- Uppercase characters unsupported except for syntax
- Line comments allowed, no comments on same line as code
- Self-documenting code encouraged

### Memory Safety

#### Normal Context
- No global variables (local and module-level only)
- No pointers
- No allocations
- No garbage collection
- Memory managed as part of language
- Unsafe contexts allowed

#### Why No Garbage Collection (GC)
- Manage memory safety once at compile-time, not repeatedly at run-time.
- GC indulges haphazard coding; AI-incompatible
- GC negatively impacts performance and determinism
- GC unnecessary (e.g. Rust).
- Note: GC works well and adds memory safety, but it's deprecated.

#### Unsafe Context
- No pointers
- Addresses and ranges (arrays, bounds)
- Memory-mapped structs (e.g. for drivers)
