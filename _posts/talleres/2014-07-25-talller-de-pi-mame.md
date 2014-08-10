---
layout: entrada
title:  "Como montar tu propia arcade con Raspberry pi y mame"
subtitulo: "Hirikilabs / Donostia"
date:   2014-07-25 11:21:04
tipo: "talleres"
categories: "talleres"
image: "pimame.jpg"
big: 1
columna: 0
menu: '<div class="col-sm-3 columna-rigth"> <h3>Menú</h3><ul class="menu-lateral"><a href="#componentes"><li>Componentes</li></a><a href="#montaje"><li>Montaje</li></a><a href="#raspberry"><li>Raspberry pi</li></a><a href="#mame"><li>Mame</li></a><a href="#piplay"><li>Pi play</li></a></ul></div>'
embebido: '<h2 class="title-big-seccion">Historia en el Twitter</h2><div class="storify"><iframe src="//storify.com/interzonasinfo/taller-raspberry-mame-2014-interzonas/embed?header=false&border=false&template=grid" width="100%" height=750 frameborder=no allowtransparency=true></iframe><script src="//storify.com/interzonasinfo/taller-raspberry-mame-2014-interzonas.js?header=false&border=false&template=grid"></script><noscript>[<a href="//storify.com/interzonasinfo/taller-raspberry-mame-2014-interzonas" target="_blank">View the story "Taller Raspberry Mame 2014  -Interzonas-" on Storify</a>]</noscript></div>'
---

En la década de los 80 los videojuegos se jugaban en máquinas recreativas. Hoy en día, casi todos los juegos de esa época se pueden disfrutar a través de emuladores o pequeños programas que reproducen las características de estas antiguas máquinas.

<!--mas-->

