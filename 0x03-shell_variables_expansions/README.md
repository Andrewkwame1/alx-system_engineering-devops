# Shell Variables and Expansions

This project contains shell scripts that demonstrate shell variables, expansions, arithmetic operations, and alias management.

## Scripts

### 0. `0-alias`
Creates an alias that maps the `ls` command to `rm *`.
- **Functionality**: After sourcing this script, typing `ls` will execute `rm *` instead of listing files
- **Usage**: `source ./0-alias`

### 1. `1-hello_you`
Prints a greeting with the current Linux user's name.
- **Functionality**: Displays "hello [username]" using the `$USER` or `$LOGNAME` environment variable
- **Output Example**: `hello julien`
- **Usage**: `./1-hello_you`

### 2. `2-path`
Adds the `/action` directory to the PATH environment variable.
- **Functionality**: Appends `/action` to the existing PATH as the last directory the shell searches for programs
- **Usage**: `source ./2-path`
- **Effect**: Future commands will search for executables in `/action` last

### 3. `3-paths`
Counts the number of directories in the PATH environment variable.
- **Functionality**: Counts the colon-separated directories in the `$PATH` variable by counting colons and adding 1
- **Output Example**: `11` (or more if PATH has additional entries)
- **Usage**: `. ./3-paths`

### 4. `4-global_variables`
Lists all environment variables (global variables).
- **Functionality**: Displays all exported environment variables using `printenv` or `env`
- **Usage**: `source ./4-global_variables`
- **Output**: Shows variables like HOME, PATH, USER, LANG, etc.

### 5. `5-local_variables`
Lists all local variables, environment variables, and functions.
- **Functionality**: Displays both exported variables and local shell variables using the `set` command
- **Usage**: `. ./5-local_variables`
- **Output**: Shows more variables than `4-global_variables` including bash-specific variables like BASH_VERSION, BASH_ALIASES, etc.

### 6. `6-create_local_variable`
Creates a new local variable.
- **Functionality**: Creates a local variable named `BEST` with the value `School`
- **Scope**: The variable is only available in the current shell session
- **Usage**: `source ./6-create_local_variable`

### 7. `7-create_global_variable`
Creates a new global (exported) variable.
- **Functionality**: Creates an exported variable named `BEST` with the value `School`
- **Scope**: The variable is available to child processes
- **Usage**: `source ./7-create_global_variable`

### 8. `8-true_knowledge`
Prints the result of adding 128 to the TRUEKNOWLEDGE environment variable.
- **Functionality**: Performs arithmetic: `128 + $TRUEKNOWLEDGE`
- **Usage**: `export TRUEKNOWLEDGE=1209 && ./8-true_knowledge`
- **Output Example**: `1337` (128 + 1209 = 1337)

### 9. `9-divide_and_rule`
Prints the result of dividing POWER by DIVIDE environment variables.
- **Functionality**: Performs arithmetic: `$POWER / $DIVIDE`
- **Usage**: `export POWER=42784 && export DIVIDE=32 && ./9-divide_and_rule`
- **Output Example**: `1337` (42784 / 32 = 1337)

### 10. `10-love_exponent_breath`
Displays the result of BREATH raised to the power of LOVE.
- **Functionality**: Performs exponentiation: `$BREATH ** $LOVE`
- **Usage**: `export BREATH=4 && export LOVE=3 && ./10-love_exponent_breath`
- **Output Example**: `64` (4³ = 64)

### 11. `11-binary_to_decimal`
Converts a binary number to decimal.
- **Functionality**: Converts the value in the `BINARY` environment variable from base 2 to base 10
- **Usage**: `export BINARY=10100111001 && ./11-binary_to_decimal`
- **Output Example**: `1337` (binary 10100111001 = decimal 1337)

### 12. `12-combinations`
Prints all possible combinations of two letters (a-z), except "oo".
- **Functionality**: Generates combinations like "aa", "ab", "ac"... "oz", "pa"... "zz", excluding "oo"
- **Constraints**: 
  - Only lowercase letters (a-z)
  - One combination per line
  - Alphabetically ordered
  - Maximum 64 characters in script file
- **Output Count**: 675 lines (26² - 1 = 675, excluding "oo")
- **Usage**: `./12-combinations`

### 13. `13-print_float`
Prints a number with two decimal places.
- **Functionality**: Formats the number stored in the `NUM` environment variable to display exactly 2 decimal places
- **Usage**: `export NUM=3.14159 && ./13-print_float`
- **Output Examples**: 
  - `0.00` (when NUM=0)
  - `98.00` (when NUM=98)
  - `3.14` (when NUM=3.14159265359)

## Key Concepts

- **Aliases**: Shortcuts for commands (created with `alias`)
- **Environment Variables**: Global variables accessible to child processes (created with `export`)
- **Local Variables**: Variables only available in the current shell session
- **Shell Expansion**: Techniques to substitute values (variables, commands, arithmetic)
- **Shell Arithmetic**: Mathematical operations using `$(( ))` syntax
- **PATH**: The environment variable that tells the shell where to find executables

## Requirements

- All scripts are exactly two lines long
- All scripts start with `#!/bin/bash`
- All scripts end with a newline
- All scripts are executable
- No use of `&&`, `||`, or `;` operators
- No use of `bc`, `sed`, or `awk` utilities
