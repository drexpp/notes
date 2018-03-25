March 2018
==========

Tech
----

### Introduction to JavaScript and ECMAScript6



* Difference between **`var, let and const`**
   - **Var**: Declare a variable, it is weak in ECMAScript 6, since the variable might or might not be reassigned. (Use `var` for variables within the scope of a function, but can also be used outside of a function)
   - **Let**: Its use is limited to block-scope, they are more specific about errores, better suited than  `var`
   - **Const**: Protect variables from being overwritten, `const` and `let` are block-scoped. `Const` allows mutability if the object or data structure is mutable (for example `Array`)
   

- Use of **`this`** [You don't know JS](https://github.com/getify/You-Dont-Know-JS/blob/master/this%20%26%20object%20prototypes/)
   - `This` does not, in any way, refer to a function's lexical scope. If you create variable `a` within a function, you can't call `a` within another function with the use of `this`
   - In JavaScript the value of `this` is determined mostly by the invocation context of function, by this I mean, that we have to look to the function stack of declarations, to see how the original function did use of `this`, not just inside the function where `this` is declared
   - If strict mode is in effect (inside the function where `this` is used), the global object is not eligible for the default binding, so the this is instead set to undefined
   - They both take, as their first parameter, an object to use for the this, and then invoke the function with that this specified. Since you are directly stating what you want the this to be, we call it explicit binding.
   Hard binding will work in any case: We create a function bar() which, internally, manually calls foo.call(obj), thereby forcibly invoking foo with obj binding for this. No matter how you later invoke the function bar, it will always manually invoke foo with obj
   - 
