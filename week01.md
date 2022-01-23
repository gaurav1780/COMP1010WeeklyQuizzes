# Week 1

### Primitive datatypes, modulo and division

What are the data types for each of the following variables? Remember to use `double` instead of `float`.  
`??? data = 10;`  
`??? data = 70.2;`  
`??? data = 'a';`  
`??? data = "COMP1010";`  
`??? data = 3 < 5;`  

Given that `16 % 3 = 1`, fill in the values of `16 {1:SA:/} 3 = 5 {1:SA:+} 1`.

### Function calls
Fill in the blanks.
```java
public static void main(String[] args) {
  double ans = foo(true, 5);
}

public static ??? foo(??? a, ??? b) {
  // some code
}
```

What will the function call `foo(3, 4)` return?
```java
public static int foo(int a, int b) {
  if (a > b) {
    return 1;
  } else if (b < a) {
    return -1;
  }
  return 0;
}
```


In which order will the functions be called?
```java
public static void main(String[] args) {
  a(5);
}

public static int a(int data) {
  return c(data + 1) + b(true);
}

public static int b(boolean data) {
  if(data == true) {
    return 1;
  }
  return -1;
}

public static int c(int data) {
  int b = data * 2;
  b -= 3;
  return b;
}
```

main(String[] args) calls a(5)  
a(5) calls `c(6)`
`c(6)` returns `9`
`a(5)` calls `b(true)`  
`b(true)` returns `1`  
`a(5)` returns `10`  

## for and while loops

Complete the for loop so that sum becomes the sum of the first `n` numbers.
```java
int sum = 0;
int n = 5;
for(int ??? = 0; i < n; ???) {
  sum += i;
}
System.out.println(sum); // 0 + 1 + 2 + ... + n
```

Complete the while loop so that sum becomes the product of the first `n` numbers.
```java
int sum = 1;
int n = 5;
int ??? = 1;
while(???) {
  sum *= i;
  ???;
}
System.out.println(sum); // 1 * 2 * ... * n
```

### Arrays

### Strings
