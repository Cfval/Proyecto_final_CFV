# Guía para Configurar y Utilizar el Entorno de Desarrollo

Este manual detalla los pasos necesarios para establecer y operar el entorno de desarrollo de este proyecto.

## Requisitos Previos

Antes de iniciar, verifica que tu sistema tenga instalados los siguientes programas:

- **Docker**: Herramienta para crear y gestionar contenedores.
- **Docker Compose**: Utilidad para coordinar múltiples contenedores de Docker.
- **Apache2**: Servidor web para entornos locales.

Si alguno de estos programas no está presente en tu sistema, puedes instalarlos ejecutando:

```bash
# Instalación de Docker
sudo apt update && sudo apt install -y docker.io

# Instalación de Docker Compose
sudo apt install -y docker-compose

# Instalación de Apache2
sudo apt install -y apache2
```

## Instalación del Proyecto

### Clonar el Repositorio

Para obtener una copia local del proyecto, ejecuta:

```bash
git clone https://github.com/Cfval/Proyecto_final_CFV.git
```

## Puesta en Marcha de los Contenedores

El proyecto se divide en dos directorios principales:

- **backend** y **frontend**

Cada directorio posee un archivo `docker-compose-dev.yml` para iniciar los contenedores.

### Backend

Para arrancar el contenedor del backend, navega al directorio correspondiente y ejecuta:

```bash
cd films-backend
docker-compose -f docker-compose-dev.yml up -d
```

### Frontend

Para iniciar el contenedor del frontend, dirígete al directorio adecuado y ejecuta:

```bash
cd films-frontend
docker-compose -f docker-compose-dev.yml up -d
```

## Acceso

Con los contenedores en ejecución, puedes acceder a la aplicación mediante las siguientes URLs:

**Backend:** [http://films.api.dev.com:8080/](http://films.api.dev.com:8080/)
**Frontend:** [http://films.dev.com:8081/](http://films.dev.com:8081/)

Para que tu sistema reconozca estos dominios, es necesario modificar el archivo `hosts` (/etc/hosts) añadiendo:

127.0.0.1 backend.api.dev.com
127.0.0.1 frontend.api.dev.com

## Detener los Contenedores

Cuando desees finalizar las operaciones, puedes detener los contenedores con:

```bash
cd backend
docker-compose -f docker-compose-dev.yml down

cd ../frontend
docker-compose -f docker-compose-dev.yml down
```

Siguiendo estos pasos, tendrás tu entorno de desarrollo correctamente configurado y listo para su uso.


## Adicional - Uso de la Base de Datos

Para acceder a la base de datos MySQL dentro del contenedor, ejecuta el siguiente comando:

```bash
docker exec -it films-backend-db mysql -u root -p
```

La contraseña de acceso es: **toor**

Una vez dentro de MySQL, puedes ejecutar los siguientes comandos para ver las bases de datos y las tablas disponibles:

```sql
SHOW DATABASES;
USE films;
SHOW TABLES;
```




