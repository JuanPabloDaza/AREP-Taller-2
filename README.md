# AREP-Taller-2
En este taller se tuvo como objetivo realizar un servidor web que respondiera a las peticiones con archivos .html que contengan codigo CSS o JavaScript, tambien devuelve la informacion de las imagenes solicitadas.

Este taller es una continuacion del primero [AREP Taller 1](https://github.com/JuanPabloDaza/AREP-Taller-1).

## Para ejecutar el programa

Se puede hacer uso del comando git clone y usar la URL del repositorio:
```
https://github.com/JuanPabloDaza/AREP-Taller-2
```

## Prerequisitos

Es necesario tener instalado maven para compilar y probar los test del programa, si no se tiene maven puede instalar [aqui](https://maven.apache.org/install.html).

## Instalacion 

Una vez clonado, se debe hacer uso del comando:

```
mvn package
```

Este comando compilara el programa y tambien ejecutara las pruebas. 

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

En este programa se usa la clase HttpServer para responder las solicitudes REST que sean necesarias, dentro de la pagina principal hay un buscador que permite ingresar el nombre del archivo que se quiere mostrar.

Los archivos deben ser almacenados en la carpeta resources.

De base el programa contiene tres archivos de prueba:
* index.html
* imagen.html
* css.html

#### index.html:
Permite la busqueda de archivos que esten en la carpeta resources

#### image.html:
Permite ver la funcionalidad al mostrar una imagen.

#### css.html:
Permite ver la funcionalidad al mostrar un archivo html con el codigo CSS dentro del mismo.

### Expansion:

Para expandir la aplicacion se puede lograr introduciendo los archivos que se quieran mostrar en la carpeta resources. Al ser archivos html se recomienda incluir el siguiente codigo dentro del body del archivo html para volver a index.html y comprabar mas funcionalidades:

```
    <button id="redirectButton">Redireccionar al inicio</button>
    <br>
    <script>
        document.getElementById("redirectButton").addEventListener("click", function() {
            window.location.href = "index.html";
            setTimeout(function() {
                    location.reload();
                }, 100);
        });
    </script>
```

El anterior codigo agrega un botón y el script para volver a index.html.

## Construido con:

* [Maven](https://maven.apache.org/) - Manejo de dependecias.
* [OMDb API](https://www.omdbapi.com/) - API Externa

## Autor

* Juan Pablo Daza Pinzon

## Reconocimientos

* Ayuda en la construccion de la tabla para la informacion suministrada - [Juan Sebastian Rodriguez Peña](https://github.com/JSebastianRod)
* [Implementacion del Cache LRU](https://www.youtube.com/watch?v=efiWbPSinD8)