




**Iván Gutiérrez Raimundo**

**DAW 2º DISTANCIA   2024-2025**

**DESPLIEGUE**







# ACTIVIDAD EVALUABLE- 3

## EJERCICIO 1



[TOC]


##### **1.Crear una red Bridge**

Primero descargo el plugin de `PortNavigator`  para poder configurar y crear redes desde Docker Desktop

![](./imagenes1/1-Plugin portnavigator.png)



Creo la red : `redej1` con el ese plugin en el botón `Add Network`

![](C:\Users\Guty\Desktop\TAREA DOCKER\ejercicios\ejercicio1\imagenes ejercicio 1\2-red creada.png)



##### **2.Crea un contenedor con una imagen de `mariaDB` que estará en la red `redej1` ,accesible a través del puerto 3306. **

Bajamos la imagen y la ejecutamos directamente con run para crear el contenedor directamente.

![](C:\Users\Guty\Desktop\TAREA DOCKER\ejercicios\ejercicio1\imagenes ejercicio 1\3-descarga imagen y crear contenedor.png)



Docker nos da la opción antes de ejecutarla de hacer algunas configuraciones, le ponemos el nombre al contenedor y el puerto, y  mediante variables de entorno le ponemos el nombre a la base de datos , una contraseña `root` que es obligatoria, un usuario y su contraseña.

![](C:\Users\Guty\Desktop\TAREA DOCKER\ejercicios\ejercicio1\imagenes ejercicio 1\4-CONF BD 1.png)



![](C:\Users\Guty\Desktop\TAREA DOCKER\ejercicios\ejercicio1\imagenes ejercicio 1\5-CONF BD 2.png)



Conectamos el contenedor de la base datos a la red `redej1` 

![](C:\Users\Guty\Desktop\TAREA DOCKER\ejercicios\ejercicio1\imagenes ejercicio 1\6-conectar container bd a red.png)



Vemos que la conexión esta creada y conectada. 

![](C:\Users\Guty\Desktop\TAREA DOCKER\ejercicios\ejercicio1\imagenes ejercicio 1\7-conexion creada.png)

Entramos a la base de datos 

```
$docker exec -it miMariaDB bash
```

 y creamos los módulos:

![](C:\Users\Guty\Desktop\TAREA DOCKER\ejercicios\ejercicio1\imagenes ejercicio 1\8-CREAR BD MODULOS.png)



Vemos los módulos de la base de datos creados:

![](C:\Users\Guty\Desktop\TAREA DOCKER\ejercicios\ejercicio1\imagenes ejercicio 1\9.ver modulos de la base de datos.png)

##### **3.Creamos un contenedor con `phpMyAdmin` que se pueda conectar al contenedor de la BD**

![](C:\Users\Guty\Desktop\TAREA DOCKER\ejercicios\ejercicio1\imagenes ejercicio 1\10-descarga y contenedor phpmyadmin.png)

Vemos el contenedor

![](C:\Users\Guty\Desktop\TAREA DOCKER\ejercicios\ejercicio1\imagenes ejercicio 1\11-contenedor phpmyadmin.png)

Lo conectamos a la red `redej1`

![](C:\Users\Guty\Desktop\TAREA DOCKER\ejercicios\ejercicio1\imagenes ejercicio 1\12-conecto contenedor phpmadm a red.png)

Vemos los dos contenedores conectados a la misma red:

![](C:\Users\Guty\Desktop\TAREA DOCKER\ejercicios\ejercicio1\imagenes ejercicio 1\13-dos contenedores conectados.png)

##### **4.Conexión a la base de datos por la interfaz gráfica** 

![](C:\Users\Guty\Desktop\TAREA DOCKER\ejercicios\ejercicio1\imagenes ejercicio 1\14-ENTRAR A LA BD CON PHPADMIN.png)

Vemos la tabla creada con los módulos. 

![](C:\Users\Guty\Desktop\TAREA DOCKER\ejercicios\ejercicio1\imagenes ejercicio 1\15-BD CON PHPADMIN.png)

##### **5.Instalamos la extensión `Disk Usage` que muestra el espacio ocupado**

![](C:\Users\Guty\Desktop\TAREA DOCKER\ejercicios\ejercicio1\imagenes ejercicio 1\16-extension disk usage.png)

![](C:\Users\Guty\Desktop\TAREA DOCKER\ejercicios\ejercicio1\imagenes ejercicio 1\17-extension disk usage funcionando.png)

