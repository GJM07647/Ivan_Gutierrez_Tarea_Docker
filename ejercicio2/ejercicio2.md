




**Iván Gutiérrez Raimundo**

**DAW 2º DISTANCIA   2024-2025**

**DESPLIEGUE**







# ACTIVIDAD EVALUABLE- 3

## EJERCICIO 2



[TOC]

##### **1.Fichero `compose.yaml`**

Ponemos tres servicios ,la propia aplicación `filebrowser` (son su imagen, su puerto, volúmenes usados , variables de entorno necesarias y la opción `restart` para reiniciarse en caso de problemas), una base de datos `mariaDB` (donde incluimos variables de entorno para la contraseña y nombre , y su propio volumen para persistir los datos), y un servidor `nginx`. Por último añadimos los volúmenes usados anteriormente.

![](./imagenes2/1-docker compose yaml.png)



Ejecutamos el compose creado con el comando :

```bash
$ docker compose up -d
```



![](./imagenes2/2-ejecutando compose descarga y run.png)

Vemos que se creo el multicontenedor compose desde Docker desktop

![](./imagenes2/3-compose creado .png)



Vemos los contenedores que lo componen :

![](./imagenes2/4-contenedores creados.png)

##### **2.Aplicación funcionando **

![](./imagenes2/5-entrada a aplicacion.png)

![](./imagenes2/6-aplicacion.png)



Vamos a realizar un par de operaciones para luego ver en las carpetas de los volúmenes si se registraron correctamente, primero subimos un fichero y luego cambiamos el idioma  a español.

![](./imagenes2/7-fichero subido.png)

![](./imagenes2/8-lenguaje español.png)

![](./imagenes2/9-español 2.png)



##### **3.Carpetas de los volúmenes**

Vemos las dos carpetas creadas para guardar los volúmenes y sus datos 

![](./imagenes2/10-carpetas donde se acumulan datos.png)

Aquí es donde guarda los datos de configuración de la aplicación,como el cambio del idioma

![](./imagenes2/11-config dir.png)

Aquí es donde guarda los datos como  los ficheros

![](./imagenes2/12-data dir.png)

Podemos ver los volúmenes creados con este comando :

```bash
$ docker volume ls
```

![](./imagenes2/13-volumenes de bd y nginx.png)

NOTA: Al finalizar el ejercicio me doy cuenta que no es recomendable guardar los volúmenes en una ruta local con subcarpetas ya que si quiero exportar el proyecto en otro equipo tendría que crear todo ese árbol de subcarpetas, mejor configurar el `compose.yaml` con una ruta para los volúmenes mas sencilla como: `C:/` o `C:/volumenes`, en principio lo hice así para que quedaran guardados en la carpeta del ejercicio.

##### **4. Funcionamiento de la aplicación**

Filebrowser es una aplicación de gestión de archivos, de manera grafica e intuitiva, permite crear, eliminar, renombrar, previsualizar y editar archivos y carpetas. También puedes subir y descargar archivos fácilmente.
Su propósito principal es facilitar la gestión de archivos y carpetas desde un navegador y además al ser una herramienta basada en la web, puedes acceder a tus archivos desde cualquier lugar con conexión a internet.
Permite la creación de múltiples usuarios y cada usuario puede tener su propio directorio.

