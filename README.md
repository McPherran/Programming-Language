## The McPherran Programming Language

Copyright 2026 McPherran  
See LICENSE

#### Inspired By
- F#
- C and C++
- Go and Rust
- Shell scripts
- Google code style

See Also:
- [CISA - Memory Safety](https://www.cisa.gov/sites/default/files/2023-12/CSAC_TAC_Recommendations-Memory-Safety_Final_20231205_508.pdf)
- [F# native compiler initiative](https://github.com/FidelityFramework/Firefly)

### Language Features
- **Functional-Programming Oriented**
- **OO: Interfaces, but no classes**
- **Function Syntax: Example()**
- **No Braces for Code Blocks**
- **Memory Safety**

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
- No classes
- No Inheritance (override by interface spec.)
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

##### Reduce Unproductive Debates
- Compiler disallows tabs
- Compiler enforces 2 space indentation (and auto-corrects)
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
- Manage memory once at compile-time, not repeatedly at run-time.
- GC indulges haphazard coding; AI-incompatible
- GC negatively impacts performance and determinism
- GC unnecessary (e.g. Rust).
- Note: GC works well; Simply stating that it's suboptimal/deprecated.

#### Unsafe Context
- No pointers
- Addresses and ranges (arrays, bounds)
- Memory-mapped structs (e.g. for drivers)

