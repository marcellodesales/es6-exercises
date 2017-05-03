# Iterators and for…of

## Getting Started with Iterators

1. In the Chrome console, create an array `arr1` and assign it to a variable.

   What is the type of `arr1[Symbol.iterator]`?

typeof 

2. Assign the result of calling `arr1[Symbol.iterator]()` to a variable, `it1`.

   1. What is its type?

object
   
   2. Inspect it. What fields does it have?
   
```javascript
Object.getPrototypeOf(it1)
function () { [native code] }
arr1[Symbol.iterator]
function values() { [native code] }
let it2 = arr1[Symbol.iterator]()
undefined
it2
Array Iterator {}
```

3. Call `it1.next()`. What is returned? Call it again and again until you reach the end of the array, and note how you are informed of the reaching the end.


```javascript
it2.next
function next() { [native code] }
it2.next()
Object {value: 1, done: false}
it2.next()
Object {value: 2, done: false}
it2.next()
Object {value: 3, done: false}
it2.next()
Object {value: undefined, done: true}
typeof arr1[Symbol.iterator]()
"object"
 
```


4. For each of the following values, (1) investigate the `myObject[Symbol.iterator]` property, and (2) call the iterator's `next()` function a few times to retrieve its values, and (3) use the `for...of` statement to iterate over the values:

    1. A `String`, eg `"abcd"`.
    
    "abcd"[Symbol.iterator ]
function [Symbol.iterator]() { [native code] }
    
    2. A `Set`.

```javacript
new Set()[Symbol.iterator]()

```
    
    3. A `Map`. What value is returned by the iterator each time?

```javascript

```
    
    4. A `TypedArray`.
    5. Are plain objects iterable?

## Consuming _iterables_

You've already used the `for...of` loop to consume iterables.
Investigate some other ways:

- Destructuring using an Array pattern
- `Array.from()``
- The spread operator
- Constructors of Maps and Sets


## Creating your own _iterator_

1. Write a function `makeIntIterator` that can be used as follows:

    ```
    let it = makeIntIterator(4);    // count of 4
    it.next();                      // {value: 0, done: true}
    it.next();                      // {value: 1, done: true}
    it.next();                      // {value: 2, done: true}
    it.next();                      // {value: 3, done: false}
    ```

## Creating your own _iterable_

1. Create an object which conforms to the _iterable_ interface. The object should return an iterator that returns integers in increasing value, stopping after 10 such values.
2. Consume these values using the `for...of` loop, and then the four other methods listed above.
