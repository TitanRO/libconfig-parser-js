## a Libconfig Parser for js

Implemented after the [Specs](https://hyperrealm.github.io/libconfig/libconfig_manual.html#Configuration-Files) and powered by [Sprache-js](https://github.com/luggage66/Sprache-js).

## Implementation Status

- [X] Parsing whole files
    - [X] read files
    - [X] Comments
        - [X] ignore them
        - [X] Script-style comments `# comment line`
        - [X] C++-style comments `// comment line`
        - [X] C-style comments `/* comment */`
    - [X] Include Directives (maximum of 10 levels)
- [X] Settings
    - [X] Groups
    - [X] Arrays
    - [X] Lists
    - [X] scalar value
        - [X] Integer
            - [X] hex notation
            - [X] decimal notation
            - [X] octal notation
            - [X] signed Integers
        - [X] 64-bit Integer (*ignores the 64bit part for now)
        - [X] Float
            - [X] Normal Floats
            - [X] Signed Floats
            - [X] Exponents
        - [X] Boolean
        - [X] Strings
            - [X] Strings
            - [X] Strings with escape sequences
            - [X] Adjacent strings are automatically concatenated
            - [X] Multiline string with `<"` and `">` (Is not in the specs but used in the libconfig file I want to parse)

- [ ] serialization of js objects to libconfig files

## Stages/Steps/TODO:

- Writing code and tests for parsing ✔️
- Optimizing code for parsing
- Writing code and tests for serialization to libconfig files
- Documentation and examples


## Quirks

- You can do mixed number types (floats and its in same array) in Arrays which is not possible with normal libconfig

- Multiline string with `<"` and `">` are not in the official specs, but **they are supported** by this module.