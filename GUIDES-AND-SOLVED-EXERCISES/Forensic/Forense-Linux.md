# Archivos de registros (LOGS)

Los logs son esencial a la hora de detectar fallos e intentar solucionarlos. Lo más recomandable es buscarlos en el directorio /var/log y listar los archivos contenidos dentro de ese directorio. Los nombres que tendrán estos archivos son auto explicativos.

```
cd /var/log && ls -la
```

```
/var/log/message //registro de mensajes del sistema
```
```
/var/log/auth.log //log de autenticación 
```
```
/var/log/kern.log //registro del kernel     
```  
``` 
/var/log/cron.log //registro de crond      
```
``` 
/var/log/maillog //registro del servidor de mails      
```
``` 
/var/log/qmail //registros de Qmail      
```
``` 
/var/log/httpd //registro de errores y accesos a Apache      
```
``` 
/var/log/lighttpd //registro de errores y accesor a Lighttpd      
```
``` 
/var/log/boot.log //registro de inicio del sistema      
```
``` 
/var/log/mysqld.log //registro de la base de datos MySQL      
```
``` 
/var/log/secure.log //log de autenticación      
```
``` 
/var/log/utmp //registro de logins      
```
 ``` 
/var/log/utmp //registro de logins
``` 


# Registros del sistema en la Terminal

Cualquier usuario, ya sea root o no, puede acceder y leer los archivos del directorio /var/log.

# Ver listado de paquetes instalados

Una de las tareas frecuentes de gestión es conocer en detalle qué elementos está instalados en un sistema operativo, esto nos ayudará para:
> - Organización de licenciamiento
> - Auditorías
> - Adquisiciones de softwares
> - Tareas de soporte y mantenimiento

Si queremos listar los paquetes que está listados en el sistema podemos hacer uso del siguiente comando:

```
dpkg-query -l
```

Si queremos exportar los paquetes instalados a un archivo txt podremos ejecutar los siguiente: 

```
Debian-y-derivados (DPKG) : $ dpkg -l > packages.txt
```

```
Debian-y-derivados (APT): $ apt list --installed > packages.txt

```
RPM: $ rpm -qa --last > packages.txt
```

```
RedHat/CentOS: $ dnf list installed > packages.txt
```

```
OpenSuSE: $ zypper se --installed-only > packages.txt
```

```
Arch: $ pacman -Q > packages.txt
```

# Comando Grep

Pertenece al entorno Linux, es una herramienta muy útil y versátil. Este busca un patrón que le indiquemos en un archivo de texto. Es uno de los principales comandos para un administrador de sistemas, porque manejan muchos servicios con varios archivos de configuración. Los administradores lo usan para consultar o buscar líneas específicas dentro de esos archivos.

Para mirar la documentación ejecuta el siguiente comando:

```
grep -help
```

> Las opciones más importantes son las siguientes

```
grep -i //la búsqueda que haga no distinguirá entre mayúsculas y minúsculas. Es decir, si quieres buscar la palabra <<netplan>> será lo mismo que <<NETPLAN>>
```

``` 
grep -c //solo muestra el número de líneas que coinciden con el patrón buscado
```

```
grep -r //habilita la búsqueda recursiva en el directorio actual
```

```
grep -n //busca líneas y precede cada línea coincidente con un número de líneas
```

```
grep -v //con esta opción, se nos muestran las líneas que no coinciden con el patrón que hemos buscado
```

## Encontrar palabra en un archivo de texto

Para buscar una palabra en un archivo de texto, ejecuta el siguiente comando:

```
grep query file
```
> - Query: la palabra que está buscando 
> - File: el archivo en el que estás buscando la palabra

- Agregar la opción –i para encontrar una palabra sin tener en cuenta las mayúsculas y
minúsculas:

```
grep -i query file
```

- Agregar la opción –c para saber cuántas veces se usa una palabra en el archivo de texto:

```
grep -c query file
```

- Admite múltiples consultas en un solo comando para buscar múltiples palabras clave:

```
grep query1 file | grep query2 file
```

- Encontrar una palabra en un conjunto de archivos:

```
grep -l word_to_search ./*
```

# Ejemplos prácticos

Se recomienda copiar los archivos importantes del sistema por si alguna vez nos pasa algo tener los archivos del sistema originales y así poder contrastar la información.

- Copiar archivo para comprobar si hay algún usuario no registrado por nosotros

```
sudo cp /etc/sudoers/ ~/firmas/sudoersoriginal
```

> Para firmar un documento podemos usar el siguiente comando:

```
sha256sum sudoersoriginal > sudoersoriginalofical.txt
```

- Copiar archivo shadow y firmarlo

```
sudo cp /etc/shadow ~/firmas/shadowsoriginal ;   sha256sum shadoworiginal > shadoworiginaloficial.txt
```

- Analizar el historial de la terminal bash y redireccionar a archivo de texto

```
cat /home/$USER/.bash_history >> historial-bash.txt
```

- Analizar el historial de la terminal ZSH y redireccionar a archivo de texto                                                                                                   ```                                                                                     
cat /home/$USER/.zsh_history >> historial-zsh.txt                                     
```  

- Analizar entorno de red y guardarlo en un archivo txt. Primero necesitamos instalar las net-tools y luego redireccionar la información a un archivo txt de la siguiente manera: 

```
sudo apt install net-tools
```

```
netstat -an >> red.txt
```

- Para analizar y realizar diagnóstico de las interfaces ejecutaremos lo siguiente

```
dig >> red.txt
```

```
route >> red.txt
```



 




7







