#### VPC End Interface Endpoint
allow access to other aws service from inside private instance
#### VPC Private Link
allow other vpc can access to your service that you has been deployed in your VPC
1. it don't  require VPC peering, internet gateway, Nat or change router table
2. Requires a network load balancer and ENI(Customer VPC)
##### to create 
1. in your vpc create vpc endpoint service, this service will link to the private load balancer in your private vpc
2. in customer vpc, create vpc end point to link to your vpc endpoint service that you have just created in step 1( with *service Category* = Find by service)
