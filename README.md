# CLO835_Assignment2

### Terraform codes:

- ssh-keygen -f assignment
- Terraform init 
- terraform validate
- terraform plan
- terraform apply

- Copy all the files that are installed to the instance `scp -i assignment init_kind.sh kind.yaml <public IP>:/tmp`
- ssh into the newly created ec2 instance `ssh -i assignment <public ip>`
- `cd /tmp`
- `chmod 777 init_kind.sh`
- Run the installation scrip for kind cluster ``./init_kind.sh`
- Verify the cluster in running ` kubectl get nodes `
