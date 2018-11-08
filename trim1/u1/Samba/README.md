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

![](./img/img15.PNG)

Comprobamos la lista de usuarios Samba.

![](./img/img16.PNG)

## 1.7 Reiniciar.

Ahora que hemos terminado con el servidor, hay que reiniciar el servicio para que se lean los cambios de configuración.

Reiniciamos el servicio smb.

![](./img/img17.PNG)

Reiniciamos el servicio nmb.

![](./img/img18.PNG)

Verificamos la sintaxis del fichero de configuración del servidor Samba.

![](./img/img19.PNG)

Observamos que el servicio SMB/CIF está a la escucha.

![](./img/img20.PNG)

# 2. Windows.

Configuramos los hosts de Windows.

![](./img/img21.PNG)

> C:/Windows/System32/drivers/etc/hosts

## 2.1 Cliente Windows GUI.

Desde un cliente Windows vamos a acceder a los recursos compartidos del servidor Samba.

![](./img/img22.PNG)

Intentamos conectarnos como un usuario en uno de los grupos del servidor.

![](./img/img23.PNG)

> Debemos tener algún problema con el cortafuegos por lo que no podemos entrar.

Observamos las conexiones desde el servidor.

![](./img/img24.PNG)

Desde el cliente Windows.

![](./img/img25.PNG)

## 2.2 Cliente Windows comandos.

 Consultamos todas las conexiones/recursos conectados.

![](./img/img26.PNG)

> `net use * /d /y` para cerrar las conexiones SMB.

Vemos las máquinas accesibles por la red.

![](./img/img27.PNG)
