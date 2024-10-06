# Imagen
Es un archivo único que contiene todos los programas, librerías, dependencias y configuraciones necesarias para instalar y/o ejecutar una aplicación o un conjunto de aplicaciones.
![Imagen](img/imagen.PNG)

## ¿Cuál es la relación entre una imagen y un contenedor? 
La imagen es el modelo o plantilla, mientras que el contenedor es una instancia ejecutable de esa imagen. La imagen contiene todos los archivos y configuraciones necesarias, y el contenedor utiliza esa imagen para correr como un proceso aislado en el sistema.

![Imagen y contenedores](img/imagenContenedores.JPG)
## Comandos para imágenes

### Descargar imagen
Descarga la última versión de la imagen disponible en el registro de Docker.

```
docker pull <nombre imagen> 
```

Descarga una versión específica de la imagen, cada imagen tiene etiquetas (tags) para diferentes versiones.
Una imagen puede tener la etiqueta latest para representar la última versión, si no se especifica una etiqueta se hará referencia a la versión latest.

```
docker pull <nombre imagen>:<tag>
```

Descargar la imagen **hello-world**
![Imagen](img/hello.png)

**¿Qué es nginx?**
Nginx es un servidor web de código abierto que se utiliza para servir contenido estático, actuar como proxy inverso, balanceador de carga y servidor de caché. Es conocido por su alto rendimiento, baja utilización de recursos y capacidad para manejar múltiples conexiones concurrentes de manera eficiente.

Además de servir contenido estático (como HTML, CSS, e imágenes), Nginx también se utiliza comúnmente para distribuir tráfico entre servidores backend, mejorar la seguridad y acelerar la entrega de aplicaciones web.

Descargar la imagen  **nginx** en la versión **alpine**
![Imagen](img/alpine.png)

### Listar imágenes

```
docker images
```
![Imagen](img/images.png)

**Identificadores**

En Docker, se utilizan varios identificadores para diferenciar de manera única los elementos del sistema, como imágenes, contenedores, volúmenes y redes. Estos identificadores son generados automáticamente por Docker y son únicos dentro del contexto del sistema Docker en el que se encuentran. 

### Inspeccionar una imagen
El comando docker inspect se utiliza para obtener información detallada sobre un objeto de Docker específico, como un contenedor, una imagen, un volumen o una red.  Proporciona información en formato JSON sobre el objeto especificado.

```
docker inspect <nombre imagen>
docker inspect <nombre imagen>:<tag>
```

Inspeccionar la imagen hello-world 
![Imagen](img/inspect.png)

**¿Con qué algoritmo se está generando el ID de la imagen**
sha256

### Filtrar imágenes

```
docker images | grep <termino a buscar>

```

### Para eliminar una imagen
Eliminar permanentemente la imagen de tu sistema Docker.

```
docker rmi <nombre imagen>:<tag>
```

Eliminar la imagen hello-world 
![Imagen](img/elimi.png)

-f: Es la opción para forzar la eliminación de la imagen incluso si hay contenedores en ejecución que utilizan esa imagen.
Cuando eliminas una imagen Docker, Docker no elimina automáticamente los contenedores que se han creado a partir de esa imagen. Esto significa que, aunque hayas eliminado la imagen, el contenedor seguirá ejecutándose normalmente.  
**Considerar**
Eliminar una imagen no afecta a los contenedores que se han creado a partir de esa imagen, a menos que esos contenedores dependan de archivos o configuraciones específicas de la imagen eliminada. En ese caso, es posible que los contenedores se comporten de manera inesperada después de eliminar la imagen.
Es una buena práctica detener y eliminar todos los contenedores que dependan de una imagen antes de eliminar la imagen en sí.

```
docker rmi -f <nombre imagen>:<tag>
```

