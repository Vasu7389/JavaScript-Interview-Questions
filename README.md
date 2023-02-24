---
title: "Tricky Javascript Code Snippets Asked in the Interview (es6/es7/es8/es9)"
description: "Prepare for your next 2023 JavaScript interview with these tricky code snippets. Covering ES6/ES7/ES8/ES9 syntax and features, this article provides examples and explanations to help you ace your interview."
githubPath: "https://github.com/Vasu7389/JavaScript-Interview-Questions-2023"
---

<span style=" font-size: 0.8rem; border-bottom: 1px solid grey;"> Updated Feb 25, 2023 </span>

In this article, we will cover a range of JavaScript interview questions, including those related to the latest versions of the language (ES6, ES7, ES8, and ES9).

We'll also compare the differences between ES5 and the newer versions of the language and provide examples of ES6 code snippets.

Additionally, we'll include multiple choice questions (MCQs) on ES6 and explore some of the trickiest code snippets that are commonly asked in JavaScript interviews.

Whether you're preparing for a job interview or simply want to brush up on your knowledge of the language, this article has something for you.

## Javascript ES6 ES7 ES8

ECMAScript (ES) is a standardized version of JavaScript, a programming language that is widely used to create interactive web pages and applications. ECMAScript is a formal specification developed and maintained by the Ecma International organization.

JavaScript is a programming language that is commonly used to create interactive web pages and applications. It is based on the ECMAScript specification and is an implementation of it. JavaScript is a client-side scripting language, meaning it is executed by the user's web browser rather than a server. It is used to create dynamic and interactive elements on web pages, such as form validation, image sliders, and modal windows.

ECMAScript and JavaScript are closely related, and the terms are often used interchangeably. However, ECMAScript is the formal specification, and JavaScript is the implementation of that specification.

<span style=" font-size: 0.5rem;"> \*Discover the answers by clicking on the questions.</span>

<details>
<summary>
    <h3>1. Guess the output of this code?

```js
let a = {};
let b = { key: "b" };
let c = { key: "c" };

a[b] = 123;
a[c] = 456;

console.log(a[b]);
```

</h3>
</summary>

The output of this code will be `456`.

In this code, a is an empty object that is being assigned properties using the square bracket notation. The values of the properties are being set to the numbers `123` and `456`. The keys of the properties are the objects b and c.

When the `console.log` statement is executed, it logs the value of the property of a whose `key` is the object `b`. In this case, the value of this property is 456, because the value of the property was last set to 456 when the object c was used as the key.

This behavior occurs because when objects are used as keys in an object, the object's default behavior is to convert the object to a string representation. In this case, both b and c are converted to the string `[object Object]`, which means that they both end up being used as the same key in the a object. As a result, the value of the property that is set using the object c as the key overwrites the value of the property that was set using the object b as the key.

So the object `a` looks like -

```js
{
    "[object Object]": 456
}
```

</details>

<details>
<summary>
    <h3>2. Guess the output of this code?

```js
let obj1 = { key: "value" };
let obj2 = obj1;
let obj3 = obj2;

obj1.key = "new value";
obj2 = { key: "another value" };

console.log(obj1.key, obj2.key, obj3.key);
```

</h3>
</summary>
The output of this code will be `new value` `another value` `new value`.

In this code, we are declaring three variables obj1, obj2, and obj3, and assigning an object to each of them. Then, we are reassigning a new object to obj2 and modifying a property of obj1.

When the console.log statement is executed, it logs the values of the key property for each object. The value of the key property for obj1 is "new value", the value of the key property for obj2 is "another value", and the value of the key property for obj3 is "new value".

This is because when an object is assigned to a variable, the variable stores a reference to the object in memory rather than the object itself. Changing the value of a property of the object using one variable will affect the value of that property when accessed using a different variable that references the same object. However, reassigning a new object to a variable will change the reference stored in that variable, so the original object is no longer accessible using that variable.

In this case, the value of the key property for obj1 was changed to "new value" using the obj1 variable, which affected the value of the key property when accessed using the obj3 variable, because both variables reference the same object. However, the value of the key property for obj2 was not affected, because the obj2 variable was reassigned to reference a new object.

</details>

<details>
<summary>
    <h3>3. Guess the output of this JavaScript code?

