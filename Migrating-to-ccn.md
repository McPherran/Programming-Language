# Migration to ccn
Copyright 2026 McPherran  

### General
ccn is designed for migration from both C and C++. However, migration
from other languages is certainly possible and the simplicity of migration
would vary with the lanaguage under migration. E.g. Go, Rust, and C#, may
be relatively easy to migrate from.

### Classes
See https://github.com/McPherran/Programming-Language/blob/main/Classes.md

### C++ Features Excluded from ccn

#### The following functionality of C++ is not planned for ccn.

- ADL
- Exceptions
- Metaprogramming
  - Macros
  - SFINAE
  - Template‑based (e.g. implicit, context-based)

#### Metaprogramming
ccn Design:
- Typed metaprogramming for simple, clear, and controlled code synthesis
- Semantic conditional compilation (e.g. platform/feature support)
