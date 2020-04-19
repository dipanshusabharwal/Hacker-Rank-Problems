# [Masai Divisors](https://www.hackerrank.com/contests/cohort-3-module-2-2-2/challenges/count-divisors-2-1)

### Solution

```javascript
function processData(input) {
  input = input
    .trim()
    .split(" ")
    .map((e) => Number(e));
  // console.log("Input =>", input)

  let left = input[0];
  let right = input[1];
  let k = input[2];

  let count = 0;

  for (let i = left; i <= right; i++) {
    if (i % k === 0) {
      ++count;
    }
  }

  console.log(count);
}
```
