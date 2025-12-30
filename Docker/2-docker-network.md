---
title: Networks
layout: home
parent: Docker
nav_order: 2
---

# Networks
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

--- 

Si dos o más contenedores están en la misma red, podrán hablar entre sí. Si no lo están, no podrán.

https://docs.docker.com/engine/network/tutorials/standalone/

* Listar redes: 

    ```bash
    docker network ls
    ```
* Crear red:

    ```bash
    docker network create nombre-red
    ```

* Eliminar redes:
    ```bash
    docker network prune
    ```
* Agregar un contenedor a una red:
    ```bash
    docker network connect nombre-red nombre-contenedor
    ```

* inspect. Show list of containers in the selected network. In Json name `Containers`
    ```bash
    docker network inspect <NAME o ID>
    ```

## cambiar configuracion

Desde la carpeta del `docker-compose.yml`:

```bash
docker compose down
docker compose up -d --build
```

## Conectar dos contenedores

first, create a new network and put the name.

In te yml file write this:

```yml
    networks:
      - net-postgres

networks:
    net-postgres:
        external: true
```
