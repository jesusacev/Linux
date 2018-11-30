Explicación de Sudo
=====================================

1. sudo
+++++++++++

Es un paquete que te permite realizar los comandos como root. Esto lo hace autorizando el acceso a los binarios de root, que estan ubicados en el directorio /sbin y a cualquier otro binario que sea propiedad de root. Tiene un archivo de configuración que está ubicado en la ruta /etc/sudoers, el cual debe tener una permisología exclusiva de 440, que si no la tiene no funcionará. Se debe editar preferiblemente con el comando visudo.

En cualquier distribución con instalación mínima esta paquete debe ser instalado.

2. su

Es un comando que te permite cambiarte a root. Si se coloca solo, se carga con las variables de entorno del usuario que lo está ejecutando, pero si se coloca acompañado del menos (-), se cargan las variables de entorno de root.

3. Diferencia entre "sudo su -" y "su -"

Los 2 comandos llegan al mismo resultado, con la acotación de que "sudo su -" te pide la clave del usuario que lo está ejecutando y "su -" te pide la clave de root.


