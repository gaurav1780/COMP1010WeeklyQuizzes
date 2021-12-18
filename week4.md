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
{1:SAC:=Lecture} {1:SAC:=data} = {1:SAC:=new} {1:SAC:=Lecture}({1:SAC:="Gaurav"}, {1:SAC:100});

## local or class varaiables
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
  Rectangle r = new Rectangle({a}, {b});
  System.out.println(r.foo());
  System.out.println(r.foo({c}));
}
```

What is the value printed in the **first** `System.out.println()` statement? {1:{a}*{b}}  
What is the value printed in the **second** `System.out.println()` statement? {1:{a}*{b}}

## Method vc constructor
Consider the following class:

```java
public class Rectangle {
 public int width, height;

public Rectangle(int w, int h) {
   width = w;
   height = h;
 }

public int area() {
    return heigth * width;
  }
}
```

What is the header of the method in the `Rectangle` class? {1:SAC:=public int area()}  
What is the header of the constructor in the `Rectangle` class? {1:SAC:=public Rectangle(int w, int h)}  
