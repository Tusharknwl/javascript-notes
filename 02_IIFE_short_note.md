# Short Note on IIFE (Immediately Invoked Function Expression)

- **Definition**: 
  - An IIFE (Immediately Invoked Function Expression) is a JavaScript function that is executed immediately after it is defined and ***used for Creating a new scope for variables and to avoid polluting the global namespace.***

- **Purpose**:
  - Encapsulation: Variables declared inside an IIFE are scoped to the function, preventing namespace pollution and naming conflicts.
  - Avoiding Global Scope Pollution: Helps keep the global scope clean by not exposing variables unnecessarily.
  - Initialization: Useful for initializing code or executing setup tasks that need to run once.

- **Syntax**:
  ```javascript
  ;(function() {
      // IIFE code goes here
  })(); // IMP. to end iife with ; to separate it with other code
  
  //with arrow function
  ;(() => {
      //iife code here
    })();

- **Importance to start IIFE with ;**
  - When an IIFE is not preceded by a semicolon, it may be concatenated with the preceding code, causing unintended behavior. Here's an example to illustrate this:

    ```javascript
      // Without semicolon
      var x = 10

      (function() {
          console.log(x); // Output: undefined
      })();
    
  - In this case, `console.log(x)` throws an error because `x` is `undefined`. This happens because the code is interpreted as `(var x = 10)(function() {...})();`, which is not what we intended.
  - By starting the IIFE with a semicolon, we ensure it is treated as a separate statement, and x is properly accessed within the function. This practice helps avoid potential syntax errors and ensures code clarity and reliability.
    ```javascript
    var x = 10

    ;(function() {
       console.log(x); // Output: 10
    })();

  
