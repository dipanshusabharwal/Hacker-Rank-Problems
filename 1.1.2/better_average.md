# [Better average](https://www.hackerrank.com/contests/cohort-3-module-1-1-2/challenges/better-average)

You are given scores of last N matches of two different batsmen in form of arrays. Your task is to print the ceil value of better average among the two in case that value is even. If that value is not even, print -1.

### Input Format

```
First line contains the number of matches N.

Second line contains N space separated integers describing scores of first batsman. Third line contains N space separated integers descibing scores of second batsman.
```

### Constraints

```
N<100
```

### Output Format

```
Print an integer which can either be ceil of better average of the two batsmen or -1 depending upon the ceil of better average.
```

### Sample Input 0

```
3
10 20 30
40 80 60
```

### Sample Output 0

```
60
```

### Explanation 0

```
Here, the number of matches is 3. And average of first batsman is 20 while average of second batsman is 60. Since 60>20 and 60 is also even, 60 is the output.
```

### Solution

```javascript
function processData(input) {
  input = input.trim().split("\n");
  // console.log("Input =>", input)

  let matches = Number(input[0].trim());
  // console.log("Matches =>", matches)

  let scoresA = input[1]
    .trim()
    .split(" ")
    .map((e) => Number(e));
  let scoresB = input[2]
    .trim()
    .split(" ")
    .map((e) => Number(e));

  // console.log("Scores: A and B =>", scoresA, scoresB)

  let sumA = scoresA.reduce((a, c) => a + c);
  let sumB = scoresB.reduce((a, c) => a + c);

  // console.log("SumA, SumB =>", sumA, sumB)

  let averageA = sumA / matches;
  let averageB = sumB / matches;

  // console.log("AverageA, AverageB =>", averageA, averageB)

  let betterAverage = averageA > averageB ? averageA : averageB;
  // console.log("Better Average =>", betterAverage)

  if (betterAverage % 2 === 0) {
    console.log(Math.ceil(betterAverage));
  } else {
    console.log(-1);
  }
}
```
