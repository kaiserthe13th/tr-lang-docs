# Language Specification

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

### None

```py
hiç
```

### Block
```py
blok block-name
  3 -> a
  5 -> b
son
```

## Keywords

### yükle
imports or includes a module
#### Including
you can think of including as copy-pasting the code in the module
```py
yükle "my-module"* # notice the star
```
#### Importing
importing is different however as it creates what we call named modules.
you can use them under their names in this case.
This is what we recommend you to use, especially when dealing with third-party modules.
```py
yükle "my-module" -> my-module
# imports "my-module" inside a variable called my-module
```

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
> :memo: You can use `?` instead

```py
10 > 0 ise
  "Hello\n" de
son
```

### yoksa
else statement in tr-lang
What dould you do if `if` was wrong?
> :memo: You can use `:?` instead

```py
10 < 0 ise
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
:. kpy > 0 iken
  kpy de '\n' de --
son at
```
#### Stdout
```
10
9
8
7
6
5
4
3
2
1
```

### işlev
functions in tr-lang
they are reusable bits of code that you can call.
They have their own stack and namespace.
They can return the last variable on the stack using the `ver` keyword.
```py
işlev recursive-sum-up-to -> a
  a > 0 ise
    a + (a --)recursive-sum-up-to ver
  yoksa
    0 ver
  son
son

5 recursive-sum-up-to de "\n" de
```

#### Stdout
```
15
```

### ver
returns the last value in the stack from a function
> Look above for an example in code

### son
ends an if-else, while, block<sup>(confusing isn't it?)</sup> or function block
> :memo: you can use `=?` instead

### üst
copy the variable second to last
```py
10 5 üst -* same as 10 5 10 *-
```

### tks
swap the last variable on stack with the second last
```py
32 64 tks -* same as 64 32 *-
```

### girdi
take input from user as string
```py
"What's your name? " de girdi -* Terminal: What's your name? [some input from user] *-
"Your name is " de de ".\n" de -* Terminal: Your name is [some input from user]. *-
```

### dön
rotate last three elements on the stack
```py
10 20 30 dön -* same as 30 20 10 *-
```

### at
dispose last element on the stack
```py
3 at de
```
#### Stderr
```

[ERROR] <FILE>, Line 1, Column 8
    NotEnoughVarsInStack: because there weren't enough variables in the stack, the operator `de` couldn't be used
```

## Operators

### Maths

#### Plus
just an addition operator. But it can also concat strings together
```py
40 + 20 de "\n" de
"a" + "b" de
```

##### Stdout
```
60
ab
```

#### Minus
substraction operator
```py
40 - 20 de
```

##### Stdout
```
20
```

#### Star
multiplication operator
```py
40 * 20 de
```

##### Stdout
```
800
```

#### Slash
division operator
```py
40 / 20 de
```

##### Stdout
```
2
```

#### Percent Sign
modulo operator
```py
40 % 20 de '\n' de
30 % 20 de
```

##### Stdout
```
0
10
```

### Comparison

#### Equal
checks if two things are equal
```py
10 = 10 de '\n' de
10 = 11 de
```
##### Stdout
```
doğru
yanlış
```

#### Not Equal
checks if two things are **not** equal
```py
10 != 10 de '\n' de
10 != 11 de
```
##### Stdout
```
yanlış
doğru
```

#### Greater
checks if a is greater than b
```py
10 > 9 de '\n' de
10 > 11 de
```
##### Stdout
```
doğru
yanlış
```

#### Greater or Equal
checks if a is greater than b or a equals b
```py
10 >= 10 de '\n' de
10 >= 11 de
```
##### Stdout
```
doğru
yanlış
```

#### Lesser
checks if a is lesser than b
```py
10 < 11 de '\n' de
10 < 9 de
```
##### Stdout
```
doğru
yanlış
```

#### Lesser or Equal
checks if a is greater than b or a equals b
```py
10 <= 9 de '\n' de
10 <= 10 de
```
##### Stdout
```
yanlış
doğru
```

#### Not
negation operator
```py
!yanlış de '\n' de
!doğru de
```
##### Stdout
```
doğru
yanlış
```

#### And
and operator
```py
doğru ve doğru de '\n' de
yanlış ve doğru de
```
##### Stdout
```
doğru
yanlış
```

#### Or
or operator
```py
yanlış veya doğru de '\n' de
yanlış veya yanlış de
```
##### Stdout
```
doğru
yanlış
```

### Assignment
the assignment operator assigns the last value in the stack to a identifier
```py
10 -> a
5 -> b
a de '\n' de
b de '\n' de
a + b de
```
#### Stdout
```
10
5
15
```

### Type Conversion
an operator to convert between data types
```py
3@yazı = '3' de
0@bool de
```
#### Stdout
```
doğru
yanlış
```

### Accessor
an operator to access fields of a block or named module
```py
yükle "math.trl" -> math # math.trl from tests/
blok my-block
  3 -> a
  5 -> b
son
my-block:a de '\n' de
my-block:b de '\n' de
4 math:factorial
```
#### Stdout
```
3
5
24
```

## Comments

### Block Comments
start a block comment with `-*` and end it with `*-`
```
-* This will be ignored by tr-lang *
 * "This won't do anything" de     *-
```

### Line Comments
start a line comment with `#`. it will last until the end of the line.
```py
# yup, ignored
```

