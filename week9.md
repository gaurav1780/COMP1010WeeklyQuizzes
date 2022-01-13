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
