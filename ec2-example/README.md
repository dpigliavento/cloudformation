## ec2-example

Template deploys a simple nginx web server

# Requirements

- Must first deploy export-example stack to create the referenced cross stack export value
- Create EC2 keypair and provide as KeyName parameter
- Existing Subnet provided as SubnetId parameter

# Deploy command

aws cloudformation deploy \
--stack-name ec2-example \
--template-file stack.yaml \
--parameter-overrides KeyName=ec2-example-key SubnetId=subnet-xxxxxxxx
