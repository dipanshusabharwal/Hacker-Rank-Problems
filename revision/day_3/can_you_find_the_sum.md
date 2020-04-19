# [Can you find the sum](https://www.hackerrank.com/contests/cohort-3-revision-day-3/challenges/can-you-find-the-sum)

### Solution

```javascript
function processData(input) {
  input = input.trim().split("\n");
  // console.log("Input =>", input)

  let size = Number(input[0]);
  let arr = input[1]
    .trim()
    .split(" ")
    .map((e) => Number(e));
  // console.log("Size, Array =>", size, arr)

  let result = "";

  for (let i = 0; i < size; i++) {
    let x = -1;
    let y = -1;

    for (let j = i; j >= 0; j--) {
      if (arr[j] > arr[i]) {
        x = j + 1;
        break;
      }
    }

    for (let k = i; k < size; k++) {
      if (arr[k] > arr[i]) {
        y = k + 1;
        break;
      }
    }

    // console.log(arr[i], x, y)
    result += x + y + " ";
  }

  console.log(result);
}
```
