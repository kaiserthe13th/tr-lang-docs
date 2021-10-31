# Specification

## Datatypes

### Strings

```py
"This is a string\n"
'Hello, World!\n'
```

### Number

```py
10328
142.32
```

### Boolean

```py
doğru
yanlış
```
## Keywords

### de
used to display datatypes to the screen
```py
"Hello, World!\n" de
1232 de ' ' de
doğru de
```
#### Stdout
```stdout
Hello, World!
1232 doğru
```

### kpy
copies a variable
```py
10 kpy de de
```

### ise
if statement in tr-lang
check conditions!
```py
10 0 > ise
  "Hello\n" de
son
```

### yoksa
else statement in tr-lang
What dould you do if `if` was wrong?
```py
10 0 < ise
  "How did we get here?\n" de
yoksa
  "The universe still works!\n" de
son
```

### iken
while statement in tr-lang
they are used to repeat something on a condition.
```py
10
:. kpy 0 > iken
  kpy de
son
```

### işlev
functions in tr-lang
they are reusable bits of code that you can call.
However unlike most other programming languages functions, functions in tr-lang do not take arguments.
Rather than taking special arguments they instead can interact with the stack as any other part of the program.
```py
işlev recursive-sum-up-to
  kpy 0 > ise
    kpy -- recursive-sum-up-to +
  son
son

5 recursive-sum-up-to de "\n" de
```

#### Stdout
```
15
```

### son
ends an if-else, while or function block

## Comments
so how do you comment code? just start a block comment with `-*` and end it with `*-`
```
-* This will be ignored by tr-lang *-
-* "This won't do anything" de *-
```
