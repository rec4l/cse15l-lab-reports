# Week 10 Lab Report
By: Jonathan Nguyen
PID: A17418793 <br>

# Part 1 - Debugging

Post from a student:

User: jmn003
Hello, I'm trying to figure out why the test below fails. The actual assertEquals line on line 39 appears to be correct, and line 33 appears to have the ideal expected result. I just can't figure out 
why the filter method applied on s1 will give an ArrayList of ("a", "a").

https://i.ibb.co/vJdqSq4/Screenshot-466.png
https://i.ibb.co/BGC9yDq/Screenshot-467.png

Reply from a TA:
Hey, jmn003! Thanks for the question. Yes, you are correct. The tests have the correct intended functionality, so you might want to consider looking at the implementation of the filter method!
Since the method returns "result", do you think it could be something to do with that variable?

Response from jmn003:
Thank you so much for the help! I realized that the result variable was initialized outside of the method and caused some unintended issues. I added a new line and was able to fix it quite easily!

https://i.ibb.co/QHssC2f/Screenshot-469.png


File structure needed:
- /home
  - /lib
    - hamcrest-core-1.3.jar
    - junit-4.13.2.jar
  - ListExamples.java

```
import java.util.Arrays;
import java.util.List;
import java.util.ArrayList;

interface StrChecker { boolean checkString(String s); }
    class ListEx {
        private static List<String> result = new ArrayList<>();
        // Returns a new list that has only the elements of the
        // input where the given StringChecker returns true
        static List<String> filter(List<String> list, StrChecker sc) {
            if(list.size() == 0) { return list; }
            result.clear();
            for(String s: list) {
                if(sc.checkString(s)) {
                    result.add(s);
                }
            }
            return result;
        }
}
```

  - TestListExamples.java
```
import static org.junit.Assert.*;
import org.junit.*;
import java.util.Arrays;
import java.util.List;

class IsA implements StrChecker {
    public boolean checkString(String s) {
        return s.equalsIgnoreCase("a");
    }
}

public class TestListExamples {
    @Test
    public void testFilter() {
        List<String> s1 = Arrays.asList("a", "b", "c");
        List<String> s2 = Arrays.asList("d", "a");

        List<String> expect = Arrays.asList("a");

        List<String> result1 = ListEx.filter(s1, new IsA());
        List<String> result2 = ListEx.filter(s2, new IsA());

        assertEquals(expect, result1);
        assertEquals(expect, result2);

    }

    @Test
    public void testFilter2() {
        List<String> s1 = Arrays.asList("a", "b", "c");
        List<String> s2 = Arrays.asList("d", "a", "a");

        List<String> expect1 = Arrays.asList("a");
        List<String> expect2 = Arrays.asList("a", "a");

        List<String> result1 = ListEx.filter(s1, new IsA());
        List<String> result2 = ListEx.filter(s2, new IsA());

        assertEquals(expect1, result1);
        assertEquals(expect2, result2);
    }
}
```
  - test.sh
```
javac -g -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java
java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore TestListExamples
```
