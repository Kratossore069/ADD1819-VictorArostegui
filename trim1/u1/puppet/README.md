# PUPPET

# 1. Introducción.

Es una herramienta diseñada para administrar la configuración de sistemas Windows de forma declarativa. El usuario describe los recursos del sistema y sus estados, ya sea un declarativo de Puppet o un DSL (lenguaje específico del dominio) de Ruby.

## 1.1 Requisitos.

![](./img/0.PNG)

## 1.2 Servidor DNS y el fichero /etc/resolv.conf.

![image](./img/1.PNG)

![image](./img/2.PNG)

![image](./img/aa.PNG)

## 1.3 Hostname y dnsdomainname.

![](./img/3.PNG)

![](./img/4.PNG)

![](./img/5.PNG)

## 1.4 Resolución de nombres.

Comandos a usar:

* `synaptic&` para entrar en paquetes para desinstalar.

* Desinstalar `Networkmanager`

* Volver a escribir en `/etc/resolv.conf -> nameserver 8.8.4.4` y reiniciar la máquina.

# 2. Instalación y configuración del MASTER.

## 2.1 Configurar servidor DNS.

![](./img/6.PNG)

![](./img/7.PNG)

Comprobaciones.

![](./img/8.PNG)

**Cómo deberia quedar para tener conexión.**

![](./img/9.PNG)

# 4. Fichero pp VERSION-1.

![image](./img/10.PNG)

![image](./img/11.PNG)

![image](./img/12.PNG)

![image](./img/13.PNG)

> `/var/log/syslog` para observar los fallos por si hubiera.

# 5. Instalación y configuración del cliente puppet Debian.

## 5.1 Preparativos para CLIENT1.

![image](./img/14.PNG)

## 4.2 Instalación del agente.

![image](./img/15.PNG)

![image](./img/16.PNG)

> Hay que incluir esa línea en esa dirección en el cliente.

![image](./img/17.PNG)

# 6. Aceptar certificado.

Antes de que el master acepte a `pp-client14d.curso1819`, como cliente, se deben intercambiar los certificados.

## 6.1 Aceptar certificado.

![image](./img/18.PNG)

![image](./img/19.PNG)

## 6.2 Comprobación.

Vamos a comprobar que las órdenes (manifiesto) del master, llega
bien al cliente y éste las ejecuta.

![image](./img/20.PNG)

> Iniciamos el servicio Puppet y, si tuviéramos fallos, consultar los dos comandos siguientes.

# 7. Fichero pp VERSION-2.

Primero hemos probado una configuración sencilla en PuppetMaster. Ahora podemos pasar a algo más complejo en este apartado.

Contenido para `hostlinux2.pp`, versión 2 en `/etc/puppet/manifests/classes/`:

![image](./img/21.PNG)

![image](./img/22.PNG)

Modificar `site.pp` con:

![image](./img/23.PNG)

# 8. Fichero pp VERSION-3: Cliente puppet windows.

En el master vamos a crear una configuración puppet para las máquinas windows, dentro del fichero `/etc/puppet/manifests/classes/hostwindows3.pp`, con el siguiente contenido:

![image](./img/24.PNG)

Ahora vamos a modificar el fichero `site.pp` del master, para que tenga en cuenta la configuración de clientes GNU/Linux y clientes Windows, de la siguiente forma:

![image](./img/25.PNG)

Entramos a Windows.

![image](./img/26.PNG)

Modificar el fichero de la misma forma que hicimos para client1.
