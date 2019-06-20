# Al ' Gore ' Rithms

Just Solving Algorithms For fun - From Basic to Advanced! 

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
  if(num === 0) return 1;
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
  )[0].length;
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
  .substr(str.length - target.length) === target;
}
```

<hr>

### Repeat a String Repeat a String

Repeat a given string str (first argument) for num times (second argument). Return an empty string if num is not a positive number.

```js
function repeatStringNumTimes(str, num) {
  return num <= 0 ? "" 
  : 
  new Array(num).fill(str).join("");
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

Boolean primitives are true and false

```js
function booWho(bool) {
  return typeof bool === "boolean";
}
```

<hr>

###  Title Case a Sentence

Return the provided string with the first letter of each word capitalized. Make sure the rest of the word is in lower case.

For the purpose of this exercise, you should also capitalize connecting words like "the" and "of".

```js
function titleCase(str) {
  return str
    .toLowerCase()
    .split(" ")
    .map(substr => (
      substr.replace(substr.charAt(0),
        substr.charAt(0).toUpperCase())
    ))
    .join(" ");
}
```

<hr>

### Slice and Splice

You are given two arrays and an index.

Use the array methods slice and splice to copy each element of the first array into the second array, in order.

Begin inserting elements at index n of the second array.

Return the resulting array. The input arrays should remain the same after the function runs.

```js
function frankenSplice(arr1, arr2, n) {
  let newArr = [...arr2];
  newArr.splice(n, 0, ...arr1); 
  return newArr;
}
```

<hr>

### Where do I Belong

Return the lowest index at which a value (second argument) should be inserted into an array (first argument) once it has been sorted. The returned value should be a number.

For example, getIndexToIns([1,2,3,4], 1.5) should return 1 because it is greater than 1 (index 0), but less than 2 (index 1).

Likewise, getIndexToIns([20,3,5], 19) should return 2 because once the array has been sorted it will look like [3,5,20] and 19 is less than 20 (index 2) and greater than 5 (index 1).

```js
function getIndexToIns(arr, num) {
  arr.sort((a, b) => a - b)
  for(let elem of arr){
    if(elem >= num) return arr.indexOf(elem);
  }
  return arr.length;
}
```

<hr>

### Mutations

Return true if the string in the first element of the array contains all of the letters of the string in the second element of the array.

For example, ["hello", "Hello"], should return true because all of the letters in the second string are present in the first, ignoring case.

The arguments ["hello", "hey"] should return false because the string "hello" does not contain a "y".

Lastly, ["Alien", "line"], should return true because all of the letters in "line" are present in "Alien".

_Not the most elegant solution_ 🤦‍♂️

```js
function mutation(arr) {
	let counter = 0;
 	let arr2 = arr.splice(1,1);
	arr2 = arr2.join("").toLowerCase().split("");
	arr = arr.join("").toLowerCase().split("");
	arr2.forEach(elem => (
	arr.includes(elem) && counter++));
	return counter === arr2.length;
}
```

<hr>

### Bubble Sort

Bubble sort is one of the simplest sorting algorithms to write but not the most efficient by any means.

This algorithm will travese a given array and compare the element in the current iteration to the element in the next iteration. If the current element is larger than the next element, the algorithm will swap these elements in place until reaching the end of the array. There must also be some sort of mechanism in place to repeat this process until all the element values are sorted in the given array from smallest to largest. In the recursion section, I've solved this as well using a recursive solution

##### Big O Analysis 
  
1. We have one loop nested inside another so this would be a time complexity of: `O(n^2)`

2. Since we're not having to create anymore space for the array we're sorting in place we get a space complexity of: `O(1)`


```js
function bubbleSort(arr) {
	let swapped; 
	do {
		swapped = false; 
        for(var i = 0; i < arr.length - 1; i++){
            if(arr[i] > arr[i + 1]) {
                var temp = arr[i];
                arr[i] = arr[i + 1];
                arr[i + 1] = temp;
				swapped = true;
            }
        }
	} while (swapped)
	return arr;
}

```

<hr>

### Insertion Sort

Think of when you're playing poker (The card game), when provided a hand, we usually sort the card based on their values from right to left. When we see a card with a smaller value in front, we pick it up and move it all the way to the right, or to a position on the right we'd considered sorted relative to neighboring cards. When working with arrays, this behavior along with dividing the array into one side being sorted and another side being unsorted is what gives this ineffecient algorithm it's name. Did I say inefficient? Yes, that's right, this algorithm has the worst big O time complexity out there.

**Solution A**

```js
function insertionSort(arr) {
  const sortedArr = [...arr];
    for(let i = 0; i < sortedArr.length; i++) {
      let currentElement = arr[i];
      let j;
      for(j = i - 1; j >= 0 && sortedArr[j] > currentElement; j--) {
        sortedArr[j + 1] = sortedArr[j];
		  }
		  sortedArr[j + 1] = currentElement;
	  }
	return sortedArr;
}
```

**Solution B**

```js

function insertionSort(arr) {
  let sortedArr = [...arr];
  for(let i = 1; i < sortedArr.length; i++) {
    for(let j = 0; j < i; j++) {
      if(sortedArr[i] < sortedArr[j]) {
        let spliced = sortedArr.splice(i, 1);
        sortedArr.splice(j, 0, splice[0]);
			}
		}
	}
	return sortedArr;
}
```

*Both of these solutions preserve the original array*


##### Big O Analysis 

1. Space complexity - `O(1)` - because we're not creating more space - we're working on and returning one array

2. Time Complexity - `O(n^2)` - because for each iteration of `n` we must perform steps/iterations


<hr>



# Recursion Practice

### Find Max

Write a function returns the largest number in a given array.

I've also made it so that it will work with negative numbers as well!

```js
function findMax(arr, index = 0, max = -1){
  if(index === arr.length) return max;
  if(arr[index] > max) max = arr[index];
  return findMax(arr, ++index, max);
} 
```

<hr>

### Factorial

Write a function that returns the factorial of a given number

```js
function factorial(num){
  if(num === 0) return 1;
  return num * factorial(--num);
}
```

<hr>

## Fibonacci

This function returns the nth number in the fibonacci sequence.

I've written it so that any number can be passed and it would only return the last number in the fibonacci sequence up to nth.

<hr>

```js
function fibonacci(nth, first = 1, last = 1) {
  if(last > nth) {nth = first - last; return nth;}
  last = first + last;
  return fibonacci(nth, last, first);
}
```

<hr>

### Falling Distance in Meters
Write a function that returns the distance in meters an object has fallen in seconds

Design a program that calls the function in a loop that passes time values 1-10 (seconds) as args
```js
function fallingDistance(seconds = 1, distance = null) {
	if(seconds === 11) return;
	distance = .5 * (9.8 * Math.pow(seconds, 2));
	console.log(`After ${seconds} seconds, an object falls ${distance.toFixed(2)} meters`);
	return fallingDistance(++seconds, distance);
}

```

### Bubble Sort

Return a sorted array using the bubble sort principle (See above for explaination)

```js
function bubbleSort(arr, pointer = arr.length - 1) {
// 1 Define the base case - return a sorted array
if(pointer === 0) return arr;

// 2 Perform the action - make swaps
  for(var i = 0; i < arr.length - 1; i++){
       if(arr[i] > arr[i + 1]) {
           var temp = arr[i];
           arr[i] = arr[i + 1];
           arr[i + 1] = temp;
       }
  }

// 3 Recursively call the function again passing in the current state of array
	return bubbleSort(arr, --pointer);
}
```
  
<hr>

### Chunky Monkey

Write a function that splits an array (first argument) into groups the length of size (second argument) and returns them as a two-dimensional array.

```js
function chunkArrayInGroups(arr, size, newArr = []) {
  if(arr.length === 0) return newArr;
  newArr.push(arr.splice(0, size));
  return chunkArrayInGroups(arr, size, newArr);
}

chunkArrayInGroups(["a", "b", "c", "d"], 2);
```
