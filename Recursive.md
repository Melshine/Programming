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
# A good example
Some problems are easier to solve with recursion than with loops. Most often these are problems that require exploring or processing several “branches”, each of which might branch out again into even more branches.

*Consider this puzzle: by starting from the number 1 and repeatedly either adding 5 or multiplying by 3, find a sequence of such additions and multiplications to reach a number "target" ?*
````javascript
function findSolution(target){
  function find(current, history){
    if(current == target) return history;
    if(current > target) return null;
    return find(current+5, `(${history}+5)`) || 
           find(current*3, `(${history}*3)`)
    }
  return find(1,"1");
}
````
# Exercise
https://www.hackerrank.com/challenges/game-of-stones-1/problem
