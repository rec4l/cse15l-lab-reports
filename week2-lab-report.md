# Week 1 Lab Report
By: Jonathan Nguyen
PID: A17418793

Code for ChatServer.java: <br>

![Image](https://i.imgur.com/Vdy3UGF.png)

Screenshot 1: <br>
![Image](https://i.imgur.com/g6tlez0.png)

What methods are called? handleRequest is called. <br>
What are the relevant arguments to those methods? The only argument to handleRequest is url of type URI. <br>
What are the values of the relevant fields of those classes? <br>
chatLog contains the previous messages of the conversastion. <br>
Given the input url, `http://localhost:4000/add-message?s=Hello&user=jpolitz3`: <br>
String[] parameters initializes as `{add-message?s=Hello, user=jpolitz3}` <br>
message initializes as `Hello` <br>
user initializes as `jpolitz3` <br>
Then, the correct formatting of the chat message is added to chatLog, and displayed. <br>

How do the values change/not change from the specific request? <br>
parameters, message, user, is dependent on the request given by the url. <br>
chatLog is appended to, based on the contents of the request and displayed to the user. <br>

Screenshot 2: <br>
![Image](https://i.imgur.com/hjcxRWm.png)

What methods are called? handleRequest is called. <br>
What are the relevant arguments to those methods? The only argument to handleRequest is url of type URI. <br>
What are the values of the relevant fields of those classes? <br>
chatLog contains the previous messages of the conversastion. <br>
Given the input url, `http://localhost:4000/add-message?s=Hel33333lo&user=jpolitz3`: <br>
String[] parameters initializes as `{add-message?s=Hel33333lo, user=jpolitz3}` <br>
message initializes as `Hel33333lo` <br>
user initializes as `jpolitz3` <br>
Then, the correct formatting of the chat message is added to chatLog, and displayed. <br>

How do the values change/not change from the specific request? <br>
parameters, message, user, is dependent on the request given by the url. <br>
chatLog is appended to, based on the contents of the request and displayed to the user. <br>
