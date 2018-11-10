Fibonnacci as a recursive function :
````javascript
function fib(n){
  if(n == 0) return 0;
  if(n == 1) return 1;
  return fib(n-1) + fib(n-2);
}
````

Simple Memoize (O(n) complexity):
````javascript
function fib(n){
  var m = [0,1];
  for(let i=2; i<=n; i++)
    m[i] = m[i-1] + m[i-2];
  return m[n];
}
````
