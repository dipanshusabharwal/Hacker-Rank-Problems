# [Battle of Odd & Even](https://www.hackerrank.com/contests/cohort-3-module-1-1-2/challenges/battle-of-odd-even)

You are given an array A of N integers. Your task is to write a programme that prints "Odd" (without quotes) if the sum of all odd numbers present in the array is greater than sum of all the even numbers present in the array. In all other cases, print "Even" (without quotes).

### Input Format

First line contains N which is the number of elements present in the array.

Second line contains N space separated integers which are the elements of array.

### Constraints

N<100

### Output Format

Print either "Odd" or "Even" depending upon the condition mentioned above.

### Sample Input 0

```
4
1 2 3 4
```

### Sample Output 0

```
Even
```

### Explanation 0

Odd numbers present are 1 and 3, whose sum is 4

Even numbers present in array are 2 and 4, whose sum is 6

Since 6>4, Even is the required output.

### Solution

```javascript
function processData(input) {
  input = input.trim().split("\n");
  // console.log(input)

  let size = Number(input[0].trim());
  let arr = input[1]
    .trim()
    .split(" ")
    .map((e) => Number(e));

  // console.log("Size, Array =>", size, arr)

  let evenSum = 0,
    oddSum = 0;

  for (let i = 0; i < size; i++) {
    if (arr[i] % 2 === 0) {
      evenSum += arr[i];
    } else {
      oddSum += arr[i];
    }
  }

  // console.log("Even and Odd sum", evenSum, oddSum)

  if (oddSum > evenSum) {
    console.log("Odd");
  } else {
    console.log("Even");
  }
}
```
