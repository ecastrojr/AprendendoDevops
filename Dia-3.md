# Setup necessário para aula
Para esta aula é necessário que você tenha em seu Windows/Linux/Mac o Terraform, o kubectl e o Docker instalados.

Também é interessante ter uma conta na AWS para brincar e fazer alguns testes :)

Estas documentações oficiais podem te ajudar:

https://aws.amazon.com/pt/premiumsupport/knowledge-center/create-and-activate-aws-account/
https://learn.hashicorp.com/tutorials/terraform/install-cli
https://kubernetes.io/docs/tasks/tools/
https://docs.docker.com/get-docker/



## Material de apoio
Materiais que podem te ajudar na aula de hoje para você se aprofundar:

https://docs.aws.amazon.com/eks/latest/userguide/getting-started-eksctl.html
https://aws.amazon.com/pt/premiumsupport/knowledge-center/eks-kubernetes-services-cluster/
https://towardsdatascience.com/kubernetes-application-deployment-with-aws-eks-and-ecr-4600e11b2d3c
https://docs.aws.amazon.com/eks/latest/userguide/getting-started-eksctl.html
https://networking.workshop.aws/beginner/lab1.html - Lab de Redes da AWS
https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Scenario2.html
https://kubernetes.io/docs/tutorials/stateful-application/mysql-wordpress-persistent-volume/
https://github.com/99designs/aws-vault/blob/master/USAGE.md
https://www.youtube.com/watch?v=IHE6xR5qylY - Vídeo sobre Processos Seletivos de DevOps
https://eksctl.io/
https://kubernetes.io/docs/tasks/configure-pod-container/configure-liveness-readiness-startup-probes/
https://semver.org/
https://github.com/ahmetb/kubectx


## ####### KUBECTL FLOW

aws eks --region us-west-2 update-kubeconfig --name test-eks-xGFqhdkO
kubectl get nodes
kubectl get ns
kubectl get pods -A
kubectl get nodes
kubectl get deploy -A
kubectl describe pod $podname -A
kubectl describe pod $podname -n kube-system
kubectl get pods -A
kubectl logs --follow -l k8s-app=aws-node -n kube-system
kubectl apply -f nginx-deployment.yaml
kubectl get pods -A
kubectl get pods -l 'app=nginx' -o wide | awk {'print $1" " $3 " " $6'} | column -t
kubectl apply -f clusterip.yaml #pode usar kubectl delete para deletar também
kubectl expose deployment nginx-deployment  --type=ClusterIP  --name=nginx-service-cluster-ip
kubectl get svc
kubectl delete svc nginx-service-cluster-ip
kubectl expose deployment dockercami --port=8080 --target-port=8080 --type=LoadBalancer  --name=dockercami-loadbalancer
kubectl config --help
kubectl config get-clusters
kubectl config set-context minikube


## SUBINDO IMAGEM NO ECR

docker images
docker tag camillamartins/dockernode:7.0 799643693239.dkr.ecr.us-west-2.amazonaws.com
aws ecr get-login-password --region us-west-2 | docker login --username AWS --password-stdin 799643693239.dkr.ecr.us-west-2.amazonaws.com
docker push 799643693239.dkr.ecr.us-west-2.amazonaws.com/linuxtips-docker-cami:1.0
docker build -t 799643693239.dkr.ecr.us-west-2.amazonaws.com/linuxtips-docker-cami:2.0 .
docker push 799643693239.dkr.ecr.us-west-2.amazonaws.com/linuxtips-docker-cami:2.0

## EXERCÍCIOS E DOCUMENTAÇÕES

Exercício do Cluster, Node e Load Balancer:
https://aws.amazon.com/pt/premiumsupport/knowledge-center/eks-kubernetes-services-cluster/

Exercício subindo o Docker Cami com ECR no EKS e com Dockerhub:
https://github.com/camilla-m/terraform-aulas-do-linuxtips

Repositório para criar o EKS com Terraform:
https://github.com/terraform-aws-modules/terraform-aws-eks/tree/v17.18.0/examples/basic