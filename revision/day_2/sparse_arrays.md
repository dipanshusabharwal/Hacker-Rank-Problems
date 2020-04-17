# [Sparse Arrays](https://www.hackerrank.com/contests/cohort-3-revision-day-2/challenges/sparse-arrays)

There is a collection of input strings and a collection of query strings. For each query string, determine how many times it occurs in the list of input strings.

For example, given input and , we find instances of ', of '' and of ''. For each query, we add an element to our return array, .

### Function Description

Complete the function matchingStrings in the editor below. The function must return an array of integers representing the frequency of occurrence of each query string in strings.

matchingStrings has the following parameters:

strings - an array of strings to search
queries - an array of query strings

### Input Format

The first line contains and integer , the size of .
Each of the next lines contains a string .
The next line contains , the size of .
Each of the next lines contains a string .

### Output Format

Return an integer array of the results of all queries in order.

### Solution

```javascript
function matchingStrings(strings, queries) {
  let inputStr = strings;
  let queryStr = queries;

  console.log(inputStr, queryStr);

  let obj = {};

  for (let i = 0; i < inputStr.length; i++) {
    if (obj[inputStr[i]] == undefined) {
      obj[inputStr[i]] = 1;
    } else {
      obj[inputStr[i]] = obj[inputStr[i]] + 1;
    }
  }

  console.log(obj);

  let result = [];

  for (let i = 0; i < queryStr.length; i++) {
    if (obj[queryStr[i]] == undefined) {
      result.push(0);
    } else {
      result.push(obj[queryStr[i]]);
    }
  }

  console.log(result);
  return result;
}
```
