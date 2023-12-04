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
