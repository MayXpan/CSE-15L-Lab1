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
  - The working directory for the screenshot below is ~/docsearch/technical/government/About_LSC.  The only difference from the commands above is that I used --color before the search term which highlighted the search term in the result.  This makes it much more easier to see what you were looking for when using a system that doesn't already do that for you.
 <img width="375" alt="image" src="https://github.com/MayXpan/cse-15l-labs/assets/130320757/50681211-91ff-4535-8474-2fb50c33eff7"> 

  - The working directory for the screenshot below is ~/docsearch/technical/government.  It does the same thing as above, but this time I used a path to specify the file because I wasn't in the directory that the file was located in.
  <img width="367" alt="image" src="https://github.com/MayXpan/cse-15l-labs/assets/130320757/8b7f3ee8-64be-4937-82dc-37ab7931e6f1">

3. Using -r to search recursively:
  - The working directory is ~/docsearch/technical.  By using -r, I'm able to search recursively through all of the subdirectories and files contained in the current working directory to search for the search term and return the lines that contain it.  This is useful for when you have a particular term you're looking for but don't necessarily remember where exactly it is stored.
```
$ grep -r "tomorrow" *
government/About_LSC/Progress_report.txt:Cultivating leaders of tomorrow
government/Gen_Account_Office/d01376g.txt:tomorrow. For example, one state CIO that we interviewed said that
government/Gen_Account_Office/d01591sp.txt:However, this trade-off between today's consumption and tomorrow's
government/Gen_Account_Office/d01591sp.txt:tomorrow's fiscal challenges. Saving the surpluses would allow the
government/Gen_Account_Office/Testimony_cg00010t.txt:government of tomorrow must be leaner, that it must eliminate
government/Post_Rate_Comm/Gleiman_gca2000.txt:Norm, I see that Gene's performance is tomorrow---afternoon. So,
government/Post_Rate_Comm/Gleiman_gca2000.txt:program tomorrow---with Gene---is rabid. Oops, I mean he is a
government/Post_Rate_Comm/Gleiman_gca2000.txt:say---Today a peacock tomorrow a feather duster! So, here goes-
plos/journal.pbio.0020164.txt:        models rapidly join tomorrow's trash heaps. Second, because biological phenomena are
plos/pmed.0020118.txt:        training tomorrow's doctors. However, follow-up studies of those who graduate suggest that
```
  - The working directory is ~/docsearch/technical/plos.  Additionally, when looking for a search term, it does not look for the exact word so if you want to search for an exact word you'd have to do the next command line option after this example.
```
$ grep -r "well-d" *
journal.pbio.0020101.txt:        after fights by means of a kiss and embrace. Such reunions are well-documented in a
journal.pbio.0020101.txt:        well-documented monkey example of social culture is the inheritance of rank positions in
journal.pbio.0020113.txt:        well-defined concept because it is not possible to optimize every species, says Deriso.
journal.pbio.0020147.txt:        Other areas where biologists have well-developed theories of the influences and impacts
journal.pbio.0020214.txt:        well-defined criteria, to only the strongest labs doing the best research. An often-heard
journal.pbio.0020263.txt:        of racism, including the historically well-documented Tuskegee Syphilis Study, Reid asks
journal.pbio.0020406.txt:        describes. It is one of the most venerable, well-documented, and controversial large-scale
journal.pbio.0020431.txt:        specificity and in a well-defined fashion. This property is not common among other
journal.pbio.0020431.txt:        with specificity and in well-defined structures, but the number of such pairs is limited
journal.pbio.0020431.txt:        can vary widely (Lilley 2000). It is impossible to construct well-defined large structures
pmed.0010008.txt:        well-described clinical syndromes with poorly understood pathogenesis [1,2,3]. A role for T
pmed.0010013.txt:        including private practice, to become active participants in well-designed,
pmed.0010021.txt:          recommendations to give high-dose therapy that have not been based on well-designed
pmed.0010056.txt:        available to researchers and—eventually—manufacturers. As we explain below, well-designed
pmed.0010061.txt:        There is a well-documented relationship between short sleep duration and high body mass
pmed.0020103.txt:          + , and appeared healthy, with abundant cytoplasm and a well-defined
pmed.0020162.txt:          The selected health outcomes were chosen because of their well-documented associations
```
4. Using -w to look for exact matching word:
  - The working directory is ~/docsearch/technical/plos.  Because I'm using -w it is specifically looking for lines that contain "monday" in the current working directory, which evidently is none so it returns nothing.
```
$ grep -w "monday" *

```
  - The working directory is ~/docsearch/technical/plos.  This time I'm using "Monday" instead of "monday" and because -w looks for the exact match this time it found lines in the .txt files in /plos that contained "Monday".  Additionally I could have used -i to ignore case sensitivity but I didn't.  By using -w it ensures that you are looking and getting exactly what you're searching for, although you need to be careful of when you type it in in case of any typos or lack of capitalization.
```
$ grep -w "Monday" *
pmed.0020059.txt:          The first step is to stratify the data by day of week: Monday, Tuesday,…, Sunday. The
pmed.0020059.txt:          z, given that it was observed on a Monday, is the same for all Mondays,
pmed.0020059.txt:          the same hospital and the same day of week. That is, if Monday was missing during the
```
