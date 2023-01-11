## Cognito authorizer
### Sử dụng được authenticated role trong identity pool
- để sử dụng được role này thì trong lambda function chúng ta sẽ cần phải manual call tới STS service để lấy được các thông tin như Access Token. 
  Secret token ... , sau đó chúng ta sẽ dùng thông tin này để call tới service mong muốn như S3 hay DynamoDB
- sample code in lambda function for nodejs
  ````
  let credential = new AWS.CognitoIdentityCredentials({
        IdentityPoolId: identity_pool_id,
        Logins: { 
            [provider] : token
        }
    }, {
        "region": region
    });
    
    
    const dynamo = new AWS.DynamoDB({
        apiVersion: '2012-08-10',
        credentials: credential
    });
    
    const client = new AWS.DynamoDB.DocumentClient({
        service: dynamo
    })
    
    // call 
    
     let params = {
      TableName : 'products'
    };

    let results = client.scan(params).promise();
    return results;
  ````
