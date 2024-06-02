## aws sso or aws identity center will intergrate with aws orgernization
## to use aws sso we need 
- create an account and assign this account to an Organizaiton Unit in aws Organization
- in aws idendentity center, create some users or group and assign them to specific account on aws organization
- create permission sets( policies) and assign this permission set to account that is being used
- provider login portal url for all user that you created previous step
- user login success and their will have permission that already restricted by permission sets
## Example
- we had account vanhungbkcbg1@+account@gmail.com is new account in organizationn
- we have created dev user acccount and assign them to that account
- we have setup permission sets for all user in account in side Iam Idenntity center to readonly
- we have loged in dev user, and this user only have view permission: ex S3
