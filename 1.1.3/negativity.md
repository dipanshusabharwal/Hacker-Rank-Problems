# [Negativity!](https://www.hackerrank.com/contests/cohort-3-module-1-1-3/challenges/negativity)

You are given an array of N integers. Find the total count of negative elements present in the array.

### Input Format

First line contains N integers

Second line contains N space separated integers which constitute the array.

### Constraints

N < 100

### Output Format

Output the number of negative integers present in the array

### Sample Input

```
5
-3 0 -5 9 8
```

### Sample Output

```
2
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

  let count = 0;

  for (let i = 0; i < size; i++) {
    if (arr[i] < 0) {
      ++count;
    }
  }

  console.log(count);
}
```
