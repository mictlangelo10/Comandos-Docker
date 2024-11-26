
# Lista de Comandos Docker

## Índice
1. [Docker Engine](#docker-engine)
2. [Docker Compose](#docker-compose)
3. [Docker Swarm](#docker-swarm)

---

## Docker Engine

### Comandos básicos:

- **Listar contenedores en ejecución:**  
Muestra una lista de todos los contenedores que están corriendo actualmente.  
```shell
docker ps
```

- **Listar todos los contenedores:**  
Incluye tanto los contenedores en ejecución como los detenidos.  
```shell
docker ps -a
```

- **Iniciar un contenedor detenido:**  
Activa un contenedor previamente detenido.  
```shell
docker start <nombre_o_id_contenedor>
```

- **Detener un contenedor en ejecución:**  
Finaliza un contenedor que se encuentra en ejecución.  
```shell
docker stop <nombre_o_id_contenedor>
```

- **Eliminar un contenedor:**  
Borra un contenedor detenido del sistema.  
```shell
docker rm <nombre_o_id_contenedor>
```

- **Eliminar todos los contenedores:**  
Elimina todos los contenedores detenidos.  
```shell
docker rm $(docker ps -aq)
```

- **Eliminar una imagen:**  
Elimina una imagen específica por su ID o nombre.  
```shell
docker rmi <id_imagen>
```

- **Limpiar recursos no utilizados (contenedores, imágenes, volúmenes y redes):**  
```shell
docker system prune -a
```

- **Inspeccionar un contenedor:**  
Proporciona información detallada en formato JSON sobre un contenedor.  
```shell
docker inspect <nombre_o_id_contenedor>
```

- **Ver estadísticas de uso de recursos de contenedores:**  
Muestra datos en tiempo real de CPU, memoria y red de los contenedores.  
```shell
docker stats
```

- **Ver los logs de un contenedor:**  
Muestra los logs de salida de un contenedor.  
```shell
docker logs <nombre_o_id_contenedor>
```

- **Eliminar todos los recursos de Docker:**  
Limpia todos los contenedores, imágenes, redes y volúmenes no utilizados.  
```shell
docker system prune -a --volumes
```

---

### Explicación del comando de la imagen:

El comando visto en la imagen es:

```shell
docker compose -f stack-cronojobs.yaml up -d
```

- **docker compose:** Ejecuta Docker Compose, que se utiliza para definir y ejecutar aplicaciones multi-contenedor.
- **-f stack-cronojobs.yaml:** Especifica el archivo de configuración a utilizar. En este caso, se llama `stack-cronojobs.yaml`.
- **up:** Levanta los servicios definidos en el archivo YAML.
- **-d:** Ejecuta los contenedores en segundo plano (modo "detached").

**Descripción completa:** Este comando levanta todos los servicios definidos en el archivo `stack-cronojobs.yaml` en segundo plano. Es ideal para configurar aplicaciones complejas que involucren múltiples contenedores.

---

## Docker Compose

### Comandos básicos:

- **Iniciar contenedores definidos en `docker-compose.yml`:**  
Ejecuta los servicios descritos en el archivo de configuración por defecto (`docker-compose.yml`).  
```shell
docker-compose up
```

- **Iniciar contenedores desde un archivo específico:**  
```shell
docker-compose -f <archivo.yml> up
```

- **Detener contenedores y servicios definidos:**  
```shell
docker-compose down
```

- **Recrear contenedores sin borrar volúmenes:**  
```shell
docker-compose up --force-recreate
```

- **Construir imágenes sin iniciar contenedores:**  
```shell
docker-compose build
```

- **Escalar servicios:**  
Ejemplo: Ejecutar tres instancias de un servicio llamado `web`.  
```shell
docker-compose up --scale web=3
```

---

## Docker Swarm

### Comandos básicos:

- **Inicializar Docker Swarm:**  
Convierte el nodo actual en un nodo principal de un clúster Swarm.  
```shell
docker swarm init
```

- **Unirse a un clúster Swarm existente:**  
```shell
docker swarm join --token <token> <ip>:<puerto>
```

- **Listar nodos del clúster:**  
```shell
docker node ls
```

- **Salir del clúster Swarm:**  
Elimina el nodo actual del clúster Swarm.  
```shell
docker swarm leave
```

- **Crear un servicio:**  
Ejecuta un servicio gestionado por Swarm.  
```shell
docker service create --name <nombre_servicio> <imagen>
```

- **Listar servicios en el clúster:**  
```shell
docker service ls
```

- **Actualizar un servicio:**  
Permite cambiar la configuración de un servicio existente.  
```shell
docker service update <opciones> <nombre_servicio>
```

- **Eliminar un servicio:**  
Borra un servicio del clúster.  
```shell
docker service rm <nombre_servicio>
```

---

## Comandos Adicionales

- **Eliminar todos los contenedores detenidos y las imágenes no utilizadas:**  
```shell
docker system prune -a
```

- **Detener todos los contenedores en ejecución:**  
```shell
docker stop $(docker ps -q)
```

- **Eliminar todos los contenedores:**  
```shell
docker rm $(docker ps -aq)
```

- **Eliminar todas las imágenes de Docker:**  
```shell
docker rmi $(docker images -q)
```
