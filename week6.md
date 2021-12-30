# Week 6 (Recursion - 1)

## count method calls
How many times (including the initial call) is the method `foo` called if the initial call is `foo(pow(2, {a}))`?

```java
public int foo(int n) {
  if(n == 0) {
    return 0;
  }
  return 2 + foo(n/2);
}
```
Answer: {a}+2

## Trace method call
```java
public int foo(int n) {
  if(n < 100) {
    return n;
  }
  int a = n % 100;
  int b = foo(n/100);
  return Math.max(a, b);
}
```
Trace the method call where the initial call is foo(174629)

foo(174629) calls {1:SAC:=foo(4629)}
{1:SAC:=foo(4629)} calls {1:SAC:=foo(29)}
{1:SAC:=foo(29)} returns {1:NM:=29}
{1:SAC:=foo(4629)} returns {1:NM:=46}
{1:SAC:=foo(174629)} returns {1:NM:=46}

Trace the method call where the initial call is foo(1274539)

foo(1274539) calls {1:SAC:=foo(74539)}
{1:SAC:=foo(74539)} calls {1:SAC:=foo(539)}
{1:SAC:=foo(539)} calls {1:SAC:=foo(9)}
{1:SAC:=foo(9)} returns {1:NM:=9}
{1:SAC:=foo(539)} returns {1:NM:=53}
{1:SAC:=foo(74539)} returns {1:NM:=74}
{1:SAC:=foo(1274539)} returns {1:NM:=74}



## Parameter function call - Daniels idea
The parameters passed to the **third** call to the function foo, assuming the first call is foo("aabab", 1), is:
foo("{1:SAC:=aab}", {1:NM:=4})

```java
public int foo(String str, int power) {
  if(str.isEmpty()) {
    return 0;
  }
  String sub = str.substring(0, str.length() - 1);
  if(str.charAt(str.length() - 1) == 'a') {
    return power + foo(sub, power * 2);
  }
  return foo(sub, power * 2);
}
```
