# Instalación de Ubuntu 18.04

## En Virtual Box

Es sencillo, damos clic en **"Nueva"** y ponemos el nombre de la máquina, el tipo de sistema operativo y la versión, luego seleccionamos la cantidad de memoria que le pondremos de memoria **2048 mb** y dejando la opción de crear el disco virtual ahora, también el tipo de archivo y en reservado dinámicamente. Después solo pondremos **20 GB** de memoria de disco duro y creamos.

> Importante: Para la instalación de cualquier máquina virtual en VB se necesita de una imagen ISO que podemos descargar en internet.

Antes de iniciarlo, iremos a configuración y en la parte de *Red* dejamos al primer adaptado como NAT y habilitamos un segundo adaptador de red, solo que este será **Adaptador sólo-anfitrión**. Deseleccionamos el disquete en *Sistema* en la parte de Orden de arranque. Bien, ahora solo faltaría ir a Herramientas Globales y asegurarnos que en *Propiedades* en la parte de Servidor DHCP este habilitada; habiendo hecho todo esto, ahora sí, podemos dar en Iniciar la máquina.

> Nota: También, para que nuestra máquina no sea tan lenta podemos dejarle dos procesadores en el apartado de *Sistema*; con que no pase del límite de procesadores (o sea que llegue en rojo) esta bien.

![collage2](C:\Users\Particular\Documents\aplicaciones\ubuntu\collage2.jpg)

Una vez que haya cargado, iniciaremos con lo básico como el configurar el idioma, el del teclado y después nos viene la opción de Instalar Ubuntu donde obviamente daremos Enter. En *configuración de sistema de archivos* damos enter en Manual, una vez abierto damos enter en el dispositivo disponible que tenemos que es del virtualBox, luego damos enter en Add Partition damos un tamaño de **7.998 G** y damos en Create. Luego creamos otra partición con el espacio sobrante **(1.999 G)** y en formato cambiamos a **swap**. Luego damos enter en Hecho y en continuar para confirmar.

Después crearemos la cuenta dando nuestro nombre y el nombre de usuario junto a su contraseña; cuando terminemos tendremos que esperar un rato mientras se instala el sistema. Una vez terminado Ubuntu tardara en cargar, iniciamos sesión con nuestro usuario y contraseña.

Y con esto ya habríamos ingresado y por ende terminado la instalación de Ubuntu 18.04.

------

### Comandos

Existen comandos básicos como **_clear_** para limpiar la pantalla cuando se sutura de código, así como **_shutdown_** para apagar el sistema, tambien es

- **_Clear_**: Para limpiar la pantalla cuando se sutura de código la terminal.
- **_Shutdown_**: Para apagar la máquina.
- **_ls_**: Es una lista; nos muestra el contenido de la carpeta que estaremos usando.
  - **_-a_**: Muestra cada archivo que hay incluso los archivos ocultos, (que por cierto, empiezan por un **.** al principio. Ejem. .archivooculto).
  - **_-l_**: Vendría siendo casi lo mismo que el -a solo que este muestra información de los archivos de una forma muy detallada, como la fecha de creación, tamaño o ultima vez que fue editado.
- **_cd_**: Cambiar directorio o carpeta en la terminal.
- **_rm_**: Eliminar archivos o directorios que se le indica.
- **_mv_**: Mover un archivo a una ubicación que se le indica.
- **_sudo_**: Es un súper usuario; permite ejecutar acciones con los privilegios de seguridad del root.
- **_apt_**: Para gestionar los paquetes instalables disponibles en los repositorios, ya que es una herramienta de paquetes.

#### Para descargar actualizaciones

Es muy importante hacer este paso cuando recién instalamos Ubuntu. Con los siguientes comandos:

```
set apt-get update
```

podemos ver todas las actualizaciones que podemos instalar, pero con este comando _update_ solo podemos ver las actualizaciones, no instalarlas. Para esto usaremos **_upgrade_**, quedaría así:

```
set apt-get upgrade
```

