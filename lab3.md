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
    int[] input2 = {1, 1, 1, 1};
    assertArrayEquals(new int[]{1, 1, 1, 1}, ArrayExamples.reversed(input2));
  }
}
```
