# Week 1

### Primitive datatypes, modulo and division
What is the datatype for the following expressions? Remember that we use `double` instead of `float`.
`??? data = 10;`
`??? data = 70.2;`
`??? data = 'a';`
`??? data = "COMP1010";`
`??? data = 3 < 5;`

What is the value of `data` in the following expressions? - already in diagnostic quiz.
`int data = 10;`
`int data = 10.5;`
`double data = 10.5;`
`int data = 10/3;`
`double data = 10/3;`
`int data = 10.0/3;`
`double data = 10.0/3;`

Given that `16 % 3 = 1`, what is the values of `16 ??? 3 = 5 ??? 1`?

### Boolean expressions

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


### Arrays

### Strings
