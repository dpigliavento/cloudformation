## s3-example

Multiple templates to create a cross region S3 replica

# Deploy command

aws cloudformation deploy \
--stack-name s3-example \
--template-file remote-stack.yaml \
--parameter-overrides BucketName=s3-example-bucket \
--region us-west-2

aws cloudformation deploy \
--stack-name s3-example \
--template-file stack.yaml \
--parameter-overrides BucketName=s3-example-bucket RemoteRegion=us-west-2 \
--capabilities CAPABILITY_NAMED_IAM \
--region us-east-1

# Notes

You must deploy the remote-stack.yaml first before deploying stack.yaml. stack.yaml expects the remote S3 bucket to exist or will fail to deploy.

You can pass in an IAM role as ReplicationRole, otherwise the stack will create one for you.

If you expect he role to be created you'll need to run with appropriate access and include --capabilities CAPABILITY_NAMED_IAM in the deploy command
