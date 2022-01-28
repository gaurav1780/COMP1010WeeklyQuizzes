# Week 10 - Stack and queue

## Difference between stack and queue
* First in - First out is a {1:MC:=Queue~Stack}
* Last in - First out is a {1:MC:=Stack~Queue}

## Reverse polish notation
#### Version 1
Given the expression `(10 + 70) / (20 - 90)`.

What would the reverse polish notation be?  
{1:SA:=10}{1:SA:=70}{1:SA:=+}{1:SA:=20}{1:SA:=90}{1:SA:=-}{1:SA:=/}

What would the stack look like before the division operation?  
{1:SA:=80}{1:SA:=110}

#### Version 2
Given the expression `(10 + 70) / (20 - 90)`.

What would the reverse polish notation be?  
{1:SA:=10}{1:SA:=70}{1:SA:=+}{1:SA:=20}{1:SA:=90}{1:SA:=-}{1:SA:=/}

What would the stack look like before the subtraction operation?  
{1:SA:=80}{1:SA:=20}{1:SA:=90}

#### Version 3
Given the expression `((10 + 70) / 20) * 90`.

What would the reverse polish notation be?  
{1:SA:=10}{1:SA:=70}{1:SA:=+}{1:SA:=20}{1:SA:=/}{1:SA:=90}{1:SA:=*}

What would the stack look like before the multiplication operation?  
{1:SA:=40}{1:SA:=90}

## add/remove
Given the following `add()` and `remove()` methods, determine if the class is for a **stack** or **queue**.

The methods may not be the same as you have seen in class!

#### Version 1 - stack
```java
public int add(int val) {
  if(this.isFull()) {
    grow();
  }
  data[nItems++] = val;
}

public int remove() {
  if(nItems == 0) {
    return -1;
  }
  int val = data[nItems - 1];
  nItems--;
  return val;
}
```

#### Version 2 - stack
```java
public int add(int val) {
  if(this.isFull()) {
    grow();
  }
  data[nItems--] = val;
}

public int remove() {
  if(nItems == data.length() - 1) {
    return -1;
  }
  int val = data[nItems + 1];
  nItems++;
  return val;
}
```

#### Version 3 - queue
```java
public int add(int val) {
  if(this.isFull()) {
    grow();
  }
  data[lastItem++] = val;
}

public int remove() {
  if(firstItem >= lastItem) {
    return -1;
  }
  int val = data[firstItem++];
  return val;
}
```

#### Version 4 - queue
```java
public int add(int val) {
  if(this.isFull()) {
    grow();
  }
  data[lastItem--] = val;
}

public int remove() {
  if(firstItem <= lastItem) {
    return -1;
  }
  int val = data[firstItem--];
  return val;
}
```
