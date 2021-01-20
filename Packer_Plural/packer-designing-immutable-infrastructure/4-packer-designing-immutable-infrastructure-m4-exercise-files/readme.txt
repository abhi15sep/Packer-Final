Hello awesome infrastructure person!

Don't forget that you need to set these two environment variables with your own AWS credentials before running these templates:

AWS_ACCESS_KEY_ID
AWS_SECRET_ACCESS_KEY

Also, I've included the source for Globalmantics middle-tier app in Go, in case you want to customize it yourself. The built binary in the ToUpload folder was built for Linux amd64.

Note that depending on which OS you have Docker installed on, you may need to configure your Docker client to talk to the Docker agent before running the Docker builder.

Happy Packering!

1. packer build -only="docker" -var 'ami_id=ami-9abea4fb' -var 'supervisor_version=3.0b2-1' template.packer
2. cat middletier.tar | docker import - middletier:latest
3. docker run -d -it middletier:latest /bin/bash -c "sudo service supervisor start && sudo service nginx start && bash"