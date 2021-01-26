# Flask Boilerplate para desarrolladores profesionales

[![Open en Gitpod](https://gitpod.io/button/open-in-gitpod.svg)](https://gitpod.io/from-referrer/)
<p align="center">
    <a href="https://youtu.be/ORxQ-K3BzQA"><img height="200px" src="https://github.com/4GeeksAcademy/flask-rest-hello/blob/master/docs/assets/how-to.png?raw=true" /></a>
</p>

## Características

- Documentación completa [aquí](https://github.com/4GeeksAcademy/flask-rest-hello/tree/master/docs)
- Pipenv integrado para manejo de paquetes y dependencias
- Implementación rápida a heroku con `$ pipenv run deploy`
- Uso de archivos `.env` para gestión de variables de ambiente
- SQLAlchemy integrado para gestión de base de datos MySQL

## Instalación (automática si usas gitpod o docker)

> Importante: Este boiplerplate está hecho para python 3.7 pero puedes cambiar eso fácilmente en la variable `python_version` del Pipfile.

Los pasos siguientes se ejecutan de forma automática en gitpod o el contenedor docker. Si estás haciendo una instalación local debes ejecutarlos manualmente:

```sh
pipenv install;
mysql -u root -e "CREATE DATABASE example";
pipenv run init;
pipenv run migrate;
pipenv run upgrade;
```

## ¿Cómo empezar a escribir código?

Hay un ejemplo en funcionamiento incorporado en este boilerplate para un endpoint (punto final de red) de una API y para una clase implementada en la base de datos MySQL. Tu aplicación, y todo tu código, debería estar contenido en el directorio `./src/`.

- src/main.py (configuración de tu aplicación y tus endpoints)
- src/models.py (clases para base de datos, con sus propiedades y métodos)
- src/utils.py (funciones y clases reusables)
- src/admin.py (agrega tus modelos a flask-admin para gestionar tus datos fácilmente)

Para una explicación más detallada, revisa el tutorial dentro del directorio `docs`.

## Recuerda migrar cada vez que cambias tus clases

Debes migrar e implementar las migraciones cada vez que actualizas o cambias una propiedad en tus clases implementadas en base de datos:
```
$ pipenv run migrate (crea las migraciones)
$ pipenv run upgrade  (implementa las migraciones en base de datos)
```


# Instalación manual para Ubuntu & Mac

⚠️ Asegúrate de tener `python 3.6+` y `MySQL` instalados en tu computadora; con MySQL corriendo, ejecuta los siguientes comandos:
```sh
$ pipenv install (para instalar paquetes y dependencias listados en el Pipfile)
$ mysql -u root -e "CREATE DATABASE example" (para crear tu base de datos example en MySQL)
$ pipenv run upgrade (para implementar las migraciones en base de datos)
$ pipenv run start (para iniciar el servidor web de flask)
```

# Flask boilerplate con docker

1. ⚠️ Si no tienes `docker` instalado en tu computadora, por favor ve a [instalar docker](https://docs.docker.com/get-docker/)
2. ⚠️ Si estas en linux o macOS, verifica que tienes o instala `docker-compose` siguiendo [estas instrucciones](https://docs.docker.com/compose/install/)
3. Clona el repo y crea un archivo `.env`; completa los pares **propiedad=valor** tal como aparecen en el archivo de ejemplo `.env.example`
4. Ejecuta `docker-compose up` y dale unos minutos
5. Tómate un café
6. Al finalizar la creación del contenedor y la imagen, deberías ver tu **API** (servidor web flask) corriendo en el puerto `3000` (desde el anfitrión, es decir, tu SO)
7. Tu **base de datos** debería estar disponible en el puerto `33060` (desde el anfitrión, de nuevo, tu SO)

## Desplegar a Heroku

Esta plantilla es 100% compatible con Heroku[https://www.heroku.com/], sólo asegúrate de entender y ejecutar estos pasos:

```sh
// Instala heroku
$ npm i heroku -g
// Entra en tu cuenta de heroku a través de la terminal
$ heroku login -i
// Crea una aplicación (si no la tienes ya)
$ heroku create <nombre_de_tu_app>
// Empuja tus cambios a heroku (haz commit de tus cambios)
$ git push heroku main
```
⚠ Para una explicación detallada sobre archivos .env o la base de datos MySQL [lea la guía completa](https://github.com/4GeeksAcademy/flask-rest-hello/blob/master/docs/DEPLOY_YOUR_APP.md).
