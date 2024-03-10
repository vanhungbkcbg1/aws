## Note
1. **Task role**: Your Amazon ECS tasks can have an IAM role associated with them. The permissions granted in the IAM role are assumed by the containers running in the task
2. **Task execution role**: The task execution role grants the Amazon ECS container and Fargate agents permission to make AWS API calls on your behalf: permission for pull image, send log to cloud watch, reference sensitive information from Secret manager ....

### CI, CD ecs
#### when integrate between ecs and codepipeline only we need to change imageuri for image in container
1. you need a cluster on ecs
2. you need definition for a service on ecs
3. you need create a service on ecs

### Config code pipeline
1. please note that the field image definition is important, it must be the name of the file that is outputted from code build process
![image](./images/code_pipeline.png)  

2. output from code build  
![image](./images/codebuild.png)

## ImageDefinition file
[Image Definition.json](https://docs.aws.amazon.com/codepipeline/latest/userguide/file-reference.html)

## in case there is permission error with ECR please add this policy to the role which is being used to build image
**EC2InstanceProfileForImageBuilderECRContainerBuilds**
