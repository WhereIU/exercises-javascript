
In the lesson on concatenation, we solved the task of creating an email header out of two constants and punctuation marks. You probably solved it this way:

```javascript
const firstName = 'Joffrey';
const greeting = 'Hello';

console.log(greeting + ', ' + firstName + '!');
// => 'Hello, Joffrey!'
```

It's a fairly simple task, but even here you should struggle to see what kind of string you end up with. You have to watch out for several quotation marks and spaces, and you can't tell where something starts and ends without paying attention.

There is a more convenient and elegant way to solve the same problem – **interpolation**. Here's what it looks like:

```javascript
const firstName = 'Joffrey';
const greeting = 'Hello';

// Note that we are using backticks
// Interpolation won't work with single and double quotes
console.log(`${greeting}, ${firstName}!`);
// => 'Hello, Joffrey!'
```

We simply create a string and "insert" constants in proper places using the dollar sign and curly brackets `${ }`. It's like we have a blank form where we can enter the desired values. And we no longer have to worry about separate strings for punctuation marks and spaces – all of these characters already exist in our template string.

You can create as many of these blocks as you want in a single string.

Interpolation only works with strings wrapped in [backticks](https://en.wikipedia.org/wiki/Grave_accent#Use_in_programming). This is the `\`` sign.

Nearly all languages favor interpolation over concatenation for combining strings. It glues a string together, and you see spaces and other characters inside it. Firstly, interpolation helps you to avoid confusing strings with numbers (thanks to the + sign), secondly, it is much easier (once you've practiced a little) to read a string as a whole.
