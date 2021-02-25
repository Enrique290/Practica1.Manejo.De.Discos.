# Practica 1. Manejo De Discos.
## 1. Identificar y describir las diferencias entre hda, sda y vda, además explicar qué significa la letra y el número al final de los identificadores (no requiere captura de pantalla).

### hda
dev/hda : es el disco maestro en el controlador IDE primario.

En el cual la letra del final, puede cambiar y verse de la siguiente manera:

* **dev/hda:** disco maestro en la primera controladora
* **dev/hdb:** disco esclavo en la primera controladora
* **dev/hdc:** disco maestro en la segunda controladora
* **dev/hdd:** disco esclavo en la segunda controladora

Además, puede estar numerado según las particiones que tenga:
* De 0 a 3 se denominan las primeras cuatro particiones posibles
* De 4 en adelante las particiones lógicas que el usuario establece, por ejemplo:
   * **dev/hda0:** disco maestro en la primera controladora, primera partición primaria.
   * **dev/hda1:** disco maestro en la primera controladora, segunda partición primaria.
   * **dev/hda4:** disco maestro en la primera controladora, primera partición lógica.
   * **dev/hda5:** disco maestro en la primera controladora, segunda partición lógica.

### sda
dev/sda: el primer disco SCI SCSI ID address-wise.

En el cual podemos cambiar la última letra para indicar el número de disco que es, por ejemplo:
* **dev/sda:** el primer disco SCI SCSI ID address-wise.
* **dev/sdb:** el segundo disco SCI SCSI ID address-wise.
* **dev/sdc:** el tercer disco SCI SCSI ID address-wise.

De igual forma se pueden enumerar las particiones colocando un número al final, por ejemplo, si el disco sda tiene 3 particiones, los nombres de estas particiones serían:

* **dev/sda1:** para la primera partición.
* **dev/sda2:** para la segunda partición.
* **dev/sda3:** para la tercera partición.

Se puede aplicar lo mismo para las particiones de los demás discos.

### vda
dev/vda: es el primer controlador de disco paravirtualizado detectado.

Permite el acceso a aplicaciones y escritorios virtuales de Linux, desde cualquier lugar y cualquier dispositivo donde está instalada la aplicación Citrix Workspace.

Puede entregar aplicaciones y escritorios virtuales basados en distribuciones RHEL, CentOS, SUSE o Ubuntu.


## 2. ¿Cómo montar y desmontar un USB en el sistema por terminal?
Abrimos la terminal de Linux.

Una vez ahí utilizaremos el comando **_df -h_** para poder visualizar la USB y asegurarnos que la USB no
esté montada.

