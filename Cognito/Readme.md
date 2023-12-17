## To Use cognito dentity pool for role base access selection
1. in api gateway we need to use IAM authorizer
2. in amplify js library don't set Authorization header value in order to amplify will automatic sign request for us
3. to test, we just need to change policy in auth role to test

## Config authenticated role base on custom attribute
- Identity Provider
  ![image](./images/identity.png)
- change rule to choose role for authenticated user base on custom attribute
  
