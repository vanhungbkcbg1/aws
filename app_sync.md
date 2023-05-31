## Datasource
are resources of your aws account that grapql apisde can interact with
## Resolved
## Function
function se duoc chay lan luot, function nay qua funtion khac, function se tuong tac voi data source

### trigger event for appsync subscriber
only we need to make request ro grapql url
````
req.method = 'POST';
    req.path = '/graphql';
    req.headers.host = endpoint;
    req.headers['Content-Type'] = 'application/json';
    req.body = JSON.stringify({
      query: graphqlQuery,
      operationName: 'notificationMutation',
      variables: notificationObj
    });
    
    
// action.js
module.exports = {
  mutation: `mutation notificationMutation(
  $id: ID
  $clientID: ID
  $personID: ID
  $types: NotificationTypes
  $displayFormat: DisplayFormat
  $displayText: String
  $workflow: String
  $createdAt: AWSDateTime
) {
  notificationMutation(
    id: $id
    clientID: $clientID
    personID: $personID
    types: $types
    displayFormat: $displayFormat
    displayText: $displayText
    workflow: $workflow
    createdAt: $createdAt
  ) {
    id
    clientID
    personID
    types
    displayFormat
    displayText
    workflow
    createdAt
  }
}`,
};


//notificationJS
let notificationObj = {
      id: Date.now() + '-' + event.clientID,
      clientID: event.clientID,
      personID: event.personID,
      types: event.types,
      displayFormat: event.displayFormat,
      displayText: event.displayText,
      workflow: event.workflow,
      createdAt: new Date().toISOString()
    };

````


### subscription with parameter
1. create subscription in backend grapql
````
type Subscription {
    onCreateSpecialTodo(name: String!): Todo
        @aws_subscribe(mutations: ["createTodo"])
}
````
2. defined query
````
export const onCreateSpecialTodo = /* GraphQL */ `
  subscription OnCreateTodo($name: String!) {
    onCreateSpecialTodo(name: $name) {
        createdAt
        description
        id
        name
        priority
        updatedAt
  }
  }
`;
````
3. use above query to subscribe 
````
const sub = API.graphql(graphqlOperation(onCreateSpecialTodo, { name: 'hung'})).subscribe({next(value) {
              setLoading(false);
              console.log('data', value);
              console.log('done');
          }})
````

4. above callback only be called when create todo using mutation that have name = hung

