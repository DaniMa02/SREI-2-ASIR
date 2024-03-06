## Subida de nota contenedor de Docker con servidor DNS en BIND9 y servidor web nginx

Antes que nada, vamos a crear una red a la cual pertenecerán ambos contenedores.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/cabd3cca-f9e0-4d38-9e77-350bc75c4688)

Ahora vamos a comenzar con la creación de nuestros contenedores.

Lo primero que tenemos que hacer es crear una carpeta en la que almacenaremos todos los archivos necesarios para la instalación de nuestro servidor bind, esta será la siguiente en mi caso:

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/cdb7b551-6ec7-4562-b99f-2410e344c75e)

Ahora vamos a hacer un pull al siguiente repositorio de github fuera de esta carpeta.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/798cdfaf-516f-4281-af72-ae7d2cab3ac9)

Una vez lo hemos clonado, vamos a comprobar que todos los ficheros se han descargado correctamente.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/09be4611-03c7-43ce-9c8b-de9a930067ef)

Ahora que tenemos todos los ficheros podemos proceder a la instalación del servidor DNS.

Lo primero que necesitamos hacer es copiar los ficheros de docker-compose y del DNS primario en la primera carpeta
que hemos creado.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/dc268aa6-8290-459e-b0cc-79e7941ac9a6)

Ahora vamos a editar el archivo de docker-compose para que la ruta del volumen coincida con la que hemos creado y
adicionalmente vamos a insertar una nueva linea con la que vamos a crear una red puesto que los dos servidores que
vamos a crear queremos que estén en la misma red.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/5a0acdb7-8831-452f-8e71-c9f8dbb57b68)

Ahora vamos a renombrar el fichero de zona y a configurarlo con el nombre e IPs que deseemos.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/bcc97856-c4e6-405e-ba17-1ecdd67c7701)

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/bf6c3565-2bca-4a4d-96eb-35dd941cd480)

Ahora vamos a configurar el fichero de zonas:

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/297b3b85-e17b-43cc-bc63-06ecafb2f922)

Una vez configurado podemos iniciar el contenedor.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/76892963-58c3-4e96-b5c1-7957bbca5363)

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/55b4b1db-3506-4c2c-96ee-cde99ca6cf72)

A la hora de iniciar el contenedor por primera vez el puerto 53 ya se estaba usando en mi máquina local por lo que he tenido que redireccionar la salida del puerto 53 del contenedor a la 56 de mi máquina para poder iniciarlo.

Ahora vamos a comprobar que funciona correctamente:

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/80354902-029b-4da6-90d4-545429e8da69)

Como podemos ver nos responde correctamente.

Con esto, el servidor DNS quedaría funcionando correctamente, ahora tenemos que crear el servidor nginx.

Para ello, vamos a crear otra carpeta en la que tendremos todos los archivos necesarios para el mismo.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/b60f9d5d-6d11-49d4-bf81-8ff3f4d02060)

Una vez creado vamos a descargar la imagen de nginx.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/a3ed6e07-1a78-43dc-931b-6a1bf34a19cf)

Y seguidamente vamos a crear y modificar el fichero docker-compose para iniciarlo.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/395c5b84-28fa-41ed-b82a-cee51365bdf1)

Ahora que está configurado, tenemos que crear la carpeta que hemos especificado en el volumen y añadir un fichero index.html
con algo de contenido para realizar posteriormente la comprobación del servicio nginx.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/11c0bd92-8b0a-4dfc-afb6-d245ce4f8faf)

Ahora que ya está creado podemos iniciar el contenedor.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/421cb1b5-c846-4896-837d-288de054b078)

Y comprobaremos que sirve el contenido que esperamos.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/7d11f34a-7d51-46bb-bc81-6e54e3a4962d)
