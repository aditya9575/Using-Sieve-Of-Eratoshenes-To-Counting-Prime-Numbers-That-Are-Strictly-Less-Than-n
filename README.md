# Using-Sieve-Of-Eratoshenes-To-Counting-Prime-Numbers-That-Are-Strictly-Less-Than-n
This is a explanatory repository that helps anyone to understand Sieve Of Eratoshenes approach


🔍 Algorithmic Marvel: Count Primes
Ever wondered how to efficiently count prime numbers below a given integer? 🧠 Look no further! 🚀 Let's delve into the intricacies of the "Sieve of Eratosthenes" algorithm using JavaScript. 🤖
🔢 Problem Statement:
Given an integer n, we aim to determine the count of prime numbers that are strictly less than n.
📊 Examples:
For n = 10, the output is 4 as prime numbers below 10 are 2, 3, 5, and 7.
For n = 0, the output is 0 (because there are no prime numbers less than 0).
For n = 1, the output is 0 (as 1 is not considered prime).
🚀 JavaScript Implementation:

var countPrimes = function(n) {
  let prime = new Array(n+1).fill(true);
  let count = 0;
  prime[0] = prime[1] = false;

    for (let i = 2; i < n; i++) {
        if (prime[i] === true) {
            count++;

            for (let j = 2 * i; j < n; j += i) {
                prime[j] = false;
            }
        }
    }

    return count;
};

🛠️ Algorithm Walkthrough:
Array Initialization:
Initialize an array prime of length n+1 filled with true.
Set the first two elements (0 and 1) to false.
Why n+1 length?
To accommodate indexing starting from 0 and facilitate ease in array traversal.
let prime = new Array(n+1).fill(true);
prime[0] = prime[1] = false;

Counting Primes:
Iterate from 2 to n and count prime numbers.
Make a variable count to keep track of prime numbers encountered, initialized to 0.
Initialize the loop from index 2 to ensure we don't complicate the algorithm's complexity.
Example loop:
let count = 0;
for (let i = 2; i < n; i++) {

Sieve of Eratosthenes:
Use the "Sieve of Eratosthenes" to mark multiples of prime numbers as false.
The inner loop starts from 2*i and increments by i in each iteration.
Example loop:
if (prime[i] === true) {
 count++;
 for (let j = 2 * i; j < n; j += i) {
  prime[j] = false;
 }
}
Return Prime Count:
Return the final count of prime numbers strictly less than n.
Example return statement:
return count;
Overall Execution:
The algorithm efficiently identifies prime numbers using the Sieve of Eratosthenes, progressively marking non-prime multiples as false.
By starting the loop from index 2 and employing an array of n+1 length, we seamlessly handle indexing intricacies, simplifying the iteration logic.
The resulting count provides the total number of prime numbers below the given integer n.

🎯 Constraints:
Ensure 0 <= n <= 5 * 10^6 for optimal performance.
🚨 Important Note:
This algorithm employs an optimized approach to swiftly identify prime numbers, making it a stellar choice for your prime-counting needs! 🌟
