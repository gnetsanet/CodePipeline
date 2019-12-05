# CodePipeline

## Steps

1. Cloud Formations creates an instance

2. Put version 1 of your application in an S3 bucket.

```
aws cloudformation create-stack --stack-name CodeDeployDemoStack \
--template-url https://<MY_BUCKET_NAME>.s3-us-west-2.amazonaws.com/cloud_formation_template.json \
--parameters ParameterKey=InstanceCount,ParameterValue=1 \
ParameterKey=InstanceType,ParameterValue=t2.micro \
ParameterKey=KeyPairName,ParameterValue=codedeploy \
ParameterKey=OperatingSystem,ParameterValue=Linux \
ParameterKey=SSHLocation,ParameterValue=0.0.0.0/0 \
ParameterKey=TagKey,ParameterValue=Name \
ParameterKey=TagValue,ParameterValue=CodeDeployDemo \
--profile default --region us-west-2 --capabilities CAPABILITY_IAM —profile default
```
