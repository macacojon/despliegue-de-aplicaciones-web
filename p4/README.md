# Servidores virtuales de Apache

Para comenzar instalamos el Apache poniendo este comando:

![image](https://github.com/macacojon/despliegue-de-aplicaciones-web/assets/144774960/9a81a2b2-accd-4f60-b75f-1aa344f8a619)

De seguido hago el comando:

![image](https://github.com/macacojon/despliegue-de-aplicaciones-web/assets/144774960/c9327872-8d96-454d-9dd9-4d3560386dac)

La finalidad de este comando es habilitar el módulo de reescritura de URL en Apache.
Y reinicio el servidor de Apache, haciendo un "sudo systemctl restart apache2", para aplicar todos los cambios.


Una vez hecho lo anterior, que servía para configurar Apache, empezamos creando los directorios de los servidores virtuales

![image](https://github.com/macacojon/despliegue-de-aplicaciones-web/assets/144774960/9542dc2e-0ac0-4857-b9e6-e47bd9cf0c18)

He creado dos "index.html" en cada directorio respectivamente, que los mostraré posteriormente.

También he copiado los ficheros de configuración del Apache para poder modificarlos mas tarde a mi gusto.

![image](https://github.com/macacojon/despliegue-de-aplicaciones-web/assets/144774960/93bf4ffb-43d0-412d-bfd6-c291b5998b9a)

He modificado los dos archivos de la configuración que he copiado para que funcionen correctamente.

Y ejecuto los siguientes comandos para que funcione:

![image](https://github.com/macacojon/despliegue-de-aplicaciones-web/assets/144774960/5816c790-7820-4dd0-9441-fea7a22f786b)

Una vez hecho, configuro el archivo "hosts" y añadimos las nuevas direcciones:

![image](https://github.com/macacojon/despliegue-de-aplicaciones-web/assets/144774960/9911aa74-e782-4adc-9c6b-2fbf2a61b3a7)

Hacemos lo mismo en el Ubuntu Desktop:

![image](https://github.com/macacojon/despliegue-de-aplicaciones-web/assets/144774960/3a977567-6fcc-4e5e-a1bf-10c1a4076204)

Y cuando nos metemos en la dirección nos sale lo siguiente:

![image](https://github.com/macacojon/despliegue-de-aplicaciones-web/assets/144774960/7f8ee6b5-bf90-4ac7-b9e2-5c077bf0dcf9)

![image](https://github.com/macacojon/despliegue-de-aplicaciones-web/assets/144774960/fdc3fd0f-f062-4a44-95e7-8d47d6645ee8)
