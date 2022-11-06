## GitLab CI / GitLab Runner

![](imgs/dev%20stg%20prd.png)


```bash
kubectl get secrets
kubectl get secret <secret name> -o jsonpath="{['data']['ca\.crt']}" | base64 --decode
kubectl get secret default-token-hpmmb -o jsonpath="{['data']['ca\.crt']}" | base64 --decode
kubectl apply -f gitlab-admin-service-account.yaml
kubectl -n kube-system describe secret $(kubectl -n kube-system get secret | grep gitlab | awk '{print $1}')
kubectl get secrets -A
helm repo add gitlab https://charts.gitlab.io
kubectl get ns
kubectl create ns gitlab
helm install --namespace gitlab gitlab-runner -f values.yaml gitlab/gitlab-runner
kubectl get sa -A
kubectl get sa default -o yaml -n gitlab
kubectl create clusterrolebinding default --clusterrole=cluster-admin --group=system:serviceaccounts --namespace=gitlab
```

``` yaml
####### gitlab-admin-service-account.yaml

apiVersion: v1
kind: ServiceAccount
metadata:
  name: gitlab
  namespace: kube-system
---
apiVersion: rbac.authorization.k8s.io/v1
kind: ClusterRoleBinding
metadata:
  name: gitlab-admin
roleRef:
  apiGroup: rbac.authorization.k8s.io
  kind: ClusterRole
  name: cluster-admin
subjects:
  - kind: ServiceAccount
    name: gitlab
    namespace: kube-system
```

```
####### values do runner

runners:
  config: |
    [[runners]]
      [runners.kubernetes]
        image = "ubuntu:16.04"
        helper_cpu_limit = "200m"
        privileged = true
      [[runners.kubernetes.volumes.empty_dir]]
        name = "docker-certs"
        mount_path = "/certs/client"
        medium = "Memory"

gitlabUrl: "https://gitlab.com/"

runnerRegistrationToken: "TOKEN DO RUNNER AQUI"

## helpers:
##    cpuLimit: 200m
```

``` bash
git init
git remote
git status
git add ../server.js
git commit -m "(feature/node): change app get send"
git push linuxtips main
git push origin main
git pull
git checkout main
git stash
git checkout 1-upload-project-linuxtips-punk-do-devops
git add .
git commit -m "Update readme.md removing breaklines"
git push -u origin 1-upload-project-linuxtips-punk-do-devops
git config --global user.name camilla-m
git config --global user.email "email"
git commit --allow-empty -m "Allow empty"
git log
git remote --help
git reset f04207 --hard
git blame README.md
git checkout -b new-branch
```