---
title: "Tricky Javascript Code Snippets Asked in the Interview (es6/es7/es8/es9)"
description: "Prepare for your next 2023 JavaScript interview with these tricky code snippets. Covering ES6/ES7/ES8/ES9 syntax and features, this article provides examples and explanations to help you ace your interview."
githubPath: "https://github.com/Vasu7389/JavaScript-Interview-Questions-2023"
---

<span style=" font-size: 0.8rem; border-bottom: 1px solid grey;"> Updated Dec 31, 2022 </span>

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
