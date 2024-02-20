# FTP privado y anonimo.


1. Configura proftpd para que los usuarios accedan al directorio /home/ftp (puedes usar DefaultChdir). ¿Cual es la diferencia entre DefaultRoot y DefaultChdir?

Lo primero que vamos a hacer será instalar ProFTPd, para ello usamos "sudo apt-get install proftpd".

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/b106516b-9373-4da9-9939-8b92f842461f)

Una vez instalado vamos a modificar el archivo de configuración y vamos a cambiar el valor de ServerName al nombre de nuestro host, en mi caso voy a utilizar un host que ya tengo creado del proyecto anterior llamado centro.intranet.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/d7076230-3d1c-4f9f-bff1-54c62bcc827e)

Una vez configurado reiniciamos proftpd

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/fcba4f7f-80dc-4ba0-b789-4a2e84c3b420)

Ahora comprobamos que podemos acceder utilizando el comando "ftp centro.intranet".

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/5fd571c3-edfc-45ff-813f-358c53174af5)

Como podemos ver he iniciado sesión con un usuario del sistema y funciona.

Ahora, vamos a modificar la configuración para que los usuarios que accedan a nuestro servidor ftp, por defecto, se encuentren en la ruta /home/ftp, para ello vamos a crear la ruta primero. Para establecer la ruta por defecto en mi caso voy a usar la directiva "DefaultRoot".

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/b39b3a06-46a3-481d-933a-016b616468a2)

El motivo por el que uso DefaultRoot en vez de DefaultChdir es porque DefaultChdir solo establece la ruta en la que el usuario se encontrará cuando inicie sesión pero no le restringirá el acceso a carpetas superiores, como lo hace DefaultRoot. Utilizando DefaultRoot me aseguro de establecer el límite superior de acceso.

Ahora actualizaremos el servicio y comprobaremos que el directorio por defecto es el establecido.

4. No se permitirá subir ni eliminar nada de la carpeta ftp
5. Configura el acceso mediante usuario anónimo
6. Permite que el usuario anónimo pueda escribir si accede desde la red 10.6.0.x

