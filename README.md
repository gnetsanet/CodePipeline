# CodePipeline

## Steps

1. Cloud Formations creates an instance

2. Put version 1 of your application in an S3 bucket.

## Considerations

- CloudFormation sources templates from S3

```
aws iam get-user
```


To see how you setup AWS CLI
```
aws configure list 

  Name                    Value             Type    Location
      ----                    -----             ----    --------
   profile                  default           manual    --profile
access_key     ****************NGFI shared-credentials-file
secret_key     ****************HcdM shared-credentials-file
    region                us-east-1              env    AWS_DEFAULT_REGION
```


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
