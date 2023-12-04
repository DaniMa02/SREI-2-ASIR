### Crea un script que añada un nombre de dominio y una ip al fichero host. Debemos comprobar que no existe dicho dominio
``` bash
#!/bin/bash

if [ $# -eq 2 ]; then

grep "$1" /etc/hosts>/dev/null if [ $? -eq 0 ];

then echo "$1 o $2 ya existen"

else echo "$1 $2">>/etc/hosts | echo "Añadidos con exito"

fi

else

echo "La sintaxis es erronea, introduzca IP...dominio"

fi
```
