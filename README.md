# test-keycloak

## Comenzando 🚀

_Estas instrucciones te permitirán obtener una copia del proyecto en funcionamiento en tu máquina local para propósitos de desarrollo y pruebas._

### Pre-requisitos 📋

_Configurar nuestro archivo Dockerfile para que funcione con nuestra base de datos SQL SERVER_

```
ENV KC_DB=mssql
...
ENV KC_DB_URL=jdbc:sqlserver://34.68.47.139;databaseName=keycloak_dev
ENV KC_DB_USERNAME=ridivi_jose
ENV KC_DB_PASSWORD=kUWVe5YBCSU3xsbv
ENV KC_HOSTNAME=localhost
...
```

### Instalación 🔧
_Primero abrimos la consola en el ruta donde se encuentra nuestro Dockerfile_

_Luego de eso corremos el siguiente comando_

```
$ docker build . -t prebuilt_keycloak
```
_Esperamos a que docker instale y configure todo lo necesario_

_Luego, corremos el siguiente comando para ejecutar el proyecto en modo desarrollo esto es la primera vez de contruir el proyecto, para que sea creada la imagen_

```
$ docker run --name keycloak_test -p 8081:8080 -e KEYCLOAK_ADMIN=admin -e KEYCLOAK_ADMIN_PASSWORD=change_me quay.io/keycloak/keycloak:latest start-dev
```

_Para ejecutarlo despues o de manera recurrente, usaremos el siguiente commando (Modo dev):_
```
$ docker run quay.io/keycloak/keycloak:latest start-dev
```

#### Nota: Luego miraremos como construir y ejecutar en modo produccion.

## Despliegue 📦

_Despues de correr la imagen, abrimos nuestro navegador y colocamos la url preconfigurada_

```
http://127.0.0.1:8081/
```