```js
const obj = {
  a: "foo",
  b: function () {
    console.log(this.a);
  },
};

const c = obj.b;

obj.b();
c();
```

</h3>
</summary>

Answer - foo, undefined

When the method obj.b is called directly on obj, the output will be "foo". This is because this refers to the object that the method is called on, and obj.a is equal to "foo".

When the variable c is assigned the value of obj.b, it is a reference to the function itself and not the object obj. When c is called, it is not called on an object, so this will not refer to obj and the value of this.a is undefined. As a result, the output when calling c() will be undefined.

</details>

<details>
<summary>
    <h3>4. Guess the output of this code?

```js
const x = { foo: 1 };
const y = { foo: 2 };

function addFoo(obj) {
  return obj.foo + 1;
}

console.log(addFoo(x));
console.log(addFoo(y));
```

</h3>
</summary>
Answer - 2, 3

The addFoo function takes an object as an argument and returns the value of obj.foo + 1. When addFoo is called with x as the argument, the output will be 2, because x.foo is equal to 1. When addFoo is called with y as the argument, the output will be 3, because y.foo is equal to 2.

</details>
<details>
<summary>
    <h3>5. Guess the output of below JavaScript code?

```js
const arr = [1, 2, 3, 4, 5];

for (var i = 0; i < arr.length; i++) {
  setTimeout(function () {
    console.log(i);
  }, 1000);
}
```

</h3>
</summary>
Answer - 5, 5, 5, 5, 5

The setTimeout function is called inside of a loop that iterates through the elements in the arr array. The setTimeout function will execute its callback function after a delay of 1000 milliseconds. However, by the time the delay has elapsed and the callback function is called, the loop will have already completed and the value of i will be 5. As a result, the output will be 5 printed five times.

</details>
<details>
<summary>
    <h3>6. Guess the output of this JavaScript code?

```js
const arr = [1, 2, 3, 4, 5];

arr.forEach(function (element) {
  console.log(element);
});
```

</h3>
</summary>
Answer - 1, 2, 3, 4, 5

The forEach method is called on the arr array and a callback function is passed as an argument. The callback function will be executed for each element in the array, with the element passed as an argument to the callback. As a result, the output will be the elements of the array, 1, 2, 3, 4, and 5, printed on separate lines.

</details>

<details>
<summary>
    <h3>7. Guess the output of this code?

```js
let x = 1;

if (function f() {}) {
  x += typeof f;
}

console.log(x);
```

</h3>
</summary>
Answer - 1undefined

The if statement is evaluating the function f as a boolean value. In JavaScript, functions are truthy values, so the condition will evaluate to true and the code block inside the if statement will be executed. The value of x is then incremented by the string "undefined", which is the result of calling typeof f.

</details>

<details>
<summary>
    <h3>8. Guess the output of this code?

```js
let a = {
  x: 1,
  y: 2,
};
let b = a;
a.x = 5;
console.log(a);
console.log(b);
```

</h3>
</summary>

Answer - {x:5, y:2} {x:5, y:2}

JavaScript objects are passed by reference. So when we assigned a object to b. b also pointing to the same object in memory. When we change the value of a.x it also affects b.x

</details>

<details>
<summary>
    <h3>9. Guess the output of this code?

```js
let x = [1, 2, 3];
let y = [1, 2, 3];
let z = y;

console.log(x == y);
console.log(x === y);
console.log(z == y);
console.log(z == x);
```

</h3>
</summary>
Answer -

false
false
true
false

When comparing two objects with the == operator, it compares their references, not their values. In this case, x and y are different objects with the same values. z is assigned the value of y, so they refer to the same object. As a result, the first comparison returns false, the second comparison also returns false and the third comparison returns true. and the last comparison also returns false.

</details>

<details>
<summary>
    <h3>10. Guess the output of the below JavaScript code?

```js
var x = 0;
for (let i = 0; i < 5; i++) {
  setTimeout(() => {
    x++;
    console.log(x);
  }, 1000);
}
```

</h3>
</summary>

Answer:

1
2
3
4
5

The for loop is iterating 5 times, and in each iteration, it is scheduling a function to be invoked after 1000 milliseconds (1 second) using setTimeout.
This function increments the value of `x` and logs it.

But all the 5 functions invoked after 1000 milliseconds.

