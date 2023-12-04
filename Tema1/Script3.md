### Crea un script que nos permita crear una página web con un título, una cabecera y un mensaje

``` bash
#!/bin/bash
if [ $# -lt 4 ]; then
echo "El uso correcto del script es <nombre_fichero> <título> <cabecera> <mensaje>"
else
nombre_fichero="$1"
titulo="$2"
cabecera="<h1>$3<h1>"
mensaje="<p>$4</p>"
pagina="<!DOCTYPE html>
<html>
<head>
<title>$titulo</title>
</head>
<body>
$cabecera
$mensaje
</body>
</html>
"
echo "$pagina">"$nombre_fichero"
echo "Se ha creado la página web $nombre_fichero correctamente"
fi
```
