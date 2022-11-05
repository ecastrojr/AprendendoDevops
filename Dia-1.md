## Material de apoio

Materiais que podem te ajudar nessa estrada:

``` html
https://caiodelgado.dev/docker-101/
https://github.com/caiodelgadonew/docker/blob/main/manuscript/05-docker-compose.md
https://github.com/gomex/docker-para-desenvolvedores
https://school.linuxtips.io/p/descomplicando-docker - 10% de desconto com cupom PUNKDODEVOPS
https://github.com/samcavallieri/devops_challenge
https://learnk8s.io/blog/smaller-docker-images
https://guiafoca.org/
https://docs.docker.com/engine/reference/builder
https://hub.docker.com/_/scratch
https://github.com/aquasecurity/trivy para falar de scaneamento de imagens em Docker
https://docs.docker.com/samples/wordpress/
https://stavshamir.github.io/python/dockerizing-a-flask-mysql-app-with-docker-compose/
https://docs.docker.com/samples/django/
https://github.com/docker/labs/tree/master/developer-tools/nodejs/porting/
https://nodejs.org/en/docs/guides/nodejs-docker-webapp/
https://docs.docker.com/engine/reference/builder/#add
https://docs.docker.com/compose/
https://docs.docker.com/compose/compose-file/compose-file-v3/
```

```bash
docker ps
docker images
docker system prune
docker build -t docker-linuxtips .
docker rmi --force $(docker images -aq)
docker images -aq
docker run --help
docker run -p 8080:8080 --name docker-node-4 -d docker-linuxtips
docker volume
docker network
```

```
O exercício deste primeiro vídeo foi feito baseado nesta documentação oficial: https://nodejs.org/en/docs/guides/nodejs-docker-webapp/
Para pegar este código, você também pode baixar no meu github: https://github.com/camilla-m/docker-node-linuxtips
```

