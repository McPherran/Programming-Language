## The Clay Programming Language

Copyright 2026 McPherran  
See LICENSE

#### Inspired by F#, C++, C, Rust, Go

[CISA - Memory Safety](https://www.cisa.gov/sites/default/files/2023-12/CSAC_TAC_Recommendations-Memory-Safety_Final_20231205_508.pdf)

### Language Features

- **Functional-Programming Oriented**
- **OO Interface Concept but not Traditional OO Syntax**
- **Function Syntax: Example()**
- **No Braces for code blocks**
- **Memory Safety**

##### Functions
- Pattern matchhing
- Imperative statements supported
- No return statements
- Pattern match or value as last statement is return value
- Function call acts as data/value
- Value of function uses struct member access syntax
- Boolean status optionally associated with function
- Syntax to access status and value
- General minimization of declaration of variables
- Parentheses unused for functions without params

##### General Minimization of Declaration of Variables
- Function call syntax provides effective return value variable
- Return value is either primitive or struct
- Explicit declaration of variables is generally unnecessary
- Types not merely implied, clear from context.

##### OO Aspects
- No classes
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

##### Translation Unit
- Single file translation units
- No include files

##### Traditional OO-Like Call Syntax
- Data acts as object
- Applies to functions with data as first arg
- Example function: Trim(string str)
- Example call: str.Trim

##### No Exceptions (clean, performant)
- E.g. no throw/catch
- See Functions (boolean status)

### Memory Safety

#### Normal Context
- No global variables (local and module-level only)
- No pointers
- No allocations
- No garbage collection
- Memory managed as part of language
- Unsafe contexts allowed

#### Unsafe Context
- No pointers
- Addresses and ranges (arrays, bounds)
- Memory-mapped structs (e.g. for drivers)

