## export-example

Template creates a security group and provides a cross stack export value

# Deploy command

aws cloudformation deploy \
--stack-name export-example \
--template-file stack.yaml \
--parameter-overrides VpcId=vpc-xxxxxxxx
