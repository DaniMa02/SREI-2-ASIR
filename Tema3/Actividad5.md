# ProFTPd - VirtualHost

## 1. Crea un directorio para el usuario virtual “informatica” en /home/ftp/informatica

Para esto usaremos el comando "mkdir".

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/b0092530-5a1e-4f83-8fdf-13fec84f0fc1)


## 2. Cambia el propietario del directorio creado anteriormente mediante “chown” al usuario ftp

Para cambiar el propietario a ftp usamos "chown ftp:root /ruta/del/archivo".

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/e0084da1-ac80-4d7b-84c1-9ac0f49744a0)

## 3. Crea un usuario virtual “informatica” mediante “ftpasswd”

Para crear el usuario virtual lo primero que tenemos que hacer es crear las carpetas del mismo puesto que como no serán usuarios del sistema no tendrán un directorio en /home.

Para ello los crearemos en el directorio /srv/"usuario".

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/99932a07-4b03-4588-886d-af113415797a)

Ahora vamos a modificar el propietario y los permisos.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/d765e12a-cb5e-4fc6-bda8-712f9b3edc5b)

Ahora vamos a crear el fichero donde se almacenarán los usuarios virtuales.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/5ca60304-b4e6-41bf-a06f-753a574d6d1e)

Ahora podemos crear el usuario usando el comando "ftpasswd" de la siguiente manera:

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/fb3aa6c9-61c6-4aea-988c-4da108e8dfdf)


## 4. Haz los cambios necesarios en el fichero de configuración de proftpd

Una vez creado el usuario virtual lo que tenemos que hacer es modificar algunos parametros del archivo de configuración de proftpd.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/aa073748-9682-4c6e-98dd-f4d88c7e5c8b)

Con la primera línea le decimos que incluya el archivo de configuración de módulos, con la segunda especificamos el archivo que se utilizará para autenticar a los usuarios, ya que no son usuarios de sistema y por lo tanto no se encontrarán en el fichero "passwd" del sistema. Por última, y debido a que son usuarios virtuales que no tendrán una shell habilitada, cambiamos el valor de esa opción para que no sea un requisito para entrar.

Tendremos que reiniciar el servicio para que se apliquen los cambios.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/9c7ed5e1-0039-4eb0-acb4-bf7e6644e4e0)

Como podemos ver el usuario informatica existe y puede acceder.

## 5. Crea un sitio virtual para “informatica.marisma.local”

Para crear un sitio virtual, vamos a modificar primero el fichero de configuración para que incluya el de los host virtuales.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/e694e7aa-93a6-4012-8a0d-ff93ac77a76c)

Ahora vamos a modificar el archivo de configuración de virtuals.conf para añadir el host virtual.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/74e6371c-c283-4e04-ae5d-a0e02285b329)

De esta manera quedará configurado el host. Tendremos que reiniciar el servicio.


## 6. Modifica el fichero de zona del DNS para que resuelva adecuadamente

Como estamos entrando desde local, no tenemos que modificar el fichero de zona del DNS para que resuelva si no el fichero de hosts.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/d0df7554-d2b1-48f4-a21d-f83d799d9b63)

Ahora podemos iniciar sesión en el servidor que acabamos configurar y vemos el contenido para comprobar que efectivamente nos encontramos en el directorio que hemos configurado como root.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/aa8b1e13-a749-46a8-825f-7ce9a74bea4c)

