# [Sum and conditions](https://www.hackerrank.com/contests/cohort-3-module-2-1-1/challenges/sum-and-conditions)

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

  arr.forEach((e) => (sum += e));

  sum > 100 ? console.log("Greater") : console.log("Lesser");
}
```
