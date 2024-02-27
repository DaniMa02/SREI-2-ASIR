# Proyecto 2º Trimestre

## Instalación de los módulos necesarios.

Antes de empezar a crear el script para automatizar la creación de los usuarios, directorios, hosts virtuales, subdominios DNS y base de datos con todos los permisos necesarios para que el usuario pueda gestionarla, vamos a instalar los módulos necesarios para que todo pueda funcionar correctamente.

Primero vamos a instalar apache, para ello usamos "apt-get install apache".

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/b3c0f193-840f-42ba-8160-ec2b0261756f)

Como podemos comprobar ya está instalado y en su versión más reciente.

Ahora vamos a instalar bind9 para poder gestionar nuestras zonas DNS y subzonas, para ello usamos "apt-get install bind9".

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/84362785-2457-4ca6-8262-1a4d9d34cfc7)

En este caso ya se encuentra en la versión más reciente.

Tenemos que configurar previamente las zonas y el dominio, para ello, vamos a editar el fichero "named.conf.local" de la siguiente manera:

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/6171023f-b51b-45ee-80c8-3913321fc4cf)

Ahora vamos a configurar la zona directa en el fichero especificado:

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/1a2b8a9b-5592-4633-98e6-f1afddf1a0cd)

Y por último la zona inversa:

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/1c235dc9-1d54-44d5-a317-1222aa912fcb)

Lo siguiente que necesitaremos es MySQL para crear la base de datos de la página web de nuestro cliente.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/55526a90-14a4-4af6-af1c-266b1711c579)

Este se encuentra en su versión más reciente .

También vamos a necesitar phpmyadmin para gestionar nuestra base de datos de manera gráfica.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/3b76f936-807a-473a-ad12-c9fd9bb3c84b)

Este módulo ya está instalado también.

Será necesario instalar Python, que al igual que el resto de módulos se encuentra instalado, adicionalmente, necesitamos instalar el módulo de python para apache.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/7c19c77c-e9fb-4a25-8bc5-e43f997dd5c5)

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/6ddb3f38-0b80-43f6-9ffd-83447aa902b9)

Como queremos que el usuario se conecte mediante SSH a nuestro servidor necesitaremos también ssh-cliente y ssh-server.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/99adf9d6-79fa-4517-a422-ee06d5236751)

Necesitaremos un cliente ftp para que el usuario pueda subir archivos, asique vamos a instalar proftpd para configurar conexiones seguras y filezilla para que el cliente acceda.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/40ec93d9-f3b7-4781-b2d8-66107f17c08b)

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/67ca2688-acfb-44f5-ac64-6c679e435061)

Necesitamos instalar openssl para la configuración de TLS.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/940e929c-9d92-4283-9d86-43e0f3131174)

Una vez instalado proftpd y openssl vamos a configurarlo para que el usuario acceda al servidor ftp mediante TLS.

Primero vamos a modificar el archivo de configuración general para indicar el nombre con el que los usuarios accederan y otras configuraciones necesarias.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/2ecef695-87b9-4e4e-ac03-cf58d6e49ccc)

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/90ae6444-dd2b-42da-b43c-d02402a3f114)

Una vez descomentada esta línea, vamos a editar el fichero modules.conf

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/9276d425-4822-41c0-b3fd-65507a1634cb)

Con esto activamos los modulos necesarios para el uso de TLS.

Ahora necesitamos instalar un paquete para que dichos módulos funcionen correctamente.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/58899c2d-3b51-4c2c-b5f7-5055375e3cad)

Y una vez instalado, modificamos el fichero tls.conf

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/bae6d2c7-37b8-4ac8-9c30-ea873f07ff24)

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/119af158-d802-462e-b0a9-8b03e282bf5a)

Guardamos el archivo y reiniciamos el servicio de proftpd.

Una vez reiniciado ahora tenemos que generar el certificado y la llave para TLS con openssl, para ello usamos el comando que viene en el archivo de configuración de tls.conf.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/f5fac688-4a95-4cb5-a5bf-48dc19a25f82)

En mi caso voy a hacer algunas modificaciones para que sea más seguro.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/b07702fd-b202-4cf8-ae8d-5773090fb854)

Una vez generado el certificado, podremos acceder al servidor ftp a traves de TLS.
Para comprobarlo usamos filezilla:

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/0598ef70-ff8e-447d-a894-f6f382df98ea)

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/23f9877e-72b9-45d2-be4a-1fccdac93f6f)

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/038f89c4-6b20-4e7a-a160-4d14673f9861)

Como vemos funciona correctamente.

También vamos a instalar servicios de correo como postfix, imap y pop3, para ello ejecutamos la siguiente orden:

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/3924d0fb-009f-47a5-a378-ddbbac22251f)

En mi caso se encuentran instalados ya dichos módulos.

Con los servicios de correo instalados solo restaria instalar php para que se puedan alojar páginas con php.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/a0bf3b9d-1918-4d99-b11d-84a6ad0c2156)


## Automatización de procesos

Una vez instalados todos los módulos que necesitaremos, vamos a automatizar los procesos a través de un script de linux para que el usuario solo tenga que proporcionar alguna información y el servidor se encargue del resto del proceso.

