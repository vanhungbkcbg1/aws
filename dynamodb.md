## to support query on attribute we have to create second index for that attribute 
example for query on email attribute of table users that have index on email column
````
var params = {
      TableName: 'users',
      IndexName: "email-index",
      KeyConditionExpression: 'email = :email',
      ExpressionAttributeValues: {
        ':email': email
      }
    };
    
    let result = await dynamo.query(params).promise();
````

## in a Dynamodb table each key value must be unique, however the key value in the global second index or local second index don't need to be unique

## When an application writes or deletes items in a table, any global secondary indexes on that table are updated asynchronously

## comparation between local index and global index
| Global second index| Local Second index|
|--------------------|-------------------|
| you can use any attribute for partition key and sorted key in index            | Partion key must be the same with partiion key in base table        |
| you can create index at the same time when you create a table or existing table| you only can create index at the same time when you create a table|
| asynchronous with base table| synchronized with base table|
