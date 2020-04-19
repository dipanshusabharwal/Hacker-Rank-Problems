# [Masai Palindromic Substring](https://www.hackerrank.com/contests/cohort-3-module-2-2-1/challenges/longest-palindromic-substring-5-1/problem)

### Solution

```javascript
function processData(input) {
  let str = input.trim();
  let len = str.length;
  // console.log("String, length =>", str, len)

  let maxPalindrome = 0;

  for (let i = 0; i < len; i++) {
    for (let j = len - 1; j >= i; j--) {
      let substring = generateSubstring(i, j, str);
      // console.log("Substring =>", substring)

      if (isPalindrome(substring)) {
        // console.log("Palindrome Substring =>", substring)
        if (substring.length > maxPalindrome) {
          maxPalindrome = substring.length;
        }
      }
    }
  }

  console.log(maxPalindrome);
}

function generateSubstring(i, j, str) {
  let substring = "";

  for (let k = i; k <= j; k++) {
    substring += str[k];
  }

  return substring;
}

function isPalindrome(str) {
  let palindrome = true;

  for (let i = 0; i < Math.floor(str.length); i++) {
    if (str[i] !== str[str.length - 1 - i]) {
      palindrome = false;
      break;
    }
  }

  return palindrome;
}
```
