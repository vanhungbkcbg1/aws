## Rotation
Rotation is the process of periodically updating a secret. 
When you rotate a secret, you update the credentials in both the secret and the database or service. 
In Secrets Manager, you can set up automatic rotation for your secrets.
### How rotation works
- Secrets Manager rotation uses an AWS Lambda function to update the secret and the database.  
- Create a new version of the secret (createSecret)  
  The first step of rotation is to create a new version of the secret. The new version can contain a new password, 
  a new username and password, or more secret information. Secrets Manager labels the new version with the staging label AWSPENDING
- Change the credentials in the database or service (setSecret)  
  Next, rotation changes the credentials in the database or service to match the new credentials in the AWSPENDING version of the secret. 
  Depending on your rotation strategy, this step can create a new user with the same permissions as the existing user
- Test the new secret version (testSecret)  
  Next, rotation tests the AWSPENDING version of the secret by using it to access the database or service. 
  Rotation functions based on Rotation function templates test the new secret by using read access. 
  Depending on the type of access your applications need, you can update the function to include other access such as write access
- Finish the rotation (finishSecret)  
  Finally, rotation moves the label AWSCURRENT from the previous secret version to this version. 
  Secrets Manager adds the AWSPREVIOUS staging label to the previous version, so that you retain the last known good version of the secret
