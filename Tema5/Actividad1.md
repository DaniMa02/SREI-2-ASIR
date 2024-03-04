# Instalación y configuración de docker

Para instalar docker tendremos que utilizar las siguientes ordenes:
```
sudo apt update
```
```
sudo apt install apt-transport-https ca-certificates curl gnupg
```
```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker.gpg
```
```
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu jammy stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```
```
sudo apt update
```
```
sudo apt install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

Ahora comprobamos que funciona correctamente:

```
sudo systemctl status docker
```

![image](https://github.com/DaniMa02/SREI-2-ASIR/assets/47284389/19db0a3f-c1d5-4350-a77f-99dfe2b3db7b)
