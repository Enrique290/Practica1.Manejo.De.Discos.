# Practica1.Manejo.De.Discos.
## 1. Identificar y describir las diferencias entre hda, sda y vda, además explicar qué significa la letra y el número al final de los identificadores (no requiere captura de pantalla).

### hda
dev/hda : es el disco maestro en el controlador IDE primario.

En el cual la letra del final, puede cambiar y verse de la siguiente manera:
* **dev/hda:** disco maestro en la primera controladora
* **dev/hdb:** disco esclavo en la primera controladora
* **dev/hdc:** disco maestro en la segunda controladora
* **dev/hdd:** disco esclavo en la segunda controladora

Además, puede estar numerado según las particiones que tenga:
