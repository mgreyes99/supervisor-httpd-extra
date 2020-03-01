# supervisor-httpd-extra



Este es un Centos7 con Docker , el cual incluye supervisor , el servidor web HTTPD y un servidor  FTP , en este caso al ser sistema Centos seria un vsftpd

 ##Credenciales de sesión
> Usuario: www

> Contraseña:iaw

Puede cambiarlos utilizando las variables de entorno USUARIO y CONTRASEÑA. Ejemplo:

### docker run -d -p 80:80 -p 9001: 9001 -e USUARIO = mi nombre de usuario -e CONTRASEÑA = mi contraseña mgreyes/supervisor-httpd-extra

## Credenciales de supervisor en interfaz web :

> nombre de usuario : www

> contraseña : iaw

# Incluido en este  repositorio 

**bootstrap.sh**
El cual es un boot , para iniciar el supervisor , el cual arranca en primer plano , ademas incluido van los otros servicios mediante la instalacion .

# Configuracion de Supervisor
 Los ficheros de configuracion estan dentro de **/etc/supervisor.d/***  , para gregar nuevos programas se debe de crear el fichero de configuracion , debe tener el nombre del servicio + .conf por ejemplo = **httpd.conf** y se especifica el nombre del programa y su arranque , de esta manera:
 
 ``` 
 [program:httpd]
 command=/usr/sbin/httpd -D FOREGROUND 
 ```
# Hacer la ejecución de Dockerfile

Se debe utilizar el siguiente comando 
```
docker build -t mgreyes/supervisor-httpd-extra .
``` 

# Autor
**Autor:** Maykin Reyes
**Email:** mgreyes@ilg.cat
