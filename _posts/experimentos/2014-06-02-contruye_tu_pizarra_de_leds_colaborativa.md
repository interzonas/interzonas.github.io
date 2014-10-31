---
layout: entrada
category: post
title: Contruye tu pizarra de leds colaborativa
subtitulo: Hirikilabs / Donostia
date: 2014-10-30 11:21:04
tipo: experimentos
categories: experimentos
image: leds-x.png
published: true
big: 1
columna: 0
menu: "<div class=\"col-sm-3 hidden-xs columna-rigth\"> <div class=\"mon affix-top\" data-spy=\"affix\" data-offset-top=\"250\" data-offset-bottom=\"3000\"><div class=\"menu-lateral-wrapper\"><h3 class=\"title-menu-lateral\">Menú</h3><ul class=\"menu-lateral\"><li><a href=\"#componentes\">Componentes</a></li><li><a href=\"#montaje\">Montaje</a></li><li><a href=\"#raspberry\">Raspberry pi</a></li><li><a href=\"#arduino\">Arduino</a></li><li><a href=\"#nodejs\">Nodejs</a></li><li><a href=\"#firebase\">Firebase</a></li></ul></div><div class=\"wrapper-contacto\"><p>Si estas interesado en organizar un taller o tienes cualquier duda:</p><a class=\"btn btn-orange btn-primary\" href=\"mailto:hola@interzonas.info?subject=Contacto desde Interzonas-labs\" role=\"button\">Escríbenos</a></div></div></div>"


---

En este tutorial te mostraremos como hemos montado en Interzonas una pizarra de leds para que cualquiera desde internet pueda pintar en ella y en tiempo real.

<!--mas-->

