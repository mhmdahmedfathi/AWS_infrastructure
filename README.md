# AWS_infrastructure

## this is to deploy infrastructure that is build using lucidchart

## infrastructure i drow  

<img align="center" src="https://github.com/mhmdahmedfathi/AWS_infrastructure/blob/main/infrastructure.png" width=400/>

### to start making this infrastructure you have to run network.yml first so it set up the vpc and public/private subnets that is needed to deploy (you have to make sure you logged in to aws in console using aws configure)

aws cloudformation create-stack --stack-name network --template-body file://network.yml  --parameters file://network.json --capabilities "CAPABILITY_IAM" "CAPABILITY_NAMED_IAM" --region=us-east-1

## then you have to wait until the stack is completed successfull 

### when it is completed you have to deploy the rest of the infrastructure 

aws cloudformation create-stack --stack-name infrastructure --template-body file://awsInfrastructure.yml  --parameters file://awsInfrastructure.json --capabilities "CAPABILITY_IAM" "CAPABILITY_NAMED_IAM" --region=us-east-1
