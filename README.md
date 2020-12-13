# Docker Help

Projetinho para guardar os testes com docker.

## Deletando todos os containers

```bash
docker rm -f $(docker ps -a -q)
```


## Deletando todos os volumes

```bash
docker volume rm $(docker volume ls -q)
```