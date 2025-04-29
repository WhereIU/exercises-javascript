
Logical operations are expressions. So, you can combine them with other expressions.

Let's say, for example, we want to check if a number is even, i.e., a multiple of two. In programming we do this:

  * check for a remainder when dividing by 2:
  * if the remainder is 0, then the number is even
  * if the remainder is not 0, then the number is odd

The remainder of a division is an elementary but crucial concept of arithmetic, algebra, and even number theory and cryptography. The idea is simple: divide a number into several equal groups, and if anything remains, it's the remainder of the division.

Split some candies equally among individuals:

- 7 candy, 2 persons: 2 x 3 + **remainder 1**.
  So 7 is not a multiple of 2.
- 21 candies, 3 persons: 3 x 7 + **remainder 0**.
  So 21 is a multiple of 3.
- 19 candies, 5 persons: 5 x 3 + **remainder 4**.
  So 19 is not a multiple of 5.

The `%` operator calculates the remainder of a division (not to be confused with division itself):

```javascript
7 % 2;  // 1
21 % 3; // 0
19 % 5; // 4

// Checking if even

10 % 2 // 10 is even, i.e. remainder is 0
9 % 2  // 9 odd, i.e. remainder is 1
```

Write a function to check whether a number is even:

```javascript
const isEven = (number) => number % 2 === 0;

isEven(10); // true
isEven(3);  // false
```

In one expression, we've combined the logical operator `===` (equality check) and the arithmetic operator `%`.

Arithmetic operators have higher priority than logical ones. So, we first calculate the arithmetic expression `number % 2`, and then its output is used in the logical comparison.

Literally, it means the following: *"calculate the remainder of dividing `number` by 2 and check if the remainder equals zero; then return the result of the equality check "*.

Another example: write a function to check the first letter of a string is uppercase.

Algorithm:

1. Get the initial character of the string and assign it to the variable
2. Compare whether the character is equal to its uppercase version
3. Return the result

```javascript
const isFirstLetterInUpperCase = (string) => {
  const firstLetter = string[0];
  return firstLetter.toUpperCase() === firstLetter;
};

isFirstLetterInUpperCase('marmont'); // false
isFirstLetterInUpperCase('Robb');    // true
```
