# Proyecto 2º Trimestre

## Instalación de los módulos necesarios.

Antes de empezar a crear el script para automatizar la creación de los usuarios, directorios, hosts virtuales, subdominios DNS y base de datos con todos los permisos necesarios para que el usuario pueda gestionarla, vamos a instalar los módulos necesarios para que todo pueda funcionar correctamente.

Primero vamos a instalar apache, para ello usamos "apt-get install apache".

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/b3c0f193-840f-42ba-8160-ec2b0261756f)

Como podemos comprobar ya está instalado y en su versión más reciente.

Ahora vamos a instalar bind9 para poder gestionar nuestras zonas DNS y subzonas, para ello usamos "apt-get install bind9".

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/84362785-2457-4ca6-8262-1a4d9d34cfc7)

En este caso ya se encuentra en la versión más reciente.

Lo siguiente que necesitaremos es MySQL para crear la base de datos de la página web de nuestro cliente.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/55526a90-14a4-4af6-af1c-266b1711c579)

Este se encuentra en su versión más reciente .

También vamos a necesitar phpmyadmin para gestionar nuestra base de datos de manera gráfica.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/3b76f936-807a-473a-ad12-c9fd9bb3c84b)

Este módulo ya está instalado también.

Será necesario instalar Python, que al igual que el resto de módulos se encuentra instalado.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/7c19c77c-e9fb-4a25-8bc5-e43f997dd5c5)

Como queremos que el usuario se conecte mediante SSH a nuestro servidor necesitaremos también ssh-cliente y ssh-server.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/99adf9d6-79fa-4517-a422-ee06d5236751)

Necesitaremos un cliente ftp para que el usuario pueda subir archivos.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/40ec93d9-f3b7-4781-b2d8-66107f17c08b)

Necesitamos instalar openssl para la configuración de TLS.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/940e929c-9d92-4283-9d86-43e0f3131174)

## Automatización de procesos

Una vez instalados todos los módulos que necesitaremos, vamos a automatizar los procesos para que el usuario solo tenga que proporcionar alguna información y el servidor se encargue del resto del proceso.





