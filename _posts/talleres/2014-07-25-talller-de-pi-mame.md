---
layout: entrada
title:  "Taller de montaje de una maquina Arcade con Raspberry pi y mame"
date:   2014-07-25 11:21:04
tipo: "talleres"
categories: "talleres"
image: "pimame.jpg"
big: 1
columna: 0
menu: '<div class="col-sm-3 columna-rigth"><ul class="menu-lateral"><li>Descripción</li><li>Componentes</li><li>Github</li><li>Descargas</li></ul></div>'
---

En la década de los 80 los videojuegos se jugaban en máquinas recreativas. Hoy en día, casi todos los juegos de esa época se pueden disfrutar a través de emuladores o pequeños programas que reproducen las caracterí­sticas de estas antiguas máquinas.
<!--mas-->

Esta es la documentación para la construcción del kit Arcade Pi mame. 

Con este tutorial y el kit construiremos la recreativas DIY utilizando un pequeño ordenador basado en hardware libre (Raspberry Pi), sobre el que se instala un distribución (piplay) que emula los juegos clásicos de 8 bits de la época inicial de los videojuegos. Esta documentación la usamos para un taller teórico-práctico en el que construiremos la carcasa de madera de la máquina recreativa, aprenderemos a conectar los joysticks, pantalla y pulsadores y, además, comenzaremos a introducirnos en el mundo de Raspberry Pi instalando y configurando el emulador MAME y cargando juegos.

Una vez terminada la máquina, se le pueden cargar muchos juegos clásicos; por lo tanto, resulta perfecta para convertirse en un centro de entretenimiento económico.

<h2 class="title-big-seccion">Raspberry pi</h2>
<h3 class="title-post-seccion">Componentes</h3>


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


