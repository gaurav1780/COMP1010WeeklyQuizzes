# Week 11 - Recursive data structures - 1

All questions in this quiz will be using the following Node class.
```java
class Node {
  int value;
  Node right;

  public Node(int v, Node r) {
    value = v;
    right = r;
  }
}
```

## Tracing linked list
Given the following code.
```java
class Client {
  public static void main(String[] args) {
    Node a = new Node(10, null);
    Node b = new Node(70, a);
    Node c = new Node(20, b);
    Node e = new Node(5, c);
    Node f = new Node(15, c);
    Node g = new Node(35, e);
  }
}
```
### Version 1
The value of `c.value` is {1:NM:=20}
The value of `c.next.value` is {1:NM:=70}
The value of `g.next.next.next.value` is {1:NM:=70}
The value of `f.next.next.value` is {1:NM:=20}

### Version 2
The value of `b.value` is {1:NM:=70}
The value of `g.next.value` is {1:NM:=5}
The value of `f.next.next.next.value` is {1:NM:=10}
The value of `e.next.next.value` is {1:NM:=70}


## References and instances
Count the number of references and instances in the memory when the `System.out.println()` statement executes.

```java
class Client {
  public static void main(String[] args) {
    Node a = new Node(10, null);
    a = new Node(70, a);
    Node b = new Node(20, a.next);
    Node c = new Node(90, b);
  }
}
```

The number of reference copies are {1:NM:=7}
The number of instance copies are {1:NM:=4}


## ArrayList vs LinkedList
Select if an ArrayList, LinkedList or both would be the most efficient data structure to use.

ArrayList
* Accessing the n'th value in the list.
* Takes up less space in memory.

LinkedList
* Adding a value to the front.
* Adding a value to the back.
* Removing a value in the middle of the list.

Both
* Finding the first occurrence of a value in the list.
