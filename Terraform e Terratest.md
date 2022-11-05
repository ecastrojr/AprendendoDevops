```
###### Colinha do terraform:

terraform init
terraform plan -out bla
terraform apply "bla"
terraform plan -destroy
terraform destroy
terraform validate
terraform state pull >> arquivo.tfstate ou push
terraform plan -out plano -lock=false
-refresh=false para infras grandes
terraform refresh para atualizar o state
-target=module.inquiry no apply e no plan pra pegar um módulo específico
terraform state rm tira aquele estado da sua gerência automatica
terraform state mv para mover estados
terraform import aws_instance.web ami-ewer32432432432 importar coisas que criei na mão pro estado tfstate
terraform taint (vai ser destruído e recriado)
terraform workspace (criar staging e produção) - só o estado é diferente, o físico é o mesmo. por isso separar em regiões
TF_LOG=TRACE antes dos comandos
terraform taint através de terraform state list (untaint)
terraform graph
terraform fmt format -check -diff
criar condicionais de criacao de maquinas com ternários condition ? true : false e com variáveis no variables.tf

###### LINKS 
https://www.terraform.io/docs/language/values/variables.html
https://learn.hashicorp.com/tutorials/terraform/for-each
mudar de versão fácil no cmd do terraform - https://tfswitch.warrensbox.com/Install/

###### TERRAFORM CLOUD
importações simples e complexas
```


```
###### REPOSITÓRIO

Exercício para brincar com o Terraform e que já tem as próximas etapas do nosso curso:

https://github.com/camilla-m/terraform-aulas-do-linuxtips
```

```
###### TERRATEST

Repositório para executar e brincar com os testes do Terraform.

https://github.com/gruntwork-io/terratest

Esses são os códigos que eu testei:

https://terratest.gruntwork.io/docs/getting-started/quick-start/

Nesse link tem também como começar, baixar o Go, etc. Segui exatamente esse carinha! :)
```