# [Detect Palindrome](https://www.hackerrank.com/contests/cohort-3-module-2-2-1/challenges/detect-palindrome/submissions/code/1322872140)

### Solution

```javascript
function processData(input) {
  let str = input.trim();
  // console.log("String =>", str)

  let len = str.length;
  let isPalindrome = true;

  for (let i = 0; i < Math.floor(len / 2); i++) {
    if (str[i] !== str[len - 1 - i]) {
      isPalindrome = false;
      break;
    }
  }

  isPalindrome ? console.log("Yes") : console.log("No");
}
```