El script para automatizar todos los procesos es el siguiente:


``` bash
#!/bin/bash

# Creación del usuario

userCreation() {
#Variables necesarias:

	local USER=$1
	local PASSWORD=$2


#Crear usuario y su directorio home.

sudo useradd -m -d /home/$USER -s /bin/bash $USER

# Configuración de la contraseña del usuario

echo "$USER:$PASSWORD" | sudo chpasswd
echo "Has creado el usuario del sistema ${USER} y actualizado su contraseña."
}

domainCreation() {
	local USER=$1
	local IP=$2
	local DOMAIN="${USER}.marisma.local"
	local FORWARD_ZONE="/etc/bind/zones/db.marisma.local"
	local REVERSE_ZONE="/etc/bind/zones/db.192.168.195"
# Configuración subdominio

#Zona directa

echo "\$ORIGIN ${DOMAIN}." >> $FORWARD_ZONE
echo "@	IN	A	${IP}" >> $FORWARD_ZONE
echo "www	IN	A	${IP}" >> $FORWARD_ZONE

#Zona inversa
echo "${IP}		IN	PTR	${DOMAIN}." >> $REVERSE_ZONE

service apache2 reload > /dev/null
service bind9 reload > /dev/null
service proftpd reload > /dev/null
echo "Subdominio ${DOMAIN} creado correctamente."
}

# Configuración del host virtual en Apache

virtualHostCreation() {
# Variables locales
	local USER=$1
	local IP=$2
	local CONFIGFILE_DOMAIN="${USER}.marisma.local"
	local AVAILABLE_PATH="/etc/apache2/sites-available/${CONFIGFILE_DOMAIN}.conf"
	local DOCUMENT_ROOT="/var/www/html/${USER}"
	local PYTHON_DIRECTORY="${DOCUMENT_ROOT}/python-web"
	local PYTHON_APP="${PYTHON_DIRECTORY}/mypythonapp"
	local PYTHON_PUBLIC="${PYTHON_DIRECTORY}/public_html"
	local PY_CONTROLLER="${PYTHON_APP}/controller.py"


# Agregar el host a el archivo /etc/hosts

echo "${IP} ${CONFIGFILE_DOMAIN}" >> /etc/hosts
echo "127.0.0.1 ${CONFIGFILE_DOMAIN}" >> /etc/hosts
echo "El host se ha añadido al archivo de hosts."

# Creación estructura directorios

mkdir $DOCUMENT_ROOT
mkdir $PYTHON_DIRECTORY
mkdir $PYTHON_APP
mkdir $PYTHON_PUBLIC

# Creación del fichero python básico

touch $PY_CONTROLLER

echo "# -*- coding: utf-8 -*-

def application(environ, start_response):
        status = '200 ok'
        html = 'Esta es la página principal de la web del usuario ${USER} generada con python.'
        html = bytes(html,encoding= 'utf-8')
        response_header =  [('Content-type', 'text/html')]
        start_response(status, response_header)
        yield html" > ${PY_CONTROLLER}


# Crear el archivo de configuración del host virtual
echo "<VirtualHost *:80>
	ServerAdmin admin@$CONFIGFILE_DOMAIN
	ServerName $CONFIGFILE_DOMAIN
	WSGIScriptAlias / $PY_CONTROLLER
	DocumentRoot $PYTHON_PUBLIC
	<Directory />
		Options FollowSymLinks
		AllowOverride all
	</Directory>
	ErrorLog /var/log/apache2/$CONFIGFILE_DOMAIN.errorLog.log
	CustomLog /var/log/apache2/$CONFIGFILE_DOMAIN.customLog.log combined
</VirtualHost>" | sudo tee $AVAILABLE_PATH > /dev/null

# Verificar la configuración de Apache
apache2ctl configtest

# Habilitar el sitio y reiniciar Apache si la verificación es exitosa
if [ $? -eq 0 ]; then
    a2ensite $CONFIGFILE_DOMAIN > /dev/null
    systemctl restart apache2
    echo "Se ha creado y habilitado el host ${CONFIGFILE_DOMAIN}."
else
    echo "Hay errores en la configuración de apache. No se ha habilitado el host."
fi
}

dbCreation() {

	local USER=$1
	local PASSWORD=$2
# Configuración base de datos
mysql -u root -e "CREATE DATABASE ${USER};"
mysql -u root -e "CREATE USER '${USER}'@'localhost' IDENTIFIED BY  '${PASSWORD}';"
mysql -u root -e "GRANT ALL PRIVILEGES ON ${USER}.* TO '${USER}'@'localhost';"
mysql -u root -e "FLUSH PRIVILEGES;"

echo "Has creado la base de datos ${USER} y el usuario SQL ${USER} "
}



if [ $# -eq 3 ]; then
	userCreation "$1" "$2"
	domainCreation "$1" "$3"
	virtualHostCreation "$1" "$3"
	dbCreation "$1" "$2"
    else
    echo "Error: Debes proporcionar 3 argumentos en este orden: nombre, contraseña e IP."
    exit 1
fi
```





