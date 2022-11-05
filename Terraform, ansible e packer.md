```
####### TERRAFORM e TERRATEST

terraform init
terraform plan
terraform apply
terraform destroy
terraform destroy --auto-approve
terraform apply --auto-approve
go test
go mod download github.com/gruntwork-io/terratest
go get github.com/gruntwork-io/terratest/modules/aws@v0.37.1
go get github.com/gruntwork-io/terratest/modules/k8s@v0.37.1

####### PACKER
packer build example.pkr.hcl
packer init .
packer fmt .
packer validate .
docker inspect camillamartins/dockerpacker

####### ANSIBLE

ansible-inventory -i terraform.aws_ec2.yml --graph
ansible-inventory -i terraform.aws_ec2.yml --graph
ANSIBLE_HOST_KEY_CHECKING=False ansible-playbook playbook-inicial.yml -i terraform.aws_ec2.yml -u ubuntu --key-file ~/.ssh/testecami.pem
```

####### EXERCÍCIOS

Não se esqueça que os exemplos para brincar estão aqui: https://github.com/camilla-m/terraform-aulas-do-linuxtips

```
####### COMANDOS DO EKS

aws eks --region us-west-2 update-kubeconfig --name $clustername
kubectl get pods -A
kubectl get nodes

```