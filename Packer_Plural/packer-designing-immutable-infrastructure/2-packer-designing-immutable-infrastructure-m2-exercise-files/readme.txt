Hello awesome infrastructure person!

Don't forget that you need to set these two environment variables with your own AWS credentials before running these templates:

AWS_ACCESS_KEY_ID
AWS_SECRET_ACCESS_KEY

Also, I've included the source for Globalmantics middle-tier app in Go, in case you want to customize it yourself. The built binary in the ToUpload folder was built for Linux amd64.

Happy Packering!

1. export AUTH_HEADER=SuperSecureCode
2. packer build -var 'ami_id=ami-9abea4fb' -var 'supervisor_version=3.0b2-1' template.packer
