

``` bash
docker kill $containerid
docker-compose down
docker-compose up
docker-compose up -d
docker volume ls
docker volume rm $volume
docker-compose run web django-admin startproject composeexample .
docker container prune
docker-compose build
docker stop $container
docker tag dockernode camillamartins/dockernode:5.0
docker push camillamartins/dockernode:5.0
docker scan dockernode
docker-compose --help
docker-compose run --help
docker-compose up -d --build
docker logs $containerid
docker-compose logs
docker-compose build
docker-compose ls
docker-compose logs --follow
docker pull php
docker commit
docker --help
docker login --help
```

```
Para fazer os exercícios deste vídeo, seguimos os seguintes tutoriais:

- https://docs.docker.com/samples/django/
- https://docs.docker.com/samples/wordpress/
- https://docs.docker.com/develop/develop-images/multistage-build/

Se atente nas dicas dos vídeos para os casos de bugs para que você possa corrigir e rodar com sucesso na sua máquina :)
```