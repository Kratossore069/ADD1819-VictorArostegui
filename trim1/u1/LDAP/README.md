# 1. Prerrequisitos.

En esta guía vamos a instalar y configurar del servidor LDAP con OpenLDAP.

## 1.1 Nombre del equipo FQDN.

![](./img/imgname.PNG)

![](./img/img1.PNG)

## 1.2 Opening the Required Ports in the Firewall.

Comprobamos el estado del antivirus.

![](./img/imgfire.PNG)

## 1.3 Directory Server User and Group.

Creará el siguiente recurso automáticamente.

## 1.4 Directory Suffix.

El Directory Suffix es la tercera entrada dentro del árbol de directorios. Al menos un directorio sufijo debe ser proveído cuando el directorio servidor está configurado. El directorio sufijo recomendado empareja sus nombres con tu organización de dominios de nombre DNS. Por ejemplo, si el hostname del directorio servidor is `ldap.example.com`, el directorio sufijo es `dc=example,dc=com`.

## 1.5 About the `setup-ds-admin.pl` Script.

Las instancias del directorio servidor y el servidor de administración son creadas y configuradas a partir de un script llamado setup-ds-admin.pl. El directorio servidor solo puede ser creado usando el setup-ds.pl script.

Si, simplemente, el script de configuración está operativo, entonces el script lanza un interactivo instalador que guía por herramientas de configuración en el directorio servidor y las instancias del servidor de administración. Por ejemplo:

![](./img/imgpal.PNG)

# 2. Instalar el servidor.

PARA REVISAR

Necesitaremos ajustar parámetros del kernel para asegurarnos de que la instalación no se quejará por la falta de recursos. Vamos a crear el siguiente fichero con la siguiente información:

![](./img/imga.PNG)

Ejecutamos los cambios.

![](./img/imgb.PNG)

# 2. Instalar el servidor de directorio 389.

Necesitamos añadir los repositorios con los ficheros del proyecto LDAP.

![](./img/img001.PNG)

Instalar los siguientes paquetes.

![](./img/img002.PNG)

# 3. Ajustamos la configuración.

Solucionamos problemas con las dependencias de los paquetes.

![](./img/img003.PNG)

Ahora tenemos que editar y localizar las siguientes líneas.

![](./img/img004.PNG)

Deberíamos ser capaces de ejecutar este comando sin problemas.

![](./img/img005.PNG)

# 4. Después de la instalación: arreglando 389-console.

Procedemos a la instalación del módulo Yast que sirve para gestionar el servidor LDAP `yast2-auth-server`. Para ello:

![](./img/img3.PNG)

Hay una duda ya que no aparece el `Authentication Server` así que iremos a la siguiente pantalla para poder configurar de alguna manera el LDAP.

![](./img/img4.PNG)

![](./img/img5.PNG)

![](./img/img6.PNG)

Comprobaciones después de la configuración.

![](./img/img7.PNG)

## 1.3 Problemas.

Este espacio está destinado a problemas diversos con el LDAP por si tenemos que desinstalar el software anterior. Seguir estos pasos:

`zypper remove yast2-auth-server`

`zypper remove openldap2 krb5-server krb5-client`

`mv /etc/openldap /etc/openldap.000`

`mv /var/lib/ldap /var/lib/ldap.000`

## 1.4 Crear usuarios y grupos LDAP.

![](./img/img8.PNG)

Crear grupo y usuarios.

![](./img/img9.PNG)

![](./img/img10.PNG)

Hecho esto, debemos  usar un comando para consultar en la base de datos LDAP la información del usuario con uid concreto.

![](./img/img11.PNG)

# 2. Cliente LDAP.

## 2.1 Preparativos.

![](./img/img009.PNG)

![](./img/img0010.PNG)

## Comprobación.

Comprobar que el servidor LDAP es accesible desde el cliente.

![](./img/img0011.PNG)

Comprobamos que siguen existiendo los usuarios y grupos creados.

![](./img/img0012.PNG)
