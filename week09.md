# Week 9 (Lists- 2)


### Iterator vs enhanced for loop
Select if an enhanced for loop or iterator would be most effective.

Enhanced
* Accessing all items in the list from the front.
* Sum all positive numbers in the list.

Iterator
* Accessing all items in the list from the back.
* Accessing all items in the second half of the list.
* Finding the index of the first `20` (if it exists in the list).
* Setting every odd number in the list to 0.
* Removing all negative numbers in the list.

## List Iterator
Fill in the blanks so that the code prints out the sum of the first half of the list. You can assume that the size of the list will always be even.

For example the list `[10, 70, 20, 90]` would print 80 (= 70 + 10).

```java
int sum = 0;
ListIterator<Integer> iter = list.listIterator({1:SA:=list.size()/2});
while({1:SA:=iter.hasPrevious()}) {
  sum += iter.previous();
}
System.out.println(sum);
```

### Lists inside lists
Given that `list1 = [[10, 70], [20], [90, 5, 30]]`, fill in the blanks of what `list1` and `list2` looks like after the following code.

#### Version 1
```java
ArrayList<ArrayList<Integer>> list2 = new ArrayList<>(list1);
list2.set(0, new ArrayList<>(Arrays.asList(2, 3)));
list2.get(1).set(0, 4);
list2.get(1).add(5);
```

list1 = \[[{1:NM:=10}, {1:NM:=70}], [{1:NM:=4}, {1:NM:=5}], [90, 5, 30]]  
list2 = \[[{1:NM:=2}, {1:NM:=3}], [{1:NM:=4}, {1:NM:=5}], [90, 5, 30]]  

#### Version 2
```java
ArrayList<ArrayList<Integer>> list2 = new ArrayList<>(list1);
list2.set(0, new ArrayList<>(Arrays.asList(2, 3)));
list2.get(1).set(0, 4);
list2.get(0).set(1, 5);
```

list1 = \[[{1:NM:=10}, {1:NM:=70}], [{1:NM:=4}], [90, 5, 30]]  
list2 = \[[{1:NM:=2}, {1:NM:=5}], [{1:NM:=4}], [90, 5, 30]]  

#### Version 3
```java
ArrayList<ArrayList<Integer>> list2 = new ArrayList<>(list1);
list2.get(0).set(1, 5);
list2.set(0, new ArrayList<>(Arrays.asList(2, 3)));
list2.get(1).set(0, 4);
```

list1 = \[[{1:NM:=10}, {1:NM:=5}], [{1:NM:=4}], [90, 5, 30]]  
list2 = \[[{1:NM:=2}, {1:NM:=3}], [{1:NM:=4}], [90, 5, 30]]  

#### Version 4
```java
ArrayList<ArrayList<Integer>> list2 = list1;
list2.set(0, new ArrayList<>(Arrays.asList(2, 3)));
list2.get(1).set(0, 4);
list2.get(0).set(1, 5);
```

list1 = \[[{1:NM:=2}, {1:NM:=5}], [{1:NM:=4}], [90, 5, 30]]  
list2 = \[[{1:NM:=2}, {1:NM:=5}], [{1:NM:=4}], [90, 5, 30]]  

#### Version 5
```java
ArrayList<ArrayList<Integer>> list2 = new ArrayList<>();
for(ArrayList<Integer> item : list1) {
  list2.add(new ArrayList<>(item));
}
list2.get(0).set(1, 5);
list2.set(0, new ArrayList<>(Arrays.asList(2, 3)));
list2.get(1).set(0, 4);
```

list1 = \[[{1:NM:=10}, {1:NM:=70}], [{1:NM:=20}], [90, 5, 30]]  
list2 = \[[{1:NM:=2}, {1:NM:=3}], [{1:NM:=4}], [90, 5, 30]]  
