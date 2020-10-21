# Master the Coding Interview
Ultimate coding interview bootcamp. Get more job offers, negotiate a raise: Everything you need to get the job you want!

[UDEMY](https://www.udemy.com/course/master-the-coding-interview-data-structures-algorithms/)

## Getting the interview
* Resume
  * Use Keywords used in job requirements
  * Hand craft to each job opening (no spamming)
  * Highlight relevant skills and projects
  * Online link to Github and website
  * Could use resume maker [template](https://resumemaker.online)
  * [checklist](https://github.com/aneagoie/resume-checklist)

* Get interview without experience
  * Build impressive GitHub account
  * Highlight skills and projects on website
  * 1~2 major impressive big projects
  * Blog

* LinkedIn
  * Apply to available jobs
  * Complete profile
  * Update regularly 
  * Use keywords (maybe by creating a list of top technologies for 2020)
  * Join groups
  * Get recommendations from group members
  * Connect with people working at dream jobs

* Portfolio
  * 1~2 major impressive big projects
  * Way to showcase the job you want

* Networking
  * 30% jobs come through referrals (the higher the salary the more effective networking is)
  * Connect with smart emails / linkedIn / FindAnyOnesEmail / hunter / email extractor / Twitter
  * Use Meetups, conventions and hackathons
  * Instead of sending traditional resume. Email gatekeeper (HR / CTO / Leads) a portfolio and ask if they might be interested
  * Go out for coffee with gatekeeper to pick their brain
  * Try to by-pass formalities to get your foot in the door

## Big O Notation
* Good code should be
  * Readable
  * Scalable

Big O allows us to measure how scalable our code is.

* Runtime - how long does it take to complete our code
* We can measure this in javascript with the performance.now() method

```javascript
const nemo = ['dory', 'bruce', 'nemo', 'marlin', 'gill', 'bloat', 'nigel', 'darla', 'hank'];
const largeArray = new Array(1000).fill('nemo');

function findNemo(array){
  let t0 = performance.now()
    for(let i = 0; i< array.length; i++) {
        if (array[i] === 'nemo'){
            console.log('Found NEMO!')
        }
    }
  let t1 = performance.now()
  console.log(`Runtime findNemo took ${t1 - t0} milliseconds`)
}

findNemo(nemo); // O(n) -> Linear Time complexity
findNemo(largeArray); // O(n) -> Linear Time complexity
```

## Big O Complexities / Algorithm efficiency
<img src="./img/big-O-complexity-chart.jpeg" alt="Big O complexity Chart" style="float: left margin-right: 10px;" />

* O(1) Constant - no loops
  * No matter how much inputs are added, operations are kept constant
```javascript
const compressFirstBox = (boxes) => console.log(boxes[0]);
```
* O(log N) Logarithmic - usually searching algorithms have log n if they are sorted (Binary Search)
  
* O(n) Linear - for loops, while loops through n items
  * As the inputs increase, the operations increase linearly
```javascript
const findNemo = (array) => {
  for(let i = 0; i< array.length; i++) {
      if (array[i] === 'nemo'){
          console.log('Found NEMO!')
      }
  }
}
```
* O(n * (log(n)) Log Linear - usually sorting operations
  
* O(n^2) Quadratic time (squared) - every element in a collection needs to be compared to ever other element. Two
  nested loops
```javascript
const boxes = [1,2,3,4,5];

const logAllPairsOfArray = array => {
  for (let i= 0; i < array.length; i++) {
    for (let j= 0; j < array.length; j++) {
      console.log(array[i], array[j]);
    }
  }
}
logAllPairsOfArray(boxes);
```

Three Nested loops would be O(n^3) etc. etc.
```javascript
const boxes = [1, 2, 3, 4, 5];
const logAllPairsOfArray2 = (boxes) => {
  boxes.forEach(firstBox => {
    boxes.forEach(secondBox => {
      boxes.forEach(thirdBox => {
        console.log(firstBox, secondBox, thirdBox)
      });
    });
  });
};
logAllPairsOfArray2(boxes);
```
* O(2^n) Exponential - recursive algorithms that solves a problem of size N
  
* O(n!) Factorial - you are adding a nested loop for every input we add
```javascript
const factorial = n => {
  let num = n;
  if (n === 0) return 1
  for (let i = 0; i < n; i++) {
    num = n * factorial(n - 1);
  };
  return num;
};
```

Iterating through half a collection is still O(n)
Two separate collections: O(a * b)

## What can cause time in a function?
Operations (+, -, *, /)
Comparisons (<, >, ==)
Looping (for, while)
Outside Function call (function())

## Rule Book
* Rule 1: Always worst case scenario
  Heaviest calculation scenario counts as Big O
* Rule 2: Remove all constants
  O(1 + n/2 +100) === O(n)
* Rule 3: Different inputs should have different variables. O(a+b) (+ for steps in order). 
  A and B arrays nested would be O(a*b) (* for nested steps)
* Rule 4: Drop Non-dominant terms O(n + n^2) === O(n^2)

## Three pillars of programming
* Readable
* Scalable (Big O)
  * Speed - Time complexity
  * Memory - Space complexity

## Space complexity
There is a trade off between Speed and Memory
* You want more speed, you get less Memory and vice versa

## What causes Space complexity?
Adding Variables
Adding Data Structures
Adding Function Call
Allocations

```javascript
//#4 Space complexity O(1)
const array = ['hi', 'my', 'teddy'];
array[0]; 
array[array.length-1]

//#5 Space complexity O(1)
function boooo(n) {
    for (let i = 0; i < n; i++) {
        console.log('booooo');
    }
}

// #6 Space complexity O(n)
function arrayOfHiNTimes(n) {
    var hiArray = [];
    for (let i = 0; i < n; i++) {
        hiArray[i] = 'hi';
    }
    return hiArray;
}
```
