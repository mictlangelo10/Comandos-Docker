# Docker Engine

## Índice
1. [Docker Engine](#docker-engine)
   - [docker version](#docker-version)
   - [docker info](#docker-info)
   - [docker images](#docker-images)
   - [docker ps](#docker-ps)
   - [docker run](#docker-run)
   - [docker stop](#docker-stop)
   - [docker start](#docker-start)
   - [docker rm](#docker-rm)
   - [docker rmi](#docker-rmi)
   - [docker exec](#docker-exec)
   - [docker logs](#docker-logs)
   - [docker pull](#docker-pull)
   - [docker push](#docker-push)
   - [docker build](#docker-build)
   - [docker-compose up](#docker-compose-up)
   - [docker-compose down](#docker-compose-down)

---

### docker version
- **Descripción**: Muestra la versión de Docker instalada.
```shell
docker version
docker info
Descripción: Proporciona información detallada sobre la configuración de Docker.
shell
Copiar código
docker info
docker images
Descripción: Lista todas las imágenes disponibles en el sistema local.
shell
Copiar código
docker images
docker ps
Descripción: Muestra los contenedores que están corriendo actualmente.
shell
Copiar código
docker ps
Opciones:
-a: Lista todos los contenedores, incluidos los detenidos.
shell
Copiar código
docker ps -a
docker run
Descripción: Crea y ejecuta un nuevo contenedor.
shell
Copiar código
docker run <image_name>
Ejemplo:
shell
Copiar código
docker run -d -p 8080:80 nginx
docker stop
Descripción: Detiene un contenedor en ejecución.
shell
Copiar código
docker stop <container_id>
docker start
Descripción: Inicia un contenedor detenido.
shell
Copiar código
docker start <container_id>
docker rm
Descripción: Elimina un contenedor detenido.
shell
Copiar código
docker rm <container_id>
docker rmi
Descripción: Elimina una imagen de Docker.
shell
Copiar código
docker rmi <image_id>
docker exec
Descripción: Ejecuta comandos dentro de un contenedor en ejecución.
shell
Copiar código
docker exec -it <container_id> <command>
Ejemplo:
shell
Copiar código
docker exec -it <container_id> bash
docker logs
Descripción: Muestra los registros de un contenedor.
shell
Copiar código
docker logs <container_id>
docker pull
Descripción: Descarga una imagen desde Docker Hub.
shell
Copiar código
docker pull <image_name>
docker push
Descripción: Sube una imagen al repositorio de Docker Hub.
shell
Copiar código
docker push <image_name>
docker build
Descripción: Construye una imagen Docker desde un archivo Dockerfile.
shell
Copiar código
docker build -t <image_name> .
docker-compose up
Descripción: Inicia los servicios definidos en un archivo docker-compose.yml.
shell
Copiar código
docker-compose up
docker-compose down
Descripción: Detiene y elimina los servicios definidos en un archivo docker-compose.yml.
shell
Copiar código
docker-compose down
Combinación de comandos
Ejemplo: Crear y correr un contenedor con Nginx, ver sus logs y detenerlo:
shell
Copiar código
docker run -d -p 8080:80 nginx
docker logs <container_id>
docker stop <container_id>
docker rm <container_id>
