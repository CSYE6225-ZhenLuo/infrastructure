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
ami-0a031ca3fa0442004
## Delete bucket object

aws --profile=dev s3 rm s3://bucket-name --recursive
*-dev.zhenluo.me