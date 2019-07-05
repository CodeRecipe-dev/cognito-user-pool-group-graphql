# Authorize groups of users to GraphQL using Cognito User Pool Groups

![nodejs](https://img.shields.io/badge/-nodejs-555555.svg) ![serverless](http://public.serverless.com/badges/v3.svg)

This recipe uses Cognito User Pool Groups to grant permissions to groups of users for GraphQL operations.

More info: https://coderecipe.ai/architectures/65992102

### Download the code    


```
git clone https://github.com/CodeRecipe-dev/cognito-user-pool-group-graphql.git
```
 
### Deploy to the cloud  


```
cd cognito-user-pool-group-graphql

serverless deploy --stage beta

```      

### Usage

To test access to unauthenticated endpoint, run the following curl command with the deployed api key and appsync endpoint:

```
curl -XPOST -H "Content-Type:application/graphql" -H "x-api-key:<appsync-api-key>" -d '{ "query": "query { getMessage(id:1) { id,content,author } }" }'  <appsync-graphql-endpoint>
```

Then use the AppSync GUI to login as a user and test. Make sure to add users to different groups to test the group based authorization:

![Appsync Cogntio](https://coderecipe-crlite-architectures-beta.s3.amazonaws.com/coderecipedevs/Secure+AWS+AppSync+with+AWS+Cognito+User+Pool/appsync-cognito.gif)


### Removal

To remove the stack, run the following command:


```
serverless remove --stage beta
```   