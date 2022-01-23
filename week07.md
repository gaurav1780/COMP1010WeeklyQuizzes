# Week 7 (Recursion - 2)

## Tail optimize
Tail-optimize the following function that returns the sum of the odd digits in n (assume it's not negative).

```java
public String foo(int n) {
  if(n == 0) {
    return "";
  }
  if(n%2 == 0) {
    return "0" + foo(n/2);
  }
  return "1" + foo(n/2);
}
```

```java
public int foo(int n, {1:SAC:=int} ans) {
  if(n == {1:NM:=0}) {
    return {1:SAC:=ans};
  }
  if(n%2 == 0) {
    return foo({1:SAC:=n}/2, {1:SAC:="0"} + ans);
  }
  return foo({1:SAC:=n}/2, {1:SAC:="1"} + ans);
}
```

## Tail Recursion
If java supported tail call optimization (it doesn't), what would be the most accurate answer for the following code if the first call was `foo(1, 0)`. Because `int` has limited space, `2147483647 + 1 = -2147483648`.

```java
public int foo(int n, int sum) {
  if(n == 0) {
    return sum;
  }
  return foo(n + 1, sum + n);
}
```

```java
public int foo(int n, int sum) {
  if(n == 0) {
    return sum;
  }
  return foo(n++, sum + n);
}
```

```java
public int foo(int n) {
  if(n == 0) {
    return 0;
  }
  return n + foo(n + 1);
}
```

Options: stack overflow error, infinite loop, returns a value successfully.

## Recursion with Arrays
Trace the method call where the initial call is foo([10, 70, 20, 30], 0, 40).

```java
public boolean foo(int[]arr, int idx, int sum) {
  if(sum == 0) {
    return true;
  } else if(sum < 0 || idx >= arr.length {
    return false;
  }
  if(foo(arr, idx + 1, sum - arr[idx])) {
    return true;
  }
  return foo(arr, idx + 1, sum);
}
```

foo([10, 70, 20, 30], 0, {1:NM:=40}) calls foo([10, 70, 20, 30], 1, {1:NM:=30})  
foo([10, 70, 20, 30], 1, {1:NM:=30}) calls foo([10, 70, 20, 30], 2, {1:NM:=-40})  
foo([10, 70, 20, 30], 2, {1:NM:=-40}) returns {1:SA:=false}  
foo([10, 70, 20, 30], 1, {1:NM:=30}) calls foo([10, 70, 20, 30], 2, {1:NM:=30})  
foo([10, 70, 20, 30], 2, {1:NM:=30}) calls foo([10, 70, 20, 30], 3, {1:NM:=10})  
foo([10, 70, 20, 30], 3, {1:NM:=10}) calls foo([10, 70, 20, 30], 4, {1:NM:=-20})  
foo([10, 70, 20, 30], 4, {1:NM:=-20}) returns {1:SA:=false}  
foo([10, 70, 20, 30], 3, {1:NM:=10}) calls foo([10, 70, 20, 30], 4, {1:NM:=10})  
foo([10, 70, 20, 30], 4, {1:NM:=10}) returns {1:SA:=false}  
foo([10, 70, 20, 30], 3, {1:NM:=10}) returns {1:SA:=false}  
foo([10, 70, 20, 30], 2, {1:NM:=30}) calls foo([10, 70, 20, 30], 3, {1:NM:=30})  
foo([10, 70, 20, 30], 3, {1:NM:=30}) calls foo([10, 70, 20, 30], 4, {1:NM:=0})  
foo([10, 70, 20, 30], 4, {1:NM:=0}) returns {1:SA:=true}  
foo([10, 70, 20, 30], 3, {1:NM:=30}) returns {1:SA:=true}
foo([10, 70, 20, 30], 2, {1:NM:=30}) returns {1:SA:=true}  
foo([10, 70, 20, 30], 1, {1:NM:=30}) returns {1:SA:=true}  
foo([10, 70, 20, 30], 0, {1:NM:=40}) returns {1:SA:=true}  
