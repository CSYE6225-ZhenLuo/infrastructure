# infrastructure
## AWS profile

aws config --profile=dev

aws config --profile=demo

## AWS cloudformation
### Create on default setting(using region "us-east-1")
aws --profile=dev cloudformation create-stack --stack-name STACK --template-body file://csye6225-infra.yml

aws --profile=dev cloudformation delete-stack --stack-name STACK
### Change region to others
aws --profile=dev cloudformation create-stack --stack-name STACK --template-body file://csye6225-infra.yml --parameters ParameterKey=Region,ParameterValue="us-east-2"