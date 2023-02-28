# Qué es
Electronic mail o en Español, correo electrónico, es un servicio de red que permite a los usuarios enviar y recibir mensajes electrónicos mediante redes de comunicación electrónica.  Este servicio es muy similar al correo postal, los dos pueden enviar y recibir mensajes y se utilizan buzones para almacenar estos correos. Por medio del correo electrónico se puede enviar no solamente texto, sino todo tipo de archivo digitales, aunque suele existir limitaciones en cuanto al tamaño de los archivos adjuntos . 

Los sistemas de correo electrónico se basan en un modelo de almacenamiento y reenvío, de modo que no es necesario que ambos extremos se encuentren conectados en el momento. Para esto, se emplea un servidor de correos que realiza las funiones de intermediario, guardando temporalmente los mensajes antes de enviarse a sus destinatarios. Las ventajas del correo electrónico son las siguientes:

- Seguridad: ofrece una mayor seguridad, incluso hay tipos específicos de correo con seguridad extra (SMTPS, POP3S...)
- Eficiencia: puede llegar a muchos más usuarios, ya que un solo correo se puede enviar a muchísimas personas en un corto periodo de tiempo. 
- Rapidez: un correo electrónico puede tardar entre medio segundo en llegar a su destino.
- Precio: suele ser de 0, si cuentas con un ordenador e internet (cosa común hoy en día), empresas como google tienen este servicio gratuito.
---
# Cuando surgió
El correo electrónico surgió antes de la creación de internet. El primero registro que tenemos de esto es del año 1962, cuando el instituto Massachusetts Institute of Technology adquirió un ordenador de tiempo compartido modelo IBM 7090, que permitía a varios usaurios iniciar sesión desde terminales remotas, y así guardar archivos en el disco. Este sistema se utilizó para intercambiar mensaje pero ya en 1965 se desarrolló el servicio **MAIL**, que facilitaba el envío de mensajes entre los usuarios del ordenador.

El primer correo electrónico enviado a través de una red nos consta que fue en el 1971. Este mensaje conteía únicamente el texto "QWERTYUIOP", se envió a través de la red ARPANET. Fue Tomlinson quien incorporó el uso de "@" para dividir el usuario y el ordenador que aloja la cuenta del usuario de destino. Este símbolo se eligió porque en inglés la arroba se lee «at» (en español en). Así, la dirección  ejemplo@ordenador.com se lee ejemplo en ordenador punto com.

En los próximos años se definión diferentes estándares, a continuación expondré los más importantes:
- En 1977, se creó el estándar del correo electrónico (RFC 733). 
- En 1982 surgió el estándar del SMTP (RFC 822).
- En 1984 surgió el estándar del POP (RFC 918).
- En 1992 se incluyeron los MIME

---

# Cuentas de correo y buzones
Para poder y recibir un correo es necesario tener una cuenta de usuario en un servidor de correo o una dirección de correo electrónico. La mayoría de veces, el proveedor de correos, el ISP o el proveedor de tu hosting tiene la opción de tener una cuenta de correo en sus servidores desde un programa de lectura de correo, el cuál se le suele llamar cliente de correo, MUA (Mail User Agent), por ejemplo thunderbird. Las cuentas de correo tienen dos partes:
- El nombre del usuario
- El nombre o dirección IP del servidor de correo electrónico
Ambas partes tienen que estar separadas por el símbolo "@" y en total el correo no debe sobrepasar los 256 carácteres.

Los buzones son subcarpetas del sistema de correo electrónico del usuario, en dónde se almacenan los mensajes recibidos, por lo que pueden ser distintas cuentas de un mismo usuario, carpetas de una misma cuenta, o distintos usuarios en un servidor de correo concreto. Dichas carpetas pueden ser reales o virtuales. 
---
# Cómo funciona
Voy a exponer un caso para mostrar el funcionamiento básico del servicio de correos:
> Alonso (alo@alo.es) envia un correo electrónico a Pineda (pinedilla@pineda.com). Cada uno de estos usuarios tiene su cuenta de correo electrónico en un servidor distinto (Alonso en **alo.es** y Pineda en **pinedilla.com**), pero esto no es un impedimento, porque entre ellos podrán intercambiar mensajes sin problemas.

Los pasos que realiza son los siguientes: 
1. Alonso escribe el correo en su cliente de correo electrónico. Cuando este envía el mensaje, el programa hace contacto con el servidor de correo usado por Alonso (smtp.alo.es). Se comunica usanndo el protocolo SMTP (Simple Mail Transfer Protocol). Le transfiere el propio correo y da la orden de enviaro.
2. El servidor smtp.alo.es debe entregar un correo a un usario del dominio pinedilla.com, pero no sabe con qué ordenador tiene que comunicarse. Para ello, realiza una consulta al servidor DNS de su red, usando el protocolo DNS (Domain Name System). Técnicamente, lo que le pregunta exactamente es sobre el registro MX asociado a este dominio.
3. La respuesta que obtiene es el nombre de dominio del servidor de correo de Pineda. en este caso es **mx.pineda.com**. 
4. El servidor SMTP (smtp.alo.es) ya puede conectarse con mx.pineda.com y transferirle el mensaje, que quedará guardado en este ordenador. Se vuelve a usar el protocolo SMTP.
5. A continuación, cuando Pineda inicie su MUA (cliente de correo), su ordenador inicia una conexión mediante el protocolo POP3 o IMAP, el servidor que guarda los correos nuevos que le han llegado. Este ordenador (pop3.pineda.com) es el mismo que el del paso anterior (mx.pineda.com), ya que se encarga tanto de recibir correos del exterior como de entregárselos a sus usarios. En el esquema, pineda se descargar el mensaje de Alonso  mediante el protocolo POP3.
---
# Agentes
Los servicios de correo electrónico se basan en un modelo cliente-servidor y pueden usarse en cualquier tipo de red TCP/IP. En el proceso de envío y recepción de correo electrónico participan tres tipos de programas:
- MTA: Mail Transport Agent (Agente de Transferencia de Correo) es un software que transfiere correo electrónico de un ordenador a otro, es el servidor SMTP el que envía el mensaje.
- MDA: Mail Delivery Agent (Agente de Entrega de Correo) es un software que acepta correo entrante y lo distribuye a los buzones de los destinatarios o lo reenvía a un servidor MTA.
- MUA: Mail User Agent (Cliente de Correo Electrónico): es el que permite enviar, recibir y editar correos.
---
# Formato del mensaje de correo
La mayoría del software que se usa en el transporte de correo hoy en día, usa un formato de cabecera definido en el RFC 822, que se estableció en 1982. Su labor principal era especificar un estándar para usar en la red ARPANET. Los mensajes de correo electrónico deben llevar una cabecera y un cuerpo. La cabecera tiene que llevar una serie de campos. Los básicos son:
- Remitente (De X FROM): quién envía el correo, cuenta de correo electrónico delemisor del mensaje. 
- Destinatario (Para X TO): correo electrónico del destinatario.
- Destinatario de copia (CC): campo opcional, que permite que enviemos correos electrónicos hasta a 256 destinatarios, separados entre sí por "," o por ";".
- Destinatario de copia oculta (CCO o BCC): tiene la misma utilidad que el campo CC, solo que envía los correos a los destinatarios sin que estos puedan ver las demás direcciones.
- Responder (REPLY TO): campo opcional que lleva la dirección a la que queremos que nos respondan. 
- Fecha (DATE): en este campo se reflejan la fecha y la hora del sistema emisor del mensaje.
- Tema (SUBJECT): en este campo se reflejan la fecha y la hora del sistema emisor del mensaje.