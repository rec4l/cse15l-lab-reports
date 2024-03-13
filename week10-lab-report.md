# Week 10 Lab Report
By: Jonathan Nguyen
PID: A17418793 <br>

# Part 1 - Debugging

Post from a student:

**User: jmn003** <br>
Hello, I'm trying to figure out why the test below fails. The actual assertEquals line on line 39 appears to be correct, and line 33 appears to have the ideal expected result. I just can't figure out 
why the filter method applied on s1 will give an ArrayList of ("a", "a"). I additionally looked at the filter method and cannot find anything wrong, so could it be the test, filter method, or even running the test.sh file???

![Image](https://i.ibb.co/vJdqSq4/Screenshot-466.png)
![Image](https://i.ibb.co/BGC9yDq/Screenshot-467.png)

**Reply from a TA:** <br>
Hey, jmn003! Thanks for the question. Yes, you are correct. The tests have the correct intended functionality, so you might want to consider looking at the implementation of the filter method!
Since the method returns "result", do you think it could be something to do with that variable?

**Response from jmn003:** <br>
Thank you so much for the help! I realized that the result variable was initialized outside of the method and caused some unintended issues. I added a new line and was able to fix it quite easily!

![Image](https://i.ibb.co/QHssC2f/Screenshot-469.png)


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


How to trigger the bug:
`bash test.sh`

What to edit to fix the bug:
```
static List<String> filter(List<String> list, StrChecker sc) {
            List<String> result = new ArrayList<>(); // <<<-------- NEW LINE!!!!!!!!!
            if(list.size() == 0) { return list; }
            result.clear();
            for(String s: list) {
                if(sc.checkString(s)) {
                    result.add(s);
                }
            }
            return result;
        }
```

# Part 2 - Reflection

My favorite part about the second half of the quarter was learning how to use vim, I've always heard a lot about vim but using it myself was quite an experience! I had fun using the vim tutorial on the lab computers, and I found out that it was a completely new experience of programming that I hadn't experienced before! I can't say for sure whether it'll stick with me but it's an added tool that I can use whenever I'd like, and I feel a bit more competent now that I'm aware of its existence and I have (admittedly very novice) experience using it! Thank you for showing me vim and I hope to use it again soon.

