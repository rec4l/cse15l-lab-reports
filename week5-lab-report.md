dddd

# Part 1 - Bugs

Bug chosen: bug in ``ArrayExamples.java`` in the ``reversed`` method

A failure-inducing input for the buggy program:
```
@Test
public void testReversed2() {
  int[] input1 = {1, 2, 3};
  assertArrayEquals(new int[]{3, 2, 1}, ArrayExamples.reversed(input1));
}
```
The symptom: (place imgur link)

An input that does not cause a failure:
```
@Test
public void testReversed2() {
  int[] input1 = {0, 0, 0};
  assertArrayEquals(new int[]{0, 0, 0}, ArrayExamples.reversed(input1));
}
```
The symptom: (place imgur link)

The bug: 
```
static int[] reversed(int[] arr) {
  int[] newArray = new int[arr.length];
  for(int i = 0; i < arr.length; i += 1) {
    arr[i] = newArray[arr.length - i - 1];
  }
  return arr;
}
```

The fixed code:
```
static int[] reversed(int[] arr) {
  int[] newArray = new int[arr.length];
  for(int i = 0; i < arr.length; i += 1) {
    newArray[i] = arr[arr.length - i - 1];
  }
  return newArray;
}
```

My reasoning for the bugfix:

The programmer was affecting the input array instead of the initialized array and additionally returned the wrong array. Grabbing values in reverse from a initialized array will not reverse the array. 


# Part 2 - Researching Commands

##Chosen command: ``less``

### The argument: ``-N`` 
The directory: ``~/Downloads/docsearch/`` \n
The command: ``less -N biomed-sizes.txt`` \n
Output: (insert imgur link) \n
Explanation: It output a column of line numbers on the left hand side. I expect this to be helpful if the file was sorted in some meaningful order. 

The command: ``less -N gb-2003-4-9-r60.txt``
The directory: ``~/Downloads/docsearch/technical/biomed``
Output: (insert imgur link)
Explanation: It output a column of line numbers on the left hand side. I expect this to be helpful if the file was sorted in some meaningful order.

### The argument: ``-w``
The directory: ``~/Downloads/docsearch/technical/government/media``
The command: ``less -w Law_Schools.txt``
Output: (insert imgur link)
Explanation: It highlights the line previously at the bottom when scrolling. It seems to mostly be an accessibility thing, and I quite like it.

The directory: ``~/Downloads/docsearch/technical/biomed``
The command: ``less -w gb-2003-4-9-r60.txt``
Output: (insert imgur link)
Explanation: It highlights the line previously at the bottom when scrolling. It seems to mostly be an accessibility thing, and I quite like it.

### The argument: ``--window=n``
The directory: ``~/Downloads/docsearch/technical/government/media``
The command: ``less --window=1 -w Law_Schools.txt``
Output: (insert imgur link)
Explanation: It changes the default scroll setting to be in n lines, in this case I wanted it to scroll only 1 line when I clicked space. It is useful if your reading style varies from the default setting.

The directory: ``~/Downloads/docsearch/technical/plos``
The command: ``less --window=3 -w pmed.0020201.txt``
Output: (insert imgur link)
Explanation: It changes the default scroll setting to be in n lines, in this case I wanted it to scroll only 1 line when I clicked space. It is useful if your reading style varies from the default setting.

### The argument: ``-f``
The directory: ``~/Downloads/docsearch``
The command: ``less -f lib``
Output: (insert imgur link)
Explanation: It forces a file to be opened by the less command, whether or not it is allowed by default. In this case, using it on a directory output nothing, which makes sense to me.

The directory: ``~/Downloads/docsearch/technical/government/About_LSC``
The command: ``less -f conference_highlights.txt``
Output: (insert imgur link)
Explanation: -f forces a file to be opened regardless if it can or not, but if used on a normal .txt file then it appears to just open it normally.


Cited source: https://linux.die.net/man/1/less

