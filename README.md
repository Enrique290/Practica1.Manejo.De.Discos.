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

Una vez ahí utilizaremos el comando **df -h** para poder visualizar la USB y asegurarnos que la USB no
esté montada.

![Imagen1]

Para empezar a montar la USB primero utilizaremos el comando **mkdir** para crear una carpeta con el nombre de USB (esta será la carpeta en donde se montará la USB).

Después utilizaremos el comando **ls** para poder visualizar que la carpeta USB ha sido creada.

![Imagen2]

Utilizaremos el comando **sudo -i** para entrar al modo root para tener privilegios (nos pedirá contraseña) y ahí aplicar el comando **mount /dev/sdb1** y la dirección de la carpeta USB como se puede ver en la imagen.







