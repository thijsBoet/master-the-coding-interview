# Master the Coding Interview
Ultimate coding interview bootcamp. Get more job offers, negotiate a raise: Everything you need to get the job you want!

[UDEMY](https://www.udemy.com/course/master-the-coding-interview-data-structures-algorithms/)

---

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

findNemo(nemo);
findNemo(largeArray);
```

## Big O's

<img src="./img/big-O-complexity-chart.jpeg"
     alt="Markdown Monster icon"
     style="float: left; margin-right: 10px;" />

* O(1) Constant- no loops
* O(log N) Logarithmic- usually searching algorithms have log n if they are sorted (Binary Search)
* O(n) Linear- for loops, while loops through n items
* O(n log(n)) Log Liniear- usually sorting operations
* O(n^2) Quadratic- every element in a collection needs to be compared to ever other element. Two
  nested loops
* O(2^n) Exponential- recursive algorithms that solves a problem of size N
* O(n!) Factorial- you are adding a loop for every element