# Arrow Functions

1. Rewrite this function as a fat-arrow function:

        var add = function(a, b) {
          return a + b;
        }
        
        ```
        const add = (a, b) => a + b;
        
        ```

2. Rewrite this function as a fat arrow function:

        var square = function(x) {
          return x * x;
        }
        
        
        ```
        const square = x => x * x;
        ```

3. Rewrite this function as a fat arrow function:

        var pi = function(x) {
          return Math.PI;
        }
        
        
        ```
        const pi = x => Math.PI * x
        ```

4. Write a single-line fat arrow function `makeObj` that, given three
   arguments `a`, `b` and `c`, returns a single object with the
   parameters as values:

        let res = makeObj(1, 2, 3);
        console.log(res);              // {first: 1, second: 2, third: 3}
        
        ```
        const makeObj = (x, y, z) => { 
          let obj = new Object();
          obj.first = x;
          obj.second = y;
          obj.third = z;
          return obj;
        }
        
        const makeObj = (x, y, z) => { return {first: x, second: y, third: z}; };
        
        // DOES NOT COMPILE AS "{" is evaluated as a function body, that requires "return"
        const makeObj = (x, y, z) => {first: x, second: y, third: z};
        
        // Evaluate an instance with an object and return the object without evaluation
        const makeObj3 = (x, y, z) => ({first: x, second: y, third: z});
        ```
        
       
5. Given the array `[1, 2, 3, 4, 5, 6]`, use the Array `map()` function
   with an arrow function to generate the squares of the elements:

        console.log(squares);         // [1, 4, 9, 16, 25]

     ```
     [1, 2, 3, 4, 5, 6].map(x => x * x)
     
     ```
