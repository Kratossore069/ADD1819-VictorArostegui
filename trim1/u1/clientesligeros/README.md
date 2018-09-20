# Clientes Ligeros con LTSP/Ubuntu

## 2. Preparativos

Se usarán dos máquinas virtuales para montar clientes ligeros con LTSP.

## 3. Servidor LTSP

### 3.1 Preparar la MV Server

La máquina servidor tendrá dos interfaces de red y usaremos como sistema
operativo un SO Xubuntu.

![](./img/img1.PNG)

> La primera interfaz será la externa y servirá para comunicarse con Internet.

![](./img/img2.PNG)

> La segunda interfaz servirá para conectarse con los clientes ligeros. Esta
interfaz debe ser estática y debe estar en la misma red que los clientes.
