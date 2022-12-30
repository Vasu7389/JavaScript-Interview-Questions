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
