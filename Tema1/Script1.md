### Crea un script que añada un puerto de escucha en el fichero de configuración de Apache. El puerto se recibirá como parámetro en la llamada y se comprobará que no esté ya presente en el fichero de configuración.

``` bash
#!/bin/bash 
if [ $# -eq 0 ];
then echo "La sintaxis del script es: bash script NUM_PUERTO" 
else
grep "Listen $1" /etc/apache2/ports.conf >/dev/null
if [ $? -eq 0 ];
then echo "El puerto $1 ya existe" else echo "Listen $1" >>/etc/apache2/ports.conf | echo El puerto ha sido añadido
fi
fi
```
