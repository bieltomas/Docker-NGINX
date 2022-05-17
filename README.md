# Docker-NGINX

## Instalación

Buscaremos la imagen de NGINX en DockerHub.

![image](https://user-images.githubusercontent.com/91564872/168853450-5d55ffb4-7988-4879-8860-2fafaf764c37.png)

Como vemos en la imagen deberemos usar el comando `docker pull nginx` en la terminal para descargar dicha imagen.

![image](https://user-images.githubusercontent.com/91564872/168853647-355c03c2-8ff3-4b2c-9f8a-545467d6f066.png)

Luego usaremos `docker run --rm -d -p 8000:80 --name web nginx` en la terminal para iniciar nuestra imagen de NGINX.

![image](https://user-images.githubusercontent.com/91564872/168857608-f5c32c26-74c2-4434-91ee-1089943cb504.png)

Comprobaremos que se ha iniciado correctamente introduciendo `localhost:8000` en nuestro navegador.

![image](https://user-images.githubusercontent.com/91564872/168857843-f95e4d2c-6b7a-4158-9011-d72c7cc0c7b9.png)

## Configuración

Ahora pasaremos a configurar nuestro html para que se ejecute en nuestro servidor nginx. La ruta donde buscará nuestro html será en la carpeta de nginx original, pero para mayor comodidad crearemos otra y le introduciremos nuestro html.

![image](https://user-images.githubusercontent.com/91564872/168869686-ebefeb3f-43fe-4108-bf05-6a7d0adf1d73.png)

![image](https://user-images.githubusercontent.com/91564872/168869546-0ee658ad-60c6-4a52-8916-2bcac959fd89.png)

Guardaremos este codigo fuente dentro de la nueva carpeta con el nombre de index.html y ejecutaremos el siguiente comando:
`sudo docker run --rm -d -p 8000:80 --name web -v /home/ciber/Documentos/nginx/site-content:/usr/share/nginx/html nginx`
De esta manera pondremos en marcha el html en nuestro docker nginx.

![image](https://user-images.githubusercontent.com/91564872/168871499-ffcadec8-f19a-4b10-99e0-96218ace65f2.png)

Finalmente introducimos de nuevo `localhost:8000` en el navegdaor para corroborar su funcionamiento:

![image](https://user-images.githubusercontent.com/91564872/168871421-bc87380b-b564-4a65-9cae-e7e6aa7549c4.png)

Y podemos comprobar que funciona perfectamente
