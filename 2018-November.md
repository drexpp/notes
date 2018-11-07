November 2018
==========

Tech
----


### Go

  - Assign variables
```
// First option
var e int
e = 10
// e = 10

//Second option, in this case go infers the type of the variable
x := 3
x = 4
// x = 4

//This will print error
x := 1
x := 2
// COMPILER ERROR:
// no new variables on left side of :=
```
