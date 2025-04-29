
We know two different data types: numbers and strings. For example, we can add numbers, because addition is an operation for the "numbers" type.

But what if you add a number to a string?

```javascript
console.log(1 + '7'); // => '17'
```

Even though `'7'` is a string, the JavaScript interpreter returned `17` as if we were adding two strings. When JavaScript notices a type mismatch, it tries to convert the data. In our case, it converts the number `1` to a string `'1'` and then just concatenates `'1'` and `'7'`.

Not all languages can do this. JavaScript is a weakly typed language. It recognizes different data types (numbers, strings, etc.), but doesn't use them too strictly, trying to convert data when it seems reasonable. JavaScript sometimes even rushes into extremes. Most expressions that don't work in other languages work perfectly well in JavaScript. Try to perform any arithmetic operation (except addition) with strings or another data type (except when both operands are numbers or strings consisting only of numbers). You will see that they always work and return `NaN`, which makes sense.

```javascript
const result = 'one' * 'two';
console.log(result); // => NaN
```

In **strongly typed** languages, adding a number to a string won't work.

JavaScript was created for the Internet, where all information is stored in strings. Even when you type a phone number or a birth year on a website, that information goes to the server as a string, not as a number. So the designers of the language decided that automatic type conversion is suitable and convenient.

This tacit automatic type conversion is indeed convenient. But in practice, this feature causes a lot of errors, which are difficult to find. The code may work or fail, depending on whether you are lucky enough for the automatic conversion to have been done correctly. A programmer may not notice this immediately.

You will encounter these cases more than once in further tasks. You'll often ask "Why doesn't my code work the way I expect?"

Weak typing runs like a thread through the whole Javascript development process.
