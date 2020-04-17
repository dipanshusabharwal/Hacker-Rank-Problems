# [Smallest and Largest of all](https://www.hackerrank.com/contests/cohort-3-module-1-1-2/challenges/smallest-and-largest-1)

Given an array, A, of N integers, print the smallest and largest element present in the array

```
**YOU MUST NOT USE ANY BUILT-IN FUNCTION **
```

### Input Format

The first line contains an integer, N (the number of integers in A). The second line contains N space separated integers describing A.

### Constraints

N<100

### Output Format

Print 2 integers in different lines where first integer represents the minimum of all elements and second integer represents the maximum of all

### Sample Input

```
4
-2 0 8 4
```

### Sample Output

```
-2
8
```

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

  let min = (max = arr[0]);

  for (let i = 0; i < size; i++) {
    if (arr[i] < min) {
      min = arr[i];
    }
    if (arr[i] > max) {
      max = arr[i];
    }
  }

  console.log(min);
  console.log(max);
}
```
