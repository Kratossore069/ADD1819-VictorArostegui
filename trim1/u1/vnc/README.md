# Práctica de VNC.

## 1. Introducción.

## 2. Conexiones remotas con VNC.

Vamos a proceder a instalar, a través de máquinas virtuales, a observar el comportamiento de herramientas VNC.

## 3. Instalación en Windows.

Necesitaremos dos máquinas virtuales Windows 7 para empezar.

![](./img/img1.PNG)

Ahora debemos configurar las máquinas virtuales.

![](./img/img2.PNG)

![](./img/img3.PNG)

Una vez configuradas las máquinas ahora descargamos un programa llamado **TightVNC** en la máquina cliente.

![](./img/img4.PNG)

![](./img/img5.PNG)

> "Complete"

![](./img/img6.PNG)

> Elegimos las contraseñas de acceso desde el cliente.

### 3.1 Ir al servidor VNC en Windows.

En el cliente vamos a instalar el **TightVNC server** y tendremos que tener precaución con la configuración del cortafuegos para aceptar el VNC.

![](./img/img7.PNG)

![](./img/img8.PNG)

###	 3.2 Ir a la máquina real en Linux.

Poner en la consola **nmap -Pn IP-VNC-SERVER** para comprobar que los servicios son visibles desde fuera de la máquina VNC-SERVER. Deben verse los puertos 5801, 5901, etc.

![](./img/img17.PNG)

### 3.3 Ir al cliente Windows.

Vamos intentar establecer conexión entre Windows y Windows.

![](./img/img20.PNG)

> En esta foto podemos observar que la máquina de la izquierda es el cliente y vamos a conectar a la máquina de la derecha, que es el servidor.

![](./img/img21.PNG)

> A la hora de conectar con el servidor vemos que es necesario una contraseña que, anteriormente, introducimos para ambas máquinas. Es necesaria para establecer conexión.

![](./img/img22.PNG)

> Podemos observar que se ha establecido conexión y que vemos las dos pantallas.

### 3.4 Comprobaciones finales.

Utilizando el comando **netstat -n** podemos observar que se abren puertos para las conexiones vnc.

![](./img/img19.PNG)

## 4. Instalación en OpenSUSE.

Configurar las máquinas virtuales servidor y cliente.

![](./img/confsuse.PNG)

![](./img/confsuse2.PNG)

![](./img/confsuse3.PNG)

![](./img/confsuse4.PNG)

### 4.1 Ir al servicio VNC OpenSUSE.

**Yast -> VNC**

![](./img/img9.PNG)

> En la imagen vemos que hay que ajustar de esa manera las opciones de VNC y abrir el cortafuegos para que no nos de problema la conexión.

![](./img/img10.PNG)

> Insertamos una contraseña que nos servirá para entrar en nuestro VNC.

![](./img/img11.PNG)

> De la manera anterior, podemos observar que existe .vnc debido a nuestra antigua gestión.

![](./img/img12.PNG)

> De esta forma podemos comprobar que están operativos los servicios de vnc.

![](./img/nota1.PNG)

> Puede haber problemas y tengamos que recurrir al paso anterior de instalar, aunque estén obsoletas, esas herramientas.

### 4.2 Ir a la máquina real.

Ejecutar **nmap -Pn IP-VNC-SERVER**, desde la máquina real GNU/Linux para comprobar que los servicios son visibles desde fuera de la máquina VNC-SERVER. Deben verse los puertos 5801, 5901, etc.

![](./img/img13.PNG)

### 4.3 Ir al cliente GNU/Linux.

**vncviewer** es un cliente VNC que viene con OpenSUSE.

![](./img/img14.PNG)

Accedemos de la siguiente forma en el cuadro de texto.

![](./img/img15.PNG)

Y vemos que funciona.

![](./img/img16.PNG)

### 4.4 Comprobaciones finales.

## 5. Comprobaciones.

Vamos a conectar la máquina virtual OpenSUSE a la máquina Windows. Es importante para hacer esta prueba desactivar el cortafuegos ya que puede interferir en nuestra prueba.

![](./img/img23.PNG)

![](./img/img24.PNG)

![](./img/img25.PNG)

> Nos pedirá una contraseña que antes ya habíamos insertado en la configuración.

![](./img/img26.PNG)

Vemos que funciona perfectamente. Ahora vamos a probar desde OpenSUSE hasta OpenSUSE.

![](./img/img28.PNG)

> Podemos ver que en la pantalla de la derecha está el comando **vncviewer IP:5901**. Lo último es el puerto al que debemos conectarnos

![](./img/img29.PNG)

> Vemos que conecta pero vemos la pantalla en negro.

## 6. Display 0.

Como último paso, cuando queremos ejecutar **vncserver** para controlar directamente la pantalla local usaremos **x0vncserver -display :0 -passwordfile /home/nombrealumno/.vnc/passwd**.

Para más información, véase **man x0vncserver**.

![](./img/img27.PNG)
