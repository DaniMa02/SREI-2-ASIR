# Comprobación del script

Primero lo ejecutamos pasandole los parametros necesarios y como vemos en la salida se ha creado todo.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/4874d163-7a96-44c3-a1ef-f7f9979c9c48)

Ahora vamos a comprobar que todo funciona correctamente:

Primero veremos que se ha creado el directorio del usuario y su página web.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/78129b18-4189-4f0e-81d4-637174cbe8ec)

Como comprobamos, se ha creado la estructura de directorios donde se aloja una pequeña aplicación de Python 
que muestra el contenido de la página principal y un directorio al que acceden los usuarios para ver el contenido.

Ahora vamos a ver la configuración del VirtualHost.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/b9202b2a-9323-489a-9bac-50ddd22cc4fd)

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/1f07cec1-196f-41d7-bd2a-ed5819cd5894)

Vemos una configuración básica que nos permite la ejecución de aplicaciones Python.

Si accedemos al sitio web podremos ver dicha aplicación Python.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/4cc09134-593f-469b-ab5b-f4022c55ef38)

Ahora vamos a comprobar que se ha creado su base de datos junto a su usuario, para ello simplemente voy a mostrar todas 
las bases de datos y a iniciar sesión en la correspondiente al usuario con su mismo usuario.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/bacae8f9-6e4f-4a80-a778-528cc4af38e8)

Y también a acceder a phpmyadmin desde el navegador.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/fc349297-11fa-4860-b37f-5d98fc135ad6)

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/597641dd-4087-413b-8b07-e4676b877a7c)

Lo siguiente que vamos a comprobar es que el usuario pueda hacer conexiones FTP con TLS, para ello vamos a utilizar Filezilla.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/79f23f5b-c463-44e8-89f1-f77b3e3f9d9e)

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/726576fa-d91c-4165-bff2-c1b051934a22)

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/054d518b-2558-4a64-9757-f600aa19075c)

Ahora vamos a comprobar que también podemos utilizar el protocolo SFTP, que utiliza SSH para la conexión, por lo que también
comprobaremos que SSH funciona correctamente.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/d568f4a5-e662-46d5-9e5b-6965d84b9791)

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/608c3d50-dd2a-4a87-9731-a15145318278)

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/ef9997ac-f2f4-4c49-a347-f72c950a060e)

Con esto comprobamos que funciona correctamente y que efectivamente tenemos acceso.

Por último vamos a comprobar que el subdominio del usuario se ha creado junto a sus zona inversa y directa.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/356ff415-629c-4e23-90b4-c4ec213004b5)

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/45dacddb-dcaf-443f-bec2-515b1671548c)

Ahora que vemos que ambas zonas se han creado, comprobamos utilizando dig que nos responden.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/3894a3bd-bf0b-460f-815c-3eb27a2db679)

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/ae8c0aa0-d3d0-4785-a9c0-6e121eb80982)

Con esto queda comprobado que todos los requisitos del proyecto se cumplen y que el script funciona correctamente.
