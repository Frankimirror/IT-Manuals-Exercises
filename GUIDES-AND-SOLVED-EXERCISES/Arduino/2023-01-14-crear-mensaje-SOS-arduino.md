## Primeros pasos
Supongamos que tienes una situación de emergencia y necesitas mandar un mensaje SOS en código morse para pedir un rescate y que da la casualidad que en tu mochila llevas un kit de arduino, ¿Cómo podrías crear este mensaje? En el tutorial de hoy vamos a ver paso a paso como vamos a crear esto mensaje y cómo nuestro arduino ejecutará el código que crearemos, ¡Comencemos!

## Materiales
Necesitaremos los siguientes materiales para empezar a rodar:

![](/assets/images/articulos/mensajesos/foto1.jpg)

1. Cable USB
2. Arduino (yo usaré el elegoo uno r3)
3. 9V Battery with Snap-on Connector clip
4. LED
5. [Arduino IDE](https://www.arduino.cc/en/software)

## Funciones de cada componente

- **Cable USB**: este cable lo usaremos para conectar nuestro arduino al ordenador para configurarlo con su IDE oficial
- **9V bateria con Snap-on Connector clip**: no es esencial, pero así podremos usarlo en la calle y en cualquier sitio sin necesidad de tener corriente ni ordenador cerca nuestra.
- **LED**: lo usaremos para que el código morse SOS se vea bien 

## Creamos el código

Ahora, ya que tenemos los componentes y el IDE de arduino instalado, solo nos quedará desarrollar el código. Lo primero para hacer el código SOS en morse, es conocer como es la S y la O en este código. Es muy sencillo, **la S son tres pulsos cortos (S = - - -)** y **la O son tres pulsos largos (O = * * * )**. Ahora vamos a crear poco el código, podrás encontrar la versión completa [pinchando aquí](https://github.com/FrancMirror/Projects-for-arduino/blob/main/sos-morse/sos-morse.ino)

- Primero vamos a definir el pin LED y lo inicializamos
  
```bash
// Define LED pin
int led = 13;

// Initialization
void setup(){
  pinMode(led,OUTPUT);
}

void loop() {
```

- Ahora vamos a crear la letra S, que como hemos dicho antes, en el código morse son tres pitidos cortos, esto lo haremos  lo definiremos de la siguiente manera:
  
```bash
for (int x=0; x < 3 ; x++){
   digitalWrite(led, HIGH);
   delay(150);
   digitalWrite(led, LOW);
   delay(100);
}
```
- Dejamos un delay para que se note que hay un cambio de letra

```bash
delay(100);
```
- Ahora vamos a emitir la O, que como hemos dicho antes, en el código morse son tres pitidos largos, esto lo haremos  lo definiremos de la siguiente manera:

```bash
for (int x=0; x<3 ; x++){
   digitalWrite(led, HIGH);
   delay(400);
   digitalWrite(led, LOW);
   delay(100);
}
```

- Ahora, vamos a dejar otro pequeño delay para un espacio entre la O y la última S y volveremos a escribir la letra S:

```bash
delay(100);

// letter S
for (int x=0; x < 3 ; x++){
   digitalWrite(led, HIGH);
   delay(150);
   digitalWrite(led, LOW);
   delay(100);
}
```

- Con esto, nuestro código ya tendríamos el mensaje SOS en morse hecho, por último, dejamos otro delay entre mensajes SOS de la siguiente manera:

```bash
delay(2000);
```

## Conectar componentes
Ahora vamos a conectar los distintos componentes. Primero, conectamos nuestra pila al arduino, para darle energía.

![](/assets/images/articulos/mensajesos/foto2.png)

Para conectar el LED, tendremos que tener en cuenta su polaridad, para explicarlo de manera sencilla, la pata más corta estarás situada a la derecha y la larga a la izquierda, tendrá que quedarnos de la siguiente manera:

![](/assets/images/articulos/mensajesos/foto3.png)

## Pruebas

Ahora que tenemos todo conectado, solo ejecutaremos este codigo en nuestro arduino y si todo lo hemos hecho bien tendrá que quedarnos algo cómo el siguiente video:

![](/assets/images/articulos/mensajesos/video1.gif)


