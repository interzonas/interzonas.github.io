---
layout: entrada
category: post
title: Como montar tu propia arcade con Raspberry Pi y MAME
subtitulo: Hirikilabs / Donostia
date: {}
tipo: talleres
categories: talleres
image: pimame.jpg
big: 1
columna: 0
menu: "<div class=\"col-sm-3 columna-rigth\"> <div class=\"mon affix-top\" data-spy=\"affix\" data-offset-top=\"250\" data-offset-bottom=\"3000\"><div class=\"menu-lateral-wrapper\"><h3 class=\"title-menu-lateral\">Menú</h3><ul class=\"menu-lateral\"><li><a href=\"#componentes\">Componentes</a></li><li><a href=\"#montaje\">Montaje</a></li><li><a href=\"#raspberry\">Raspberry pi</a></li><li><a href=\"#mame\">Mame</a></li><li><a href=\"#piplay\">Pi play</a></li></ul></div><div class=\"wrapper-contacto\"><p>Si estas interesado en organizar un taller o cualquier duda:</p><a class=\"btn btn-orange btn-primary\" href=\"mailto:hola@interzonas.info?subject=Contacto desde Interzonas-labs\" role=\"button\">Escríbenos</a></div></div></div>"
embebido: "<h2 class=\"title-big-seccion\">Historia en Twitter</h2><div class=\"storify\"><iframe src=\"//storify.com/interzonasinfo/taller-raspberry-mame-2014-interzonas/embed?header=false&border=false&template=grid\" width=\"100%\" height=750 frameborder=no allowtransparency=true></iframe><script src=\"//storify.com/interzonasinfo/taller-raspberry-mame-2014-interzonas.js?header=false&border=false&template=grid\"></script><noscript>[<a href=\"//storify.com/interzonasinfo/taller-raspberry-mame-2014-interzonas\" target=\"_blank\">View the story \"Taller Raspberry Mame 2014  -Interzonas-\" on Storify</a>]</noscript></div>"
published: true
---

En la década de los 80 los videojuegos se jugaban en **máquinas recreativas**. Hoy en día, casi todos los juegos de esa época se pueden disfrutar a través de emuladores o pequeños programas que reproducen las características de estas antiguas máquinas.

<!--mas-->

Este es un tutorial para que te puedas construir un Arcade con una Raspberry Pi y MAME. 

