# ProFTPd - TLS

## Lee el artículo anterior y configura proftp para acceso seguro mediante TLS

Para configurar TLS primero necesitaremos instalar openssl para generar un certificado SSL.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/b24ac227-a25d-43a7-b96f-87c6b01a90ea)

En mi caso ya está instalado asique vamos a generar el certificado de la siguiente manera:

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/e6b5904c-2053-4a9b-bf1e-7120529543e1)

Con esto ya habremos generado el certificado.

Ahora vamos a dar los permisos necesarios a los ficheros generados, a la llave, solo le daremos permisos al usuario root porque solo debe ser leida por el servidor y no debe conocerse por los usuarios que accedan al mismo, en cambio, el certificado debe ser accesible por los usuarios que accedan al servidor.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/cf345151-0696-4277-adb2-a6fc67e5f33e)

Ahora podemos configurar ProFTPD para que use SSL, para ello vamos a modificar el fichero de configuración de ProFTPd.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/cebed643-f02f-4e5e-9058-789f90bcdbed)

Una vez descomentada esta linea guardamos el fichero.

Ahora tenemos que modificar el fichero "tls.conf".

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/08d0f58b-2482-4a68-b3f2-c6eeedc1fe79)

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/8f6b2a26-fea9-4c18-b3bf-e26b485b0af1)

Una vez modificado el fichero tls.conf tendremos que descomentar algunas lineas de "modules.conf".

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/6f660e14-9390-4c5b-9580-9a6c89c6eca5)

Y por último instalar un paquete adiccional de proftpd para que este pueda arrancar con dichos módulos activos.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/c75b13a5-a3f3-482a-a9fe-5e49d40a2f37)

Con esto quedaría configurado por completo.

## Crea un usuario del sistema

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/2ef578a7-0728-4b3b-8b9e-78dbbe625188)

## Instala filezilla

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/5065d556-1a1e-41bd-8c11-ae6127c6a541)

## Configura filezilla para usar una conexión TLS y comprueba que funciona correctamente.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/bad8c3ee-5873-4da2-a798-1457eead748f)

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/eaf9bb1d-33b6-47cc-ae54-83aaa29e57e8)

Como podemos comprobar podemos establecer conexión mediante TLS.
