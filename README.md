# infrastructure
## AWS profile

aws config --profile=dev

aws config --profile=demo

## AWS cloudformation
### Create on default setting(using region "us-east-1")
aws --profile=dev cloudformation create-stack --stack-name STACK --template-body file://csye6225-infra.yml

aws --profile=dev cloudformation delete-stack --stack-name STACK
### Use parameters
aws --profile=dev cloudformation create-stack --stack-name STACK --template-body file://csye6225-infra.yml --parameters ParameterKey=KeyName,ParameterValue="AmazonEC2-ED" ParameterKey=ImageID,ParameterValue= --capabilities CAPABILITY_IAM


aws --profile=demo cloudformation create-stack --stack-name DeployPolicy --template-body file://CICD.yml --capabilities CAPABILITY_IAM

aws --profile=demo cloudformation create-stack --stack-name STACK --template-body file://csye6225-infra.yml --parameters ParameterKey=KeyName,ParameterValue="MacBook" ParameterKey=ImageID,ParameterValue=ami-04ebb8cf6eef0349d ParameterKey=DomainName,ParameterValue=demo.zhenluo.me --capabilities CAPABILITY_IAM
ami-0a031ca3fa0442004

ami-03c46808e6fe8d75c
## Delete bucket object

aws --profile=dev s3 rm s3://bucket-name --recursive
*-dev.zhenluo.me

## import ssl to ACM
aws --profile=demo acm import-certificate --certificate fileb://demo_zhenluo_me.crt --private-key fileb://demossl.key --certificate-chain fileb://demo_zhenluo_me.ca-bundle