# [Equal to 42 or not](https://www.hackerrank.com/contests/cohort-3-module-2-1-1/challenges/greater-than-42-or-not)

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
  // console.log("Size, array =>", size, arr)

  for (let i = 0; i < size; i++) {
    if (arr[i] === 42) {
      console.log("Yes");
      return;
    }
  }

  console.log("No");
}
```
