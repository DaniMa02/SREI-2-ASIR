# Servidores Web

### Instalación del servidor web apache. Usaremos dos dominios mediante el archivo hosts: centro.intranet y departamentos.centro.intranet. El primero servirá el contenido mediante wordpress y el segundo una aplicación en python.
Primero que nada, para instalar apache en nuestro sistema, buscaremos actualizaciones para comprobar que los archivos del sistema se encuentran actualizados. Para ello usaremos apt update y tras eso apt upgrade (nos pedira confirmación).
![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/c91f0db6-6250-445b-b57c-07912b2e1786)
![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/7db8a2f2-b7b3-4377-8aa4-cf60478908e3)

Una vez descargadas las actualizaciones, descargaremos apache con el comando apt install apache2
![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/59dae303-853a-41b4-9a40-4b391df662a7)
En mi caso ya lo tengo instalado y aparece que ya tengo la última versión.  

Primero crearemos sus respectivas carpetas y páginas principales. Para ello accedemos a /var/www y creamos las dos carpetas y dentro sus respectivos index.
![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/fa7180e3-3755-45c5-b2b7-1983f1031103)
![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/6ad10bfe-c463-4349-bccd-4ca7126cd5c0)
![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/39e24f1a-1d7b-4d3a-830b-7b4dc91f7d24)
Después de crear sus respectivos sitios, tendremos que crear los archivos de configuración de dichos sitios.
![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/2687b153-aa94-4ded-b459-df77282dfadc)
![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/6d1d7179-c681-45d1-ade4-54e627281a5f)

Ahora damos permisos a las carpetas para que apache pueda acceder a ellas y pueda abrir el archivo index.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/8945e739-90ac-4a89-9c77-2569bd860227)

Una vez tiene permisos vamos a habilitar los VirtualHosts con a2ensite y el nombre del dominio y reiniciando apache para que los cambios se apliquen.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/954835ce-365a-4d50-b420-d3b1420c62cc)

Por último vamos a configurar las IPs de los dominios en el archivo de hosts
![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/b7cdb0b6-86ec-427c-b466-55d4bb79f0e7)

En mi caso usare el 127.0.0.1 para centro.intranet y 127.0.1.1 para departamentos.centro.intranet.
Una vez hecho todo, comprobamos que ambas direcciones funcionen si intentamos acceder a ellas.
![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/d37c1bcc-48a5-431b-986c-1285babcc1bb)
![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/4fb8b884-08d0-441a-a74a-473df91b352f)


### Activar los módulos necesarios para ejecutar php y acceder a mysql.

Para instalar MySQL usamos el siguientes comando:
sudo apt install mysql-server
![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/1bc03a28-2a84-48a5-91b7-fa876776fc9b)


Para comprobar que funciona probamos a iniciar sesión con el comando sudo mysql
![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/b59ce719-a7d5-4aa1-8790-b1747f45bd54)

Ahora, para instalar PHP usamos el siguiente comando para instalar las librerias necesarias:
sudo apt install php libapache2-mod-php php-mysql, en caso de que no encuentre la librería, realizaremos primero un apt update y un apt upgrade.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/fb0523dc-5197-4a08-8950-742f8ef59c3f)

Una vez instalado, para comprobar que así ha sucedido y la versión que se ha instalado usamos el comando php -v.
![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/e1598a1f-4101-4d58-9cd9-05a4aeb94890)


### Instala y configura wordpress.

Para instalar y configurar wordpress lo primero que necesitaremos es crear una base de datos, para ello entraremos a mysql como usuario root con el siguiente comando:

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/7ded5977-cc79-4098-bef9-3fd907f6a3be)

Una vez hayamos iniciado sesión, crearemos una base de datos con el siguiente comando:
CREATE DATABASE centrointranet DEFAULT CHARACTER SET utf8 COLLATE utf8_unicode_ci;
![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/b87e2ad6-ba8a-48db-bd6b-a70e982d8f9c)

Lo siguiente será crear el usuario con el que realizaremos operaciones en nuestra base de datos e iniciaremos sesión con él en la base de datos.
![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/21e03c96-ca71-4e71-b430-6bb931b2d75a)

Y le otorgamos acceso completo a la base de datos.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/bab0e1d6-6178-40e5-a1b9-8c8b6a1237d4)

Ahora recargamos mysql para que los cambios surtan efecto y la cerramos.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/1fc7629f-aca0-4838-bdf2-73e78c05c492)

Ahora vamos a instalar extensiones adicionales de PHP.
![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/3255228d-709d-4323-a568-7bef38e2093c)

Y reiniciamos apache con service apache2 restart.

Una vez instalados dichos modulos vamos a cambiar la configuración de apache para permitir reemplazos y reescrituras .htacces. Para ello, abriremos el archivo de configuración de apache y configuramos la directiva AllowOverride para permitir que apache lea los ficheros de tipo .htaccess.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/de62899f-ff7d-44b5-b020-d01d763d014e)

Ahora habilitamos el módulo de reescritura:

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/f62ef764-9ea2-4332-bbfc-137e7fb76436)

