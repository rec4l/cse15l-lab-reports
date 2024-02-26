# Week 7 Lab Report
By: Jonathan Nguyen
PID: A17418793 <br>

# Step 4 (log into ieng6)
screenshot:
https://i.ibb.co/NxGP0Cm/ss1.png

commands used:
``ssh jmn003@ieng6-201.ucsd.edu``
``yes``
``[password]``

explanation:
I just signed onto my ieng6 account.

# Step 5 (clone repository)
screenshot:
https://i.ibb.co/2cSCMqk/ss2.png

commands used:
git clone git@github.com:rec4l/lab7.git

explanation:
I used git clone with the ssh url on my forked repository.

# Step 6 (show that tests initially failed)
screenshot:
https://i.ibb.co/4VMY0B6/ss3.png

keys pressed:
<up><up><up><up><up><up><up><up><enter>
<up><up><up><up><up><up><up><up><up><up><up><up><enter>

explanation:
My commands for `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` and `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests` were 8 and 12 commands up respectively, so I used up arrow to traverse my command history.

# Step 7 (edit file)
screenshot:
https://i.ibb.co/58YKzpF/ss4.png

commands used:
`vim ListExamples.java`
`r2:wq!`

explanation:
I first used the command `vim ListExamples.java` to open `ListExamples.java` in vim, then all I had to do was type `r2` to replace the character at my cursor position with 2, since my cursor was already there (likely from previously attempting this in a past repository)
I then used `:wq!` to save and exit my changes.

# Step 8 (re-run tests)
screenshot:
https://i.ibb.co/LRR3ZR4/ss5.png

keys pressed:
<up><up><up><up><enter>
<up><up><up><up><up><enter>

explanation:
My commands for `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` and `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests` were 4 and 5 commands up respectively, so I used up arrow to traverse my command history.

# Step 9 (git commit and push)
screenshot:
https://i.ibb.co/2vYQK0B/Capture.png

keys pressed:
`git commit -a`
<down><down><down><down><down><down><down><down><down><down><down>r2:wq!
`git push`

explanation:
I first used the command `git commit -a` to start the commit, and I went down to the 12th line, added a character "2" into the commit message, then saved. After that, I just needed to push my changes to my repository.
