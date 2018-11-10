# How to efficiently implement a recursive function ?
Most of the time, it's not a good idea to use recursion.
In fact, previous results are not stored so we need to compute multiple times the same function.

**Recursive Fibonacci :**
````javascript
function fib(n){
  if(n < 2) return n;
  return fib(n-1) + fib(n-2);
}
````
````
Time complexity : O(2^n)
Space complexity : O(n)
````
# Alternatives
Hopefully, there are some alternatives :

**Memoize Fibonacci :**
````javascript
function fib(n){
  var m = [0,1];
  for(let i=2; i<=n; i++)
    m[i] = m[i-1] + m[i-2];
  return m[n];
}
````
````
Time complexity : O(n)
Space complexity : O(n)
````
**Loop Fibonacci :**
````javascript
function fib(n){
  var a = 0, b = 1;
  for(let temp, i=2; i<=n; i++){
    temp = b;
    b += a;
    a = temp;
  }
  return b;
}
````
````
Time complexity : O(n)
Space complexity : O(1)
````

# Exercise
https://www.hackerrank.com/challenges/game-of-stones-1/problem
