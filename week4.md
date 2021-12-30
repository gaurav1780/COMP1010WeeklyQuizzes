# Week 4 (Classes and objects - 1)

## Create objects
Consider the following class:
```java
public class Lecture {
  public int students;
  public String lecturer;
	public Lecture(String l, int s) {
		lecturer = l;
    students = s;
	}
}
```
Complete the code that creates an object named `data` of class `Lecurer` that has the lecturer "Gaurav" and 100 students.  
{1:SAC:=Lecture} {1:SAC:=data} = {1:SAC:=new} {1:SAC:=Lecture}({1:SAC:="Gaurav"}, {1:SAC:=100});

## local or class variables
Consider the following class:

```java
public class Rectangle {
	public int width, height;
	public Rectangle(int w, int h) {
		width = w;
		height = h;
	}

  public int foo(int widht) {
    return heigth * width;
  }

  public int foo() {
    return heigth * width;
  }
}

public class Client {
  public static void main(String[] args) {
    Rectangle r = new Rectangle({a}, {b});
    System.out.println(r.foo());
    System.out.println(r.foo({c}));
  }
}
```

What is the value printed in the **first** `System.out.println()` statement? {1:{a}*{b}}  
What is the value printed in the **second** `System.out.println()` statement? {1:{c}*{b}}

## Method vs constructor
Consider the following class:

```java
public class Rectangle {
 public int width, height;

public Rectangle(int w, int h) {
   width = w;
   height = h;
 }

public int area() {
    return height * width;
  }
}
```
**Remember to add spaces between words**

What is the header of the method in the `Rectangle` class? {1:SAC:=public int area()}  
What is the header of the constructor in the `Rectangle` class? {1:SAC:=public Rectangle(int w,int h)~=public Rectangle(int w, int h)}  

## References and instances

### Q1
Count the number of references and instances in the memory when the `System.out.println()` statement executes.
```java
public class House {
  public int bedrooms;
  public boolean hasPool;

  public House(int b, boolean h) {
    bedrooms = b;
    hasPool = h;
  }
}

public class Client {
  House h1 = new House(2, true);
  House h2 = new House(4, false);
  House h3 = h1;
  System.out.println("Done");
}
```
Number of references = {1:NM:=3}  
Number of instances = {1:NM:=2}  

### Q2
Count the number of references and instances in the memory when the `System.out.println()` statement executes.
```java
public class Lecture {
  public int students;
  public int lecturerID;

  public Lecture(int s, int l) {
    students = s;
    lecturerID = l;
  }
}

public class Client {
  public static void main(String[] args) {
    Lecture a = new Lecture(100, 1234);
    Lecture b = new Lecture(400, 5678);
    Lecture c = a;
    b.students += 10;
    a = null;
    b = null;
    System.out.println("Done");
  }
}
```
Number of references = {1:NM:=3}  
Number of instances = {1:NM:=1}  
