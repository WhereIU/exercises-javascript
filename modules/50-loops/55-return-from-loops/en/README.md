
Dealing with loops usually comes down to two cases:

1. Aggregation. Accumulation of data during iterations and handling it after the loop. String reversal is just one of these cases
2. Executing a loop until you get the required result and breaking from it. For example, if the job of the loop is to find prime numbers. Remember that a prime number is a number that can only be divided without a remainder by itself and by one

Consider a simple algorithm to check prime numbers. We will divide a given number `x` by all numbers between 2 and `x - 1` and check the remainder. If we don't find a divisor that divides the number `x` without a remainder in this range, then we are looking at a prime number.

If you think about it, it's actually enough to check numbers not up to `x - 1`, but up to half the given number. For example, 11 is not divisible by 2, 3, 4, or 5. But it's also guaranteed that it can't be divided by numbers greater than its half. So, you can do a little optimization and check division only up to `x / 2`.

```javascript
const isPrime = (number) => {
  if (number < 2) {
    return false;
  }

  let divider = 2;

  while (divider <= number / 2) {
    if (number % divider === 0) {
      return false;
    }

    divider += 1;
  }

  return true;
}

isPrime(1); // false
isPrime(2); // true
isPrime(3); // true
isPrime(4); // false
```

The algorithm is built like so: if during the successive division by numbers up to `x / 2`, there is at least one result without a remainder, then the given argument is not a prime number, and therefore further computations are pointless. At this point, it returns `false`.

And only if the entire loop is completed can we say that the number is prime since no number by which it can be divided without a remainder can be found.
