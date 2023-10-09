# P3

### 1

Para añadir el module info hay que añadir el siguiente comando:

![image](https://github.com/macacojon/despliegue-de-aplicaciones-web/assets/144774960/9caf8de8-aa3e-4efb-b44b-efc1e539d17d)

Posteriormente hacemo el siguiente comando:

![image](https://github.com/macacojon/despliegue-de-aplicaciones-web/assets/144774960/84c1f550-71e4-4def-8780-afa11289ae69)

Este último se hace para que los cambios surtan efecto.

### 2

Edito este el archivo "/etc/apache2/apache2.conf".

Y al final del archivo añado las siguientes lineas:

![image](https://github.com/macacojon/despliegue-de-aplicaciones-web/assets/144774960/4f427339-99ac-4d70-a86a-a3fb700683a0)

Y reinicio el servidor otra vez.

### 3

Creo estas dos carpetas:

![image](https://github.com/macacojon/despliegue-de-aplicaciones-web/assets/144774960/2b6e5b01-f55b-4684-9e24-88edb389e4a6)

Cambio de propietario y de permisos:

![image](https://github.com/macacojon/despliegue-de-aplicaciones-web/assets/144774960/ec742643-4919-434a-8ee9-642e3ae2d95e)

Vuelvo a meterme en el archivo "/etc/apache2/apache2.conf" y añado el siguiente código:

![image](https://github.com/macacojon/despliegue-de-aplicaciones-web/assets/144774960/2d0cb1cf-390a-4014-915e-268ab1390e68)

Reinicio de nuevo y listo.

### 4

Creo el archivo ".htaccess", con el comando:

![image](https://github.com/macacojon/despliegue-de-aplicaciones-web/assets/144774960/f9fb702a-84a7-4949-b313-fb7c63862957)

Después en el archivo recien creado añado lo siguiente:

![image](https://github.com/macacojon/despliegue-de-aplicaciones-web/assets/144774960/37e828ef-56eb-4c13-91cd-8854a8b20fb7)

### 5

Primero hay que descargar el tema, posteriormente descomprimirlo y moverlo a la carpeta del servidor web.
Hacer estos dos comandos:

```sh
sudo a2enmod autoindex
sudo systemctl restart apache2
```

Y ya estaría

### 6

Creo la carpeta donde se va a hacer todo:

![image](https://github.com/macacojon/despliegue-de-aplicaciones-web/assets/144774960/114d0eed-f1a0-45df-8d60-e1f52a2c7d10)

Creo el archivo .css y le meto código:

![image](https://github.com/macacojon/despliegue-de-aplicaciones-web/assets/144774960/84d29898-42d1-4241-bc62-4ff3e0fad6fe)

Abro el archivo .htaccess y le añado la siguiente linea:

![image](https://github.com/macacojon/despliegue-de-aplicaciones-web/assets/144774960/d6c05237-8c10-4d41-8670-b167713b1c9b)

Y cuando reinicias ya iría.
