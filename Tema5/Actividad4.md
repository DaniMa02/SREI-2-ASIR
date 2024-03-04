## Docker #4


### Ejemplo 1: Despliegue de aplicación Guestbook
Lo primero que debemos hacer es descargar ambos contenedores para ello hacemos un pull:

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/455abb02-dc79-4cf8-b4e8-1146e5773bed)

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/e4c3ca87-83f4-4960-8482-14ebfad556d4)

Ahora vamos a crear una red para que ambos volúmenes estén en la misma red:

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/0154c05d-275b-41b8-b445-cb6125f58316)

Una vez creada vamos a inciar los contenedores de la siguiente manera:

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/53eb0a0f-6d90-4db7-a3d9-ae45544be37e)

Ahora desde nuestro navegador, podremos acceder a localhost y comprobar que efectivamente accedemos a Guestbook.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/8d4b8e26-b117-44d7-9444-179adfb39401)

### Ejemplo 2: Despliegue de la aplicación Temperaturas

Primero vamos a crear la red para que ambos contenedores se comuniquen:

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/7b0c0a5c-0b63-437a-abb0-06db13690535)

Ahora vamos a ejecutar los dos contenedores:

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/6d1b8640-99e2-486b-a044-e035f5ba10e8)

Ahora vamos a comprobar que efectivamente funciona accediendo desde el navegador a localhost:

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/40637f7e-fb47-4b0f-864d-491d492282bc)

### Ejemplo 3: Despliegue de Wordpress + mariadb

Para este ejemplo también vamos a crear otra red:

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/04a2f8a7-fbfb-4936-9d1c-9e32d92da831)

Ahora vamos a crear los contenedores:

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/65ea1b66-f00c-4de9-aef7-34fbe8367672)

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/30449059-7405-4867-b458-4c9e54f5b3c1)

Y ahora probamos a acceder desde el navegador:

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/d68ff416-3813-4be6-af89-10a2ee11845b)
