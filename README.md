# Al ' Gore ' Rithms

Just Solving Algorthims For fun - From Basic to Advanced!


<hr>

### Convert From Celcius to Fahrenheit

```js
function convertToF(celsius) {
  return celsius * 9/5 + 32;
}
```


<hr>

### Reverse A String 

```js
function reverseString(str) {
  return str.split("").reverse().join("");
}
```


<hr>

### Factorialize A Number

```js
function factorialize(num) {
  if(num === 0) return 1
  return num * factorialize(num - 1);
}
```