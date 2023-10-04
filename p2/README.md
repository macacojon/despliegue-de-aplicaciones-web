# P2

### 1

Para instalar apache2 simplemente hay que poner el siguiente comando

```sh
sudo apt install apache2
```

### 2

- GET: Una petición GET es utilizada para obtener información de un recurso específico en un servidor web. La petición mediante get se hace por URL y se suele utilizar para recuperar datos.
- POST: Una petición POST se utiliza para enviar datos al servidor para su procesamiento. Los datos aquí se envían mediante el cuerpo de la solicitudo, lo que significa que no se ve en la URL, así que se suele utilizar para enviar información de una manera más segura.
- PUT: La petición PUT se utiliza para actualizar o reemplazar un recurso existente en el servidor con el recurso proporcionado en la solicitud. Hace la misma función que el POST, pero este se utiliza cuando se conoce la ubicación exacta del recurso a actualizar.
- DELETE: La petición DELETE se utiliza para borrar cualquier tipo de dato del servidor. Igual que el PUT se debe conocer la información exacta del recurso a eliminar.


### 3

Para cambiar el puerto, introducimos la siguiente línea de código:

```sh
sudo nano /etc/apache2/ports.conf
```

Una vez dentro modificamos la línea, donde pone "Listen 80", y la cambiamos por "Listen 4444".
Cuando ya hemos modificado este archivo, pasamos al siguiente, añadimos esta línea de código:

