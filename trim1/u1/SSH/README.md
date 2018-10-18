# Acceso remoto SSH.

# 1. Preparativos.

## 1.1 Servidor SSH.

Configuramos la MV de OpenSUSE que funcionará como servidor.

![](./img/img1.PNG)

![](./img/img2.PNG)

![](./img/img3.PNG)

Vamos a hacer los mismo con una máquina virtual más que será el cliente.

![](./img/imga.PNG)

Añadimos en **/etc/hosts** los equipos **ssh-clientXXg** y **ssh-clientXXw**.

![](./img/imgserverhosts.PNG)

Comprobamos los cambios.

![](./img/img5.PNG)

![](./img/img6.PNG)

Creamos los siguientes usuarios en el servidor.

![](./img/img7.PNG)

> Yast2 -> Gestión de usuarios y grupos.

## 1.2 Cliente GNU/Linux

Configuramos el cliente de la siguiente manera,

![](./img/img9.PNG)

Añadimos en **/etc/hosts** el equipo **ssh-serverXXg** y **ssh-clientXXw**.

![](./img/imgclienthosts.PNG)

Comprobamos que existe ping entre ambos equipos.

![](./img/img10.PNG)

## 1.3 Cliente Windows.

Configuramos la IP del cliente Windows.

![](./img/img11.PNG)

Cambiamos el nombre del equipo.

![](./img/img12.PNG)

Añadimos las direcciones de las demás máquinas.

![](./img/img13.PNG)

Probamos a hacer ping para observar si se conectan entre ellas.

![](./img/img14.PNG)

# 2. Instalación del servicio SSH.

![](./img/img15.PNG)

## 2.1 Comprobación.

![](./img/img16.PNG)

Observamos los puertos a los que se conecta el ssh.

![](./img/img17.PNG)

## 2.2 Primera conexión SSH desde cliente GNU/Linux.

Comprobamos la conectividad con el servidor desde el cliente.

![](./img/img18.PNG)

Desde el cliente comprobamos que el servicio SSH es visible con el servidor. Debe mostrarnos que el puerto 22 está abierto.

![](./img/img19.PNG)

Vamos a comprobar el funcionamiento de la conexión SSH desde cada cliente usando el usuario 1er-apellido-alumno1.
Desde el cliente GNU/Linux nos conectamos mediante ssh 1er-apellido-alumno1@ssh-serverXXg. Tendrá lugar una creación de contraseñas que habrá que mostrar con cada usuario.

![](./img/img20.PNG)

![](./img/img21.PNG)
