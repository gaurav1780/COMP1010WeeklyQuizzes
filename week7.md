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


## DP - find better question

```java
int[] lookup;
public int fib(int n) {
  if(lookup[n] != 0) {
    return lookup[n];
  }
  lookup[n] = fib(n - 3); // Notice it's 3 NOT 2
  lookup[n] = lookup[n] + fib(n - 1);
  return lookup[n];
}

public void main(String[] args) {
  lookup = new int[6];
  lookup[1] = 1;
  lookup[2] = 2;
  fib(5);
}
```

Trace the method call where the initial call is fib(5)

fib(5) calls fib({1:NM:2})
fib({1:NM:=2}) returns {1:NM:=2}
lookup[5] = {1:NM:=2}
fib({1:NM:=5}) calls fib({1:NM:=4})
fib({1:NM:=4}) calls fib({1:NM:=1})
fib({1:NM:=1}) returns {1:NM:=1}
lookup[{1:NM:4}] = {1:NM:=1}
fib({1:NM:=4}) calls fib({1:NM:=3})
fib({1:NM:=3}) calls fib({1:NM:=0})
fib({1:NM:=0}) returns {1:NM:=0}
lookup[{1:NM:3}] = {1:NM:=0}
fib({1:NM:=3}) calls fib({1:NM:=2})
fib({1:NM:=2}) returns {1:NM:=2}
lookup[{1:NM:3}] = {1:NM:=2}
fib({1:NM:=3}) returns {1:NM:=2}
lookup[{1:NM:4}] = {1:NM:=3}
fib({1:NM:=4}) returns {1:NM:=3}
lookup[{1:NM:5}] = {1:NM:=5}
fib({1:NM:=5}) returns {1:NM:=5}