![2.1](https://github.com/Enrique290/Practica1.Manejo.De.Discos./blob/main/ImagenesSO/1.png)

Para empezar a montar la USB primero utilizaremos el comando **_mkdir_** para crear una carpeta con el nombre de USB (esta será la carpeta en donde se montará la USB).

Después utilizaremos el comando **_ls_** para poder visualizar que la carpeta USB ha sido creada.

![2.2](https://github.com/Enrique290/Practica1.Manejo.De.Discos./blob/main/ImagenesSO/Imagen1.jpg)

Utilizaremos el comando **_sudo -i_** para entrar al modo root para tener privilegios (nos pedirá contraseña) y ahí aplicar el comando **_mount /dev/sdb1_** y la dirección de la carpeta USB como se puede ver en la imagen.

Salimos del modo root y ponemos los comandos **ls cd usb** y **ls** para ahí poder ver la información que contiene nuestra USB montada.

![2.3](https://github.com/Enrique290/Practica1.Manejo.De.Discos./blob/main/ImagenesSO/Imagen1.jpg)

Usamos el comando **_df –h_** otra vez y podemos verificar que la USB ya aparece lo cual significa que ya está montada.

![2.4](https://github.com/Enrique290/Practica1.Manejo.De.Discos./blob/main/ImagenesSO/Imagen1.jpg)

Para desmontar la USB entramos nuevamente al modo root y ahí pondremos el comando **_umount /dev/sdb1_**.

Salimos del modo root y ponemos los comandos **_ls_** cd USB y **_ls_** para poder verificar que la USB ha sido desmontada.

![2.5](https://github.com/Enrique290/Practica1.Manejo.De.Discos./blob/main/ImagenesSO/Imagen1.jpg)

También podemos usar el comando **_df -h_** para verificar que la USB ha sido desmontada.

![2.6](https://github.com/Enrique290/Practica1.Manejo.De.Discos./blob/main/ImagenesSO/Imagen1.jpg)

## 3. Enlistar la información de los dispositivos de bloque conectados, aunque no estén montados en terminal.

Para poder enlistar la información de los dispositivos de bloque conectados que están y no están montados usamos el comando **_lsblk_**.

![3.1](https://github.com/Enrique290/Practica1.Manejo.De.Discos./blob/main/ImagenesSO/Imagen1.jpg)

Podemos desplegar diferentes tipos de tablas dependiendo de la letra que le agreguemos al comando **_lsblk_** como se muestra a continuación:
   **lsblk -a:** muestra los dispositivos vacíos.
   **lsblk -b:** muestra el tamaño de cada dispositivo en bytes.
   **lsblk -d:** Imprime los dispositivos de bloque titulares y no las particiones.

![3.2](https://github.com/Enrique290/Practica1.Manejo.De.Discos./blob/main/ImagenesSO/Imagen1.jpg)

   **lsblk -d:** muestra la tabla de permisos.
   **lsblk -o:** muestra una tabla personalizada de los dispositivos de bloque.

![3.3](https://github.com/Enrique290/Practica1.Manejo.De.Discos./blob/main/ImagenesSO/Imagen1.jpg)

## 4. Mostrar la tabla de particiones del disco donde está instalado el sistema operativo en terminal.

Primero ponemos el comando **_sudo -i_** para entrar al modo root y tener privilegios (nos pedirá nuestra contraseña).

Ponemos el comando **_fdisk -l_** para mostrar la tabla de particiones del disco donde esta instalados el sistema operativo.

![4.1](https://github.com/Enrique290/Practica1.Manejo.De.Discos./blob/main/ImagenesSO/Imagen1.jpg)

![4.2](https://github.com/Enrique290/Practica1.Manejo.De.Discos./blob/main/ImagenesSO/Imagen1.jpg)

## 5. Conectar una memoria usb (“usb”) y mostrar su tabla de particiones en terminal (hacer Respaldo antes porque se va a borrar toda la información dentro del usb en pasos posteriores).

Una vez conectada la USB ponemos el comando **_fdisk -l /dev/sdb_** para poder visualizar la tabla de
particiones de la USB en terminal.

![5.1](https://github.com/Enrique290/Practica1.Manejo.De.Discos./blob/main/ImagenesSO/Imagen1.jpg)

También podemos utilizar los comandos **_fdisk -l /dev/sda_** y **_fdisk -l /dev/sdb1_** y ahí poder visualizar una tabla de partición más específica.

![5.2](https://github.com/Enrique290/Practica1.Manejo.De.Discos./blob/main/ImagenesSO/Imagen1.jpg)

## 6. Borrar todas las particiones del “usb” en terminal.

Primero ponemos el comando **_sudo -i_** para entrar al modo root y tener privilegios (nos pedirá nuestra contraseña).

Para borrar las particiones de la USB primero debemos de usar el comando **_fdisk /dev/sdb_** para entrar al modo **_fdisk_**.

![6.1](https://github.com/Enrique290/Practica1.Manejo.De.Discos./blob/main/ImagenesSO/Imagen1.jpg)

En **_fdisk_** escribimos el comando **_p_** para imprimir la tabla de particiones y ahí podemos observar que existe una partición.

![6.2](https://github.com/Enrique290/Practica1.Manejo.De.Discos./blob/main/ImagenesSO/Imagen1.jpg)

![6.3](https://github.com/Enrique290/Practica1.Manejo.De.Discos./blob/main/ImagenesSO/Imagen1.jpg)

![6.4](https://github.com/Enrique290/Practica1.Manejo.De.Discos./blob/main/ImagenesSO/Imagen1.jpg)

![6.5](https://github.com/Enrique290/Practica1.Manejo.De.Discos./blob/main/ImagenesSO/Imagen1.jpg)





