# Week 5 (Classes and objects - 2)

## CompareTo
Consider the following class:

```java
public class Rectangle {
  public int width, height;\

  public Rectangle(int w, int h) {
    width = w;
    height = h;
  }

  public int area() {
    return width * height;
  }

  public int compareTo(Rectangle other) {
    int diff = this.area() - other.area();
    if(diff > 0) {
      return 1;
    } else if(diff < 0) {
      return -1;
    }
    return 0;
  }
}

public class Client {
  public static void main(String[] args) {
    Rectangle a = new Rectangle({a}, {a});
    Rectangle b = new Rectangle({b}, {c});
    System.out.println(a.compareTo(b));
  }
}
```
What will be printed to the console? {max(-1, min(1, {a}\*{a} - {b}\*{c}))}


## Memory diagrams
Fill in the blanks so that the code matches the memory diagram.
```java
public class Student {
  public int wam, studentID;

  public Rectangle(int wam, int s) {
    {1:SAC:=this.wam} = {1:SAC:=wam};
    studentID = s;
  }
}

public class Client {
  public static void main(String[] args) {
    {1:SAC:=Student[]} data = new Student[4];
    data[0] = {1:SAC:=new Student(75, 123)};
    data[1] = {1:SAC:=data[0]};
    data[2] = {1:SAC:=null};
    data[3] = {1:SAC:=new Student(65, 567)};
  }
}
```
