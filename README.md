# AREP-Taller-1
En este taller se tuvo como objetivo realizar una aplicación para consultar películas de cine, en la cual se establece una conexión a una API externa que contiene toda la información que se requiere mostrar.

## Para ejecutar el programa

Se puede hacer uso del comando git clone y usar la URL del repositorio:
```
https://github.com/JuanPabloDaza/AREP-Taller-1
```

## Prerequisitos

Es necesario tener instalado maven para compilar y probar los test del programa, si no se tiene maven puede instalar [aqui](https://maven.apache.org/install.html).

## Instalacion 

Una vez clonado, se debe hacer uso del comando:

```
mvn package
```

Este comando compilara el programa y tambien ejecutara las pruebas. 

## Ejecutar pruebas

Si se quiere ejecutar solamente las pruebas se puede hacer uso del comando:

```
mvn test
```
Las pruebas verifican el funcionamiento del cache y de la conexion del programa a la API externa.

## Despliegue del programa:

Para ejecutar el programa se usa el comando:

```
mvn exec:java -D "exec.mainClass"="edu.escuelaing.arep.ASE.app.HttpServer"
```
Una vez ejecutado se debe acceder a traves de un buscador y con la direccion:
```
127.0.0.1:35000
```

## Descripcion del programa:

### Diseño:

En este programa se usa la clase HttpServer para responder las solicitudes REST que sean necesarias, dentro de la pagina principal hay un buscador que permite ingresar el nombre de la pelicula para que se busque la misma.

Para la busqueda de la información primero se verifica que no este en el cache, el cache utiliza el modelo LRU (Least Recently Used), que consiste en ir eliminando las busquedas que menos se realicen con la finalidad de mejorar el tiempo de respuesta.

Si la información no esta en el cache entonces se usa la clase APIConnection para establecer una conexión a la API externa y luego transformar la información solicitada en una tabla que la muestre al usuario.

### Expansion:

Para expandir la aplicacion se puede lograr por medio de la URI de la petición REST, se puede realizar otra página que utilice otra API y que dependiendo de como este construida la URI se utilice cada un metodo para cada API.

## Construido con:

* [Maven](https://maven.apache.org/) - Manejo de dependecias.
* [OMDb API](https://www.omdbapi.com/) - API Externa

## Autor

* Juan Pablo Daza Pinzon

## Reconocimientos

* Ayuda en la construccion de la tabla para la informacion suministrada - [Juan Sebastian Rodriguez Peña](https://github.com/JSebastianRod)
* [Implementacion del Cache LRU](https://www.youtube.com/watch?v=efiWbPSinD8)