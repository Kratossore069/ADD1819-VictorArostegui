# Vagrant y VirtualBox.

# 1. Introducción.

Vagrant es una herramienta para la creación y configuración de entornos
de desarrollo virtualizados.

# 2. Primeros pasos.

## 2.1 Instalar.

Necesitamos instalar Vagrant en la máquina real. Hay varias formas de instalar Vagrant:

`apt-get install vagrant` o
usando un paquete vagrant.deb. Disponible para descargar del servidor Leela.

`vagrant version`, para comprobar la versión actual de Vagrant.

`VBoxManage -v`, para comprobar la versión actual de VirtualBox.

Si vamos a trabajar Vagrant con MV de VirtualBox, hay que comprobar que las versiones de ambos son compatibles entre sí.

## 2.2 Proyecto.

Crear un directorio para nuestro proyecto Vagrant (Donde XX es el número de cada alumno):

![](./img/1.PNG)

## 2.3 Imagen, caja o box.

Ahora necesitamos obtener una imagen de un sistema operativo. Vamos, por ejemplo, a conseguir una imagen de un `Ubuntu Precise de 32 bits`. Utilizamos `nmap -Pn host`.

![](./img/2.PNG)
