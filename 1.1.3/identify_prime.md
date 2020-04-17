# [Identify Prime](https://www.hackerrank.com/contests/cohort-3-module-1-1-3/challenges/identify-prime)

You are provided an integer N, print "Yes" (without quotes) if the given integer is prime, else print "No" (without quotes).

### Input Format

First and the only integer contains N

### Constraints

N<100000

### Output Format

Output Yes or No depending on the conditions mentioned above.

Please note that the case of each character matters.

### Sample Input

```
13
```

### Sample Output

```
Yes
```

### Explanation

Since 13 is a prime number, the output is Yes

### Solution

```javascript
function processData(input) {
  let n = Number(input);
  // console.log("Number =>", n)

  if (n === 1) {
    console.log("No");
    return;
  }

  let isPrime = true;
  for (let i = 2; i < n; i++) {
    if (n % i === 0) {
      isPrime = false;
    }
  }

  if (isPrime) {
    console.log("Yes");
  } else {
    console.log("No");
  }
}
```
