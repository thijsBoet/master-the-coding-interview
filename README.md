# Master the Coding Interview
Ultimate coding interview bootcamp. Get more job offers, negotiate a raise: Everything you need to get the job you want!

[UDEMY](https://www.udemy.com/course/master-the-coding-interview-data-structures-algorithms/)

# 1) Getting the interview
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

# 2) Big O Notation
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
* Adding Variables
* Adding Data Structures
* Adding Function Call
* Allocations

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

# 3) How to solve coding Problems
## What skills interviewer is looking for?
* Analytic Skills - How can you think through problems and analyze things?
* Coding Skills - Do you code well, by writing clean, simple, organized, readable code?
* Technical knowledge - Do you know the fundamentals of the job you're applying for?
* Communication skills - Does your personality match the companies’ culture?

# Step By Step through a problem:
1. When the interviewer says the question, write down the key points at the top (i.e. sorted
array). Make sure you have all the details. Show how organized you are.

2. Make sure you double check: What are the inputs? What are the outputs?

3. What is the most important value of the problem? Do you have time, and space and memory,
etc.. What is the main goal?

4. Don't be annoying and ask too many questions.

5. Start with the naive/brute force approach. First thing that comes into mind. It shows that
you’re able to think well and critically (you don't need to write this code, just speak about it).
6. Tell them why this approach is not the best (i.e. O(n^2) or higher, not readable, etc...)

7. Walk through your approach, comment things and see where you may be able to break things.
Any repetition, bottlenecks like O(N^2), or unnecessary work? Did you use all the information
the interviewer gave you? Bottleneck is the part of the code with the biggest Big O. Focus on
that. Sometimes this occurs with repeated work as well.

8. Before you start coding, walk through your code and write down the steps you are going to
follow.

9. Modularize your code from the very beginning. Break up your code into beautiful small pieces
and add just comments if you need to.

10. Start actually writing your code now. Keep in mind that the more you prepare and understand
what you need to code, the better the whiteboard will go. So never start a whiteboard
interview not being sure of how things are going to work out. That is a recipe for disaster.
Keep in mind: A lot of interviews ask questions that you won’t be able to fully answer on time.
So think: What can I show in order to show that I can do this and I am better than other
coders. Break things up in Functions (if you can’t remember a method, just make up a function
and you will at least have it there. Write something, and start with the easy part.

11. Think about error checks and how you can break this code. Never make assumptions about the
input. Assume people are trying to break your code and that Darth Vader is using your
function. How will you safeguard it? Always check for false inputs that you don’t want. Here is
a trick: Comment in the code, the checks that you want to do… write the function, then tell the
interviewer that you would write tests now to make your function fail (but you won't need to
actually write the tests).

12. Don’t use bad/confusing names like i and j. Write code that reads well.
    
13. Test your code: Check for no params, 0, undefined, null, massive arrays, async code, etc… Ask
the interviewer if we can make assumption about the code. Can you make the answer return
an error? Poke holes into your solution. Are you repeating yourself?

14. Finally talk to the interviewer where you would improve the code. Does it work? Are there
different approaches? Is it readable? What would you google to improve? How can
performance be improved? Possibly: Ask the interviewer what was the most interesting
solution you have seen to this problem.

15. If your interviewer is happy with the solution, the interview usually ends here. It is also
common that the interviewer asks you extension questions, such as how you would handle the
problem if the whole input is too large to fit into memory, or if the input arrives as a stream.
This is a common follow-up question at Google, where they care a lot about scale. The answer
is usually a divide-and-conquer approach — perform distributed processing of the data and only
read certain chunks of the input from disk into memory, write the output back to disk and
combine them later.
```javascript
// Given 2 arrays, create a function that let's a user know (true/false) whether these two arrays contain any common items
//For Example:
//const array1 = ['a', 'b', 'c', 'x'];//const array2 = ['z', 'y', 'i'];
//should return false.
//-----------
//const array1 = ['a', 'b', 'c', 'x'];//const array2 = ['z', 'y', 'x'];
//should return true.

// 2 parameters - arrays - no size limit
// return true or false

function containsCommonItem(arr1, arr2) {
  for (let i=0; i < arr1.length; i++) {
    for ( let j=0; j < arr2.length; j++) {
      if(arr1[i] === arr2[j]) {
        return true;
      }
    }
  }
  return false
}

//O(a*b)
//O(1) - Space Complexity

const array1 = ['a', 'b', 'c', 'x'];
const array2 = ['z', 'y', 'a'];

function containsCommonItem2(arr1, arr2) {
  // loop through first array and create object where properties === items in the array
  // can we assume always 2 params?

  let map = {};
  for (let i=0; i < arr1.length; i++) {
    if(!map[arr1[i]]) {
      const item = arr1[i];
      map[item] = true;
    }
  }
  // loop through second array and check if item in second array exists on created object. 
  for (let j=0; j < arr2.length; j++) {
    if (map[arr2[j]]) {
      return true;
    }
  }
  return false
}

//O(a + b) Time Complexity
//O(a) Space Complexity

// containsCommonItem2(array1, array2)

function containsCommonItem3(arr1, arr2) {
  return arr1.some(item => arr2.includes(item))
}

containsCommonItem(array1, array2)
containsCommonItem2(array1, array2)
containsCommonItem3(array1, array2)
```