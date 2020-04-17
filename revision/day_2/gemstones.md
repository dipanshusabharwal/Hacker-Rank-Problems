# [Gemstones](https://www.hackerrank.com/contests/cohort-3-revision-day-2/challenges/gem-stones)

### Solution

```javascript
function gemstones(arr) {
  let rocks = arr;
  console.log("Rocks =>", rocks);

  let allMinerals = {};

  for (let i = 0; i < rocks.length; i++) {
    let mineralsInThisRock = {};

    for (let j = 0; j < rocks[i].length; j++) {
      if (mineralsInThisRock[rocks[i][j]] == undefined) {
        mineralsInThisRock[rocks[i][j]] = 1;
      } else {
        mineralsInThisRock[rocks[i][j]] = mineralsInThisRock[rocks[i][j]] + 1;
      }
    }

    console.log("Minerals in this rock =>", mineralsInThisRock);

    for (let mineral in mineralsInThisRock) {
      if (allMinerals[mineral] == undefined) {
        allMinerals[mineral] = 1;
      } else {
        allMinerals[mineral] = allMinerals[mineral] + 1;
      }
    }
  }

  console.log("All Minerals => ", allMinerals);

  let gemstones = 0;

  for (let mineral in allMinerals) {
    if (allMinerals[mineral] === rocks.length) {
      ++gemstones;
    }
  }

  console.log(gemstones);
  return gemstones;
}
```
