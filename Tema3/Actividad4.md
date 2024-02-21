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

Ahora actualizaremos el servicio y comprobaremos que el directorio por defecto es el establecido. Para ello vamos a crear un fichero en el directorio puesto que si utilizamos el compando "pwd" para comprobar el directorio en el que nos encontramos nos devolvera "/" puesto que es el directorio raiz establecido.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/d0befced-88ab-4334-9a3f-72ab6f1f03a5)

Como podemos comprobar, el usuario se encuentra por defecto en la ruta /home/ftp y, adicionalmente, podemos comprobar que el usuario no puede cambiar de carpeta hacia arriba usando "cd ..".

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/3523d05c-1390-4036-8562-4416ddffc598)

Comprobamos así que el usuario permanece en el directorio raiz.

2. No se permitirá subir ni eliminar nada de la carpeta ftp

Para restringir dichas acciones en la carpeta ftp, vamos a modificar el archivo proftpd.conf, añadiendo la directiva "Directory" y configurandola de la siguiente manera:

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/e1fc0c28-4221-4612-98c7-1527221af40e)

Para comprobarlo, vamos a iniciar sesión con un usuario e intentaremos subir algún archivo o aliminar uno existente.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/60de564e-7b41-45d8-abc5-be577578f5ef)

3. Configura el acceso mediante usuario anónimo

Para configurar el acceso mediante usuario anónimo, primero tenemos que crear un usuario del sistema que será el usuario con el que los usuarios entraran al sistema de archivos. En mi caso he creado uno que se llama "anonimo" utilizando "useradd".
Una vez creado, en el fichero de configuración, vamos a definir una directiva de la siguiente manera:

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/7f44a77c-3c6f-4df9-9b2c-4c8d74b57788)

Ahora podremos iniciar sesión como usuario anónimo con cualquiera de los alias definidos.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/e6b58a09-fba8-48b1-b3ff-bf8c9f0e21bc)


4. Permite que el usuario anónimo pueda escribir si accede desde la red 10.6.0.x

Para conseguir esto, vamos a la directiva "Anonymous" y dentro de "LimitWrite" escribimos lo siguiente:

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/638289a9-84f2-4297-9d89-5b49e7006c59)


En mi caso voy a utilizar la 10.4.0.x porque es la que puedo utilizar desde mi máquina.

Con esto, todos los usuarios anonimos que accedan desde dicha red podrán hacer trabajos de escritura.


