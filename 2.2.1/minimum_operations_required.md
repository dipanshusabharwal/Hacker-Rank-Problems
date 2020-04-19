# [Minimum Operations Required](https://www.hackerrank.com/contests/cohort-3-module-2-2-1/challenges/the-minimum-number-of-moves)

### Solution

```javascript
function processData(input) {
  input = input.trim().split("\n");
  // console.log("Input =>", input)

  let size = Number(input[0]);
  let arr = input[1]
    .trim()
    .split(" ")
    .map((e) => Number(e))
    .sort();

  let min = arr[0];
  let minOps = 0;

  arr.forEach((e) => {
    minOps += Math.abs(min - e);
  });

  console.log(minOps);
}
```