Since, javascript is single threaded and event loop queue all the functions in the event loop and execute them one by one.

But inside each `setTimeout` callback execution, `x++` increments `x` value by 1.

_It makes difference when position of `x++` code changes wrt the setTimout callback._

So all the 5 `callbacks` logs the values in `incremental` way, which is `1 2 3 4 5`.

</details>

<details>
<summary>
    <h3>11. Guess the output of this JavaScript code?

```js
let a = { x: 1 };
let b = { x: 2 };
let c = { x: 3 };
let d = { x: 4 };
let e = { x: 5 };
let arr = [a, b, c, d, e];

arr.forEach((obj) => (obj.x = obj.x * 2));

console.log(a.x, b.x, c.x, d.x, e.x);
```

</h3>
</summary>
Answer:

2 4 6 8 10

The code is using the `forEach` method to iterate over an array of objects, and it is modifying the `x` property of each object by multiplying it by 2.

It's updating the original objects with `x*2` values.

So, the output of the code is 2 4 6 8 10.

</details>

<details>
<summary>
    <h3>12. Guess the output of the JavaScript code?

```js
let num = 0;

function test() {
  var num = 1;
  return num;
}

console.log(test());
console.log(num);
```

</h3>
</summary>
Answer:
1
0

The code defines a global variable num with the value of 0 and then a function test which declares a local variable num with the value of 1 and returns it.

When test() is called, it first declares a local variable num with the value of 1.

Then the function return statement logs 1 on the console.

After that, it logs the value of global variable num which is 0.

Because the global and local variables have different scope and different memory allocation.

</details>

<details>
<summary>
    <h3>13. Guess the output of the below JavaScript code?

```js
let obj = { name: "John", age: 25 };
let newObj = { ...obj, age: 30 };

console.log(obj.age);
console.log(newObj.age);
```

</h3>
</summary>
Answer:
25
30

The code creates an object obj with properties name and age. Then it creates a new object newObj using the spread operator to copy the properties of obj and then it updates the age property to 30.

The spread operator `...` creates a new object with properties copied from the original object.

So, the first console.log statement logs the value of age property of obj which is `25`.

And, the second console.log statement logs the value of age property of newObj which is `30`.

It doesn't affect the original object `obj`.

</details>

<details>
<summary>
    <h3>14. Guess the output of the below JavaScript code?

```js
const add = (a = 1, b = 2) => a + b;
console.log(add());
console.log(add(5));
console.log(add(undefined, 10));
```

</h3>
</summary>

Answer:

```bash
3
7
11
```

The code defines a function add which takes two parameters a and b and returns the sum of both. It uses default parameters to assign default values 1 to a and 2 to b if they are not provided.

So, the first console.log statement logs the result of add() which is 1 + 2 = 3 as both the parameters are not provided and default values are used.

The second console.log statement logs the result of add(5) which is 5 + 2 = 7 as only the first parameter is provided and the default value of b is used.

The third console.log statement logs the result of add(undefined, 10) which is 1 + 10 = 11 as the first parameter is provided as undefined and it takes the default value 1 and the second parameter is provided as 10.

</details>

<details>
<summary>
    <h3>15. Guess the output of the below JavaScript code?

```js
const name = "John";
const age = 25;

const user = { name, age };
console.log(user);
```

</h3>
</summary>

Answer:

```js
{ name: "John", age: 25 }
```

The code defines two variables name and age with values "John" and 25 respectively.

Then, it uses `object literal` notation to create an object user with properties `name` and `age` and the values are assigned from the variables name and age respectively.

So, the `console.log` statement logs the user object which is `{ name: "John", age: 25 }`.

In `ES6+`, you can use object literal notation to create objects with properties using the same name as the variables with the values assigned to them.

</details>

<details>
<summary>
    <h3>16. Guess the output of the below JavaScript code?

```js
const arr = [1, 2, 3];
const [a, b, c] = arr;

console.log(a);
console.log(b);
console.log(c);
```

</h3>
</summary>

Answer:

```bash
1
2
3
```

The code defines an array arr with values [1, 2, 3].

Then, it uses `destructuring assignment` to extract the values from the array `arr` and assign them to variables `a`, `b`, and `c` respectively.

So, the first console.log statement logs the value of a which is `1`.

