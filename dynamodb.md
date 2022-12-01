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
