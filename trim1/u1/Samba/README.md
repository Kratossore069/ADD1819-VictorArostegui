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

> Cuidado con copiar y pegar.

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

Abrimos una shell de Windows y usamos el comando `net use /?`, para consultar la ayuda del comando.

![](./img/img28.PNG)

Ahora probamos conectarnos desde el cliente de Windows al servidor de Samba.

![](./img/img29.PNG)

Comprobamos las conexiones.

![](./img/img30.PNG)

Comprobamos los resultados.

![](./img/img31.PNG)

![](./img/img32.PNG)

# 3. Cliente GNU7Linux.

Configuramos el cliente OpenSUSE de Samba.

![](./img/img33.PNG)

> /etc/hosts

## 3.1 Cliente GNU/Linux GUI.

Entramos a Yast y observamos que tenemos conexión al servidor de Samba.

![](./img/img34.PNG)

Probamos a crear carpetas.

![](./img/img35.PNG)

![](./img/img36.PNG)

La carpeta `public` es solo de lectura.

![](./img/img37.PNG)

Comprobaciones.

![](./img/img38.PNG)

![](./img/img39.PNG)

## 3.2 Cliente GNU/Linux comandos.

Primero comprobar el uso de las siguientes herramientas. El siguiente comando hay que observarlo desde Ubuntu, no desde OpenSUSE.

![](./img/img40.PNG)

> El comando debería mostrar cierta información.

![](./img/img41.PNG)

Ahora crearemos en local la carpeta.

![](./img/img42.PNG)

Montamos la carpeta siguiente.

![](./img/img43.PNG)

Comprobamos.

![](./img/img44.PNG)

![](./img/img45.PNG)

## 3.3 Montaje automático.

Para configurar acciones de montaje automáticos cada vez que se inicie el equipo, debemos configurar el fichero `/etc/fstab`.

![](./img/img46.PNG)

Reiniciamos el equipo y comprobamos que se realizan los cambios.

![](./img/img47.PNG)

# 4. Preguntas para resolver.

**¿Por qué tenemos dos servicios (smb y nmb) para Samba?**

Son dos servicios que son necesarios para que tanto Windows como OpenSUSE puedan compartir la información del samba.

**¿Las claves de los usuarios en GNU/Linux deben ser las mismas que las que usa Samba?**

No, deben ser distintas por seguridad.

**¿Puedo definir un usuario en Samba llamado soldado3, y que no exista como usuario del sistema?**

No, primero hay que definirlo en la máquina y luego implementarle la configuración de Samba.

**¿Cómo podemos hacer que los usuarios soldado1 y soldado2 no puedan acceder al sistema pero sí al samba? (Consultar /etc/passwd)**

![](./img/img48.PNG)

**Añadir el recurso [homes] al fichero smb.conf según los apuntes. ¿Qué efecto tiene?**

![](./img/img49.PNG)

Se crearía el recurso `homes` y, por consiguiente, la carpeta.

**¿Cómo pueden los clientes acceder al CDROM del servidor usando Samba?**

A través del `smbguest`, ya que es un usuario de ese grupo.

**/dev/cdrom ¿Dónde apunta? ¿Qué permisos tiene?**

![](./img/img50.PNG)

**/dev/sr0 ¿Que permisos tiene?**

![](./img/img51.PNG)