![image](https://github.com/macacojon/despliegue-de-aplicaciones-web/assets/144774960/4dfea1ad-f08a-4138-82d3-f180c58a3fcb)


```sh
sudo nano /etc/apache2/sites-available/000-default.conf
```

Y dentro de este archivo, donde pone "<VirtualHost *:80>", lo cambiamos a "<VirtualHost *:4444>"

![image](https://github.com/macacojon/despliegue-de-aplicaciones-web/assets/144774960/22e36526-0e5a-4f10-8d49-f9522f88a3c7)

Y ya funciona.

![image](https://github.com/macacojon/despliegue-de-aplicaciones-web/assets/144774960/2ba4746a-e01f-4c6b-8beb-74fbe1339ab2)


### 4

Lo primero de todo, genero un certificado SSL autofirmado:

![image](https://github.com/macacojon/despliegue-de-aplicaciones-web/assets/144774960/ea326880-adf8-4188-8100-6435d91eb29a)

De siguiente me voy a la configuración del siguiente archivo de Apache para usar el certificado SSL y lo dejo así:

![image](https://github.com/macacojon/despliegue-de-aplicaciones-web/assets/144774960/e345bc94-8acb-40f7-ac21-f74c8973ea9a)

Introduzco los siguientes dos comandos, uno para habilitar el archivo y otro para el módulo SSL:

![image](https://github.com/macacojon/despliegue-de-aplicaciones-web/assets/144774960/74f6457c-1eb8-486e-8ea5-7122d27a9451)

De siguiente configuro este archivo también para ya acabar con la configuración sobre el puerto SSL:

![image](https://github.com/macacojon/despliegue-de-aplicaciones-web/assets/144774960/cf2e213e-f576-4d04-86e3-8442d6b44fee)

Una vez configurado, ya debería funcionar, por lo tanto procedo a meterme en la web.

Si pongo http, me da error:

![image](https://github.com/macacojon/despliegue-de-aplicaciones-web/assets/144774960/b3c45279-0f04-4bac-acf4-aef5bc8081d1)

Aunque si me meto en https, si me funciona:

![image](https://github.com/macacojon/despliegue-de-aplicaciones-web/assets/144774960/033275ba-e931-44a1-935b-d8f8ad7afdf1)


### 5

*¿Dónde se encuentran los ficheros de configuración de Apache2?* 

- *Ubicación principal*: Se encuentra en /etc/apache2/apache2.conf
- *apache2.conf*: El archivo contiene configuraciones globales de Apache, como la configuración del servidor y la de los modulos cargados. Luego las directivas más importantes son, "ServerRoot", "User", "Group" y "Directory".
- *sites-available*: En este directorio estan los archivos de configuración de los sitios disponibles.
- *sites-enable*: Este otro directorio contiene enlaces simbólicos a los archivos de configuración de los sitios habilitados.
- *mods-available*: Contiene los archivos de configuración para los diferentes módulos de Apache que están disponibles.
- *mods-enabled*: Aquí están los enlaces simbólicos a los archivos de configuración de módulos que están habilitados.

### 6

*¿Dónde se encuentran los ficheros de ejecución de Apache2?*

- *Ubicación principal*: El archivo principal de ejecución de Apache se encuentra en "/usr/sbin/apache2".
-  *Control de servicio*:
- - *Iniciar*: sudo systemctl start apache2
  - *Detener*: sudo systemctl stop apache2
  - *Recargar*: sudo systemctl reload apache2
  - *Reiniciar*: sudo systemctl restart apache2
-  *Comprobación de sintaxis*: Para comprobar la sintaxis de tu configuración de Apache, puedes hacerlo en "sudo apachectl configtest".

### 7

 *¿Dónde se encuentran los ficheros de monitorización de Apache2?*

 - *Ubicación principal*: el directorio principal de los archivos de monitorización de Apache2 "/var/log/apache2/".
 - *error.log*: Este archivo registra los mensajes de error generados por el servidor.
 - *acces.log*: Este otro archivo registra cada solicitud de acceso que recibe el servidor.
 - *Rotación de logs*: Este archivo define las reglas como la frecuencia de rotación o el número de versiones de logs a mantener. Es importante para evitar que los archivos de log crezcan indefinidamente y consuman demasiado espacio del disco. Y los puedes configurar en la siguiente ruta "/etc/logrotate.d/".
 - *Monitorización en tiempo real*: Para monitorear en tiempo real, puedes utilizar el comando "tail -f" seguido de la ruta del archivo .log que quieres seguir.

Por ejemplo:

![image](https://github.com/macacojon/despliegue-de-aplicaciones-web/assets/144774960/b8d2d6cd-b7f8-4fee-8f4b-7c90f0a58e47)


 - *Análisis de logs*:

Primero que nada instalamos "goaccess":

![image](https://github.com/macacojon/despliegue-de-aplicaciones-web/assets/144774960/9ebc369e-af57-4ff4-acdf-bf559a51a61b)

Si introducimos el comando "goaccess /var/log/apache2/access.log", se nos abrira esto:

![image](https://github.com/macacojon/despliegue-de-aplicaciones-web/assets/144774960/3655c109-d59f-4ff2-9e12-88a0c1bf9e49)

Que es básicamente una interfaz de línea de comandos con estadísticas sobre los accesos al servidor.

### 8

Un Firewall lo que hace es controlar y supervisar el tráfico de red entre un sistema y otras redes. El proposito del Firewall es proteger los sistemas contra amenazas de accesos no autorizados.

*Instalación y configuración de un Firewall*

Primero que nada lo instalamos:

![image](https://github.com/macacojon/despliegue-de-aplicaciones-web/assets/144774960/f5d6821b-56b4-4b6f-8249-a6b9a5fa3d4c)

Lo habilitamos:

![image](https://github.com/macacojon/despliegue-de-aplicaciones-web/assets/144774960/aa9b41f1-cfc0-450e-ae27-5f911a823d9d)

Hacemos reglas para permitir HTTP y HTTPS:

![image](https://github.com/macacojon/despliegue-de-aplicaciones-web/assets/144774960/f678292a-4799-43cf-928e-d9010042a002)

Bloqueamos el resto de puertos:

![image](https://github.com/macacojon/despliegue-de-aplicaciones-web/assets/144774960/7cfda92b-22a5-4624-9107-97960dcd8e95)

Y verificamos las reglas impuestas:

![image](https://github.com/macacojon/despliegue-de-aplicaciones-web/assets/144774960/c655173c-b3f1-47fa-af46-e6a66719f2cd)

![image](https://github.com/macacojon/despliegue-de-aplicaciones-web/assets/144774960/c3bc8ecb-b487-4e7a-960a-db63782dbaf6)