En [interzonas](http://labs.interzonas.info/) cuando empezamos a okupar un pedazo de oficina de [biko](http://www.biko2.com/) se nos planteo un reto, de hecho un gran reto. Biko es una emprea que abraza la metodologia de desarrollo agil y su sistema organizativo se basa en equipos autogestionados. Estos equipos tiene su propio nombre he icono que cuelgan del techo.

<div class="img-wrapper">
  <img src="{{site.url}}/images/matrix/carteles_biko.png" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Carteles equipo biko</div>
</div>

¿Que podíamos hacer para que el cartel de interzonas fuera especial?
Después de darle unas vueltas lo vimos claro. Una pantalla de led que pudieramos pintar a nuestro antojo, claro todo controlado por una web, en tiempo real y colaborativo.
El resultado final:

<iframe width="660" height="500" src="//www.youtube.com/embed/ZvB0OpAjqis" frameborder="0" allowfullscreen></iframe>

Como se puede ver en el vídeo, hemos conectado un arduino a una pantalla de leds y una reapberry a este arduino. La raspberry esta conectada a internet con un usb wifi, y es mediante las raspberry como nos comunicamos con el arduino que manda la información para encender y apagar los led.

La idea desde el principio era usar raspberry para poder instalar nodejs y que hiciera de demonio (Oreja que dice [Aitor](http://twitter.com/aitor_rl)) Después de unas pruebas vimos interesante usar el proyecto [Firebase](http://firebase.com) para la persistencia de datos y el tiempo real, ya que nos evitaba tener  mantener una base de datos propia.

Nos interesaba tener un interfaz web/humano/maquina, un sistema de donde "cosas" escuchan en internet y actúan en consecuencia y no al revés intentar conectarnos a las cosas desde internet, que siempre da problemas.

<!--Componentes-->
<a name="componentes"></a>
<h2 class="title-big-seccion">Componentes del pizarra leds</h2>

Estas son las piezas que hemos usado para montar la pizarra.

* Fuente de alimentación 5v mínimo 2 Amperios
* Cable Mini usb
* Jumpers Hembra
* Raspberry Pi
* Arduino
* Tornillo largos y tuercas
* placa de metacrilato
* Pantalla led 16x32 Adafruit (Se puede hacer con otros sistemas)


<div class="img-wrapper">
  <img src="{{site.url}}/images/matrix/pantalla_alante.jpg" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Nuestra pantalla elegida</div>
</div>

<div class="img-wrapper">
  <img src="{{site.url}}/images/matrix/ArduinoUno_R3_Front_450px.jpg" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Arduinio</div>
</div>

<div class="img-wrapper">
  <img src="{{site.url}}/images/matrix/raspberry.jpg" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Raspberry pi</div>
</div>

<!--fin-->

<!-- montaje-->
<a name="montaje"></a>
<h2 class="title-big-seccion">Montaje</h2>

El montaje y los componentes son parte del experimento que realizamos, el mismo resultado se podría obtener de formas diferentes pero este fue el que mejor resultado nos dio.

Estas diferentes partes del desarrollo

* **Caja**: Queríamos poder contener todos los elementos en la propia pantalla.
* **Fuente de alimentación**: La fuente tiene que alimentar a la raspberry, al arduinio y a la pantalla.
* **Cableado botonera**: Montaje y cableado de la botonera.
* **Conexiones**: Las conexiones entre arduino y la pantalla.


<h3 class="title-post-seccion">Caja</h3>

Como queremos poder colgar la pantalla desde el techo y no queríamos que subiera más el cable de alimentación se nos ocurrió que podíamos usar la trasera de la pantalla como "contenedor" de los componentes. En esta serié de fotos podemos ver el proceso


<div class="img-wrapper">
  <img src="{{site.url}}/images/matrix/pantalla1.jpg" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Pantalla y lamina de metacrilato</div>
</div>

<div class="img-wrapper">
  <img src="{{site.url}}/images/matrix/pantalla2.jpg" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Colocación del metacrilato con unos tornillos largos y unas tuercas para que hagan de limite</div>
</div>

<div class="img-wrapper">
  <img src="{{site.url}}/images/matrix/pantalla3.jpg" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Vista detalle metacrilato y tornillos</div>
</div>

<div class="img-wrapper">
  <img src="{{site.url}}/images/matrix/pantalla_atras.jpg" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Resultado final</div>
</div>


<h3 class="title-post-seccion">Fuente de alimentación</h3>

Para la fuente de alimentación se necesita que de una tensión de 5V y mínimo dos amperios, ya que para los colores vivos, sobre todo el blanco requiere de mucha potencia. El cableado es simple un conector microusb para la raspberry py e hicimos un empalme para con el conector de la pantalla.

<div class="img-wrapper">
  <img src="{{site.url}}/images/matrix/soldadurafuente.jpg" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Soldando el conector de la pantalla y el conector microusb a la fuente de alimentación</div>
</div>

Para la conexión de arduino lo simplificamos mucho conectamos el usb de Arduino al usb de la raspberry pi, de esta manera alimentamos el Arduinio y a su vez trasmitimos los datos de internet a la pantalla

<div class="img-wrapper">
  <img src="{{site.url}}/images/matrix/usbarduino.jpg" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Conexión del usb Arduino al usb raspberry</div>
</div>


<h3 class="title-post-seccion">Raspberry pi</h3>

Intentamos con las rapberry poder pintar en la pantalla pero vimos que el controlador de la misma funcionaba mucho mejor en arduinio. Pero teníamos claro que para la conectividad de la pantalla era obligado usar raspberry, con arduino se puede pero los shield de conexión, son caros y tediosos. Así que en esta configuración tenemos una instalación básica con la distribución [Raspian](http://www.raspberrypi.org/downloads/)

Para la conectar la raspberry usamos un "pintxo" usb wifi [aquí](http://geekytheory.com/tutorial-raspberry-pi-configurar-wif/) un buen tutorial de como hacerlo. Con esto solo nos falta configurar el usb al arduinio

Y configurar con upstart el arranque automatico del demonio de nodejs, aqui el fichero serialmatrix.conf que va a /etc/init

<script src="https://gist.github.com/karlosgliberal/cd0d96b144298e097970.js"></script>


<h3 class="title-post-seccion">Nodejs</h3>

Una vez instalada la distribución en la tarjeta SD, tenemos que instalar nodejs, se puede compilar, pero es largo y tedioso, en e[este tutorial](http://revryl.com/2014/01/04/nodejs-raspberry-pi/) explican como hacerlo con apt.

<div class="img-wrapper">
  <img src="{{site.url}}/images/matrix/conexiones_raspberry.jpg" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Primeras pruebas entre la raspberry y la pantalla</div>
</div>

Es importante ser ordenado en esta fase sobre todo en el joystick done tendremos que tener identificados qué cable es cada cosa. En el taller utilizamos cinta aislante de colores para poner el nombre del cable (arriba, abajo, boton1, ESC, etc)

<div class="img-wrapper">
  <img src="{{site.url}}/images/cableado0.jpg" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Replanteo de todas las soldaduras de los cables y preparación de las cintas identificativas </div>
</div>

Una vez tenemos todo cableado y montado tenemos que probarlo antes de cerrar la carcasa. En la foto de abajo se puede ver como todos los cables están identificados y como también están las conexiones hechas entre los botones y el Gpio de Raspberry.

<div class="img-wrapper">
  <img src="{{site.url}}/images/cableado1.jpg" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Cableado y conexiones realizadas</div>
</div>

<h3 class="title-post-seccion">Conexión Gpio</h3>

La Raspberry como producto educativo que es, pone a nuestra disposición un conjunto de pines que llamados GPIO. En la Wikipedia esto lo describen de esta manera:

GPIO (General Purpose Input/Output, Entrada/Salida de Propósito General) es un pin genérico en un chip, cuyo comportamiento (incluyendo si es un pin de entrada o salida) se puede controlar (programar) por el usuario en tiempo de ejecución.

Nosotros hemos mapeado estos puertos para que una vez que se detecta el cierre del circuito mediante la pulsación de un botón (o el movimiento de la palanca del joystick) el ordenador interprete esta acción como si la pulsación de una tecla se tratará. Esto lo hacemos con un pequeño programa creado por Adafruit y que nosotros hemos modificado. En la imagen siguiente se puede ver nuestro mapeo.

<div class="img-wrapper">
  <img src="{{site.url}}/images/gpio.jpg" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Esquema y mapeo del GPIO con el sistema de botones </div>
</div>

En esta otra imagen se puede ver el sistema de conexiones que hemos diseñado para esta versión de la Arcade
<div class="img-wrapper">
  <img src="{{site.url}}/images/gpio_image.jpg" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Soldaduras sobre pin hembra conectadas a la Raspberry pi</div>
</div>

Estas conexiones se pueden hacer de muchas formas diferentes, hemos localizado unos [jumpers](http://www.adafruit.com/products/1952) hembra/macho que podrían simplificar mucho esta tarea

En la sección de las Raspberry explicaremos como hacemos funcionar este mapeo.

<!--fin-->


<!--Raspberry pi-->
<a name="raspberry"></a>
<h2 class="title-big-seccion">Raspberry pi</h2>

<div class="img-wrapper">
  <img src="{{site.url}}/images/pi.jpg" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Logo Raspberry pi</div>
</div>

Raspberry Pi es un ordenador de placa reducida o (placa única) (SBC) de bajo coste, desarrollado en Reino Unido por la Fundación Raspberry Pi, con el objetivo de estimular la enseñanza de ciencias de la computación en las escuelas. (Wikipedia).

En nuestro arcade Raspberry pi es el cerebro, y hacemos uso de la tarjeta gráfica para poder conectarla con la pantalla de 7 pulgadas. Para el almacenamiento usamos una tarjeta SD, en el caso del kit es mínimo de 8GB ya que la distribución Piplay la tiene en esta dimensión. Nosotros para el kit hemos modificado la distribución Piplay para dejar configurada la biblioteca de Adafruit para nuestra disposición de teclas (relacionadas con los botones).

La tarjeta SD hace dos funciones, por un lado se instala el sistema operativo (En nuestro caso una versión de Debian para Raspberry) y por otro lado el espacio libre lo usamos como sistema de almacenamiento para las roms.

Tenemos esta imagen preparada que es la que usamos para el taller.
[Descargar Piplay Interzonas](https://mega.co.nz/#!pQpzAR4K!nXhC1OT0LXtC_piNWXIwI-dxibT331H_q0qFhT8do9E)

Para poder instalar esta imagen en vuestras tarjeta SD existen muchas maneras de hacerlo, dependerá en parte de tu sistema Operativo. Os dejo este [enlacee](http://computers.tutsplus.com/articles/how-to-flash-an-sd-card-for-raspberry-pi--mac-53600) con un buen tutorial sobre como hacerlo en distintos sistemas.

Una vez instalada la distribución se tiene que hacer overclock desde el menú de configuración de Piplay. Estos son los valores a añadir:

* arm_freq=900
* core_freq=300
* sdram_freq=500

Si habéis instalado nuestra imagen preparada de Piplay la tendréis configurada para poder jugar con los 5 botones y el joystick. Podréis manejaros por los menús de configuración tanto de Piplay como del juego. En caso contrario tendrás que instalar la aplicación de Adafruit que convierte las pulsaciones de los botones en letras.

En [Adafruit-Retrogame](https://learn.adafruit.com/retro-gaming-with-raspberry-pi) tienes otro estupendo tutorial para montarte un Arcade con Raspberry y aquí tienes el [código del programa](https://github.com/adafruit/Adafruit-Retrogame)

[En nuestro repositorio](https://github.com/interzonas/Adafruit-Retrogame) tienes el código modificado para que funcione con 5 botones.

En el proyecto [Adafruit-Retrogame](https://learn.adafruit.com/retro-gaming-with-raspberry-pi) tienes la info de como instalar el programa.

<!--fin-->


<!--mame-->
<a name="mame"></a>
<h2 class="title-big-seccion">Mame</h2>

Para esta Arcade hacemos uso de distintos emuladores que nos permitirán cargar roms con los que jugar. En esto caso nos hemos centrado en MAME.

Multiple Arcade Machine Emulator («emulador de múltiples máquinas recreativas»), más conocido por sus siglas MAME, es un emulador de máquinas recreativas. Las máquinas de videojuegos que funcionan con monedas que suelen estar en lugares públicos (bares, boleras, salones recreativos, etc.). Para hacer funcionar un juego, se requiere su correspondiente ROM (archivo con una imagen de la ROM de la máquina, que contiene el juego en sí). Mame es un programa de código abierto y gratuito si se utiliza sin ánimo de lucro. (Wikipedia)

En nuestro caso para poder hacer funcionar la Mame (y otros emuladores) usamos una distribución especifica para Raspberry pi [http://www.pimame.org](Piplay) con un entorno gráfico para lanzar diversos emuladores y gestionar roms.

Nuestro Arcade que se enfoca en el emulador MAME funciona sin teclado.

<div class="img-wrapper">
  <img src="{{site.url}}/images/tresbotones.jpg" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Tres botones con pantalla y lateral sin montar</div>
</div>

Con los 5 botones y el joystick podemos movernos por la interfaz del Piplay y también jugar

* Joystick
* Botón 1
* Botón 2
* 1 player
* Insert coin
* Menú (Esc)

Hemos modificado la configuración por defecto de Piplay en mame para que el botón 1 haga las veces de enter y así podamos navegar y entrar en los distintos menús.

<div class="img-wrapper">
  <img src="{{site.url}}/images/configure-joystick.jpg" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Menú de acceso en la MAME a la configuración del teclado</div>
</div>

Para cambiar esta configuración necesitamos un teclado, dándole a tabulador podemos acceder a este menú de configuración de Mame nosotros hemos accedido al apartado de input para cambiar la asignación de boton1.

<div class="img-wrapper">
  <img src="{{site.url}}/images/menuinput.jpg" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Mapeo del teclado de la mame</div>
</div>

Aquí en el menú de asignaciones de teclas, nosotros hemos modificado el P1 Button 1 asignándole la tecla "enter"

En este [enlace](http://www.raspberrypi.org/forums/viewtopic.php?f=78&t=29427) tenemos un foro de discusión sobre roms de MAME que funcionan correctamente en la Raspberry pi

[http://coolrom.com/](coolrom.com) Es la web con un gran cantidad de juegos para nuestros emuladores

<!--fin-->

<!--Piplay-->
<a name="piplay"></a>
<h2 class="title-big-seccion">Piplay</h2>
Como ya hemos ido comentado Piplay (antes Pimame) es la distribución especialmente montada para poder usar emuladores en la Raspberry pi. Es un proyecto vivo y con mucho movimiento.

La propia distribución tiene muchos emuladores y opciones. Este tutorial no abarca su configuración pero vemos interesante explicar cómo subir roms

<h3 class="title-post-seccion">Cargar roms en el kit</h3>

Una vez que tengamos nuestro kit montado y queremos añadir más roms la distribución Piplay nos lo pone muy fácil, solo tendremos que conectar la Raspberry a una red local y mediante un equipo remoto se pueden subir Roms.

Si nuestra Raspberry esta conectada a una red, podemos cargar roms de una manera muy sencilla. Desde otro equipo, abrimos un navegador y tecleamos la dirección ip de la Raspberry ( se muestra en la parte derecha del Piplay).

<div class="img-wrapper">
  <img src="{{site.url}}/images/uno_rom.png" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Acceso servidor web para la subida de roms</div>
</div>

Pulsamos en Roms Uploader

<div class="img-wrapper">
  <img src="{{site.url}}/images/dos.png" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Localización de los directorios dependiendo de emulador</div>
</div>

Veremos un listado de directorios por emuladores, en nuestro caso nos interesa añadir mas roms a la carpeta advmame. Seleccionamos el directorio.

<div class="img-wrapper">
  <img src="{{site.url}}/images/tres.png" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Directorio para subir la rom</div>
</div>

<!--fin-->
