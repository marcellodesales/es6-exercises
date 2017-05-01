# Destructuring


1. Using destructuring, write a function that swaps
  its two input parameters without using a temporary
  variable. Test it.
  
```javascript
let swap = (a, b) => [b, a]
let swap = (...[a, b]) => [b, a]

```

2. Given this array:

        let arr1 = ['one', 'two', 'three', 'four', 'five', 'six', 'seven', 'eight'];

   Using a single destructuring assignment, assign to three variables, `a`, `b` and `c` so that `a` contains `one`, `b` contains `two`, and `c` contains all of the remaining parameters as an array.

```javascript
let [aa, bb, ...ccc] = arr1
undefined
aa
"one"
bb
"two"
ccc
["three", "four", "five", "six", "seven", "eight"]
````

3. What is the value of `p3` here?

        let phonetic = ['sierra', 'charlie'];
        let [p1, p2, p3 = "not provided"] = phonetic;
 
 ```javascript
 let [p1, p2, p3] = phonetic;
undefined
 ```

   How do you think you could _default_ `p3` to a suitable value?
   Try it.

```javascript
let [p11, p22, p33 = "not provided"] = phonetic;
```

4. Given this array:

        let arr1 = ['one', 'two', ['three', ['four', ['five', 'six', 'seven']], 'eight']];

   Create a destructuring pattern to give this result:

        console.log(m, n, o);       // two six eight

```javascript
        ['one', 'two', ['three', ['four', ['five', 'six', 'seven']], 'eight']];
  const [, m, [, [, [ , n, ]], o]] = arr3;
```

5. Given this object:

        let stats = {
        	packetForwarded: 5345,
        	redirectSent: 427,
        	forwardCacheHit: 4821,
        	forwardCacheMiss: 524,
        };

   1. Use destructuring to assign variables such that:

          console.log(hits);            // 4821
          console.log(misses);          // 524
 
 ```javascript
 // creates the vars hits from the properties of the object
 let { forwardCacheHit: hits, forwardCacheMiss: misses} = stats;
 ```

    2. What happens when this line is executed? Why, and how would you fix it?

           { forwardCacheHit: myhits, forwardCacheMiss: mymisses } = stats;
 
 ```javascript
 declare the variable let 
 ```

6. Can you destructure a string? Try it.

```javascript
let [, vowel1, , , volwel2] = "Marcello"
vowel1
"a"
volwel2
"e"
```

7. These contrived functions connect to a server and extract
   data from a 'config' object:

       function connectTo(host, port) {
         console.log('Connecting to ' + host + ' on port ' + port);
       }

       function initialize(configObj) {
        var host = configObj.host;
        var port = configObj.port;

        connectTo(host, port);
       }

       initialize({host: 'localhost', port: 8080});


      1. Make suitable conversions to these functions by using ES6 syntax.
      2. If `host` or `port` are not provided, default
         them to `localhost` and `8080` respectively.

```javascript
       function connectTo(host, port) {
         console.log(`Connecting to ${host} on port ${port}`);
       }

    function initialize({host: "localhost", port: 80} => {}) {
        connectTo(host, port);
       }
````
