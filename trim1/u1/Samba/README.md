# Samba

Para esta práctica voy a usar **VNC**, **OpenSUSE_server** y **OpenSUSE_cliente**.

# 1. Servidor Samba.

## 1.1 Preparativos.

Configurar la máquina Samba servidor añadiendo también los hosts de las otras máquinas.

![](./img/imga.PNG)

![](./img/imgb.PNG)

Comandos de comprobación.

![](./img/img1.PNG)

![](./img/img2.PNG)

## 1.2 Usuarios locales.

Creamos grupos.

![](./img/img3.PNG)

Creamos el usuario `smbguest` y lo gestionamos para que no pueda usarlo nadie.

![](./img/img4.PNG)

![](./img/img5.PNG)

Creamos usuarios dentro de los grupos.

![](./img/img6.PNG)

![](./img/img7.PNG)

> El nombre cdrom no estaba disponible.

## 1.3 Crear las carpetas para los futuros recursos compartidos.

![](./img/img8.PNG)

> Haciendo uso de los comandos `chown`, `chmod`, `chgrp` podemos cambiar el usuario propietario de la carpeta, sus permisos y el grupo propietario en ese orden.

## 1.4 Configurar el servidor Samba.

Vamos a hacer una copia de seguridad del fichero de configuración existente.

![](./img/img9.PNG)

Vamos a Yast -> Servidor Samba.

![](./img/img10.PNG)

![](./img/img11.PNG)

![](./img/img12.PNG)

## 1.5 Crear los recursos compartidos Samba.

Vamos a configurar los recursos compartido del servidor Samba. Vamos al terminal y vamos a `/etc/samba/smb.conf` e insertamos la siguiente información.

![](./img/img13.PNG)

Y un último comando llamado `testparm`.

![](./img/img14.PNG)

## 1.6 Usuarios Samba.

Después de crear los usuarios en el sistema, hay que añadirlos a Samba.