Esta es el tutorial para que te puedas construir un Arcade con una Raspberry Pi y mame. Pero también es un kit que forma parte del taller que hacemos en [http://interzonas.info](Interzonas). Parte del tutorial tiene que ver con el material que aportamos en el taller, pero la idea será similar si buscas los compoentes por tu cuenta.

Con este tutorial y el kit construiremos la recreativas DIY utilizando un pequeño ordenador basado en hardware libre (Raspberry Pi), sobre el que se instala un distribución (piplay) que emula los juegos clásicos de 8 bits de la época inicial de los videojuegos. Esta documentación la usamos para un taller teórico-práctico en el que construiremos la carcasa de madera de la máquina recreativa, aprenderemos a conectar los joysticks, pantalla y pulsadores y, además, comenzaremos a introducirnos en el mundo de Raspberry Pi instalando y configurando el emulador MAME y cargando juegos.

Una vez terminada la máquina, se le pueden cargar muchos juegos clásicos; por lo tanto, resulta perfecta para convertirse en un centro de entretenimiento económico.

<!--Componentes-->
<a name="componentes"></a>
<h2 class="title-big-seccion">Componentes</h2>

Desde Interzonas hemos preparado un kit con todo lo necesario para poder montar tu propia Arcade, esta es la lista de componentes.

* Fuente de alimentación dual 12v + 5v
* Cable Mini usb
* 1 cable RCA Macho/Macho
* Jumpers Hembra
* Raspeberry pi
* Joystick
* 2 botones de juego
* 3 botones de maniobra
* Pantalla de 7” TFT con entrada VGA


<div class="img-wrapper">
  <img src="{{site.url}}/images/componentespimame.jpg" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Listado de componentes</div>
</div>
<!--fin-->

<!-- montaje-->
<a name="montaje"></a>
<h2 class="title-big-seccion">Montaje</h2>

El montaje esta muy determiando a la carcaras sobre todo en la botonera pero para dar un orientación serian tres fase diferentes.

* Carcasa: Nosotros estamos usando el estupendo diseño realizao por [http://www.arqma.es/](Arquimaña) y es el que repartimos en los talleres.
* Fuente de alimentación: Aquí es donde montamos el cableado que alimente la Raspberry y la pantalla así.
* Cableado botonera: Montaje y cableado de la botonera.
* Conexión Gpio: El cableado de la botonera acaba conectado al sistema de puertos de las raspberry Gpio


Para montar la arcade tenemos el diseño de la carcasa realizado para [http://www.arqma.es/](Arquimaña). El montaje tiene una serie de pasos determinado por esta carcasa y que si tienes tu propio diseño podría ser distinto.
<div class="img-wrapper">
  <img src="{{site.url}}/images/carcasaunida.jpg" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Carcasa arcade diseñada por Arquimaña</div>
</div>

La primera parte consiste en desmontar la carcasa para poder montar la botonera.
<div class="img-wrapper">
  <img src="{{site.url}}/images/carcasabotones1.jpg" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Paso montaje botonera</div>
</div>

<div class="img-wrapper">
  <img src="{{site.url}}/images/carcasabotones2.jpg" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Botonera y lateral </div>
</div>

<h3 class="title-post-seccion">Fuente de alimentación</h3>

Para alimentar la pantalla tft y la Raspberry Pi hacemos uso de una sola fuente de alimentación (de 2 amperios)

<div class="img-wrapper">
  <img src="{{site.url}}/images/fuentecable.jpg" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Fuente de alimentación y cable micro usb</div>
</div>

Tenemos que cortar el cable de salida de la fuente de alimentación para contarlos mediante soldadura con el cable micro usb y el cable de alimentación de la pantalla.

<div class="img-wrapper">
  <img src="{{site.url}}/images/cablesconectados.jpg" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Conexión cable micro usb con pantalla y con fuente de alimentación </div>
</div>

Es importante diferenciar cada cable sus positivos y sus negativos.

Esta fuente de alimentación nos da 2 amperios en 5 y 12 voltios, el cable amarillo es negativo y dependiendo con que lo usemos (blanco o rojo) nos dará 5 o 12 voltios.

* Amarillo + Rojo = 12V
* Amarillo + Blanco = 5V
* Amarillo = tierra o negativo

<div class="img-wrapper">
  <img src="{{site.url}}/images/cablefuente.jpg" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Sección de cable fuente de alimentación</div>
</div>

Para alimentar la raspberry necesitamos 5 voltios
En la imagen de abajo podemos ver el corte del cable micro usb que alimentara la raspberry. Para obtner los 5 voltios que necesitamos tenemos que unir el cable negro micro usb con el amarillo de la fuente (tierra) y el rojo de del usb con el blanco de la fuente de alimentación.

<div class="img-wrapper">
  <img src="{{site.url}}/images/cableusb.jpg" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Sección cable micro usb (usamos el blanco y el negro) solo alimentación</div>
</div>

Ahora tenemos que conectar el cable de la pantalla con la fuente de alimentación pero necesitamos 12v, la relación de cables es negro de la pantalla con amarillo de la fuente alimentación (tierra) y rojo de la pantalla con rojo de la fuente de alimentación. Abajo la imagen del cable de la pantalla

<div class="img-wrapper">
  <img src="{{site.url}}/images/cablepantalla.jpg" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Cable de pantalla, con fuente conexión pantalla y entradas de vídeo</div>
</div>

En esta otra imagen podemos ver todas las conexiones realizadas dejando las tres piezas unidas, fuente de alimentación, cable usb, pantalla.

<div class="img-wrapper">
  <img src="{{site.url}}/images/cablesconectado.jpg" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Todas las conexiones</div>
</div>

<h3 class="title-post-seccion">Cableado botonera</h3>

El acade queremos que sea autónomo y que pueda función completamente sin la necesidad de usar un teclado, para lograrlos tenemos el Jostick y los 5 botones, estos botones tienen que conectarse de una forma especifica al Gpio de las raspberry (Hablaremos de eso mas adelante) pero la idea es que cada boton tinene su propios lugar en el sistema de puertos de nuestra rpi. Por lo tanto necesitaremos soldar un cable en cada uno de los botones que irá a las rapberry y que luego configuraremos para que sepa que hemos pulsado el botón, y soldaremos otro cable para que también vaya a la Rpi pero en este caso a unos puertos especiales llamados GND o tierras.

<div class="img-wrapper">
  <img src="{{site.url}}/images/cableado.jpg" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Soldaduras de los cables en los botones</div>
</div>

Es importante ser ordenado en esta fase sobre todo en el jostick que tendremos que tener identificados que cable es cada cosa. En el taller usamos cinta aislante de colores para poner el nombre del cable (arriba, abajo, boton1, ESC, etc)

<div class="img-wrapper">
  <img src="{{site.url}}/images/cableado0.jpg" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Replanteo de todas las soldaduras de los cables y preparación de las cintas identificativas </div>
</div>

Una vez que tenemos todo cableado y montado tenemos que probarlo antes de cerrar la carcasa. En la foto de abajo se puede ver como todos los cables están identificados y como también estan las conexiónes echas en entre los botones y el Gpio de raspberry.

<div class="img-wrapper">
  <img src="{{site.url}}/images/cableado1.jpg" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Todas el cablado y conexiones realizadas</div>
</div>

<h3 class="title-post-seccion">Conexión Gpio</h3>

La raspberry como producto educativo que es tiene a nuestra disposición de un conjunto de pines que se les llama GPIO. En la Wikipedia esto lo describen de esta manera:

GPIO (General Purpose Input/Output, Entrada/Salida de Propósito General) es un pin genérico en un chip, cuyo comportamiento (incluyendo si es un pin de entrada o salida) se puede controlar (programar) por el usuario en tiempo de ejecución.

Nosotros hemos mapeado estos puertos para que una vez detecta el cierre del circuito mediante la pulsación de un botón (o el movimiento de la palanca del jostick) el ordenador interprete esta acción como si la pulsación de una tecla se tratará. Esto lo hacemos con un pequeño programa creado por Adafruit y que nosotros hemos modificado. En la imagen siguiente se puede ver nuestro mapeo.

<div class="img-wrapper">
  <img src="{{site.url}}/images/gpio.jpg" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Esquema y mapeo del GPIO con el sistema de botones </div>
</div>

En la sección  de las raspberry explicaremos como hacemos función este mapeo

<!--fin-->


<!--Raspberry pi-->
<a name="raspberry"></a>
<h2 class="title-big-seccion">Raspberry pi</h2>

<div class="img-wrapper">
  <img src="{{site.url}}/images/pi.jpg" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Logo Raspberry pi</div>
</div>

Raspberry Pi es un ordenador de placa reducida o (placa única) (SBC) de bajo coste, desarrollado en Reino Unido por la Fundación Raspberry Pi, con el objetivo de estimular la enseñanza de ciencias de la computación en las escuelas. (Wikipedia).

En nuestro arcade Raspberry pi es el cerebro, hacemos uso de la tarjeta gráfica para poder contextarla con la pantalla de 7 pulgadas. Para el almacenamiento usamos una tarjeta SD, en el caso del kit es minimo de 8GB ya que la distribución Piplay la tiene en esta dimensión. Nosotros para el kit hemos modificado la distribución pyplay para dejar configurado la biblioteca de adafruit para nuestra disposición de teclas (relacionadas con los botones).

La tarjeta SD hace dos funciónes, por un lado se instala el sistema operativo, (En nuestro caso una verisón de de debian para raspberry) y por otro lado el espacio libre, lo usamos como sistema de almacenamiento para depositar las roms.

Para poder cargar la imagen que nos descargamos de pymame
<!--fin-->


<!--mame-->
<a name="mame"></a>
<h2 class="title-big-seccion">Mame</h2>

Para esta Arcade hacemos uso de distintos emuladores que nos permitirán cargar roms con los que jugar, el emuldor mas famoso es mame.

El Multiple Arcade Machine Emulator («emulador de múltiples máquinas recreativas»), más conocido por sus siglas MAME, es un emulador de máquinas recreativas, las máquinas de videojuegos que funcionan con monedas que suelen estar en lugares públicos (bares, boleras, salones recreativos, etc.). Para hacer funcionar un juego, se requiere su correspondiente ROM (archivo con una imagen de la ROM de la máquina, que contiene el juego en sí). Mame es un programa de código abierto y gratuito si se utiliza sin ánimo de lucro. (wikipedia)

Nosotros para poder hacer funcionar la Mame (y otros emuladores) usamos una distribución especifica para raspberry pi [http://www.pimame.org](Piplay) con un entorno gráfico para lanzar diversos emuladores y gestionar roms.

Nuestro Arcade que se enfoca en el emulador MAME queremos que pueda funcionar sin teclado.

<div class="img-wrapper">
  <img src="{{site.url}}/images/tresbotones.jpg" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Tres botones con pantalla y lateral sin montar</div>
</div>

Con los 5 botones y el jostick podemos movernos por la interfaz del Piplay y también jugar

* Joystick
* Botón 1
* Botón 2
* 1 player
* Insert coin
* Menu (Esc)

Hemos modificado la configuración por defecto de Pi play en mame para que el boton 1 haga las veces de enter y así podamos navegar y entrar en los distintos menús.

<div class="img-wrapper">
  <img src="{{site.url}}/images/configure-joystick.jpg" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Menú de acceso en la mame a la configuración del teclado</div>
</div>

Para cambiar esta configuración necesitamos el teclado, dándole a tabulador podemos acceder a este menún de configuración de Mame nosotros hemos accedido al apartado de input para cambier la asignación de boton1

<div class="img-wrapper">
  <img src="{{site.url}}/images/menuinput.jpg" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Mapeo del teclado de la mame</div>
</div>

Aquí el menú de asignaciones de teclas, nosotros hemos modificado el P1 Button 1 asignándole la tecla "enter"

En este [enlace](http://www.raspberrypi.org/forums/viewtopic.php?f=78&t=29427) tenemos un foro de discusión sobre roms de mame que funcionan correctamente en la raspberry py

[http://coolrom.com/](coolrom.com) Es la web con un gran cantidad de jugos para nuestros emuladores
<!--fin-->

<!--Piplay-->
<a name="piplay"></a>
<h2 class="title-big-seccion">Pi play</h2>
DEFINICIón

<h3 class="title-post-seccion">Cargar roms en el kit</h3>

Una vez que tengamos nuestro kit montado y queremos añadir mas roms la distribución Piplay nos lo pone muy fácil, solo tendremos que conectar la raspberry a una red local y mediante un equipo remoto se pueden subir Roms.

Si nuestra raspberry esta conectada a una redl, podemos cargar roms de una manera muy sencilla. Desde otro equipo, abrimos un navegador y tecleamos la dirección ip de la raspberry ( se muestra en la parte derecha del piplay).

<div class="img-wrapper">
  <img src="{{site.url}}/images/uno_rom.png" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Acceso servidor web para la subida de roms</div>
</div>

Pulsamos en Rom Uploader

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




