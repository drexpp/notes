March 2018
==========

Tech
----

### Introduction to JavaScript and ECMAScript6



* Difference between **`var, let and const`**
   - **Var**: Declare a variable, it is weak in ECMAScript 6, since the variable might or might not be reassigned. (Use `var` for variables within the scope of a function, but can also be used outside of a function)
   - **Let**: Its use is limited to block-scope, they are more specific about errores, better suited than  `var`
   - **Const**: Protect variables from being overwritten, `const` and `let` are block-scoped. `Const` allows mutability if the object or data structure is mutable (for example `Array`)
   

- Use of **`this`** [You don't know JS](https://github.com/getify/You-Dont-Know-JS/blob/master/this%20%26%20object%20prototypes/ch1.md)
   - `This` does not, in any way, refer to a function's lexical scope. If you create variable `a` within a function, you can't call `a` within another function with the use of `this`
   - In JavaScript the value of `this` is determined mostly by the invocation context of function
