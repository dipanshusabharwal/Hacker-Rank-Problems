# [Your First Maze Problem](https://www.hackerrank.com/contests/cohort-3-module-2-2-2/challenges/your-first-maze-problem)

### Solution

```javascript
function processData(input) {
  input = input.trim();
  // console.log("Input =>", input)

  let x = 0,
    y = 0;

  for (let i = 0; i < input.length; i++) {
    switch (input[i]) {
      case "L":
        --x;
        break;
      case "R":
        ++x;
        break;
      case "D":
        --y;
        break;
      case "U":
        ++y;
        break;
    }
  }

  console.log(x + " " + y);
}
```
