# Week 3 (JUnit, problem solving)

## JUnit format

Assume that the function `sum(int[])` is already implemented so that it returns the sum of all elements in the array. Fill in the blanks to ensure the syntax is correct and all tests pass.

```java
@Test
public void testSum() {
  int[] data = new int[] {10, 70, 20, 90};
  {1:SAC:=assertEquals}(190, {1:SAC:=sum(data)});
  {1:SAC:=assertTrue}(190 == sum(data));
  assertFalse(190 {1:SAC:=!=} sum(data));
}
```


## Array + memory diagram
Fill in the code blocks so that the memory diagram correctly represents the code. Remember not to add any spaces in the answer.

```java
int[][] data = new int[4][];
data[0] = {1:SAC:=new int[]{10,70,20,90}}
data[1] = {1:SAC:=new int[]{5,20,15}}
data[2] = {1:SAC:=null}
data[3] = {1:SAC:=data[0]}
```

## Test quality
Consider a function that returns the sum of all positive numbers between two indices. Pair the test case together with the best fit for what it tests. Assume the input for the function is in the format `(int[] data, int start, int end)`

Test cases
* {10, 20, 90, 70}, 1, 3 // Sum's the values incusive of both ranges.
* {10, 20, 90, 70, 5}, 1, 4 // Ensures the `end` limit is not hard coded.
* {10, 20, 90, 70}, 0, 4 // Can handle invalid `end` value.
* {10, 20, 90, 70}, -1, 2 // Can handle invalid `start` value.
* {10, 20, -90, 70}, 1, 3 // Does not sum the invalid number.
* {10, -20, -90, -70}, 2, 3 // Returns 0 if there are no valid numbers.
