# jupyter-edu

## Configuração de ambiente

#### Postgres

Defina as credenciais de acesso no arquivo `secrets/postgres.env`.


#### Spawn single user container

É preciso ter localmente a imagem utilizada para deploy dos containers:

```
docker pull jupyterhub/singleuser:latest
```
