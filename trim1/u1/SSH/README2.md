# Acceso remoto SSH.

# 1. Preparativos.

## 1.1 Servidor SSH.

Preparamos la máquina OpenSUSE servidor.

![](./img2/1.PNG)

![](./img2/2.PNG)

![](./img2/3.PNG)

Creamos usuarios.

![](./img2/4.PNG)

## 1.2 Cliente GNU/Linux.

![](./img2/5.PNG)

## 1.3 Cliente Windows.

![](./img2/6.PNG)

# 2. Instalación del servicio SSH.

Instalar SSH.

![](./img2/7.PNG)

## 2.1 Comprobación.

![](./img2/8.PNG)

## 2.2 Primera conexión SSH desde cliente GNU/Linux.

Desde el cliente.

![](./img2/9.PNG)

Probamos conexión con los usuarios.

![](./img2/10.PNG)

Salimos y volvemos a conectarnos.

![](./img2/11.PNG)

Comprobamos el siguiente fichero para observar la clave que contiene.

![](./img2/12.PNG)

## 2.3 Primera conexión SSH desde cliente Windows.

Nos conectamos desde Windows.

![](./img2/13.PNG)

![](./img2/14.PNG)

![](./img2/15.PNG)

# 3. Cambiamos la identidad del servidor.

Asegurarnos de que existen claves públicas y privadas.

![](./img2/16.PNG)

Quitamos líneas y sólo dejamos ésta.

![](./img2/17.PNG)

## 3.1 Regenerar certificados

![](./img2/18.PNG)

![](./img2/19.PNG)

## 3.2 Comprobamos.

Vemos que nos podemos conectar sin más que usando el password.

![](./img2/20.PNG)

# 4. Personalización del prompt bash.

Ir a la dirección e insertar el texto siguiente.

![](./img2/21.PNG)

Crear un nuevo fichero en la siguiente dirección.

![](./img2/22.PNG)

Comprobamos desde un cliente para observar los cambios.

![](./img2/23.PNG)

# 5. Autenticación mediante claves públicas.

![](./img2/24.PNG)

![](./img2/25.PNG)

![](./img2/26.PNG)

![](./img2/27.PNG)

# 6. Uso de SSH como túnel para X.
