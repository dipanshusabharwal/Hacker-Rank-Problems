# [Product of array problem](https://www.hackerrank.com/contests/cohort-3-module-2-1-1/challenges/product-of-array-2)

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

  let product = 1;

  arr.forEach((e) => (product = product * e));

  console.log(product);
}
```
