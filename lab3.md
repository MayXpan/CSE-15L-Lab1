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

grep
---
1. Using grep:
    - The working directory for the following code block is ~/docsearch/technical.  Grep is typically used to find lines that match the search term, however because technical only contains directories, it instead prints out the directories contained and says so.  It doesn't matter what the search string is as a result of there being no .txt files.
```
$ grep "" *
grep: 911report: Is a directory
grep: biomed: Is a directory
grep: government: Is a directory
grep: plos: Is a directory
```
  - The working directory for the following code block is ~/docsearch/technical/government/About_LSC.  This time because the directory this is being used in contains .txt files and I'm using * so it will look through all files, it searches all of the .txt files in the working directory to find lines in all files that contain the search term, which in this case is "and then".  If instead of *, I used a file name like commission_report.txt, it would have instead just print out the lines that the search term was found on without the file name before it.  This can be useful to find the line in a file that contains the search term you're looking for.
```
$ grep "and then" *
commission_report.txt:the October apple harvest, and then return to Mexico until the work
commission_report.txt:may spend April to October in remote parts of California and then
commission_report.txt:et. al). The need to recoup this investment, and then hopefully to
LegalServCorp_v_VelazquezDissent.txt:restriction- and then, to add insult to injury, permits to stand a
Special_report_to_congress.txt:LSC (to produce a total caseload number) and then reduced by the
State_Planning_Report.txt:created on line and then printed out in ready-to-file form. The
State_Planning_Special_Report.txt:first by the LSC Vice President for Programs and then by the LSC
Strategic_report.txt:President Randi Youells and then to President Erlenborn for final
Strategic_report.txt:American clients, and then transfer eligibility and case data over
```
2. Using --color:
   -
```
$ grep --color "and then" commission_report.txt
the October apple harvest, and then return to Mexico until the work
may spend April to October in remote parts of California and then
et. al). The need to recoup this investment, and then hopefully to
```
