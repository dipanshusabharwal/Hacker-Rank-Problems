# [Compete with Neighbour](https://www.hackerrank.com/contests/cohort-3-module-1-1-2/challenges/compete-with-neighbour)

You are provided an array A which has N elements. Your task is to find the count of such occurrence where the element is larger than its neighbour.

### Input Format

First line of input contains N which is the number of elements present in the array.

Second line contains N integer which are the elements of the array A.

### Constraints

N<100

There will always be at least 2 elements

### Output Format

Output one integer which is the count of such occurences.

### Sample Input

```
8
1 2 3 4 2 1 6 5
```

### Sample Output

```
2
```

### Explanation

In this case, 4 is bigger than both its neighbour 3 and 2. Similarly 6 is bigger than both its neighbour 5 and 1. So, the answer is 2.

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
  // console.log("Size, Arr =>", size, arr)

  let count = 0;

  for (let i = 0; i < size; i++) {
    if (i === 0) {
      if (arr[i] > arr[i + 1]) {
        ++count;
      }
    } else if (i === size - 1) {
      if (arr[i] > arr[i - 1]) {
        ++count;
      }
    } else if (arr[i] > arr[i - 1] && arr[i] > arr[i + 1]) {
      ++count;
    }
  }

  console.log(count);
}
```
