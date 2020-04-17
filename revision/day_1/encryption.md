# [Encryption](https://www.hackerrank.com/contests/cohort-3-revision-day-1/challenges/encryption)

An English text needs to be encrypted using the following encryption scheme.
First, the spaces are removed from the text. Let be the length of this text.
Then, characters are written into a grid, whose rows and columns have the following constraints:

For example, the sentence , after removing spaces is characters long. is between and , so it is written in the form of a grid with 7 rows and 8 columns.

ifmanwas  
meanttos  
tayonthe  
groundgo  
dwouldha  
vegivenu  
sroots

Ensure that

If multiple grids satisfy the above conditions, choose the one with the minimum area, i.e. .
The encoded message is obtained by displaying the characters in a column, inserting a space, and then displaying the next column and inserting a space, and so on. For example, the encoded message for the above rectangle is:

imtgdvs fearwer mayoogo anouuio ntnnlvt wttddes aohghn sseoau

You will be given a message to encode and print.

### Function Description

Complete the encryption function in the editor below. It should return a single string composed as described.

encryption has the following parameter(s):

s: a string to encrypt

### Input Format

One line of text, the string

### Constraints

is comprised only of characters in the range ascii[a-z].

### Output Format

Print the encoded message on one line as described.

### Sample Input

```
haveaniceday
```

### Sample Output 0

```
hae and via ecy
```

### Explanation 0

, is between and .
Rewritten with rows and columns:

have
anic
eday

### Sample Input 1

```
feedthedog
```

### Sample Output 1

```
fto ehg ee dd
```

### Explanation 1

, is between and .
Rewritten with rows and columns:

feed
thed
og

### Sample Input 2

```
chillout
```

### Sample Output 2

```
clu hlt io
```

### Explanation 2

, is between and .
Rewritten with columns and rows ( so we have to use .)

chi
llo
ut

### Solution

```javascript
function encryption(s) {
  let str = s.split(" ").join("");
  let l = str.length;

  console.log("Given String =>", str);
  console.log("L =>", l);

  let dimensions = Math.sqrt(l);

  let row;
  let col;

  if (dimensions - Math.floor(dimensions) === 0) {
    row = col = dimensions;
  } else {
    row = Math.floor(dimensions);
    col = row + 1;
  }

  if (checkDimensionCondition(row, col, l)) {
    row += 1;
  }

  console.log("Row, Col =>", row, col);

  let encryptionMatrix = [];
  let char = 0;

  for (let i = 0; i < row; i++) {
    let temp = [];

    for (let j = 0; j < col; j++) {
      if (char < str.length) {
        temp.push(str[char]);
        ++char;
      }
    }

    encryptionMatrix.push(temp);
  }

  console.log("Encryption Matix =>");
  console.log(encryptionMatrix);

  let encryptedMatrix = [];

  for (let i = 0; i < col; i++) {
    let temp = "";

    for (let j = 0; j < row; j++) {
      if (encryptionMatrix[j][i] != undefined) {
        temp += encryptionMatrix[j][i];
      }
    }

    encryptedMatrix.push(temp);
  }

  console.log("Encrypted Matrix=>");
  console.log(encryptedMatrix);

  return encryptedMatrix.join(" ");
}

function checkDimensionCondition(row, col, l) {
  if (row * col < l) {
    return true;
  } else {
    return false;
  }
}
```
