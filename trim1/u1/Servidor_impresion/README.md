Víctor Gabriel Carvajal Aróstegui
Eleazar Sánchez Arbelo

# Servidor de Impresión en Windows.

Necesitaremos dos máquinas virtuales Windows como Windows7_cliente y Windows Server.

![](./img/1.PNG)

> Máquina cliente.

![](./img/2.PNG)

> Máquina servidor.

# 1. Impresora compartida.

## 1.1 Rol impresión.

Vamos al servidor e instalamos  la función de servidor de impresión. Ir a `Roles y características.`

![](./img/3.PNG)

![](./img/4.PNG)

![](./img/5.PNG)

## 1.2 Instalar impresora PDF.

Vamos a conectar e instalar localmente una impresora al servidor Windows Server, de modo que estén disponibles para ser accedidas por los clientes del dominio. Vamos a descargar `PDFCreator`.

![](./img/6.PNG)

![](./img/7.PNG)

> Lo instalamos y la ruta de guardado de sus archivos será por defecto.

![](./img/8.PNG)

## 1.3 Probar la impresora en local.

Creamos un documento de texto para proceder con la impresión.

![](./img/9.PNG)

![](./img/10.PNG)

> Vamos a imprimir el documento y sale de la siguiente manera.

## 1.4 Compartir por red.
