Recursive Fibonacci :
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
Memoize Fibonacci :
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
Loop Fibonacci :
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
