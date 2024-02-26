# Week 5 Lab Report
By: Jonathan Nguyen
PID: A17418793 <br>
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
The symptom: <br> ![Image](https://i.imgur.com/kArZdAV.png)

An input that does not cause a failure:
```
@Test
public void testReversed2() {
  int[] input1 = {0, 0, 0};
  assertArrayEquals(new int[]{0, 0, 0}, ArrayExamples.reversed(input1));
}
```
The symptom: <br> ![Image](https://i.imgur.com/Zaj8bBM.png)

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
### Example 1: <br>
The directory: ``~/Downloads/docsearch/`` <br>
The command: ``less -N biomed-sizes.txt`` <br>
Output: <br> ```
      1      432     3380    24544 technical/biomed/1468-6708-3-1.txt
      
      2      533     3630    30118 technical/biomed/1468-6708-3-10.txt
      
      3      296     2166    17178 technical/biomed/1468-6708-3-3.txt 
      
      4      547     4301    31925 technical/biomed/1468-6708-3-4.txt 
      
      5      317     2312    18431 technical/biomed/1468-6708-3-7.txt 
      6      411     3181    24439 technical/biomed/1471-2091-2-10.txt
      7      615     4684    35718 technical/biomed/1471-2091-2-11.txt
      8      515     3287    25366 technical/biomed/1471-2091-2-12.txt
      9      564     3550    28534 technical/biomed/1471-2091-2-13.txt
     10      339     2496    19055 technical/biomed/1471-2091-2-16.txt
     11      826     5832    46240 technical/biomed/1471-2091-2-5.txt 
      1      432     3380    24544 technical/biomed/1468-6708-3-1.txt
      2      533     3630    30118 technical/biomed/1468-6708-3-10.txt
      3      296     2166    17178 technical/biomed/1468-6708-3-3.txt
      4      547     4301    31925 technical/biomed/1468-6708-3-4.txt
      5      317     2312    18431 technical/biomed/1468-6708-3-7.txt
      6      411     3181    24439 technical/biomed/1471-2091-2-10.txt
      7      615     4684    35718 technical/biomed/1471-2091-2-11.txt
      8      515     3287    25366 technical/biomed/1471-2091-2-12.txt
      9      564     3550    28534 technical/biomed/1471-2091-2-13.txt
     10      339     2496    19055 technical/biomed/1471-2091-2-16.txt
     11      826     5832    46240 technical/biomed/1471-2091-2-5.txt
     12      501     3167    25959 technical/biomed/1471-2091-2-7.txt
     13      481     3637    25779 technical/biomed/1471-2091-2-9.txt
     14      537     4002    29676 technical/biomed/1471-2091-3-13.txt
     15      932     7125    55781 technical/biomed/1471-2091-3-14.txt
     16      673     4858    34882 technical/biomed/1471-2091-3-15.txt
     17      702     5011    36655 technical/biomed/1471-2091-3-16.txt
     18      642     4251    30111 technical/biomed/1471-2091-3-17.txt
     19      708     5587    41266 technical/biomed/1471-2091-3-18.txt
     20      755     5001    41134 technical/biomed/1471-2091-3-22.txt
     21      605     4616    34420 technical/biomed/1471-2091-3-23.txt
     22      699     4531    34867 technical/biomed/1471-2091-3-30.txt
     23     1063     7146    57063 technical/biomed/1471-2091-3-31.txt
     24     1013     7118    53710 technical/biomed/1471-2091-3-4.txt
     25      430     3136    23921 technical/biomed/1471-2091-3-8.txt
     26      545     3908    30824 technical/biomed/1471-2091-4-1.txt
     27      521     3765    29240 technical/biomed/1471-2091-4-5.txt
     28      784     4587    37372 technical/biomed/1471-2105-1-1.txt
     29      611     4414    34872 technical/biomed/1471-2105-2-1.txt
     30     1495     8652    69647 technical/biomed/1471-2105-2-8.txt
     31      455     3425    26087 technical/biomed/1471-2105-2-9.txt
     32      393     2665    21467 technical/biomed/1471-2105-3-12.txt
     33     1173     6982    55614 technical/biomed/1471-2105-3-14.txt
     34      776     4989    38222 technical/biomed/1471-2105-3-16.txt
     35      920     5988    48159 technical/biomed/1471-2105-3-17.txt
     36     2236     9393    80798 technical/biomed/1471-2105-3-18.txt``` <br>
Explanation: It output a column of line numbers on the left hand side. I expect this to be helpful if the file was sorted in some meaningful order. <br>

### Example 2: <br>

The directory: ``~/Downloads/docsearch/technical/biomed`` <br>
The command: ``less -N gb-2003-4-9-r60.txt`` <br>
Output: <br> ![Image](https://i.imgur.com/LbPwIM2.png) <br>
Explanation: It output a column of line numbers on the left hand side. I expect this to be helpful if the file was sorted in some meaningful order. <br>

### The argument: ``-w``
### Example 1: <br>
The directory: ``~/Downloads/docsearch/technical/government/media`` <br>
The command: ``less -w Law_Schools.txt`` <br>
Output: <br>![Image](https://i.imgur.com/qngks2M.png) <br>
Explanation: It highlights the line previously at the bottom when scrolling. It seems to mostly be an accessibility thing, and I quite like it. <br>

### Example 2: <br>

The directory: ``~/Downloads/docsearch/technical/biomed`` <br>
The command: ``less -w gb-2003-4-9-r60.txt`` <br>
Output:<br> ![Image](https://i.imgur.com/lOfmaDo.png) <br>
Explanation: It highlights the line previously at the bottom when scrolling. It seems to mostly be an accessibility thing, and I quite like it. <br>

### The argument: ``--window=n``
### Example 1: <br>
The directory: ``~/Downloads/docsearch/technical/government/media`` <br>
The command: ``less --window=1 -w Law_Schools.txt`` <br>
Output:<br> ![Image](https://i.imgur.com/zJx5xa9.png) <br>
![Image](https://i.imgur.com/pEIL6vy.png) <br>
Explanation: It changes the default scroll setting to be in n lines, in this case I wanted it to scroll only 1 line when I clicked space. It is useful if your reading style varies from the default setting. <br>

### Example 2: <br>

The directory: ``~/Downloads/docsearch/technical/plos`` <br>
The command: ``less --window=3 -w pmed.0020201.txt`` <br>
Output: ![Image](https://i.imgur.com/ldgx1dD.png)
![Image](https://i.imgur.com/kLvb2ZT.png)<br>
Explanation: It changes the default scroll setting to be in n lines, in this case I wanted it to scroll only 1 line when I clicked space. It is useful if your reading style varies from the default setting.

### The argument: ``-f`` <br>
### Example 1: <br>
The directory: ``~/Downloads/docsearch`` <br>
The command: ``less -f lib`` <br>
Output:<br> ![Image](https://i.imgur.com/8xhc6H5.png) <br>
Explanation: It forces a file to be opened by the less command, whether or not it is allowed by default. In this case, using it on a directory output nothing, which makes sense to me. <br>
### Example 2: <br>
The directory: ``~/Downloads/docsearch/technical/government/About_LSC`` <br>
The command: ``less -f conference_highlights.txt`` <br>
Output:<br> ![Image](https://i.imgur.com/ssaFYIy.png) <br>
Explanation: -f forces a file to be opened regardless if it can or not, but if used on a normal .txt file then it appears to just open it normally.


Cited source: https://linux.die.net/man/1/less

