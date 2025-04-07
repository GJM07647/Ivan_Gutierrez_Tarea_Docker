




**Iván Gutiérrez Raimundo**

**DAW 2º DISTANCIA   2024-2025**

**DESPLIEGUE**







# ACTIVIDAD EVALUABLE- 3

## EJERCICIO 3



[TOC]

##### **1.Creación del fichero `dockerfile`**

Configuramos el `dockerfile` con una imagen base de `php:7.4-apache` ,una carpeta externa `public_html` que será copiada en `/var/www/html` dentro del contenedor, en el puerto 8000.

![](C:\Users\Guty\Desktop\TAREA DOCKER\ejercicios\ejercicio3\imagenes ejercicio 3\0-creacion dockerfile.png)

Creamos dicha carpeta

![](C:\Users\Guty\Desktop\TAREA DOCKER\ejercicios\ejercicio3\imagenes ejercicio 3\1-creacion de carpetas.png)

Y los ficheros en su interior, `index.html`, `sytle.css` y el script `fecha.php`

![](C:\Users\Guty\Desktop\TAREA DOCKER\ejercicios\ejercicio3\imagenes ejercicio 3\2-carpeta html.png)

##### **2.Construimos la imagen**

`$ docker build -t ejercicio3 .`

![](C:\Users\Guty\Desktop\TAREA DOCKER\ejercicios\ejercicio3\imagenes ejercicio 3\3-construida la imagen.png)

Vemos la imagen en Docker desktop

![](C:\Users\Guty\Desktop\TAREA DOCKER\ejercicios\ejercicio3\imagenes ejercicio 3\4-construida la imagen2.png)



Ejecutamos la imagen para crear el contenedor en el puerto 8000:80

```bash
$ docker run -d -p 8000:80 --name ejercicio3 ejercicio3
```

![](C:\Users\Guty\Desktop\TAREA DOCKER\ejercicios\ejercicio3\imagenes ejercicio 3\5-arrancado el container.png)

Vemos el contenedor en Docker desktop:

![](C:\Users\Guty\Desktop\TAREA DOCKER\ejercicios\ejercicio3\imagenes ejercicio 3\6-arrancado el container.png)



##### **3. Acceso por navegador**

Acceso al navegador con la página `index.html`:

![](C:\Users\Guty\Desktop\TAREA DOCKER\ejercicios\ejercicio3\imagenes ejercicio 3\7-index funcionando.png)

Acceso con el script `fecha.php`:

![](C:\Users\Guty\Desktop\TAREA DOCKER\ejercicios\ejercicio3\imagenes ejercicio 3\8-php funcionando.png)

##### **4. Subida de imagen a Docker Hub**

En este punto me doy cuenta que si no pongo el tag con el autor no me deja subirlo al repositorio de `dockerhub` así que añado la etiqueta con este código:
`$ docker tag ejercicio3 ivangutierrezraimundo/ejercicio3:v1`

![](C:\Users\Guty\Desktop\TAREA DOCKER\ejercicios\ejercicio3\imagenes ejercicio 3\9.introduzco tag nombre.png)

Lo subo a Docker Hub con Docker desktop (`Push to Docker Hub`)

![](C:\Users\Guty\Desktop\TAREA DOCKER\ejercicios\ejercicio3\imagenes ejercicio 3\10-lo subo a dockerhub.png)

Imagen subida correctamente

![](C:\Users\Guty\Desktop\TAREA DOCKER\ejercicios\ejercicio3\imagenes ejercicio 3\11-imagen subida correctamente.png)

Borramos la imagen en el repositorio local con Docker desktop

![](C:\Users\Guty\Desktop\TAREA DOCKER\ejercicios\ejercicio3\imagenes ejercicio 3\12-borrado repositorio local.png)

##### **5.Descarga de imagen desde Docker Hub**

Descargamos la imagen del repositorio remoto al local (Pull)

![](C:\Users\Guty\Desktop\TAREA DOCKER\ejercicios\ejercicio3\imagenes ejercicio 3\13-hago pull de la imagen a mi repositorio.png)

##### **6. Nuevo contenedor en puerto `-p 1234:80`**

Ejecutamos la imagen para crear otro contenedor pero esta vez en el puerto 1234:80

```bash
$ docker run -d -p 1234:80 --name ejercicio3_puerto1234 ivangutierrezraimundo/ejercicio3:v1
```

![](C:\Users\Guty\Desktop\TAREA DOCKER\ejercicios\ejercicio3\imagenes ejercicio 3\14-cambio de puerto.png)

Contenedor creado

![](C:\Users\Guty\Desktop\TAREA DOCKER\ejercicios\ejercicio3\imagenes ejercicio 3\15-contenedor nuevo puerto creado.png)

Acceso al navegador con el `index.html` con el nuevo puerto

![](C:\Users\Guty\Desktop\TAREA DOCKER\ejercicios\ejercicio3\imagenes ejercicio 3\16-cambio de puerto navegador index.png)

Acceso del script `fecha.php` desde el otro puerto

![](C:\Users\Guty\Desktop\TAREA DOCKER\ejercicios\ejercicio3\imagenes ejercicio 3\17-cambio de pueto navegador php.png)

##### **7. Borrado del contenedor**

![](C:\Users\Guty\Desktop\TAREA DOCKER\ejercicios\ejercicio3\imagenes ejercicio 3\18-borrado contenedor.png)



