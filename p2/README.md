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

