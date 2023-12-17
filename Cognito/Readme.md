## To Use cognito dentity pool for role base access selection
1. in api gateway we need to use IAM authorizer
2. in amplify js library don't set Authorization header value in order to amplify will automatic sign request for us
3. to test, we just need to change policy in auth role to test

## Config authenticated role base on custom attribute
- Identity Provider
  ![image](./images/identity.png)
- change rule to choose role for authenticated user base on custom attribute
  ![image](./images/assignment_rule.png)
  in this image, we configured when  
                                    - custom.role = admin, the role adminRole will be assigned to the user  
                                    - custom.role = normal, the role normalRole will be assigned to the user
  sample policy for adminRole and normalRole
  ````
  // Admin Role -> allow call api using amplify
  {
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "Statement1",
            "Effect": "Allow",
            "Action": [
                "execute-api:Invoke"
            ],
            "Resource": [
                "arn:aws:execute-api:ap-northeast-1:154713672373:2cnlk0u6h6/*/GET/test"
            ]
        }
    ]
}

  // normal Rolr -> block call api from amplify

  {
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "Statement1",
            "Effect": "Allow",
            "Action": [
                "execute-api:Invoke"
            ],
            "Resource": [
                "arn:aws:execute-api:ap-northeast-1:154713672373:2cnlk0u6h6/*/GET/test"
            ]
        }
    ]
}
  ````
  
