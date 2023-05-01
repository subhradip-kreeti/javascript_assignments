# What is an IIFE (Immediately Invoked Function Expression) and why would you use it in JavaScript? Give an example of IIFE.

IIFE stands for Immediately Invoked Function Expression. It is a function that is defined and called immediately. This type of function is often used to create a local scope and avoid polluting the global scope with variables and functions.

Here's an example of an IIFE in JavaScript:
```javascript
(function () {
  // code...
})();
```
In this example, the function is defined inside a pair of parentheses, which creates a function expression. The function is then immediately invoked by appending another pair of parentheses at the end of the expression.

Here's a more concrete example that demonstrates the benefits of using an IIFE to create a local scope:
```javascript
// Global variable
let count = 0;

(function () {
  // Local variable
  let count = 1;

  console.log(`Local count: ${count}`); // Output: Local count: 1
})();

console.log(`Global count: ${count}`); // Output: Global count: 0
```
In this example, there is a global variable count with a value of 0. Inside the IIFE, a local variable count is declared with a value of 1. When the IIFE is executed, the local count variable is logged to the console, which outputs 1. After the IIFE completes, the global count variable is logged to the console, which outputs 0. This demonstrates how an IIFE can create a local scope that is isolated from the global scope, allowing you to define and use variables without affecting the global state of your program.

# What is the purpose of using the bind() method in JavaScript and how is it different from call() and apply()?

With the call() method, you can write a method that can be used on different objects.

with apply() you can do same like call but you can pass arguments as a array to that function.

bind is used to call any function like call and apply but it will not be invoked immedietly , you can store that in a variable and can invoke that later.

```javascript
let userDetails = {
  name:"subhradip",
  company:"kreeti Technologies pvt ltd"
}

let userDetails2 = {
  name:"Shoham",
  company:"NRI Fintech"
}

function printDetails(){
  console.log(this.name +" is working in "+this.company);
}

function printAddress(city,state){
  console.log(this.name +" is working in "+this.company);
  console.log("currently staying in : "+city+", "+state);
}
//call

printDetails.call(userDetails);
printDetails.call(userDetails2);

//apply

printAddress.apply(userDetails,["kolkata","west bengal"])

//bind

let newfun = printAddress.bind(userDetails2,["Newtown","west bengal"])
newfun();

// output :
// subhradip is working in kreeti Technologies pvt ltd
// Shoham is working in NRI Fintech
// subhradip is working in kreeti Technologies pvt ltd
// currently staying in : kolkata, west bengal
// Shoham is working in NRI Fintech
// currently staying in : Newtown,west bengal

```
# What is a Higher-Order Function (HOF) in JavaScript and how is it different from regular functions? Explain with an example.

Higher order functions are functions that operate on other functions, either by taking them as arguments or by returning them. In simple words, A Higher-Order function is a function that receives a function as an argument or returns the function as output.

example : Array.prototype.map, Array.prototype.filter and Array.prototype.reduce are some of the Higher-Order functions built into the language.

this is a example of a higher-order function (using map method)
```javascript
const arr1 = [1, 2, 3];
const arr2 = arr1.map(function(item) {
  return item * 2;
});
console.log(arr2);
```
# Write a function called multiplyBy that takes a number as input and returns a new function that multiplies any number passed into it by the original number.


```javascript
function multiplyBy(num) {
  return function(x) {
    return num * x;
  }
}

const multiplyByFive = multiplyBy(5); // returns a new function that multiplies by 5
console.log(multiplyByFive(2)); // prints 10
console.log(multiplyByFive(3)); // prints 15
console.log(multiplyByFive(4)); // prints 20
```
# Write a function named sortArray that takes in two parameters:
# An array of numbers
# A boolean value ascending that indicates whether the array should be sorted in ascending or descending order.

```javascript
function sortArray(numbers, ascending) {
  if (ascending) {
    return numbers.sort((a, b) => a - b);
  } else {
    return numbers.sort((a, b) => b - a);
  }
}

const numbers = [3, 1, 4, 1, 5, 9, 2, 6, 5, 3, 5];
console.log(sortArray(numbers, true));  // [1, 1, 2, 3, 3, 4, 5, 5, 5, 6, 9]
console.log(sortArray(numbers, false)); // [9, 6, 5, 5, 5, 4, 3, 3, 2, 1, 1]
```
# The sortArray function should return the sorted array. Use an anonymous function to do the actual sorting, rather than using the built-in sort method.

```javascript
function bubbleSort(arr) {
  const n = arr.length;

  for (let i = 0; i < n; i++) {
    for (let j = 0; j < n - i - 1; j++) {
      if (arr[j] > arr[j + 1]) {
        const temp = arr[j];
        arr[j] = arr[j + 1];
        arr[j + 1] = temp;
      }
    }
  }

  return arr;
}

const numbers = [3, 1, 4, 1, 5, 9, 2, 6, 5, 3, 5];

console.log(bubbleSort(numbers));
```
