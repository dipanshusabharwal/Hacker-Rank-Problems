# [Left Rotation](https://www.hackerrank.com/contests/cohort-3-revision-day-2/challenges/array-left-rotation)

### Solution

```javascript
function leftRotate(a, n, d) {
  // console.log("Array, Length, Rotations =>", a, n ,d)

  let offset = d % n;
  // console.log("Offset =>", offset)

  let result = [];

  for (let i = n - 1; i >= 0; i--) {
    let pos;

    if (i - offset < 0) {
      // console.log(a[i], n+i-offset)
      result[n + i - offset] = a[i];
    } else {
      // console.log(a[i], i-offset)
      result[i - offset] = a[i];
    }
  }

  let resultStr = "";
  for (let i = 0; i < n; i++) {
    resultStr += result[i] + " ";
  }

  console.log(resultStr);
}
```
