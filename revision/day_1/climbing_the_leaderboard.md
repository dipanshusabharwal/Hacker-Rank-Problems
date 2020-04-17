# [Climbing the Leaderboard](https://www.hackerrank.com/contests/cohort-3-revision-day-1/challenges/climbing-the-leaderboard)

Alice is playing an arcade game and wants to climb to the top of the leaderboard and wants to track her ranking. The game uses Dense Ranking, so its leaderboard works like this:

The player with the highest score is ranked number on the leaderboard.
Players who have equal scores receive the same ranking number, and the next player(s) receive the immediately following ranking number.
For example, the four players on the leaderboard have high scores of , , , and . Those players will have ranks , , , and , respectively. If Alice's scores are , and , her rankings after each game are , and .

### Function Description

Complete the climbingLeaderboard function in the editor below. It should return an integer array where each element represents Alice's rank after the game.

climbingLeaderboard has the following parameter(s):

scores: an array of integers that represent leaderboard scores
alice: an array of integers that represent Alice's scores

### Input Format

The first line contains an integer , the number of players on the leaderboard.
The next line contains space-separated integers , the leaderboard scores in decreasing order.
The next line contains an integer, , denoting the number games Alice plays.
The last line contains space-separated integers , the game scores.

### Constraints

for
for
The existing leaderboard, , is in descending order.
Alice's scores, , are in ascending order.
Subtask

For of the maximum score:

### Output Format

Print integers. The integer should indicate Alice's rank after playing the game.

### Solution

```javascript
function climbingLeaderboard(scores, alice) {
  let result = {};

  for (let i = 0; i < scores.length; i++) {
    if (result[scores[i]] == undefined) {
      result[scores[i]] = 1;
    } else {
      result[scores[i]] = ++result[scores[i]];
    }
  }

  console.log("Result Object=>", result);

  let resultList = Object.keys(result)
    .sort(function (a, b) {
      return a - b;
    })
    .map((e) => Number(e));
  console.log("Result List =>", resultList);

  let aliceResult = [];

  for (let i = 0; i < alice.length; i++) {
    let aliceScore = alice[i];
    console.log("Current score of Alice =>", aliceScore);

    let rank = findRank(aliceScore, resultList);
    if (rank === -1) {
      aliceResult.push(1);
    } else {
      rank = resultList.length - rank + 1;
      aliceResult.push(rank);
    }
  }

  console.log("Result of Alice =>", aliceResult);
  return aliceResult;
}

function findRank(score, leaderboard) {
  let lo = 0;
  let hi = leaderboard.length - 1;
  let upperIndex = -1;

  while (lo <= hi) {
    let mid = lo + Math.floor((hi - lo) / 2);

    if (score < leaderboard[mid]) {
      hi = mid - 1;
      upperIndex = mid;
    } else {
      lo = mid + 1;
    }
  }
  return upperIndex;
}
```
