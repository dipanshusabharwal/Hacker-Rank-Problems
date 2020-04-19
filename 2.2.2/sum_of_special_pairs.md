# [Sum Of Special Pairs](https://www.hackerrank.com/contests/cohort-3-module-2-2-2/challenges/sum-of-special-pairs)

### Solution

```javascript
function processData(input) {
  input = input.trim().split("\n");
  // console.log("Input =>", input)

  let size = Number(input[0].trim());
  let arr = input[1]
    .trim()
    .split(" ")
    .map((e) => Number(e));
  // console.log("Size, Array =>", size, arr)

  let sum = 0;

  for (let i = 0; i < size; i++) {
    for (let j = 0; j < size; j++) {
      if (i < j && isPrime(j - i)) {
        sum += Math.abs(arr[i] - arr[j]);
      }
    }
  }

  console.log(sum);
}

function isPrime(n) {
  if (n <= 1) {
    return false;
  } else {
    for (let i = 2; i < n; i++) {
      if (n % i === 0) {
        return false;
      }
    }
  }

  return true;
}
```
