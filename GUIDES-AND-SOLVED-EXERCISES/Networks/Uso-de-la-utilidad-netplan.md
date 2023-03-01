# ¿Qué es netplan?

Netplan es una herramienta para configurar de manera sencilla nuestras redes en nuestra distribución favorita Linux. Netplan usa YAML (es un lenguaje de serialización de datos que suele utilizarse en el diseño de archivos de configuración) para crear una descripción de las interfaces de red que tenemos y para configurar cada una de ellas. A partir de esta descripción que le asignemos, Netplan generará una configuración necesaria para la herramienta de renderización elegida.

> El archivo de configuración podemos encontrarlo en el directorio **/etc/netplan** 

# Sintaxis para Netplan

Tenemos que tener en cuenta que todos los ficheros netplan siguen un estándar y para ello tenemos que empezar poniendo correctamente los encabezados para que puedan ser tratados por la aplicación sin que nos de un error

```
network:
    version: 2
    renderer: [networkd or NetworkManager]
```

> Por defecto, Ubuntu desktop utilizar para rederizar la red "Network Manager", sin embargo, Ubuntu Server hace uso de "networkd".

Ahora, tendremos que especificar en el fichero el tipo de configuración que vamos a realizar: 
- Si solo queremos configurar una o varias usaremos "ethernets",.
- Si solo vamos a crear un bonding con dos o más interfaces de red para que trabajen como una sola, escribe "bonds".
- Si lo que vamos a crear es una vlan escribiremos "vlans".

# Ejemplo con una LAN

Si queremos configurar una dirección LAN estática tendremos que tener en cuenta lo siguiente:

```
network:
  ethernets:
    enp3s0:
      addresses: 
      - 192.168.1.20/24
      nameservers:
        addresses: []
        search: []
  version: 2
``` 

# Ejemplo con DHCP automático

Si queremos que nuestra interfaz de red tenga un DHCP automático, tendremos que configurarlo de la siguiente manera:

```
network: 
  ethernets:
    enp0s3:
      dhcp4: true
  version: 2
```

# Probar la configuración

Antes de aplicar los cambios, probaremos el archivo de configuración que hayamos creado. Solo necesitaremos ejecutar el siguiente comando: 

```
sudo netplan try
```

Si queremos aplicar la configuración ejecutaremos lo siguiente:

```
sudo netplan apply
```

Si por algún motivo tuvieramos un error, podemos hacer un debugging

```
sudo netplan --d apply
```

# Reiniciar servicios en red

Si estamos en Ubuntu server y estamos haciendo uso de networkd, escribiremos 
el siguiente comando:

```
sudo systemctl restart system-networkd
```

Si estamos utilizando Ubuntu Desktop y estamos haciendo uso de network-manager, necesitaremos ejecutar lo siguiente:

```
sudo systemctl restart network-manager
```

Ahora para verificar si las configuraciones se han realizado correctamente podemos verificarlo con el siguiente comando:

```
ip a
```

O si por lo contrario tenemos las herramientas de net-tools, podemos usar el comando ipconfig. Si queremos instalar net-tools, lo instalaremos de la siguiente manera:

```
sudo apt install net-tools
```



