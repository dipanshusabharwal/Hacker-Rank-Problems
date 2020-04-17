# Count Consonant

You are provided a string S. Your task is to write a programme that counts the number of consonants (non-vowels characters) present in the string.

### Input Format

First line contains a string S

### Constraints

Length of String is always lesser than 1000

### Output Format

Output one number which is the count of number of consonants present in the string.

### Sample Input

```
masaischool
```

### Sample Output

```
6
```

### Solution

```javascript
function processData(input) {
  input = input.trim();
  // console.log("Input =>", input)

  let vowels = "aeiou";
  let consonants = 0;

  for (let i = 0; i < input.length; i++) {
    if (vowels.indexOf(input[i]) === -1) {
      ++consonants;
    }
  }

  console.log(consonants);
}
```
