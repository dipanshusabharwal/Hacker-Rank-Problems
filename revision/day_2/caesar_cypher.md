# [Caesar Cipher](https://www.hackerrank.com/contests/cohort-3-revision-day-2/challenges/caesar-cipher-1)

### Solution

```Javascript
function caesarCipher(s, k) {
    let str = s
    let key = k

    console.log("String, Key =>", str, key)

    let smallAlphabets = "abcdefghijklmnopqrstuvwxyz"
    let bigAlphabets = "ABCDEFGHIJKLMNOPQRSTUVWXYZ"

    let result = ""

    for(let i=0; i<str.length; i++){
        let index
        let offset

        if(smallAlphabets.indexOf(str[i]) > -1){
            index = smallAlphabets.indexOf(str[i])
            offset = calculateOffset(index, key)
            result += smallAlphabets[offset]
        }
        else if(bigAlphabets.indexOf(str[i]) > -1){
            index = bigAlphabets.indexOf(str[i])
            offset = calculateOffset(index, key)
            result += bigAlphabets[offset]
        }
        else{
            result += str[i]
        }
    }

    return result
}

function calculateOffset(index, key){
    let offset = index + key

    if(offset >= 26){
        offset = offset % 26
    }

    return offset
}
```