The second console.log statement logs the value of b which is `2`.

The third console.log statement logs the value of c which is `3`.

In ES6+, you can use destructuring assignment to extract values from arrays and objects and assign them to variables in a concise way.

</details>

<details>
<summary>
    <h3>17. What is the output of the below JavaScript code and why?

```js
console.log(typeof null);
console.log(typeof undefined);
console.log(null === undefined);
console.log(null == undefined);
```

</h3>
</summary>
Answer:

```bash
object
undefined
false
true
```

`typeof null` returns object which is an error in JavaScript. This is a historical bug in the language that cannot be fixed without breaking existing code. So, to check for `null`, you should use `===` null instead of `typeof` operator.

typeof undefined returns undefined.

null === undefined is false because `null` and `undefined` are two distinct types in JavaScript.

null == undefined is true because `==` is the loose equality operator in JavaScript, which performs type coercion before comparison. In this case, both null and undefined are coerced to undefined before comparison, and since they both have the same value, the comparison returns true. However, it is generally recommended to use `===` instead of `==` to avoid unexpected behavior due to type coercion.

</details>

<details>
<summary>
    <h3>18. Write a function in JavaScript that takes an array of numbers and returns the sum of all positive numbers in the array.
</h3>
</summary>
Answer:

```js
function sumOfPositiveNumbers(numbers) {
  let sum = 0;
  for (let i = 0; i < numbers.length; i++) {
    if (numbers[i] > 0) {
      sum += numbers[i];
    }
  }
  return sum;
}

// Example usage:
const arr = [1, -2, 3, 4, -5, 6];
console.log(sumOfPositiveNumbers(arr)); // Output: 14
```

The `sumOfPositiveNumbers` function takes an array of numbers as its parameter and initializes a variable sum to `0`. It then loops through each element of the array and checks if the number is greater than 0. If the number is positive, it adds the number to the sum. Finally, it returns the sum of all positive numbers in the array.

In the example usage, we pass an array `[1, -2, 3, 4, -5, 6]` to the sumOfPositiveNumbers function. The function returns the sum of all positive numbers in the array, which is `14`.

</details>

<details>
<summary>
    <h3>19. Write a function in JavaScript that takes a string as input and returns a new string with all the vowels removed.
</h3>
</summary>
Answer:

```js
function removeVowels(str) {
  const vowels = ["a", "e", "i", "o", "u", "A", "E", "I", "O", "U"];
  let newStr = "";
  for (let i = 0; i < str.length; i++) {
    if (!vowels.includes(str[i])) {
      newStr += str[i];
    }
  }
  return newStr;
}

// Example usage:
const str = "This is a test string with vowels";
console.log(removeVowels(str)); // Output: Ths s  tst strng wth vwls
```

The `removeVowels` function takes a string as its parameter and initializes an array vowels containing all the vowels. It then loops through each character of the input string and checks if the character is not present in the vowels array. If the character is not a vowel, it adds the character to the `newStr` string. Finally, it returns the newStr string with all the vowels removed.

In the example usage, we pass a string 'This is a test string with vowels' to the removeVowels function. The function returns a new string with all the vowels removed, which is 'Ths s tst strng wth vwls'.

</details>

<details>
<summary>
    <h3>20. Write a function in JavaScript that takes an array of strings as input and returns a new array with the strings sorted in alphabetical order.
</h3>
</summary>
Answer:

```js
function sortStrings(arr) {
  return arr.sort();
}

// Example usage:
const strings = ["apple", "banana", "cherry", "date", "elderberry"];
console.log(sortStrings(strings)); // Output: ['apple', 'banana', 'cherry', 'date', 'elderberry']
```

The `sortStrings` function takes an array of strings as its parameter and uses the `sort()` method to sort the array in alphabetical order. The sort() method sorts the elements of an array in place and returns the sorted array. By default, the sort() method sorts the array elements in ascending order based on the `Unicode` values of the characters. Therefore, for strings, it sorts them in alphabetical order.

In the example usage, we pass an array of strings `['apple', 'banana', 'cherry', 'date', 'elderberry']` to the sortStrings function. The function returns a new array with the strings sorted in alphabetical order, which is `['apple', 'banana', 'cherry', 'date', 'elderberry']`.

</details>
