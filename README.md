# Getting Started

## Serverless 

![IMG](https://github.com/Bernado6/React-Serverless-App-Udacity/blob/main/images/advantage.jpg?raw=true)

Serverless, which is the built-in architecture of the cloud, enables you to give AWS additional operational responsibilities while increasing your agility and innovation. Without thinking about servers, you can develop and run apps and services using serverless technology. It eliminates infrastructure management tasks including server or cluster provisioning, operating system maintenance, capacity provisioning, and patching. With them, virtually any backend service or application may be created, and all the necessary tasks for running and scaling your application with high availability are handled for you.

## AWS Lambda

![sample-blank](https://github.com/Bernado6/React-Serverless-App-Udacity/blob/main/images/lamda.jpg?raw=true)

With AWS Lambda, you can run code without setting up or managing servers. You only pay for the compute time you utilize; there is no charge when your code is not running.

Without the need for management, Lambda allows you to run code for practically any form of backend service or application. Lambda will take care of all the essential procedures to run and expand your code with high availability after you simply upload it.


## Amazon API Gateway

![api-gateway](https://github.com/Bernado6/React-Serverless-App-Udacity/blob/main/images/APIGAtewa.jpg?raw=true)


Developers can utilize the fully managed service called Amazon API Gateway to build, publish, maintain, monitor, and defend APIs of any size. It offers a full management framework for APIs. You can make hundreds of thousands of API calls simultaneously because API Gateway manages traffic, permission and access control, monitoring, and API version management.

## Amazon DynamoDB

<img width="1861" alt="db" src="https://github.com/Bernado6/React-Serverless-App-Udacity/blob/main/images/Auth0.png?raw=true">

All applications demand a consistent, single-digit millisecond latency at any scale, and Amazon DynamoDB offers a rapid and flexible NoSQL database solution that can fulfill this need.

It is a fully managed, multiregion, multimaster, persistent database with built-in backup and restore, security, and in-memory caching for internet-scale applications.

## Amazon S3

![AWS-S3](https://github.com/Bernado6/React-Serverless-App-Udacity/blob/main/images/AWS_S3.jpg?raw=true)

A cloud-based object storage service called Amazon Simple Storage Service boasts top-tier scalability, data accessibility, security, and performance. You may store and retrieve any quantity of data from anywhere on the internet with Amazon S3, a straightforward web service interface.

For a range of use cases, including websites, mobile apps, backup and restore, archiving, business applications, IoT devices, and big data analytics, users of all sizes and sectors can use it to store and preserve any quantity of data.

# Demo
<img width="1245" alt="Screenshot 2022-06-17 at 15 09 12" src="https://github.com/Bernado6/React-Serverless-App-Udacity/blob/main/images/Demo1.png?raw=true">  

<img width="1245" alt="Screenshot 2022-06-17 at 15 09 12" src="https://github.com/Bernado6/React-Serverless-App-Udacity/blob/main/images/Demo2.png?raw=true"> 

<img width="1245" alt="Screenshot 2022-06-17 at 15 09 12" src="https://github.com/Bernado6/React-Serverless-App-Udacity/blob/main/images/Demo3.png?raw=true"> 
 

# Serverless TODO

In this project, I use the Serverless framework and AWS Lambda to create and deploy a basic "TODO" application. Users will be able to add, remove, update, and obtain TODO items using this application. The following fields are present in each TODO item: 
   - todoId (string) - a unique id for an item
   - createdAt (string) - date and time when an item was created
   -  name (string) - name of a TODO item (e.g. "Change a light bulb")
   - dueDate (string) - date and time by which an item should be completed
   - done (boolean) - true if an item was completed, false otherwise
   - attachmentUrl (string) (optional) - a URL pointing to an image attached to a TODO item

# Functions implemented

To implement this project you need to implement the following functions and configure them in the `serverless.yml` file:

* `Auth` - this function should implement a custom authorizer for API Gateway that should be added to all other functions.
* `GetTodos` - should return all TODOs for a current user. 
* `CreateTodo` - should create a new TODO for a current user. A shape of data send by a client application to this function can be found in the `CreateTodoRequest.ts` file
* `UpdateTodo` - should update a TODO item created by a current user. A shape of data send by a client application to this function can be found in the `UpdateTodoRequest.ts` file
* `DeleteTodo` - should delete a TODO item created by a current user. Expects an id of a TODO item to remove.
* `GenerateUploadUrl` - returns a presigned url that can be used to upload an attachment file for a TODO item. 

All functions are already connected to appriate events from API gateway

An id of a user can be extracted from a JWT token passed by a client

You also need to add any necessary resources to the `resources` section of the `serverless.yml` file such as DynamoDB table and and S3 bucket.


## Deploy Backend

                  cd backend

                  npm install
  
                  serverless

                  npm install --save-dev serverless-iam-roles-per-function@next 

                  serverless deploy --verbose


# Endpoints
   
  - GET - https://58ip60spj9.execute-api.us-east-1.amazonaws.com/devmt/todos
  - POST - https://58ip60spj9.execute-api.us-east-1.amazonaws.com/devmt/todos
  - PATCH -  https://58ip60spj9.execute-api.us-east-1.amazonaws.com/devmt/todos/{todoId}
  - DELETE - https://58ip60spj9.execute-api.us-east-1.amazonaws.com/devmt/todos/{todoId}
  - POST -  https://58ip60spj9.execute-api.us-east-1.amazonaws.com/devmt/todos/{todoId}/attachment

functions:
  
# Lambda Functions

  - Auth: serverless-prod-Auth
  - GetTodos: serverless-prod-GetTodos
  - CreateTodo: serverless-prod-CreateTodo
  - UpdateTodo: serverless-prod-UpdateTodo
  - DeleteTodo: serverless-prod-DeleteTodo
  -  GenerateUploadUrl: serverless-prod-GenerateUploadUrl 
  
# Serverless 
  <img width="1438" alt="Screenshot 2022-06-17 at 14 52 03" src="Screenshot 2022-06-17 at 14 50 52" src="https://github.com/Bernado6/React-Serverless-App-Udacity/blob/main/images/Serverless1.png?raw=true">
  <img width="1440" alt="Screenshot 2022-06-17 at 14 50 52" src="https://github.com/Bernado6/React-Serverless-App-Udacity/blob/main/images/Serverless2.png?raw=true">
  <img width="1440" alt="Screenshot 2022-06-17 at 14 50 52" src="https://github.com/Bernado6/React-Serverless-App-Udacity/blob/main/images/Serverless3.png?raw=true">
  <img width="1440" alt="Screenshot 2022-06-17 at 14 50 52" src="https://github.com/Bernado6/React-Serverless-App-Udacity/blob/main/images/Serverless4.png?raw=true">

  
# Auth0
  
 <img width="1440" alt="Screenshot 2022-06-17 at 14 53 08" src="https://github.com/Bernado6/React-Serverless-App-Udacity/blob/main/images/Auth0.png?raw=true">

  
# AWS Cloud Formation 

  <img width="1440" alt="Screenshot 2022-06-17 at 14 55 40" src="https://github.com/Bernado6/React-Serverless-App-Udacity/blob/main/images/CloudFormation.png?raw=true">

   


# Frontend

The `client` folder contains a web application that can use the API that should be developed in the project.

To use it please edit the `config.ts` file in the `client` folder:

```ts
const apiId = '...' API Gateway id
export const apiEndpoint = `https://${apiId}.execute-api.us-east-1.amazonaws.com/dev`

export const authConfig = {
  domain: '...',    // Domain from Auth0
  clientId: '...',  // Client id from an Auth0 application
  callbackUrl: 'http://localhost:3000/callback'
}
```


# Suggestions

To store TODO items you might want to use a DynamoDB table with local secondary index(es). A create a local secondary index you need to a create a DynamoDB resource like this:

```yml

TodosTable:
  Type: AWS::DynamoDB::Table
  Properties:
    AttributeDefinitions:
      - AttributeName: partitionKey
        AttributeType: S
      - AttributeName: sortKey
        AttributeType: S
      - AttributeName: indexKey
        AttributeType: S
    KeySchema:
      - AttributeName: partitionKey
        KeyType: HASH
      - AttributeName: sortKey
        KeyType: RANGE
    BillingMode: PAY_PER_REQUEST
    TableName: ${self:provider.environment.TODOS_TABLE}
    LocalSecondaryIndexes:
      - IndexName: ${self:provider.environment.INDEX_NAME}
        KeySchema:
          - AttributeName: partitionKey
            KeyType: HASH
          - AttributeName: indexKey
            KeyType: RANGE
        Projection:
          ProjectionType: ALL # What attributes will be copied to an index

```

To query an index you need to use the `query()` method like:

```ts
await this.dynamoDBClient
  .query({
    TableName: 'table-name',
    IndexName: 'index-name',
    KeyConditionExpression: 'paritionKey = :paritionKey',
    ExpressionAttributeValues: {
      ':paritionKey': partitionKeyValue
    }
  })
  .promise()
```


## Deploy Frontend

To run a client application first edit the `client/src/config.ts` file to set correct parameters. And then run the following commands

```
cd client
npm install
npm run start
```

### Working Todo

  <img width="1260" alt="good-todo" src="https://github.com/Bernado6/React-Serverless-App-Udacity/blob/main/images/WorkingTODO.png?raw=true">


### Blank Todo 
  <img width="1304" alt="blank-todo" src="https://github.com/Bernado6/React-Serverless-App-Udacity/blob/main/images/blanktodo.png?raw=true">



This should start a development server with the React application that will interact with the serverless TODO application.

