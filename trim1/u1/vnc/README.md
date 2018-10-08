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



### 3.3 Ir al cliente.

### 3.4 Comprobaciones finales.

## 4. Instalación en OpenSUSE.

Configurar las máquinas virtuales servidor y cliente.

![](./img/confsuse.PNG)

![](./img/confsuse2.PNG)

![](./img/confsuse3.PNG)

![](./img/confsuse4.PNG)

#### 4.1 Ir al servicio VNC OpenSUSE.

**Yast -> VNC**
