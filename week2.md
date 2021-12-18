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

## format of java file
Fill in the blanks given that the class header is  
`public class Abc {`

The name of the class file is: {1:SAC:=Abc.java}  
To compile the java program: {1:SAC:=javac} {1:SAC:=Abc.java}
To run the java program from the command line: `java {1:SAC:=Abc}`
