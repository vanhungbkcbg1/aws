## aws sso or aws identity center will intergrate with aws orgernization
## to use aws sso we need 
- create an account and assign this account to an Organizaiton Unit in aws Organization
- in aws idendentity center, create some users or group and assign them to specific account on aws organization
- create permission sets( policies) and assign this permission set to account that is being used
- provider login portal url for all user that you created previous step
- user login success and their will have permission that already restricted by permission sets
