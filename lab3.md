# Lab Report 3

### Part 1
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
<img width="585" alt="image" src="https://github.com/MayXpan/cse-15l-labs/assets/130320757/658d950a-50c4-4f7c-9039-6bff5ab230e6">
