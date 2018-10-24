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

Ahora debemos comprobar  el contenido del fichero **$HOME/.ssh/known_hosts** en el equipo **ssh-client1**.

![](./img/img22.PNG)

> Podemos observar que existe una clave de acceso que es la clave de identificación de ssh-server.

## 2.3 Primera conexión SSH desde cliente Windows.

 Desde el cliente de Windows nos vamos a conectar usando **Putty** al servidor.

![](./img/img23.PNG)

![](./img/img24.PNG)

![](./img/img25.PNG)

> Hacemos lo mismo que en el punto anterior que es registrar las claves de acceso al servidor desde el cliente. Vemos que podemos conectarnos por SSH perfectamente.

# 3. ¿Y si cambiamos las claves del servidor?

Tenemos que confirmar que existen los siguientes ficheros en **/etc/ssh**. Los ficheros **ssh_host*key** y **ssh_host*key.pub** son ficheros de claves públicas y privadas que necesitamos para establecer conexión entre máquinas.

![](./img/img26.PNG)

Vamos a modificar el fichero de configuración SSH **/etc/ssh/sshd_config** para dejar una única línea **HostKey /etc/ssh/ssh_host_rsa_key**. El resto de líneas las tenemos que comentar  para que solo se permita acceder con la configuración insertada antes.

![](./img/img27.PNG)

## Regenerar certificados.

En **ssh-serverXXg** como usuario root ejecutamos **ssh-keygen -t rsa -f /etc/ssh/ssh_host_rsa_key**.

![](./img/img28.PNG)

> No poner password al certificado de la máquina.

Reiniciar el servicio SSH usando **systemctl restart sshd**.

![](./img/img29.PNG)

> Comprobar que el servicio está en ejecución correctamente con **systemctl status sshd**.

## Comprobamos.

![](./img/img30.PNG)

> Podemos observar que salta un aviso de que no se ha podido ingresar desde el cliente de OpenSUSE debido a los cambios hechos anteriormente.

# 4. Personalización del prompt bash.

Vamos a cambiar el prompt de **carvajal1**. Accedemos a **/home/carvajal1/.bashrc**

![](./img/img31.PNG)

![](./img/img32.PNG)

Además, crearemos otro fichero en la misma ruta con este contenido.

![](./img/img33.PNG)

Comprobamos la conexión.

![](./img/img34.PNG)

> Hay que volver a entrar en el servidor y volver a comentar la línea de rsa en **/etc/ssh/sshd_config** debido a que no podremos conectar con el servidor sin cambiarlo.

# 5. Autenticación mediante claves públicas.

El objetivo de este apartado es el de configurar SSH para poder acceder desde el cliente1, usando el nombre-alumno sin poner password, pero usando claves pública/privada. Vamos a entrar en el cliente y generamos nuevas claves.

![](./img/img35.PNG)

Ahora debemos copiar las claves desde el cliente hasta el otro cliente en remoto usando el siguiente comando.

![](./img/img36.PNG)

Vamos a ver que ahora, desde el cliente4, podemos acceder sin necesidad de poner contraseña.

![](./img/img37.PNG)

# 6. Uso de SSH como túnel para X.

Vamos a instalar una app en el servidor y hacer posible que los clientes, por remoto, puedan ejecutarla.

![](./img/img38.PNG)

Vamos al servidor y en la configuración dejamos la siguiente línea así.

![](./img/img39.PNG)

Vamos al cliente y nos aseguramos de que no tenemos instalada la aplicación del servidor. Una vez hecho esto, nos conectamos en remoto...

![](./img/img41.PNG)

 y observamos que, desde el cliente, podemos observar las aplicaciones instaladas en el servidor.

![](./img/img40.PNG)

# 7. Aplicaciones Windows nativas.

Instalamos el emulador Wine en el ssh-serverXXg. Puede tardar un poco.

![](./img/img42.PNG)

![](./img/img43.PNG)

Wine es una utilidad que permite ejecutar archivos propios de Windows en Linux. Ahora vamos a probar hacer justo esto.

![](./img/img44.PNG)

> Se trata de un archivo .exe que se puede instalar en Windows pero, gracias a Wine, se puede abrir también en Linux.

![](./img/img45.PNG)

![](./img/img46.PNG)

> Igualmente en esta máquina virtual no podemos arrancar el juego.
