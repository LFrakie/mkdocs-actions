## 1 Creando un **Dockerfile**
**Dockerfile** nos sirve para construir nuestra imagen
```Dockerfile
FROM ubuntu:20.04
MAINTAINER Frank frankwilsonknow@gmail.com
ARG DEBIAN_FRONTEND=noninteractive
RUN apt-get update
RUN apt-get -y install apache2
EXPOSE 80
CMD /usr/sbin/apache2ctl -D FOREGROUND
```

Nos hubicamos en la misma carpeta de donde está nuestro **Dockerfile** y ejecutamos este codigo apra construir nuestra **imagen**. 

```bash
sudo docker build -t Nombre_de_Imagen .
```
Luego de que se construya vamos a verificar con el comando ``sudo docker images`` la existencia de nuestra nueva imagen creada.

```bash
sudo docker run -dit -p 8053:80 --name nuevo-nombre Nombre_de_Imagen
```

## Abrir terminal de un contenedor
```bash
sudo docker exec -it nombre-contenedor /bin/bash
```
 
 