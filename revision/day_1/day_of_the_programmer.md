# [Day of the programmer](https://www.hackerrank.com/contests/cohort-3-revision-day-1/challenges/day-of-the-programmer)

Marie invented a Time Machine and wants to test it by time-traveling to visit Russia on the Day of the Programmer (the 256th day of the year) during a year in the inclusive range from 1700 to 2700 .

From 1700 to 1917, Russia's official calendar was the Julian calendar; since 1919 they used the Gregorian calendar system. The transition from the Julian to Gregorian calendar system occurred in 1918, when the next day after 31st January was 14th February . This means that in 1918, February 14th was the 32nd day of the year in Russia.

In both calendar systems, February is the only month with a variable amount of days; it has 29 days during a leap year, and 28 days during all other years. In the Julian calendar, leap years are divisible by 4; in the Gregorian calendar, leap years are either of the following:

Divisible by 400.
Divisible by 4 and not divisible by 100.

Given a year, y, find the date of the 256th day of that year according to the official Russian calendar during that year. Then print it in the format dd.mm.yyyy, where dd is the two-digit day, mm is the two-digit month, and yyyy is .

For example, the given . is divisible by , so it is a leap year. The day of a leap year after is September 12, so the answer is .

### Function Description

Complete the dayOfProgrammer function in the editor below. It should return a string representing the date of the day of the year given.

dayOfProgrammer has the following parameter(s):

year: an integer

### Input Format

A single integer denoting year .

### Constraints

1700 <= y <= 2700

### Output Format

Print the full date of Day of the Programmer during year in the format dd.mm.yyyy, where dd is the two-digit day, mm is the two-digit month, and yyyy is .

### Sample Input 0

```
2017
```

### Sample Output 0

```
13.09.2017
```

### Explanation 0

In the year , January has days, February has days, March has days, April has days, May has days, June has days, July has days, and August has days. When we sum the total number of days in the first eight months, we get . Day of the Programmer is the day, so then calculate to determine that it falls on day of the month (September). We then print the full date in the specified format, which is 13.09.2017.

### Sample Input 1

```
2016
```

### Sample Output 1

```
12.09.2016
```

### Explanation 1

Year is a leap year, so February has days but all the other months have the same number of days as in . When we sum the total number of days in the first eight months, we get . Day of the Programmer is the day, so then calculate to determine that it falls on day of the month (September). We then print the full date in the specified format, which is 12.09.2016.

### Sample Input 2

```
1800
```

### Sample Output 2

```
12.09.1800
```

### Explanation 2

Since 1800 is leap year. Day lies on 12 September.

### Solution

```javascript
function dayOfProgrammer(year) {
  if (year <= 1917) {
    if (checkLeapYear(year, "julian")) {
      console.log("Leap Julian Year");
      return "12.09." + year;
    } else {
      console.log("Normal Julian Year");
      return "13.09." + year;
    }
  } else if (year === 1918) {
    console.log("Transition Year");
    return "26.09." + year;
  } else if (year >= 1919) {
    if (checkLeapYear(year, "gregorian")) {
      console.log("Leap Gregorian Year");
      return "12.09." + year;
    } else {
      console.log("Normal Gregorian Year");
      return "13.09." + year;
    }
  }
}

function checkLeapYear(year, calendar) {
  if (calendar === "julian") {
    if (year % 4 === 0) {
      return true;
    } else {
      return false;
    }
  } else if (calendar === "gregorian") {
    if (year % 400 === 0 || (year % 4 === 0 && year % 100 != 0)) {
      return true;
    } else {
      return false;
    }
  }
}
```
