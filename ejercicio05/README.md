
# Ejercicio 5

Explorando Dockerfile commands


## Authors

- [@dannyds26](https://www.github.com/dannyds26)


## HEALTHCHECK

Este comando permite agregar a las imágenes de Docker una instrucción para chequear el estado de un recurso dentro del contenedor de manera
que se pueda validar si lo que se esta ejecutando en la imágen está en un estado normal o de fallo. Ejem: si un API responde correctamente a un url, si el ping a un servidor responde correctamente, etc.

## ONBUILD

Este comando registra la ejecución de comandos que luego son ejecutados en otra imágen construída a partir de esta imágen base. Estos comandos son ejecutados en el mismo orden en como fueron ejecutados en la imágen padre. 

## VOLUME

Este comando permite mapear un directorio del host con un directorio dentro del contenedor de manera que los datos que se manejen dentro del contenedor se conserven en el host indistintamente de si el contenedor es eliminado o regenerado. Ejem: datos de una base de datos, archivos estáticos de un sitio web, etc.
