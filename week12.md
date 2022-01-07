# Week 12 - recursive data structures - 2

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


## References and instances
Count the number of references and instances in the memory when the `System.out.println()` statement executes. The **only change** between this and the next question is the `add` methodsa.

```java
class LinkedList {
  Node head;

  public LinkedList(int value) {
    head = new Node(value, null);
  }

  public void add(Node n) {
    // Finds the last Node last in the list and sets last.next to n
  }

  public void add(int value) {
    // adds a new Node with the value to the end of the list.
  }
}

class Client {
  public static void main(String[] args) {
    Node a = new Node(20, null);
    a = new Node(90, a);

    LinkedList list = new LinkedList(10);
    list.add(a);
    list.add(70);
    System.out.println("Here");
  }
}
```

The number of reference copies are {1:NM:=7}
The number of instance copies are {1:NM:=5}

### Question 2
Count the number of references and instances in the memory when the `System.out.println()` statement executes. The **only change** between this and the previous question is the `add` methodsa.

```java
class LinkedList {
  Node head;

  public LinkedList(int value) {
    head = new Node(value, null);
  }

  public void add(Node n) {
    n.next = head;
    head = n;
  }

  public void add(int value) {
    head = new Node(head.value, head.right);
  }
}

class Client {
  public static void main(String[] args) {
    Node a = new Node(20, null);
    a = new Node(90, a);

    LinkedList list = new LinkedList(10);
    list.add(a);
    list.add(70);
    System.out.println("Here");
  }
}
```

The number of reference copies are {1:NM:=6}
The number of instance copies are {1:NM:=4}
