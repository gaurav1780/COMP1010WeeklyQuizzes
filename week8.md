# Week 8 (Lists- 1)

## Syntax of Lists
Fill in the blanks in the code so that the comments correctly represents the list.
The answers should not inculude any special characters.


#### Version 1
```java
ArrayList<{1:SAC:=Integer}> list = new ArrayList<>();
list.add({1:NM:=10}); //[10]
list.{1:SA:=add}(5); //[10, 5]
list.add({1:NM:=1}, 70); //[10, 70, 5]
list.add({1:NM:=20}); //[10, 70, 5, 20]
list.{1:SA:=set}(2, list.get({1:NM:=3})); //[10, 70, 20, 20]
list.{1:SA:=remove}((Integer){1:NM:=20}); //[10, 70, 20]
list.add({1:NM:=90}); //[10, 70, 20, 90]
```

#### Version 2
```java
ArrayList<{1:SAC:=Integer}> list = {1:SA:=new} ArrayList<>();
list.add({1:NM:=70}); //[70]
list.{1:SA:=add}(5); //[70, 5]
list.add({1:NM:=0}, 70); //[5, 70, 5]
list.{1:SA:=set}({1:NM:=2}, {1:NM:=20}); //[5, 70, 20]
list.add(90);  //[5, 70, 20, 90]
list.{1:SA:=remove}(list.{1:SA:=indexOf}(20)); //[5, 70, 90]
```

#### Version 3
```java
ArrayList<Integer> {1:SA:=list} = {1:SA:=new} ArrayList<>();
list.add({1:NM:=20}); //[20]
list.add({1:SA:=null}); //[20, null]
list.{1:SA:=set}(list.{1:SA:=indexOf}(null), {1:NM:=10}); //[20, 10]
list.{1:SA:=add}(70); //[20, 10, 70]
list.{1:SA:=remove}(1); //[20, 70]
list.add({1:NM:=1}, {1:NM:90}); //[20, 90, 70]
```
