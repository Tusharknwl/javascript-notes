**Scope:**

- Scope refers to the region of a program where a variable is recognized and accessible.
- `var`  variables are function-scoped, while `let`  and `const`  are block-scoped.
```node.js
var x = 10;
{
    var x = 20; // This shadows the outer variable x
}
console.log(x); // Output: 20

let y = 30;
{
    let y = 40; // This does not shadow the outer variable y
}
console.log(y); // Output: 30
```
- Shadowing occurs when a variable declared in an inner scope overlaps with a variable in an outer scope.
```node.js
let y = 30;
{
    let y = 40; // This does not shadow the outer variable y
}
console.log(y); // Output: 30

var x = 10;
{
    let x = 20; 
    console.log(x) // Output: 20
}
console.log(x) // Output: 10
```
- Illegal shadowing happens when a `var`  variable attempts to shadow a `let`  or `const`  variable.
```node.js
let x = 10;
{
    var x = 20; // Error: Identifier 'x' has already been declared
    console.log(x)
}
console.log(x)
```
**Declaration:**

- `var`  can be redeclared within the same scope, but `let`  and `const`  cannot.
- `let`  and `const`  can shadow `var`  variables in a different scope.
- `const`  must be initialized with a value upon declaration; it cannot be declared without initialization.


**Initialization:**

- `var`  and `let`  variables can be updated after initialization, but `const`  cannot.
- `const`  variables are read-only and cannot be reassigned; attempting to do so will result in an error.
  
**Hoisting:**

- Hoisting refers to the JavaScript engine moving variable and function declarations to the top of the code.
- `var`  variables are hoisted and initialized with `undefined` .
- `let`  and `const`  variables are hoisted in temporal dead zone but remain uninitialized until their actual declaration. throw referential error
- The temporal dead zone is the period between the declaration and initialization of `let`  and `const`  variables, during which accessing them will result in an error. (in the scope but not yet declared)


