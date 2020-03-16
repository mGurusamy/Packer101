# Packer101
Getting Started with Packer using AWS_Linux Academy SandBox

It creates custom aws-ami using automation tool called packer. AWS credentials are held in Environment variable.
This can be used via user and env built in functions offered by packer.

This also uses various provisioner type like shell, ansible-local, file type.

Using Shell provisioner it installs Ansible packages.

Using ansible-local provisioner it installs nginx webserver and start the service.

Using file type provisionser it copies list of files in a directory to named folder in remote ami.

Once you finish your builders, provisioners element of packer build process, you can use packer validate command to make sure that the template doesnt have any errors.
```bash
packer validate example.packer
```
## How to create ami using this repo
Export AWS_ACCESS_KEY_ID and AWS_SECRET_ACCESS_KEY of iam user account.

Make sure default vpc is running for this profile.

Use the below command to build the image.
```bash
packer build example.packer
```
If you want to debug each stages of packer build process use -debug option as below
```bash
packer build -debug example.packer
```
Once build process finished, you can verify the newly built image under AMIs section of AWS console.

You can spin up the instance using the newly built image and verify that nginx service up and running and files(filesToBeCopied dir) are copied into /tmp folder in the new instance.

## License
[MIT](https://choosealicense.com/licenses/mit/)