Además, este artículo es la documentación utilizada para el taller teórico-práctico realizado por [Interzonas](http://interzonas.info) en colaboración con [Hirikilabs](http://hirikilabs.tabakalera.eu/). Taller en el que construimos la carcasa de madera de la máquina recreativa, aprendimos a conectar el joystick, pantalla y pulsadores, y además nos introdujo en el mundo de [Raspberry Pi](http://www.raspberrypi.org/) instalando y configurando el emulador MAME y cargando juegos.  

Todas las explicaciones y pasos están realizados con el material que aportamos en dicho taller, pero será similar si buscas los componentes por tu cuenta.

La máquina recreativa DIY la construiremos utilizando un pequeño ordenador basado en hardware libre [Raspberry Pi](http://www.raspberrypi.org/) sobre el cual se instala una distribución [Piplay](http://pimame.org/) que emula los juegos clásicos de la época inicial de los videojuegos.

Una vez terminada la máquina, se le pueden cargar muchos juegos clásicos; por lo tanto, resulta perfecta para convertirse en un centro de entretenimiento económico.

<!--Componentes-->
<a name="componentes"></a>
<h2 class="title-big-seccion">Componentes del MAME Raspberry</h2>

Desde Interzonas hemos preparado un kit con todo lo necesario para poder montar tu propia Arcade, esta es la lista de componentes:
- item
- item
- item


* Fuente de alimentación dual 12v + 5v
* Cable Mini usb
* 1 cable RCA Macho/Macho
* Jumpers Hembra
* Raspberry pi
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

El montaje está muy determinado por la carcasa sobre todo en la botonera pero para dar un orientación serían cuatro fases diferentes.

* **Carcasa**: Nosotros estamos usando el estupendo diseño realizado por [Arquimaña](http://www.arqma.es/) y es el que repartimos en los talleres.
* **Fuente de alimentación**: Aquí es donde montamos el cableado que alimente la Raspberry y la pantalla.
* **Cableado botonera**: Montaje y cableado de la botonera.
* **Conexión Gpio**: El cableado de la botonera acaba conectado al sistema de puertos de las Raspberry Gpio


Para montar la arcade tenemos el diseño de la carcasa realizado para [Arquimaña](http://www.arqma.es/). El montaje tiene una serie de pasos determinado por esta carcasa y que si tienes tu propio diseño podría ser distinto.
<div class="img-wrapper">
  <img src="{{site.url}}/images/carcasaunida.jpg" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Carcasa arcade</div>
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

Para alimentar la pantalla Tft y la Raspberry Pi hacemos uso de una sola fuente de alimentación. Esta fuente de alimentación nos da 2 amperios en 5 y 12 voltios, el cable amarillo es negativo y dependiendo con que lo usemos (blanco o rojo) nos dará 5 o 12 voltios.

<div class="img-wrapper">
  <img src="{{site.url}}/images/fuentecable.jpg" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Fuente de alimentación y cable micro usb</div>
</div>

Tenemos que cortar el cable de salida de la fuente de alimentación para conectarlo mediante soldadura con el cable micro usb y el cable de alimentación de la pantalla.

<div class="img-wrapper">
  <img src="{{site.url}}/images/cablesconectados.jpg" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Conexión cable micro usb con pantalla y con fuente de alimentación </div>
</div>

Es importante diferenciar cada cable sus positivos y sus negativos, y como en nuestro caso si la fuente te permite alimentar las dos piezas (pantalla y Raspberry) hay que tener claro las equivalencias en los cables a conectar

_Estas son nuestras equivalencias_
* Amarillo + Rojo = 12V
* Amarillo + Blanco = 5V
* Amarillo = tierra o negativo

<div class="img-wrapper">
  <img src="{{site.url}}/images/cablefuente.jpg" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Sección de cable fuente de alimentación</div>
</div>

Para alimentar la Raspberry necesitamos 5 voltios.
En la imagen de abajo podemos ver el corte del cable micro usb que alimentará la Raspberry. Para obtener los 5 voltios que necesitamos tenemos que unir el cable negro del usb con el amarillo de la fuente (tierra) y el rojo de del usb con el blanco de la fuente de alimentación.

<div class="img-wrapper">
  <img src="{{site.url}}/images/cableusb.jpg" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Sección cable micro usb (usamos el blanco y el negro) sólo alimentación</div>
</div>

Ahora tenemos que conectar el cable de la pantalla con la fuente de alimentación pero necesitamos 12v la relación de cables es negro de la pantalla con amarillo de la fuente alimentación (tierra) y rojo de la pantalla con rojo de la fuente de alimentación.
Abajo la imagen del cable de la pantalla

<div class="img-wrapper">
  <img src="{{site.url}}/images/cablepantalla.jpg" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Cable de pantalla, con fuente conexión pantalla y entradas de vídeo</div>
</div>

En esta otra imagen podemos ver todas las conexiones realizadas dejando las tres piezas unidas: fuente de alimentación, cable usb, y pantalla.

<div class="img-wrapper">
  <img src="{{site.url}}/images/cablesconectado.jpg" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Todas las conexiones</div>
</div>

<h3 class="title-post-seccion">Cableado botonera</h3>

Queremos que el arcade sea autónomo y que pueda funcionar completamente sin la necesidad de usar un teclado, para lograrlo tenemos el Joystick y los 5 botones, estos botones tienen que conectarse de una forma especifica al Gpio de las Raspberry (hablaremos de eso más adelante) pero la idea es que cada botón tiene su propio lugar en el sistema de puertos de nuestra Raspberry. Por lo tanto necesitaremos soldar un cable en cada uno de los botones que irá a las Raspberry y que luego configuraremos para que sepa que hemos pulsado el botón, y soldaremos otro cable para que también vaya a la Raspberry pero en este caso a unos puertos especiales llamados GND o tierras.

<div class="img-wrapper">
  <img src="{{site.url}}/images/cableado.jpg" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Soldaduras de los cables en los botones</div>
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