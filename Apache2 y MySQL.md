# Apache2

Es cuestión de usar el comando _service apache2_, nos pedirá la contraseña de usuario y mostrará los distintos comandos de apache. Recordemos que Apache2 se instalo cuando revisamos las actualizaciones y las instalamos a nuestra máquina.

```
sudo service apache2

// Para iniciar
sudo service apache2 start

// Para detenerlo
sudo service apache2 stop
```



![start-stop-apache](C:\Users\Particular\Documents\aplicaciones\ubuntu\apaches.PNG)

------





# MySQL

## Instalación y sus comandos

Su instalación es fácil; es solo de utilizar  **_sudo apt install mysql-server_**. Al hacer esto muestra los paquetes disponibles para descargar, como adicionales, sugeridos y como los nuevos que se instalaran; nos diran el total de paquetes que se instalaran y cuanto espacio usaran, después preguntará si deseamos continuar, damos _S_ para continuar, osea decir _Si_, o _N_ para cancelar.

![installSQL](C:\Users\Particular\Documents\aplicaciones\ubuntu\mysql.PNG)



Tomará tiempo en que se descargue todos los paquetes, cuando termine nos mostrara esto:

![instalado](C:\Users\Particular\Documents\aplicaciones\ubuntu\sqlinstalado.PNG) 

Usaremos el comando **_sudo su_** para poder entrar al usuario _root_ ya que, como acaba de ser instalado, no se le ha agregado ningún otro usuario y este viene por default.

Habiendo hecho esto, notaras que algo ha cambiado: ya no aparece nuestro usuario de la máquina sino **root** esto quiere decir que ya habremos ingresado a este usuario. Bien, ahora para ingresar por completo a MySQL solo hay que escribir **_mysql_** y listo, ya estaremos dentro de MySQL.



###### ¿Cómo crear un user?

```
mysql> CREATE USER 'michi'@'localhost' IDENTIFIED BY '123';

//Identified para establecer la contraseña.
```

Para hacer al usuario con los mismos derechos de _root_ usaremos este código:

```
mysql> CREATE USER 'michi'@'localhost' IDENTIFIED BY '123';

mysql> GRANT ALL PRIVILEGES ON *.* TO 'michi'@'localhost';

mysql> UPDATE user SET plugin='auth_socket' WHERE User='michi';

mysql> FLUSH PRIVILEGES;

exit
```

Después que salimos de mysql, escribimos el comando **service mysql restart** y luego **exit**; hacemos esto para poder verificar que nuestro ya fue creado así que haremos el mismo proceso de al principio: 

```
mysql

mysql> use mysql;

mysql> SELECT User, Host, plugin from mysql.user;
```



Quedaría así:

![usercreated](C:\Users\Particular\Documents\aplicaciones\ubuntu\8.PNG)

Cuando recién usamos el _select_ solo teníamos 4 usuarios, ahora tenemos los 5 con el nuevo usuario, cuenta con los mismos datos como podemos apreciar en _plugin_ que es **auth_socket**.