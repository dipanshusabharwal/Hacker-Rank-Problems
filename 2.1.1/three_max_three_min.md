# [Three max, Three min please](https://www.hackerrank.com/contests/cohort-3-module-2-1-1/challenges/three-max-three-min-please)

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

  let uniques = Object.keys(countObj).sort((a, b) => a - b);
  // console.log("All unique elements =>", uniques)

  if (uniques.length < 3) {
    console.log("Not Possible");
    console.log("Not Possible");
    return;
  }

  let smallest = uniques[0] + " " + uniques[1] + " " + uniques[2];
  let largest =
    uniques[uniques.length - 3] +
    " " +
    uniques[uniques.length - 2] +
    " " +
    uniques[uniques.length - 1];

  console.log(smallest);
  smallest === largest ? console.log("Not Possible") : console.log(largest);
}
```
