# [Count Chars](https://www.hackerrank.com/contests/cohort-3-module-2-2-1/challenges/count-chars)

### Solution

```javascript
function processData(input) {
  let str = input.trim().split("");
  // console.log("String =>", str)

  let result = "";
  let currentChar = str[0];
  let currentCharCount = 1;

  for (let i = 1; i < str.length; i++) {
    if (currentChar === str[i]) {
      ++currentCharCount;
    } else {
      result += currentChar + currentCharCount;
      currentChar = str[i];
      currentCharCount = 1;
    }
  }

  result += currentChar + currentCharCount;

  console.log(result);
}
```
