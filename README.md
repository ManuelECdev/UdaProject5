## Project summary

## How to deploy the infrastructure:

1. Execute the below command

aws cloudformation create-stack --stack-name primaryvpc --template-body file://vpc.yaml  --parameters file://vPC1Parameters.json  --capabilities "CAPABILITY_IAM" "CAPABILITY_NAMED_IAM" --region=us-west-2

2. Execute the below command

aws cloudformation create-stack --stack-name secondaryvpc --template-body file://vpc.yaml  --parameters file://vPC2Parameters.json  --capabilities "CAPABILITY_IAM" "CAPABILITY_NAMED_IAM" --region=us-west-2

3. Execute the below command


aws cloudformation create-stack --stack-name primaryDB --template-body file://database.yaml  --parameters file://primaryDBParameters.json  --capabilities "CAPABILITY_IAM" "CAPABILITY_NAMED_IAM" --region=us-west-2

4. Execute the below command


aws cloudformation create-stack --stack-name replicaDB --template-body file://replicaDatabase.yaml  --parameters file://replicaDBParameters.json  --capabilities "CAPABILITY_IAM" "CAPABILITY_NAMED_IAM" --region=us-west-2
