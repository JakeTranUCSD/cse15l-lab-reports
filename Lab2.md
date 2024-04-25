# Lab Report 2

## Part 1


**ChatServer.java code:**


<img width="952" alt="Screen Shot 2024-04-22 at 8 03 37 PM" src="https://github.com/JakeTranUCSD/cse15l-lab-reports/assets/147591070/5b582f36-f32d-46bc-a67c-f7a7a97676fa">


**Example 1:**


<img width="605" alt="Screen Shot 2024-04-24 at 9 49 55 PM" src="https://github.com/JakeTranUCSD/cse15l-lab-reports/assets/147591070/5c666133-9d74-4233-87d9-77a0aca9961e">


The two methods in my program is called handleRequest and getAllMessages. Using the path `/add-message?s=Hello%20World!&user=Jake` adds the new message to the server. In this path, the s parameter (message) is "Hello World!" and the user parameter is "Jake". The method being called is handleRequest. The relevant argument is the URL (which changes depending on the message being added), which in this case is: `http://localhost:4000/add-message?s=Hello%20World!&user=Jake` 


**Example 2:**


<img width="745" alt="Screen Shot 2024-04-24 at 9 50 24 PM" src="https://github.com/JakeTranUCSD/cse15l-lab-reports/assets/147591070/5b1975a5-ec79-4b1e-92e9-e40de2ea773a">


Using the path `/add-message?s=My%20name%20isn%27t%20world!&user=notWorld` adds the new message to the server. In this path, the s parameter (message) is "My name isn't world!" and the user parameter is "notWorld". The method being called is handleRequest. The relevant argument is the URL (which changes depending on the message being added), which in this case is: `http://localhost:4000/add-message?s=My%20name%20isn%27t%20world!&user=notWorld`


## 



**Thanks for reading, have a great day!**
