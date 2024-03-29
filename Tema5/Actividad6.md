## Docker #6

#### Ejemplo 1: Construcción de imágenes con una página estática

Primero creamos la estructura de directorios:

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/586856a0-7b6e-415a-9161-21674602b811)

Ahora añadimos al Dockerfile el siguiente contenido:

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/e773a040-1b0b-4295-8a33-f96b39fda3d3)

Y agregamos al directorio public_html un fichero con algo de contenido:

Guardamos el fichero.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/e4386f54-9616-4f05-b73a-bd90119d25c8)

Ahora añadimos contenido a la carpeta public_html para realizar la prueba de que funciona posteriormente:

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/6349ffa3-be55-4fb7-83f9-c9eb1208f7d7)

Y ahora creamos la imagen:

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/52c835f5-6a7e-4f25-9345-7742b6fec580)

Ahora creamos un contenedor de dicha imagen:

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/b6600b4b-7837-447f-9f20-e717d7875a79)

El error que aparece es debido a que tengo un contenedor que está ocupando el puerto especificado, simplemente habrá
que parar el contenedor que lo ocupa para iniciar este.

Cuando esté iniciado accedemos a localhost por el puerto 80 y deberiamos ver el contenido del fichero HTML que hemos creado.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/cd1bc247-40ed-4300-8ef8-f2fa46f79b46)


#### Ejemplo 2: Construcción de imágenes con una aplicación PHP

Lo primero que necesitamos es crear el fichero Dockerfile y una carpeta que contendrá la aplicación PHP.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/46a6cf50-d38e-4198-88ff-a9ac37b7aabe)

Ahora añadimos el siguiente contenido a nuestro fichero Dockerfile:

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/131b0e87-5ac4-4d29-9a9a-73bb94adeb69)

Y ahora crearemos un fichero PHP para comprobar que funciona:

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/36b6e95b-113d-46f4-ab64-d5a572a87525)

Una vez creado, vamos a crear la imagen:

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/0bc1f4c8-66b0-43a3-a7e2-8966b66d7e15)

Y ahora crearemos el contenedor de Docker.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/f53bfd30-836f-44bc-8c7d-54d3a914b2ef)

Ahora accedemos a localhost y comprobamos que efectivamente se muestra el contenido de nuestra app.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/bc315b76-b527-464f-af66-a8daa21cad78)

#### Ejemplo 3: Construcción de imágenes con una una aplicación Python

Lo primero que vamos a hacer es crear la estructura de directorio con nuestra carpeta y nuestro fichero Dockerfile

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/25749a2c-e0cb-4fa9-b6d5-13316d137411)

Ahora vamos a copiar el siguiente contenido en nuestro Dockerfile.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/acbcffa5-308d-4ba6-bc7b-981e4624ee5e)

Además vamos a añadir en nuestra carpeta app un fichero "requirements.txt" que contendrá los módulos que nuestro
Dockerfile va a instalar en la línea 5.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/acd2ad4b-b942-4290-9488-49b7d3e256d2)

Y también crearemos la aplicación python que nos mostrará el contenido:

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/6b08c272-d13d-402c-bcb0-bb42d41a5a5b)

Adicionalmente vamos a necesitar crear una carpeta dentro del directorio app y añadir el fichero index.html necesario
para la aplicación python.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/a0a2003b-e725-4fc6-89ac-f5627b695cd9)

Si se ha hecho todo correctamente, vamos a poder crear la imagen y posteriormente un contenedor.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/2064d6ab-ee83-48b6-8602-e75ef7eb076d)

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/d9000188-91c4-4a89-bd15-c96cbf26ff4c)

Ahora comprobamos que la página sirve algún tipo de contenido.

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/a286bb77-c768-4519-a509-7e3c2b947d18)

En mi caso, podemos ver que sirve contenido y que está funcionando aunque no sirve el contenido que debería, esto se debe
a que el ejemplo del ejercicio está preparado para funcionar con una plantilla de jinja2 y al no cargar dicha plantilla
en el fichero html, devuelve que no la encuentra pero si que sirve contenido, por lo que funciona.

