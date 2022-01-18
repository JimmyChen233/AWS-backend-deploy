
aws cloudformation create-stack --stack-name vpc --template-body file://$PWD/vpc.yml 

aws cloudformation create-stack --stack-name iam --template-body file://$PWD/iam.yml --capabilities CAPABILITY_IAM


