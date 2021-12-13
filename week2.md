# Week 2 (environment and syntax)

### class and method syntax
Fill in the blanks.

```java
public {1:SAC:=class} Person {
  public static void main(String[] args) {
    int[] arr = new int[] {10, 70, 15, 20, 43};
    int ans = countOdd(arr);
  }

  {1:SAC:=public} {1:SAC:=static} {1:SAC:=int} countOdd(int[] data) {
    int count = 0;
    for(int i = 0; i < data.length; i++) {
      if(data[i]%2 != 0) {
        count++;
      }
    }
    {1:SAC:=return} count;
  }
}

```

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

## Syntax errors
Given the following test case
```java
@Test
	public void testIsNull() {
		assertTrue(isNull(null));
		assertFalse(isNull(new int[]{10,70,20,90}));
	}
```  
Choose all the pictures that would cause a syntax error.
