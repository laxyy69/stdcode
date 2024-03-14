# Table of Contents
1. [coding_style](#coding_style)
2. [Naming](#naming)
3. [Functions](#functions)
4. [Loops/If statements](#loopsif-statements)
5. [Spacing](#spacing)
6. [File Organizations](#file-organizations)
7. [Future Considerations](#future-considerations)

# coding_style
> My personal C (and others) coding style standard. 

* Tab size **MUST** be **4**.
* Curly bracket `{` on the **NEXT LINE**. After functions, if statements, loops, structures, etc.
* Add spaces between operators and operands for clarity and consistency.

# Naming
* Naming conventions should be concise and descriptive. Generally, aim for brevity while maintaining clarity; avoid single-letter names unless contextually appropriate (e.g. `x`, `y`, `z` for coordinates).
* Use lowercase snake_case for functions, variables, structs, etc.
* Use SCREAMING_SNAKE_CASE for #define and enums.
* Use abbreviations frequently to maintain brevity, particularly when naming gets too long, but ensure they are commonly understood within the context of your codebase. If an abbreviation is uncommon, comment the full name near its definition for clarity.
* Append `_t` after typedefs.
* However, typedefing integers/floats to specific sizes (e.g. `i8`/`u8`, `i16`/`u16`, `i32`/`u32`, `i64`/`u64`, `f32`, `f64`) is acceptable.
* Place pointers `*` next to the type name, not variable name:
```c++
int* ptr; // Correct.
int *ptr; // Incorrect.
```
# Functions
* Use `void` in functions with no arguments.
* Enclose function bodies with curly brackets on the next line:
```c++
/* OK */
void func(void)
{
    /* Function body */
}

/* WRONG */
void func(){
    /* Function body */
}
```

# Loops/If statements
* Enclose if statements, loops, and do-while loops with curly brackets on the next line. For one-line code without curlies, indentation should align with the control statement.
```c++
/* OK */
if (condition)
{
    /* Multi-line code */
}
else if (condition)
{
    /* Multi-line code */
}
else
{
    /* Multi-line code */
}

if (condition)
    /* One line code and no curlies OK */
else if (condition)
    // ...
else
    // ...

for (int i = 0; i < 10; i++)
{
    /* Multi-line code */
}

for (int i = 0; i < 10; i++)
    /* One line code and no curlies OK */

while (condition)
{
    /* Multi-line code */
}

while (condition)
    /* One line code and no curlies OK */

do {
    /* Multi-line code */
} while (condition);
```
* Avoid placing curly brackets on the same line as the control statement.
```c++
/* WRONG */
if(condition){
    /* Multi-line code */
} else if(condition){
    /* Multi-line code */
} else {
    /* Multi-line code */
}

for(int i=0;i<10;i++){
    /* Multi-line code */
}
```
# Spacing
* Add spaces between operators and operands for clarity and consistency.
```c++
/* OK */
int x = a + b;
for (int i = 0; i < 10; i++);

/* WRONG */
int x=a+b;
for(int i=0;i<10;i++);
```

# File Organizations
### File naming
* File naming conventions should follow the same rules as the coding conventions: use lowercase and underscore `_` separators (i.e. snake_case).
### Directory structure
* Forbid placing source code in the project's root directory.
* Place source code in a directory named `src`.
* Place header files in directory named `include`.
* For different components' source code in your project, use structure: `$COMPONENT_NAME/src` directory.
* Libraries should reside in a directory called `lib` or `$COMPONENT_NAME/lib`.
* Build directory should be named `build` and git ingored.

```shell
# Project's root
/
|--- include/header.h
|--- src/csource.c
|--- lib/
|   |--- library_name/
|       |--- src/csource.c
|       |--- include/header.h
|--- build/
```
```shell
# Project's root
/
|--- server/
|   |--- src/
|   |--- include/
|   |--- lib/      # Libraries only used by component (e.g. server)
|--- client/
|   |--- src/
|   |--- include/
|--- lib/          # Common libraries used by more than one component
|--- build/
```
# Future Considerations
In this section, guidelines and practices are open to consideration for potential inclusion in future updates to the coding style standard.
### Return Type and Function Name Separation
* Consider separating the return type of a function from the function name by placing them on different lines. For example:
```c++
int
add(int a, int b) 
{
    return a + b;
}

static const char*
function_name(void)
{
    /* Function body */
}
```
### Maximum Code Length
* Considering the inclusion of a guideline specifying a maximum code length, but it has not been decided yet. This guideline would impose a maximum limit on the number of characters per line or the total length of a code block.
### Commenting convention
* Considering adding a convention for consistent and descriptive comments.