Y habilitamos los cambios:
![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/dcc91447-ea15-40f3-a789-da387168421c)

Reiniciamos apache después de eso y lo siguiente que haremos será descargar WordPress.

Para descargar wordpress vamos a dirigirnos a un directorio que permita escritura, en mi caso usaré /tmp y ahí descargaré wordpress como un archivo comprimido, lo extraeré y crearé un archivo .htaccess ficticio.  
![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/e40d4093-3740-4a0a-b0e8-b6185d12069a)

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/aab2c6c9-f5a0-4acf-b5f9-baf1b8a3c2c4)

Ahora voy a copiar el archivo de configuración de muestra que se crea al instalar Wordpress a un fichero con el nombre que lee Wordpress por defecto.
![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/454e78ee-466b-4814-9400-bc0e812d1151)

Lo siguiente que voy a hacer es crear de actualización para que wordpress no tenga problemas de permisos al actualizarse por su cuenta. También moveré el contenido del directorio a nuestro directorio root de documentos.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/df828f61-d88b-4735-8626-7ddcab53c1ae)

Ahora voy a configurar dichos archivos para que sean propiedad del usuario y del grupo www-data y voy a cambiar los permisos de los directorios y archivos de WordPress para que pueda trabajar con ellos sin ningún problema.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/394fed29-29a1-4dfa-a3d5-77685ee5862d)

Una vez configurados, el siguiente paso será configurar el archivo de configuración de WordPress. Lo primero que tendremos que hacer será ajustar algunas claves secretras para proporcionar seguridad a nuestra instalación. Para ello, usaremos un generador seguro que proporciona WordPress y los sustituiremos en el archivo de configuración de Wordpress en la sección que corresponde.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/a1ead698-c847-4c3a-9520-eaa7a4430615)

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/636d07ef-24fe-4fb6-b3da-b17febef3c3c)

Ahora configuraremos los ajustes de conexión de la base de datos dentro del mismo archivo y el método que debe usar WordPress para escribir el sistema de archivos para que no solicite credenciales de FTP cuando realicemos algunas acciones.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/49a75427-8566-42ad-88b4-5ad4f1d0c3e9)

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/5a2dd347-216a-4c30-bb73-73b23580492b)

Una vez configurado guardamos el archivo y lo cerramos.

Ahora podremos acceder a nuestra página en WordPress desde la interfaz de usuario como de costumbre con las credenciales especificadas para modificar nuestra página a nuestro gusto.

Lo primero que nos pide WordPress al entrar por primera vez es el idioma, seleccionamos el que queramos.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/bfd927be-5664-497e-a44d-df4efd1c3995)

Lo siguiente será el nombre del sitio y las credenciales que queremos usar para iniciar sesión en el sitio.
![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/2071f51c-805d-4b17-88c4-0ef646146dc9)

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/77797078-357a-4d80-833b-703684011e4a)

Una vez todo está configurado, podemos comprobar que la página de WordPress se ha generado automáticamente buscando en internet el nombre de nuestro dominio.
![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/e4bf7751-9e6b-4856-9163-83805346bfae)

Ahora podremos crear y editar nuestra web como queramos.

### Activar el módulo “wsgi” para permitir la ejecución de aplicaciones Python.

Para activar dicho módulo lo instalaremos con el comando apt-get install libapache2-mod-wsgi-py3.
![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/612cd4db-20d3-4828-947a-cc80f6491aef)

Reiniciamos apache y ya funcionaría.

### Crea y despliega una pequeña aplicación python para comprobar que funciona correctamente.
Antes de poder crear y desplegar aplicaciones python, debemos crear y configurar los directorios y archivos necesarios.

Para ello, lo primero que vamos a hacer es crear la estructura de directorios para nuestra aplicación dentro de nuestro dominio.

En mi caso, voy a crear una carpeta en la que se almacenará nuestra aplicación Python que no será accesible por los usuarios y otra que será la que sirva la aplicación y por lo tanto será pública.
![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/5ff635fb-b519-459b-ba41-b93160bf8cc9)

La estructura de nuestro directorio del dominio quedaría de la siguiente manera

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/d3342b34-d200-4190-ac18-81ed7200bd29)

Ahora vamos a crear el controlador para la aplicación dentro de la carpeta.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/92cda629-b10e-455c-a596-01e9792b9e25)

Una vez creado, vamos a editar el archivo para hacer que maneje las peticiones del usuario llamando a los módulos que solicite el mismo.
![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/c46a70b0-02e2-41f9-a6b5-66f772df7558)

Ahora vamos a configurar el VirtualHost de la siguiente manera:


### Adicionalmente protegeremos el acceso a la aplicación python mediante autenticación.
### Instala y configura awstat.
### Instala un segundo servidor de tu elección (nginx, lighttpd) bajo el dominio “servidor2.centro.intranet”. Debes configurarlo para que sirva en el puerto 8080 y haz los cambios necesarios para ejecutar php. Instala phpmyadmin.
