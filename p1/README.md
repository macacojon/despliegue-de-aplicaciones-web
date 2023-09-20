# Ejercicios básicos PHP

### Analiza los headers de las peticiones cuando inicias sesión en el Moodle y comprende cómo se obtiene el token. Para ello, necesitamos saber de dónde salen TODOS los datos sensibles que se envían.

Cuando iniciamos sesión en el Moodle, direcamente nos aparecen dos documentos que se llaman index.php, uno se llama así y el otro tiene un nombre un poco más largo, uno contiene los datos del inicio de sessión y el otro es el número de la session

Este es el primero de los dos, el que contiene los datos de la sessión:

![image](https://github.com/macacojon/despliegue-de-aplicaciones-web/assets/144774960/cd996b12-13a3-4f51-b55a-f0a137bde701)

Si nos desplazamos a payload salen mis datos de inicio de sesión:

![image](https://github.com/macacojon/despliegue-de-aplicaciones-web/assets/144774960/d9d0edcb-8fc3-41ee-8bcd-7c77024f8c5b)

Y el otro que es el de el número de la sesión:

![image](https://github.com/macacojon/despliegue-de-aplicaciones-web/assets/144774960/395a844a-5b1d-4b40-9921-3bd6e19a6baf)

Y su payload:

![image](https://github.com/macacojon/despliegue-de-aplicaciones-web/assets/144774960/50977a59-956f-44ca-8b55-ef7f67b70ff7)

### ¿A qué puerto se reciben normalmente las peticiones del protocolo HTTP? ¿A qué capa del modelo TCP/IP se encuentra el protocolo HTTP? ¿Y los protocolos TCP, UDP, e IP?

El puerto por defecto para las peticiones HTTP es el 80. Se encuentra en la capa de aplicación del modelo TCP/IP. El TCP está en la capa de transporte, el UDP también, la IP en la capa de internet.

### ¿Cuál es el significado de la siguiente respuesta de un servidor?

Indica que el recurso solicitado ha sido movido temporalmente a la URL que te dice en el "Location".

### Utilizando el filtro de captura para la interfaz de red de Wireshark, analiza la petición al host: www.google.com. Mostrando la cabecera IP, la dirección IP de tu ordenador y la del servidor. Comprueba que, poniendo esa IP en el navegador, accedas a Google.

Esta es la imagen donde se solicita todo, la cabezera IP, la direccion IP de mi PC y del servidor.

![image](https://github.com/macacojon/despliegue-de-aplicaciones-web/assets/144774960/caf6c61f-874f-4391-943e-03eb2d7f32a7)

Ahora aquí adjunto foto de la IP en Google antes de darle al Enter:

![image](https://github.com/macacojon/despliegue-de-aplicaciones-web/assets/144774960/d364006b-7a19-4812-a771-6d305cb19948)

Y aquí la foto después de darle al enter con la IP de Google:

![image](https://github.com/macacojon/despliegue-de-aplicaciones-web/assets/144774960/e9e54c8a-b602-4395-851c-c5b05f9a335e)
