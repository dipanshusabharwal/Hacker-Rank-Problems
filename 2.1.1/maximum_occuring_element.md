# [Maximum occuring element](https://www.hackerrank.com/contests/cohort-3-module-2-1-1/challenges/maximum-occurring-element)

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

  let countObj = {};

  arr.forEach((e) => {
    if (countObj[e] == undefined) {
      countObj[e] = 1;
    } else {
      countObj[e] += 1;
    }
  });

  // console.log("Count object =>", countObj)

  let maxCount = 0;
  let maxElement;

  for (let e in countObj) {
    if (countObj[e] > maxCount) {
      maxCount = countObj[e];
      maxElement = e;
    }
  }

  console.log(maxElement);
}
```