Adicionalmente he probado con el código esperado por la aplicación que toma la plantilla de jinja2 de un enlace y el resultado es el mismo al anterior. Esto seguramente se deba a que la plantilla 
ya no se encuentra en esa dirección y por lo tanto no es posible cargarla desde el enlace.
```
<!doctype html>
<html lang="en" class="no-js">
<head>
    <meta charset="utf-8">
    <meta http-equiv="x-ua-compatible" content="ie=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <link rel="canonical" href="https://html5-templates.com/" />
    <title>Bootstrap Template With Sticky Menu</title>
    <meta name="description" content="Simplified Bootstrap template with sticky menu">
    <link href="{{url_for('static', filename='css/bootstrap.min.css')}}"  rel="stylesheet">
    <link href="{{url_for('static', filename='css/sticky-menu.css')}}" rel="stylesheet">
</head>
<body id="page-top" data-spy="scroll" data-target=".navbar-fixed-top">
    <nav class="navbar navbar-default navbar-fixed-top" role="navigation">
        <div class="container">
            <div class="navbar-header page-scroll">
                <button type="button" class="navbar-toggle" data-toggle="collapse" data-target=".navbar-ex1-collapse">
                    <span class="sr-only">Toggle menu</span>
                    <span class="icon-bar"></span>
                    <span class="icon-bar"></span>
                    <span class="icon-bar"></span>
                </button>
                <a class="navbar-brand page-scroll" href="#page-top">Welcome</a>
            </div>

            <div class="collapse navbar-collapse navbar-ex1-collapse">
                <ul class="nav navbar-nav">
                    <li class="hidden">
                        <a class="page-scroll" href="#page-top"></a>
                    </li>
                    <li>
                        <a class="page-scroll" href="#about">About</a>
                    </li>
                    <li>
                        <a class="page-scroll" href="#whatwedo">What We Do</a>
                    </li>
                    <li>
                        <a class="page-scroll" href="#contact">Contact</a>
                    </li>
                </ul>
            </div>	<!-- .navbar-collapse -->
        </div>		<!-- .container -->
    </nav>
    <!-- Welcome   -->
    <section id="welcome" class="welcome-section">
        <div class="container">
            <div class="row">
                <div class="col-lg-12">
                    <h1>Curso: Introducción Docker</h1>
                    <h2>Aplicación escrita en Python</h2>
                    <p>Fecha: <strong>{{hoy.day}}/{{hoy.month}}/{{hoy.year}}</strong></p>
                    <p>hostname: <strong>{{server}}</strong></p>
                    <a class="btn btn-primary page-scroll" href="#about">Click To Scroll Down!</a>
                </div>
            </div>
        </div>
    </section>

    <!-- About -->
    <section id="about" class="about-section">
        <div class="container">
            <div class="row">
                <div class="col-lg-12">
                    <h1>About</h1>
                </div>
            </div>
        </div>
    </section>

    <!-- What we do Section -->
    <section id="whatwedo" class="whatwedo-section">
        <div class="container">
            <div class="row">
                <div class="col-lg-12">
                    <h1>What We Do</h1>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="contact-section">
        <div class="container">
            <div class="row">
                <div class="col-lg-12">
                    <h1>Contact Section</h1>
                </div>
            </div>
        </div>
    </section>
	
	<a id="back2Top" title="Back to top" href="#">&#10148;</a>
	
    <!-- jQuery -->
    <script src="{{url_for('static', filename='js/jquery.js')}}"></script>

    <!-- Bootstrap Core JavaScript -->
    <script src="{{url_for('static', filename='js/bootstrap.min.js')}}"></script>

    <!-- Scrolling Nav JavaScript -->
    <script src="{{url_for('static', filename='js/jquery.easing.min.js')}}"></script>
    <script src="{{url_for('static', filename='js/sticky-menu.js')}}"></script>

</body>

</html>
```
