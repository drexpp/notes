March 2018
==========

Tech
----

### JavaScript and ECMAScript6



* Difference between **`var, let and const`**
   - **Var**: Declare a variable, it is weak in ECMAScript 6, since the variable might or might not be reassigned. (Use `var` for variables within the scope of a function, but can also be used outside of a function)
   - **Let**: Its use is limited to block-scope, they are more specific about errores, better suited than  `var`
   - **Const**: Protect variables from being overwritten, `const` and `let` are block-scoped. `Const` allows mutability if the object or data structure is mutable (for example `Array`)
   

- Use of **`this`** [You don't know JS](https://github.com/getify/You-Dont-Know-JS/blob/master/this%20%26%20object%20prototypes/)
   - `This` does not, in any way, refer to a function's lexical scope. If you create variable `a` within a function, you can't call `a` within another function with the use of `this`
   - In JavaScript the value of `this` is determined mostly by the invocation context of function, by this I mean, that we have to look to the function stack of declarations, to see how the original function did use of `this`, not just inside the function where `this` is declared
   - If strict mode is in effect (inside the function where `this` is used), the global object is not eligible for the default binding, so the this is instead set to undefined
   - They both take, as their first parameter, an object to use for the this, and then invoke the function with that this specified. Since you are directly stating what you want the this to be, we call it explicit binding
   Hard binding will work in any case: We create a function bar() which, internally, manually calls foo.call(obj), thereby forcibly invoking foo with obj binding for this. No matter how you later invoke the function bar, it will always manually invoke foo with obj
   - var bar = foo.bind( obj ); or call( obj) for instace will do the trick
* Use array spreads `...` to copy arrays. (`const itemsCopy = [...items]`)

### Node.js

* Use of **require()** in Node.js
   - Require acts like a javascript library, adding a set of functions that you can include in your application. Works as an import in other languages.


### Vim
* Indexing
   - If you don't know how many lines in advance (it may be quite large), you can use ranges. Go to the first line of the range and enter **`ma`** to place marker A. Then go to the last line and enter **`>'a`** to indent from here to marker
   - Alternatively, if you know that you want to adjust three lines, you can simply: Type 3>> to shift right or 3<< to shift left OR
   Type >2j to shift right or <2j to shift left.
* Folding
   - Press **`zf`** to fold, and **`zo`** to open. You can also add **`zf3j`** to fold the next 3 lines including the actual one.
   - Ctrl+Q you enter in Vim's visual mode. Using :, once you have selected your piece of code, we can write `sort` and the lines selected within the visual block will be sorted.
