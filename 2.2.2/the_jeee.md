# [The JEE](https://www.hackerrank.com/contests/cohort-3-module-2-2-2/challenges/the-jee)

### Solution

```javascript
function processData(input) {
  input = input.trim().split("\n");
  // console.log("Input =>", input)

  let sumA = 0;
  let sumB = 0;

  let marksA = input[0]
    .trim()
    .split(" ")
    .map((e) => {
      sumA += Number(e);
      return Number(e);
    });
  let marksB = input[1]
    .trim()
    .split(" ")
    .map((e) => {
      sumB += Number(e);
      return Number(e);
    });

  // console.log("Sum A, Sum B =>", sumA, sumB)
  // console.log("Marks A, Marks B =>", marksA, marksB)

  if (sumA > sumB) {
    console.log("First");
  } else if (sumA < sumB) {
    console.log("Second");
  } else {
    if (marksA[2] > marksB[2]) {
      console.log("First");
    } else if (marksA[2] < marksB[2]) {
      console.log("Second");
    } else {
      if (marksA[0] > marksB[0]) {
        console.log("First");
      } else {
        console.log("Second");
      }
    }
  }
}
```
