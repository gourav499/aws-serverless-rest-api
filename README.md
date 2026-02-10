<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# APIs with Lambda + API Gateway

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-compute-api)

**Author:** Gourav Tiwari  
**Email:** gouravtiwari499@gmail.com

---

![Image](http://learn.nextwork.org/calm_pink_agile_bee/uploads/aws-compute-api_c9d0e1f2)

---

## Introducing Today's Project!

In this project, I will demonstrate building a serverless API using AWS Lambda and Amazon API Gateway. This includes creating backend logic, connecting Lambda to API Gateway, and documenting the API using JSON. My goal is to learn how serverless architecture works, how APIs are built without server management, and how the logic tier functions within a three-tier architecture.

### Tools and concepts

Services I used were AWS Lambda, API Gateway, and (later) DynamoDB to build a serverless API. Key concepts I learnt include how Lambda functions handle backend logic, how API Gateway manages and secures requests, how to structure APIs with resources and methods, and the importance of documenting and deploying APIs for real-world use.

### Project reflection

This project took me approximately 60 minutes to complete. The most challenging part was setting up the API methods and connecting them correctly to the Lambda function. It was most rewarding to see a fully working serverless API that I could access through a public URL and document for others to use.

I chose to do this project today because I wanted to learn how to build a serverless API using AWS Lambda and API Gateway, and understand how backend logic connects with user requests. Something that would make learning with NextWork even better is including more real-world examples and small practice exercises alongside each step to reinforce concepts as we go.

---

## Lambda functions

AWS Lambda is a serverless compute service that allows you to run backend code in response to events without managing or provisioning servers. I’m using Lambda in this project to handle application logic, process user requests, and return data efficiently as part of a scalable serverless API.

The code I added to my function will fetch user data from the UserData DynamoDB table using a userId from the request, return it if found, handle cases when no data exists, and manage any errors that occur during retrieval. Make sure to update the placeholder region YOUR_REGION to your own region code so that the Lambda function can connect to your specific DynamoDB instance. 

![Image](http://learn.nextwork.org/calm_pink_agile_bee/uploads/aws-compute-api_a1b2c3d5)

---

## API Gateway

APIs are interfaces that allow different software systems to communicate and exchange data. There are different types of APIs, like REST, HTTP, and WebSocket, each suited for specific use cases such as standard web requests, real-time communication, or flexible routing. My API is a REST API, which uses HTTP methods to connect users with my Lambda function in a simple and widely supported way.

Amazon API Gateway is a fully managed AWS service that lets you create, secure, and manage APIs, handling incoming requests and routing them to the appropriate backend services. I’m using API Gateway in this project to provide a secure and organized way for users to access my Lambda function, manage requests, and ensure responses are correctly sent back to the client.

When a user makes a request, API Gateway receives it and acts as the front door, forwarding the request to the appropriate Lambda function. The Lambda function processes the request, performs the necessary backend operations (like fetching data), and then sends the response back through API Gateway, which delivers it to the user’s browser or client.

![Image](http://learn.nextwork.org/calm_pink_agile_bee/uploads/aws-compute-api_m3n4o5p6)

---

## API Resources and Methods

An API is made up of resources, which are individual endpoints or sections that organize how the API handles different types of requests, making it easier to manage and route calls to the correct backend functions.

Each resource consists of methods, which are actions that can be performed on that resource, such as GET to retrieve data, POST to create data, PUT to update data, or DELETE to remove data.

I created a GET method for the /users resource that is integrated with my Lambda function to retrieve user data from the DynamoDB table whenever the API endpoint is called.

![Image](http://learn.nextwork.org/calm_pink_agile_bee/uploads/aws-compute-api_c9d0e1f2)

---

## API Deployment

When you deploy an API, you deploy it to a specific stage. A stage is a named environment that represents a version of your API, like development, testing, or production. I deployed to a new stage to make my API live and accessible for users to send requests.

To visit my API, I copied the prod stage’s Invoke URL and opened it in a new browser tab. The API displayed an error because the DynamoDB table isn’t set up yet, so the backend Lambda function couldn’t retrieve any data.

![Image](http://learn.nextwork.org/calm_pink_agile_bee/uploads/aws-compute-api_3ethryj2)

---

## API Documentation

For my project's extension, I am writing API documentation to clearly explain my API's endpoints, methods, parameters, and responses, which will help developers understand and use it correctly. This can be done in API Gateway by creating and publishing the documentation in JSON format.

Once I prepared my documentation, I can publish it to the prod stage in API Gateway. You have to publish your API to a specific stage because this ensures the documentation matches the deployed version of the API, keeping it consistent with the environment users will interact with.

My published and downloaded documentation showed me a detailed overview of my API, including its description, endpoints, supported methods, and parameters. It also confirmed that the documentation was linked to the correct stage, making it clear how other developers can use and interact with my API.

![Image](http://learn.nextwork.org/calm_pink_agile_bee/uploads/aws-compute-api_z9a0b1c2)

---

---
