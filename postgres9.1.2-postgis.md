### Passo 1
Cria um container do postgres 9.1.2 já com o postgis 1.5 instalado

```bash
docker run --restart unless-stopped --name postgis -d -p 5433:5432 geographica/postgis:postgresql-9.1.2-postgis-1.5.8-patched
```


### Passo 2 (pode ser ignorado caso já tenha postgres instalado no PC host)
Acessar o bash do container (tipo ssh)

```bash
docker exec -it postgis /bin/bash
```

### Passo 3
Conectar ao postgres dentro do container e criar um banco.

```bash
psql -U postgres
create database siout_master template template1;
\q
exit
```

### Passo 4 (Caso queira restaurar um dump através do container)

```bash
docker cp C:/users/nome/Downloads/dump.backup postgis:/usr/local
docker exec -it postgis /bin/bash
pg_restore -U postgres -d siout_master ./dump.backup
exit
```
