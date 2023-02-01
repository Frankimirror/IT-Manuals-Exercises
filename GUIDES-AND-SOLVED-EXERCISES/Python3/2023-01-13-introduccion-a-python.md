---
layout: single
title: INTRODUCCIÓN A PYTHON
excerpt: "¿Quieres aprender a instalar python 3.16? Estás en el artículo adecuado. Aquí podrás aprender cómo instalar Python en una máquina Linux, además de PIP y de CLI sin ninguna complejidad. En próximos artículos enseñaré cómo escribir sencillos programas con python "
date: 2023-01-13
classes: wide
header:
  teaser: /assets/images/articulos/python-art.png
  teaser_home_page: true
  icon: /assets/images/articulos/python.png
categories:
  - Programación
toc: true
tags:
  - Python
comments: true
---

# INSTALACIÓN Y CONFIGURACIÓN DE PYTHON 3.16

Para instalar python, necesitarás un ordenador con conexión a internet, con sistema operativo basado en Unix o en Windows. Yo usaré una distribución Linux, Parrot OS. 

- Abrimos nuestra terminal y escribimos el siguiente comando

```go
┌─[francmirror@parrot]─[~]
└──╼ $ sudo apt install -y software-properties-common
```
- Actualizamos los paquetes

```go
┌─[francmirror@parrot]─[~]
└──╼ $ sudo apt update -y ; sudo apt upgrade -y
```

- Añadimos los siguientes repositorios:


```go
┌─[francmirror@parrot]─[~]
└──╼ $ sudo add-apt-repository -y ppa:deadsnakes/ppa
```

- Renovamos el caché, luego encontraremos cuál es la última versión que podemos descargar:

```go
┌─[francmirror@parrot]─[~]
└──╼ $ sudo apt update && sudo apt-cache search python3.1
```

- Como podemos ver, la última versión es la 3.16, por lo que ahora ejecutaremos el siguiente comando:

```go
┌─[francmirror@parrot]─[~]
└──╼ $ sudo apt install python3.16 -y
```

- Ahora procederemos a instalar pip:

```go
┌─[francmirror@parrot]─[~]
└──╼ $ curl -O https://bootstrap.pypa.io/get-pip.py && python3 get-pip.py
```

- Comprobamos la versión de pip:

```go
┌─[francmirror@parrot]─[~]
└──╼ $ pip --version
```

- Usamos pip para instalar la CLI de EB

```go
┌─[francmirror@parrot]─[~]
└──╼ $ pip install awsebcli --upgrade --user
```

## IDE 

Para trabajar con python necesitaremos hacer uso de un Entorno de Desarrollo Integrado. En mi caso usaré Visual Studio Code ya que en mi opinión en mis IDE favorito porque es más friendly con el usuario que empieza en el mundo de la programación. Solo tendremos que descargarlo de su página oficial:

- [https://code.visualstudio.com/](Visual Studio Code)

Con esto, ya estás preparado para iniciar y trabajar con python, podrás tener información y documentación de este lenguaje de programación gracias a mi pdf “Cheat Sheet Python3”. Gracias por tu tiempo!!!


































