## McPherran
## Memory Safe Programming Language and Toolset

#### Copyright 2026 McPherran

### Language Features

#### Functional-Programming Support
#### OO Aspects but not Traditional OO Syntax
#### Function Syntax: Example()
#### No Braces (no { })
#### Memory Safe

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

##### No Exceptions

- E.g. no throw/catch
- See Functions (boolean status)

### Memory Safety

- No global variables (local and module-level only)
- No pointers
- No allocations
- No garbage collection
- Memory managed as part of language
- Unsafe contexts allowed

#### Unsafe Contexts

- No pointers
- Predefined addresses and ranges (arrays, bounds)
