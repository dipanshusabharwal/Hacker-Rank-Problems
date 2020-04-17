# [Count such pairs](https://www.hackerrank.com/contests/cohort-3-module-1-1-3/challenges/count-such-pairs/problem)

You are given an array A of N integers along with a target integer. Your task is to find out the number of pairs of integers present in the array whose sum is equal to the target value.

### Input Format

First line contains 2 integers: N and the target respectively.

Second line contains N integers which are the elements of array.

### Constraints

N<100

### Output Format

Print one number which is number of such pairs.

### Sample Input

```
5 9
3 0 6 2 7
```

### Sample Output

```
2
```

### Explanation

There are two such pairs available whose sum equals to 9.

Such pairs are (3,6) and (2,7)

Hence the answer is 2

### Solution

```javascript
function processData(input) {
  input = input.trim().split("\n");
  // console.log("Input =>",input)

  let temp = input[0]
    .trim()
    .split(" ")
    .map((e) => Number(e));

  let size = temp[0];
  let sum = temp[1];
  // console.log("Size, Sum", size, sum)

  let arr = input[1]
    .trim()
    .split(" ")
    .map((e) => Number(e));
  // console.log("Array =>", arr)

  let pairs = 0;

  for (let i = 0; i < size; i++) {
    let key = sum - arr[i];
    // console.log("Key =>", key)

    for (let j = 0; j < size; j++) {
      if (j !== i) {
        if (arr[j] === key) {
          // console.log("Pair =>", arr[i], key)
          ++pairs;
        }
      }
    }
  }

  // console.log("Pairs =>", pairs/2)
  console.log(pairs / 2);
}
```
