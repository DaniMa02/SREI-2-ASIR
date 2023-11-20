# Servidores Web

### Instalación del servidor web apache. Usaremos dos dominios mediante el archivo hosts: centro.intranet y departamentos.centro.intranet. El primero servirá el contenido mediante wordpress y el segundo una aplicación en python.
Primero que nada, para instalar apache en nuestro sistema, buscaremos actualizaciones para comprobar que los archivos del sistema se encuentran actualizados. Para ello usaremos apt update y tras eso apt upgrade (nos pedira confirmación).
![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/c91f0db6-6250-445b-b57c-07912b2e1786)
![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/7db8a2f2-b7b3-4377-8aa4-cf60478908e3)

Una vez descargadas las actualizaciones, descargaremos apache con el comando apt install apache2
![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/59dae303-853a-41b4-9a40-4b391df662a7)
En mi caso ya lo tengo instalado y aparece que ya tengo la última versión.
Para configurar los dos dominios accederemos al archivo hosts y lo editamos, cambiando las ip de localhost para que correspondan con los dominios mencionados, quedando de la siguiente manera:
![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/b7cdb0b6-86ec-427c-b466-55d4bb79f0e7)
En mi caso usare el 127.0.0.1 para centro.intranet y 127.0.1.1 para departamentos.centro.intranet.


### Activar los módulos necesarios para ejecutar php y acceder a mysql.
### Instala y configura wordpress.
### Activar el módulo “wsgi” para permitir la ejecución de aplicaciones Python.
### Crea y despliega una pequeña aplicación python para comprobar que funciona correctamente.
### Adicionalmente protegeremos el acceso a la aplicación python mediante autenticación.
### Instala y configura awstat.
### Instala un segundo servidor de tu elección (nginx, lighttpd) bajo el dominio “servidor2.centro.intranet”. Debes configurarlo para que sirva en el puerto 8080 y haz los cambios necesarios para ejecutar php. Instala phpmyadmin.
