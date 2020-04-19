# [Maximum Element](https://www.hackerrank.com/contests/cohort-3-revision-day-3/challenges/maximum-element)

### Solution

```javascript
function processData(input) {
  input = input.trim().split("\n");
  // console.log("Input =>", input)

  let queryCount = Number(input[0]);
  // console.log("Query Count =>", queryCount)
  // console.log("\n")

  let queryStack = [];
  let maxStack = [];

  for (let i = 1; i <= queryCount; i++) {
    if (input[i].length > 1) {
      let temp = input[i].trim().split(" ");
      let n = Number(temp[1]);
      // console.log("Push operation, n =>", n)
      queryStack.push(n);

      if (maxStack.length === 0) {
        maxStack.push(n);
      } else if (n >= maxStack[maxStack.length - 1]) {
        maxStack.push(n);
      }
    } else if (input[i] == 2) {
      // console.log("Delete Operation")
      let n = queryStack.pop();
      if (n === maxStack[maxStack.length - 1]) {
        maxStack.pop();
      }
    } else if (input[i] == 3) {
      // console.log("Print Max Operation")
      console.log(maxStack[maxStack.length - 1]);
    }

    // console.log("Current Stack =>", queryStack)
    // console.log("Max Stack =>", maxStack)
    // console.log("\n")
  }
}
```
