
# Ficheros 
 
- cat -> muestra el cotenido de fichero (y concatena)
```
cat fichero.txt
```

- more -> muestra contenido de forma paginada
```
more fichero.txt
```

- less -> similar a more 
```
less fichero.txt
```

---

# Copiar y mover ficheros

- cp -> copiar ficheros y directorios
```
cp fichero1 fichero2
cp -r carpeta1 carpeta2
```

- mv -> mueve ficheros y directorios y renombra archivos
```
mv fichero1 drectorio1
```

---

# Creación borrado de archivos y directorios

- mkdir -> crea directorio
```
mkdir directorio
```

- rm -> borra archivos y directorios
```
rmdir directorio (si está vacio)
rm -r directorio
rm archivo
```

---

# Carácteres especiales:

- * -> representa cualquier cadena de carácteres
- ? -> representa cualquier carácter simple
- [--] -> uno o más carácteres de los incluidos entre corcherte  
- ! -> exclusión de carácteres

----

# Cadenas de texto

- touch -> crea un archivo de texto
- grep -> muestra las línea del fichero en las que aparece una subcadena indicada como patrón
- sort -> ordena líneas del fichero de entrada 
- head -> muestra las primeras líneas de  un fichero
- tail -> muestra las últimas líneas de  un fichero
- wc -> cuenta el número de palabras, líneas o carácteres de un fichero
- paste -> concatena línea a línea los ficheros de entrada
- cut -> escribe en la salida estándar secciones de cada del fichero de entrada

---

# Archivos del host

- uname -> muestra información del sistema
```
uname -a
```

- file -> indica naturaleza de un fichero (fichero de texto, binario ejecutable...)
- who -> muestra los usuarios conectados al sistema
- whoami -> nombre del usuario actual
- hostname -> muestra el nombre del equipo

---

# Redirección y tuberías

- stdin (standard input) -> entrada estándar
- stdout (standard output) -> salida estándar
- El terminal virtual por defecto toma como stdin el teclado y  
como stdout la pantalla
- > -> envía la salida a un fichero (destruye contenido anterior)
- >> -> envía señal (añade al contenido anterior).
- < y << -> toman la entrada de un fichero (en vez de teclado)
- Se pueden conectar más de dos comandos:
```
ls | sort -r  
ls /home/francmirror | less  
ls /home/francmirror | sort -r | less
```

---

# Tipos de archivos

- (-) -> para archivos normales
- (d) -> para carpetas
- (I) -> para enlaces
- (s) -> socket
- (p) -> tubería
- (b) -> dispositivo de bloque

---

# Permisos en UNIX/Linux

### Números de permisos

- 0 -> Sin permisos

- 1 -> Ejecución

- 2 -> Escritura

- 3 -> Lectura y escritura

- 4 -> Lectura

- 5 -> Lectura y ejecución

- 6 -> Lectura y escritura

- 7 -> Lectura, escritura y ejecución

## Letras de permisos

- Permiso de lectura (r, read)
- Permiso de escritura (w, write)
- Permiso de ejecución (x, eXecute)

## Asignación de permisos

> Los permisos se le otorgan a:
> El usuario propietario del archivo
> El grupo propietario del archivo
> El resto de usuarios del sistema

- ls -l -> se ven los permisos de los directorios y archivos que contiene.
- chmod -> comando para cambiar los permisos de un archivo o directorio. 
- chown -> cambiar el propietario. Sirve tanto como para grupos como usuariarios
- chgrp -> cambiar el grupo principal

---

# Búsqueda

- find -> comando para realizar búsquedas
- fzf -> comando para realizar búsquedas

---

# Empaquetar y comprimir

- tar -> comando para empaquetar archivos
	- -c -> empaqueta el archivo
	- -x -> desempaqueta el archivo
	- -v -> muestra lo que contiene el empaquetado
- gzip -> comprime archivos en formato .gz
	- -d -> descomprimir

---

# Montar y desmontar unidades

- mount -> puede montar sistemas de ficheros y anclarlos a puntos de montaje (directorios) 
```
mount /dev/sdb1 /media/pendrive
```

- umount -> desmonta la unidad
``` 
umount /media/pendruve
```

---

# Apagado y reinicio

- logout -> cerrar sesión
- shutdown -> apagar sistema
- reboot -> reiniciar sistema

---

# Gestión de usuarios y grupos

- adduser -> crear un usuario
- groups -> Mostrar grupos a los que pertenece un usuario
- groupadd -> crear un grupo
- usermod -> modifica el usuario elegido. Con él, puedes cambiar el nombre del usuario, su carpeta /home, grupos a los que pertenece, etc.
- userdel/deluser -> elimina el usuario escogido.
- chfn -> cambia información de un usuario
- id -> muestra el uid, el gid y los grupos a los que pertenece el usuario.
- groupdel -> elimina el grupo

>Configurar contraseña para que caduque en 40 días
```
sudo passwd -x 40 -w 1 usuario
sudo chage --list usuario
```

---

# Control de procesos

- ps -> muestra los procesos en ejecución
- kill "pid" -> finaliza un proceso
- killall "nombre-proceso" -> finaliza un proceso junto con todos los subprocesos.
- nice -> lanza un proceso con una prioridad determinada
- renice -n -> cambia la prioridad de un proceso en ejecución
- & -> al final del comando, se usa para lanzar en segundo plano el comando
- bg -> lista los trabajos en segundo plano
- fg -> trae los trabajos más recientes a primer plano.
- jobs -> lista los trabajos solo del terminal en el que estamos trabajando, apareciendo todos los procesos corriendo en primer y segundo plano.
- ctrl+z -> pausa el trabajo en curso
- ctrl+c -> finaliza el trabajo en curso

---

# Monitorización y registros

- top -> muestra una lista de procesos en tiempo real,  
permitiendo realizar varias acciones sobre ellos: matarlos,  
cambiar prioridad, y mostrando además información sobre  
el uso de los recursos consumidos (CPU, RAM, etc.)
- htop -> similar a top, pero además permite ordenar los  
procesos por parámetros, como el uso de CPU y RAM  
(hay que instalarla, no viene por defecto)