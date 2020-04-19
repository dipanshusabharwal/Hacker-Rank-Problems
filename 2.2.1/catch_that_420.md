# [Catch that 420!](https://www.hackerrank.com/contests/cohort-3-module-2-2-1/challenges/catch-that-420)

### Solution

```javascript
function processData(input) {
  input = input.trim();
  // console.log("Input =>", input)

  for (let i = 0; i < input.length - 2; i++) {
    if (input[i] == "4" && input[i + 1] == "2" && input[i + 2] == "0") {
      console.log("Caught");
      return;
    }
  }

  console.log("Escaped");
}
```
