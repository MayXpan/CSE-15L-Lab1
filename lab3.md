# Lab Report 3

### Part 1
The following code shows two tests, one that fails due to buggy code, while the other passes.
```
import static org.junit.Assert.*;
import org.junit.*;

public class ArrayTest {
  @Test
  public void testReversed() {
    // should fail
    int[] input = {1, 2, 3, 4, 5};
    assertArrayEquals(new int[]{5, 4, 3, 2, 1}, ArrayExamples.reversed(input));

    // should pass
    int[] input2 = {0, 0, 0};
    assertArrayEquals(new int[]{0, 0, 0}, ArrayExamples.reversed(input2));
  }
}
```
In the following image, it shows the output from running the tests shown above.
<img width="585" alt="image" src="https://github.com/MayXpan/cse-15l-labs/assets/130320757/658d950a-50c4-4f7c-9039-6bff5ab230e6">

The buggy code is:
```
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
```
And once fixed is:
```
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1];
    }
    return newArray;
  }
```
Originally, the buggy code made a new array but instead of copying in reverse from the argument array, it copied from the newly created array to the argument, which resulted in always returning an array of the argument length but all 0.  In order to fix this, simply had to switch the arr and newArrayin the original code around so that it would copy in reverse to the new array and return the new array.

### Part 2