<h3 class="title-post-seccion">Montaje</h3>
Para montar la arcade tenemos el diseño de la carcasa realizado para [http://www.arqma.es/](Arquimaña). El montaje tiene una serie de pasos determinado por esta carcasa y que si tienes tu propio diseño podría ser distinto. 
<div class="img-wrapper">
<img src="{{site.url}}/images/carcasaunida.jpg" class="img-responsive" alt="Responsive image">
</div>

La primera parte consiste en desmontar la carcasa para poder montar la botonera.
<div class="img-wrapper">
<img src="{{site.url}}/images/carcasabotones1.jpg" class="img-responsive" alt="Responsive image">
</div>
<div class="img-wrapper">
<img src="{{site.url}}/images/carcasabotones2.jpg" class="img-responsive" alt="Responsive image">
</div>

Una vez que tenemos montada la parte mecánica montando todos los botones, tendríamos que cablear estos botones lo explicaremos en la sección de la respberry pi ya que hemos usado unos jumpers para facilitar esta tarea.

Para alimentar la pantalla tft y la Raspberry Pi hacemos uso de una sola fuente de alimentación (de 2 amperios)
<div class="img-wrapper">
<img src="{{site.url}}/images/fuentecable.jpg" class="img-responsive" alt="Responsive image">
</div>

Tenemos que cortar el cable de salida de la fuente de alimentación para contarlos mediante soldadura con el cable micro usb y el cable de alimentación de la pantalla. 
<div class="img-wrapper">
<img src="{{site.url}}/images/cablesconectados.jpg" class="img-responsive" alt="Responsive image">
</div>

Es importante diferenciar cada cable sus positivos y sus negativos. 

Esta fuente de alimentación nos da 2 amperios en 5 y 12 voltios, el cable amarillo es negativo y dependiendo con que lo usemos (blanco o rojo) nos dará 5 o 12 voltios.

* Amarillo + Rojo = 12V
* Amarillo + Blanco = 5V
* Amarillo = tierra o negativo

<div class="img-wrapper">
<img src="{{site.url}}/images/cablefuente.jpg" class="img-responsive" alt="Responsive image">
</div>

Para alimentar la raspberry necesitamos 5 voltios
En la imagen de abajo podemos ver el corte del cable micro usb que alimentara la raspberry. Para obtner los 5 voltios que necesitamos tenemos que unir el cable negro micro usb con el amarillo de la fuente (tierra) y el rojo de del usb con el blanco de la fuente de alimentación. 

<div class="img-wrapper">
<img src="{{site.url}}/images/cableusb.jpg" class="img-responsive" alt="Responsive image">
</div>

Ahora tenemos que conectar el cable de la pantalla con la fuente de alimentación pero necesitamos 12v, la relación de cables es negro de la pantalla con amarillo de la fuente alimentación (tierra) y rojo de la pantalla con rojo de la fuente de alimentación. Abajo la imagen del cable de la pantalla

<div class="img-wrapper">
<img src="{{site.url}}/images/cablepantalla.jpg" class="img-responsive" alt="Responsive image">
</div>
En esta otra imagen podemos ver todas las conexiones realizadas dejando las tres piezas unidas, fuente de alimentación, cable usb, pantalla. 

<div class="img-wrapper">
<img src="{{site.url}}/images/cablesconectado.jpg" class="img-responsive" alt="Responsive image">
</div>
<h3 class="title-post-seccion">Mame</h3>

Para esta Arcade hacemos uso de distintos emuladores que nos permitirán cargar roms con los que jugar, el emuldor mas famoso es mame.

El Multiple Arcade Machine Emulator («emulador de múltiples máquinas recreativas»), más conocido por sus siglas MAME, es un emulador de máquinas recreativas, las máquinas de videojuegos que funcionan con monedas que suelen estar en lugares públicos (bares, boleras, salones recreativos, etc.). Para hacer funcionar un juego, se requiere su correspondiente ROM (archivo con una imagen de la ROM de la máquina, que contiene el juego en sí). Mame es un programa de código abierto y gratuito si se utiliza sin ánimo de lucro. (wikipedia)

Nosotros para poder hacer funcionar la Mame (y otros emuladores) usamos una distribución especifica para raspberry pi [http://www.pimame.org](Piplay) con un entorno gráfico para lanzar diversos emuladores y gestionar roms. 

Nuestro Arcade que se enfoca en el emulador MAME queremos que pueda funcionar sin teclado.

<div class="img-wrapper">
<img src="{{site.url}}/images/tresbotones.jpg" class="img-responsive" alt="Responsive image">
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
</div>
Para cambiar esta configuración necesitamos el teclado, dándole a tabulador podemos acceder a este menún de configuración de Mame nosotros hemos accedido al apartado de input para cambier la asignación de boton1 
<div class="img-wrapper">
<img src="{{site.url}}/images/menuinput.jpg" class="img-responsive" alt="Responsive image">
</div>
Aquí el menú de asignaciones de teclas, nosotros hemos modificado el P1 Button 1 asignándole la tecla "enter"


En este [enlace](http://www.raspberrypi.org/forums/viewtopic.php?f=78&t=29427) tenemos un foro de discusión sobre roms de mame que funcionan correctamente en la raspberry py

[http://coolrom.com/](coolrom.com) Es la web con un gran cantidad de jugos para nuestros emuladores


<h3 class="title-post-seccion">Raspberry pi</h3>
<div class="img-wrapper">
<img src="{{site.url}}/images/pi.jpg" class="img-responsive" alt="Responsive image">
</div>
Raspberry Pi es un ordenador de placa reducida o (placa única) (SBC) de bajo coste, desarrollado en Reino Unido por la Fundación Raspberry Pi, con el objetivo de estimular la enseñanza de ciencias de la computación en las escuelas. (Wikipedia)

En nuestro arcade Raspberry pi es el cerebro, la com

<strong>Cargar roms en el kit</strong>


Una vez que tengamos nuestro kit montado y queremos añadir mas roms la distribución Piplay nos lo pone muy fácil, solo tendremos que conectar la raspberry a una red local y mediante un equipo remoto se pueden subir Roms.

Si nuestra raspberry esta conectada a una redl, podemos cargar roms de una manera muy sencilla. Desde otro equipo, abrimos un navegador y tecleamos la dirección ip de la raspberry ( se muestra en la parte derecha del piplay).
<div class="img-wrapper">
<img src="{{site.url}}/images/uno_rom.png" class="img-responsive" alt="Responsive image">
</div>
Pulsamos en Rom Uploader
<div class="img-wrapper">
<img src="{{site.url}}/images/dos.png" class="img-responsive" alt="Responsive image">
</div>

Veremos un listado de directorios por emuladores, en nuestro caso nos interesa añadir mas roms a la carpeta advmame. Seleccionamos el directorio.

<div class="img-wrapper">
<img src="{{site.url}}/images/tres.png" class="img-responsive" alt="Responsive image">
</div>

<div class="storify"><iframe src="//storify.com/interzonasinfo/taller-raspberry-mame-2014-interzonas/embed?header=false&border=false&template=grid" width="100%" height=750 frameborder=no allowtransparency=true></iframe><script src="//storify.com/interzonasinfo/taller-raspberry-mame-2014-interzonas.js?header=false&border=false&template=grid"></script><noscript>[<a href="//storify.com/interzonasinfo/taller-raspberry-mame-2014-interzonas" target="_blank">View the story "Taller Raspberry Mame 2014  -Interzonas-" on Storify</a>]</noscript></div>