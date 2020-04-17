# [Longest Repeated Odd](https://www.hackerrank.com/contests/cohort-3-module-1-1-3/challenges/longest-repeated-odd)

You are given an array A of N integers. Your task is to find the maximum number of times an odd number is continuously repeated in the array.

### Input Format

First line contains N which is the number of element present in the array.

Second line contains N integers which are the values of array.

### Constraints

N<100

### Output Format

Output one integer which the maximum number of times an odd number is repeated in array.

### Sample Input

```
12
1 1 1 1 2 2 2 2 2 1 1 1
```

### Sample Output

```
4
```

### Explanation

1 is repeated 4 times from index 0 to index 3 => 4 times

2 is repeated 5 times from index 4 to index 8 => 5 times

1 is repeated 3 times from index 9 to index 11 => 3 times

So, the output is 4 since 1 is odd.

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

  let maxSequence = 0;
  let currentSequence = 0;
  let currentOdd;

  for (let i = 0; i < size; i++) {
    if (arr[i] % 2 !== 0) {
      if (currentOdd === arr[i]) {
        ++currentSequence;
      } else {
        if (currentSequence > maxSequence) {
          maxSequence = currentSequence;
        }
        currentOdd = arr[i];
        currentSequence = 1;
      }
    } else {
      if (currentSequence > maxSequence) {
        maxSequence = currentSequence;
      }
      currentSequence = 0;
    }
  }

  if (currentSequence > maxSequence) {
    maxSequence = currentSequence;
  }

  console.log(maxSequence);
}
```
