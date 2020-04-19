# [Conditional matrix sum](https://www.hackerrank.com/contests/cohort-3-module-2-2-1/challenges/conditional-matrix-sum)

### Solution

```javascript
function processData(input) {
  input = input.trim().split("\n");
  // console.log("Input =>", input)

  let dimensions = input[0]
    .trim()
    .split(" ")
    .map((e) => Number(e));
  let n = dimensions[0];
  let m = dimensions[1];
  // console.log("Row, Col =>", n, m)

  let sum = 0;

  let line = 1;

  while (line <= n) {
    let arr = input[line]
      .trim()
      .split(" ")
      .map((e) => Number(e));
    // console.log("Array =>", arr)

    arr.forEach((e) => (e % 3 === 0 ? (sum += e) : (sum += 0)));
    ++line;
  }

  console.log(sum);
}
```
