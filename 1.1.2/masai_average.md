# [Masai Average](https://www.hackerrank.com/contests/cohort-3-module-1-1-2/challenges/average-16)

Given an array, A, of N integers, print the ceil of average of numbers present in given array

### Input Format

The first line contains an integer, N (the number of integers in A). The second line contains N space separated integers describing A.

### Constraints

```
N<100
```

### Output Format

```
Print an integer which is ceil of average of integers present in array
```

### Sample Input 0

```
3
1 2 3
```

### Sample Output 0

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

  // console.log("Size, Array", size, arr)

  let sum = 0;

  for (let i = 0; i < size; i++) {
    sum += arr[i];
  }

  console.log(Math.ceil(sum / size));
}
```
