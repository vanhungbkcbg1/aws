Endpoint allow you to connect to aws services using a private network instead of the public network
they remove the need of Iternet gateway, nat gateway to access other aws services
## Gateway Endpoint
use to connect to S3 and Dynamodb
### Setup VPC gateway endpoint to allow connect from ec2 private instance to s3
  - you need to have 1 public instance(bastion host) and 1 private instance
  - attacch to instance role  that has permission to access to s3
  - in vpc menu, choose **End point** and choose information as below
   [image](./images/)
## interface Endpoint
use to connect to other services
