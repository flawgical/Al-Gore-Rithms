# Al ' Gore ' Rithms

Just Solving Algorthms For fun - From Basic to Advanced!

![algorerythim](images/algorerithm.jpg)


<hr>

### Convert From Celcius to Fahrenheit

The algorithm to convert from Celsius to Fahrenheit is the temperature in Celsius times 9/5, plus 32.

```js
function convertToF(celsius) {
  return celsius * 9/5 + 32;
}
```


<hr>

### Reverse A String 

Reverse the provided string.

You may need to turn the string into an array before you can reverse it.

Your result must be a string.

```js
function reverseString(str) {
  return str.split("").reverse().join("");
}
```


<hr>

### Factorialize A Number

Return the factorial of the provided integer.

If the integer is represented with the letter n, a factorial is the product of all positive integers less than or equal to n.

Factorials are often represented with the shorthand notation n!

```js
function factorialize(num) {
  if(num === 0) return 1
  return num * factorialize(num - 1);
}
```


<hr>

### Find The Longest Word In A String

Return the length of the longest word in the provided sentence.

Your response should be a number.

```js

function findLongestWordLength(str) {
  return str.split(" ").sort((a, b) => (
    b.length - a.length)
    )[0].length
}
```

<hr>

### Return Largest Numbers in Arrays

Return an array consisting of the largest number from each provided sub-array. 
For simplicity, the provided array will contain exactly 4 sub-arrays.


```js
function largestOfFour(arr) {
  return arr.map(elem => Math.max(...elem));
}
```

<hr>

### Confirm The Ending

Check if a string (first argument, str) ends with the given target string (second argument, target).

```js

// This could have also been solved with .endswith() as well

function confirmEnding(str, target) {
  return str.split("").join("")
  .substr(str.length - target.length) === target
}
```

<hr>

### Repeat a String Repeat a String

Repeat a given string str (first argument) for num times (second argument). Return an empty string if num is not a positive number.

```js
function repeatStringNumTimes(str, num) {
  return num <= 0 ? "" 
  : 
  new Array(num).fill(str).join("")
}
```

<hr>

### Truncate a String

Truncate a string (first argument) if it is longer than the given maximum string length (second argument). 

Return the truncated string with a ... ending.

```js
function truncateString(str, num) {
  return num < str.length ? 
  str.substr(0, num) + "...":
  str;
}
```

<hr>

### Finders Keepers

Create a function that looks through an array (first argument) and returns the first element in the array that passes a truth test (second argument). 
If no element passes the test, return undefined.

```js
function findElement(arr, func) {
  return arr.filter(num => func(num))[0];
}

findElement([1, 2, 3, 4], num => num % 2 === 0);
```

### Boo who

Check if a value is classified as a boolean primitive. Return true or false.

Boolean primitives are true and false.s

```js
function booWho(bool) {
  return typeof bool === "boolean";
}
```