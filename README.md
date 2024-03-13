# coding_style
> My personal C (and others) coding style standard. 

* Tab size **MUST** be **4**.
* Curly bracket `{` on the **NEXT LINE**. After functions, if statements, loops, structures, etc.
* Add spaces between operators and operands for clarity and consistency.

# Naming
* Naming convetions should be concise and descriptive. Generally, aim for brevity while maintaining clarity; avoid single-letter names unless contextually appropiate (e.g. `x`, `y`, `z` for coordinates).
* Use lowercase snake_case for functions, variables, structs, etc.
* Use SCREAMING_SNAKE_CASE for #define and enums.
* Append `_t` after typedefs.
* However, typedefing intgers/floats to specific sizes (e.g. `i8`/`u8`, `i16`/`u16`, `i32`/`u32`, `i64`/`u64`, `f32`, `f64`) is acceptable.
* Place pointers `*` next to the type name, not variable name:
```c++
int* ptr; // Correct
int *ptr; // Incorrent
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

# Loops/if statements
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
### WRONG
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
### Spacing
* Add spaces between operators and operands for clarity and consistency.
```c++
/* OK */
int x = a + b;
for (int i = 0; i < 10; i++);

/* WRONG */
int x=a+b
for(int i=0;i<10;i++);
```
