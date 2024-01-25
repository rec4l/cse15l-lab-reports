# Week 1 Lab Report
By: Jonathan Nguyen
PID: A17418793

Code for ChatServer.java: <br>

![Image](https://i.imgur.com/Vdy3UGF.png)

Screenshot 1: <br>
![Image](https://i.imgur.com/g6tlez0.png)

What methods are called? handleRequest is called.
What are the relevant arguments to those methods? The only argument to handleRequest is url of type URI.
What are the values of the relevant fields of those classes?
chatLog contains the previous messages of the conversastion.
Given the input url, `http://localhost:4000/add-message?s=Hel33333lo&user=jpolitz3`:
String[] parameters initializes as `{add-message?s=Hel33333lo, user=jpolitz3}`
message initializes as `Hel33333lo`
user initializes as 'jpolitz3'
Then, the correct formatting of the chat message is added to chatLog, and displayed.

How do the values change/not change from the specific request? 
parameters, message, user, is dependent on the request given by the url.
chatLog is appended to, based on the contents of the request and displayed to the user.

Screenshot 2: <br>
![Image](https://i.imgur.com/hjcxRWm.png)

What methods are called? handleRequest is called.
What are the relevant arguments to those methods? The only argument to handleRequest is url of type URI.
What are the values of the relevant fields of those classes?
chatLog contains the previous messages of the conversastion.
Given the input url, `http://localhost:4000/add-message?s=Hel33333lo&user=jpolitz3`:
String[] parameters initializes as `{add-message?s=Hel33333lo, user=jpolitz3}`
message initializes as `Hel33333lo`
user initializes as 'jpolitz3'
Then, the correct formatting of the chat message is added to chatLog, and displayed.

How do the values change/not change from the specific request? 
parameters, message, user, is dependent on the request given by the url.
chatLog is appended to, based on the contents of the request and displayed to the user.
