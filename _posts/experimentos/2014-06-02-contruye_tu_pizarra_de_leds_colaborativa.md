---
layout: entrada
category: post
title: Construye tu pizarra de leds colaborativa
subtitulo: Iruña / Donostia
date: 2014-11-06 10:46:04
tipo: experimentos
categories: experimentos
image: ledn2.jpg
published: true
big: 1
columna: 0
menu: "<div class=\"col-sm-3 hidden-xs columna-rigth\"> <div class=\"mon affix-top\" data-spy=\"affix\" data-offset-top=\"250\" data-offset-bottom=\"3000\"><div class=\"menu-lateral-wrapper\"><h3 class=\"title-menu-lateral\">Menú</h3><ul class=\"menu-lateral\"><li><a href=\"#idea\">La idea</a></li><li><a href=\"#componentes\">Componentes</a></li><li><a href=\"#montaje\">Montaje</a></li><li><a href=\"#raspberry\">Raspberry pi</a></li><li><a href=\"#arduino-pantalla\">Arduino/pantalla</a></li><li><a href=\"#nodejs\">Nodejs</a></li><li><a href=\"#firebase\">Firebase</a></li><li><a href=\"#codigo\">Código</a></li></ul></div><div class=\"wrapper-contacto\"><p>Si estas interesado en organizar un taller o tienes cualquier duda:</p><a class=\"btn btn-orange btn-primary\" href=\"mailto:hola@interzonas.info?subject=Contacto desde Interzonas-labs\" role=\"button\">Escríbenos</a></div></div></div>"

---

En este tutorial te mostraremos cómo hemos montado en Interzonas una pizarra de leds para que cualquiera desde Internet pueda pintar en ella en tiempo real.

<!--mas-->

<a name="idea"></a>
<h2 class="title-big-seccion">La idea</h2>

Cuando en [Interzonas](http://interzonas.info/) empezamos a okupar un pedazo de oficina de [Biko](http://www.biko2.com/) se nos planteó un reto, de hecho un gran reto. Biko es una empresa que abraza la metodología desde el desarrollo ágil y su sistema organizativo se basa en equipos autogestionados. Y cada equipo tiene su propio nombre y logotipo que cuelga del techo.

<div class="img-wrapper">
  <img src="{{site.url}}/images/matrix/carteles_biko.png" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Carteles equipo Biko</div>
</div>

¿Qué podíamos hacer para que el cartel de Interzonas fuera especial?
Después de darle unas vueltas lo vimos claro: una pantalla de leds que pudiéramos pintar a nuestro antojo, y claro todo controlado por una web, en tiempo real y colaborativo. Y nos pusimos a ello.

El resultado final:

<iframe width="660" height="500" src="//www.youtube.com/embed/ZvB0OpAjqis" frameborder="0" allowfullscreen></iframe>

Como se puede ver en el vídeo, hemos conectado un Arduino a una pantalla de leds y a su vez este Arduino a una Raspberry. La Raspberry está conectada a internet con un usb wifi, y mediante la Raspberry nos comunicamos con el arduino que manda la información para encender y apagar los leds.

La idea desde el principio era usar una Raspberry para poder instalar node.js y que hiciera de demonio (de oreja que dice [Aitor](http://twitter.com/aitor_rl)) . Después de unas pruebas vimos interesante usar el proyecto [Firebase](http://firebase.com) para la persistencia de datos y el tiempo real, ya que nos evitaba tener que mantener una base de datos propia.

Nos interesaba tener un interfaz web/humano/máquina, un sistema de donde "cosas" escuchan en internet y actúan en consecuencia, y no al revés, intentar conectarnos a las cosas desde internet, que siempre da problemas.

<!--Componentes-->
<a name="componentes"></a>
<h2 class="title-big-seccion">Componentes de la pizarra leds</h2>

Estas son las piezas que hemos usado para montar la pizarra.

* Fuente de alimentación 5v mínimo 2 Amperios
* Cable Mini usb
* Jumpers Hembra
* Raspberry Pi
* Arduino
* Tornillo largos y tuercas
* Placa de metacrilato
* Pantalla leds 16x32 [Adafruit](http://adafruit.com) (Se puede hacer con otros sistemas)


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

El montaje y los componentes son parte del experimento que realizamos, el mismo resultado se podría obtener de formas diferentes pero este fue el que mejor resultado nos dió.

Estas son las diferentes partes del proyecto:

* **Caja**: Queríamos poder contener todos los elementos en la propia pantalla.
* **Fuente de alimentación**: La fuente tiene que alimentar a la raspberry, al arduino y a la pantalla.
* **Cableado botonera**: Montaje y cableado de la botonera.
* **Conexiones**: Las conexiones entre arduino y la pantalla.


<h3 class="title-post-seccion">Caja</h3>

Como queríamos poder colgar la pantalla desde el techo y que sólo tuviésemos el cable de alimentación, se nos ocurrió que podíamos usar la trasera de la pantalla como "contenedor" de los componentes. En esta serie de fotos podemos ver el proceso.


<div class="img-wrapper">
  <img src="{{site.url}}/images/matrix/pantalla1.jpg" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Pantalla y lámina de metacrilato</div>
</div>

<div class="img-wrapper">
  <img src="{{site.url}}/images/matrix/pantalla2.jpg" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Colocación del metacrilato con unos tornillos largos y unas tuercas para que hagan de límite</div>
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

Para la fuente de alimentación se necesita que dé una tensión de 5V y mínimo 2 amperios, ya que para los colores vivos, sobre todo el blanco requiere de mucha potencia. El cableado es un simple conector microusb para la Raspberry Pi e hicimos un empalme con el conector de la pantalla.

<div class="img-wrapper">
  <img src="{{site.url}}/images/matrix/soldadurafuente.jpg" class="img-responsive" alt="Responsive image">
  <div class="img-footer">[@aitor_rl](http://twitter.com/aitor_rl) Soldando el conector de la pantalla y el conector microusb a la fuente de alimentación</div>
</div>

Para la conexión de Arduino lo simplificamos mucho. Conectamos el usb de arduino al usb de la Raspberry Pi, de esta manera alimentamos el arduino y a su vez trasmitimos los datos de internet a la pantalla.

<div class="img-wrapper">
  <img src="{{site.url}}/images/matrix/usbarduino.jpg" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Conexión del usb arduino al usb raspberry</div>
</div>


<a name="raspberry"></a>
<h2 class="title-big-seccion">Raspberry Pi</h2>


Intentamos pintar en la pantalla con la Raspberry pero vimos que el controlador de la misma funcionaba mucho mejor en arduino. Pero teníamos claro que para la conectividad era obligado usar Raspberry, porque con arduino se puede pero los shield de conexión son caros y tediosos. Así que hicimos una instalación básica con la distribución [Raspian](http://www.raspberrypi.org/downloads/) y una configuración también básica.

<div class="img-wrapper">
  <img src="{{site.url}}/images/matrix/conexiones_raspberry.jpg" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Primeras pruebas entre la Raspberry y la pantalla fail ;)</div>
</div>

Para conectar la Raspberry usamos un usb wifi. [Aquí](http://geekytheory.com/tutorial-raspberry-pi-configurar-wif/) un buen tutorial de cómo hacerlo.

Y configuramos un demonio (es la forma de llamar a un programa que está a la escucha) con el sistema de arranque de ubuntu [upstart](http://upstart.ubuntu.com/) para que la webapp en node.js se comunique con el puerto serie. Aquí el fichero serialmatrix.conf que va a /etc/init

<script src="https://gist.github.com/karlosgliberal/cd0d96b144298e097970.js"></script>


<a name="nodejs"></a>
<h2 class="title-big-seccion">Node.js</h2>

Una vez instalada la distribución en la tarjeta SD, tenemos que instalar node.js. Se puede compilar, pero es más largo que el paseo de frodo a mordor. En [este tutorial](http://revryl.com/2014/01/04/nodejs-raspberry-pi/) explican cómo hacerlo con apt, no es un node.js con todos los sacramentos, pero se pueden hacer muchas cosas.

Nosotros necesitamos dos cosas de node.js:

* Hablar con el puerto serie
* Hablar con [Firebase](http://firebase.com)

Para la parte del puerto serie hacemos uso del módulo serialport, que lo instalamos con `npm install serialport`. Este módulo nos permite comunicarnos con el puerto serie ya sea recibiendo información del mismo o enviándola. Aquí la definición básica


<script src="https://gist.github.com/karlosgliberal/ea642bd38716dbb0d470.js"></script>

Luego explicaremos con más detalle qué es firebase, ya que nosotros sólo usamos el envío de lo recibido desde el servicio firebase al arduino (mediante el puerto serie). Pero en el código siguiente tenemos la forma en la que enviamos los datos recibidos de firebase a arduino por el puerto serie.

<script src="https://gist.github.com/karlosgliberal/9ef27f01c30cebbd6274.js"></script>

Este código es parte central del sistema. `pixelDataRef` es nuestra referencia de firebase y con sus sistemas de evento `pixelDataRef.on` (child-added, child-changed, child-removed) y somos notificados cuando alguien ha añadido, borrado o cambiado algún registro de firebase.
Desde node.js estamos atentos a esos cambios y vamos a pasar por la misma función `var drawPixel` lo que recibimos de firebase  y con `myPort.write` mandaremos los datos por el puerto serie a arduino.


*Si aún no sabes qué es node.js aquí os dejamos una presentación que hicimos hace tiempo*

<iframe src="//slides.com/interzonas/la-anarquia-hecha-negocio/embed" width="660" height="500" scrolling="no" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>


<a name="Arduino-pantalla"></a>
<h2 class="title-big-seccion">Arduino/pantalla</h2>

Como hemos comentado hacemos uso de arduino para poder controlar la pantalla. La información técnica de la pantalla está en este [enlace](http://www.adafruit.com/products/420) de Adafruit (¡Qué sería de nuestras vidas sin este ada!)

<div class="img-wrapper">
  <img src="https://learn.adafruit.com/system/assets/assets/000/002/948/medium800/led_matrix_digitalwiring_(1).jpg?1396789286" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Imagen detalle conectores de Adafruit</div>
</div>

En este otro [enlace](https://learn.adafruit.com/32x16-32x32-rgb-led-matrix/wiring-the-16x32-matrix) explican como hacer las conexiones entre arduino y el conector de la pantalla, y en el código de abajo se ve la relación de conectores (como lo indican en el post).

Una vez conectado el arduino a la pantalla usamos la función: `matrix.drawPixel(x, y, matrix.Color333(r, g, b));`que nos permite pintar en la coordenada x, y con el color especificado.

<script src="https://gist.github.com/karlosgliberal/3ac4e23606409c7f6b0a.js"></script>

El parseo de lo recibido desde nodejs en arduino es muy pobre en próximas versiones lo mejoraremos, pero ahora hace su función.

<a name="firebase"></a>
<h2 class="title-big-seccion">Firebase</h2>

[Firebase](http://firebase.com) Como dicen ellos es una poderosa api de almacenamiento y sincronización en tiempo real. Es la caña, toda una navaja suiza, un proyecto que recientemente lo ha [adquirido google](https://www.firebase.com/blog/2014-10-21-firebase-joins-google.html) y que demuestra que está para quedarse.

En definitiva, lo que hace firebase es simple pero brutal, permite la persistencia de datos tipo  clave/valor, pero aporta un sistema de sincronización y notificación en tiempo real, osea que cuando alguien guarda algo el resto de clientes que están conectados a esta *tabla* (ya sea desde un móvil o web) son notificados de ese cambio.

<div class="img-wrapper">
  <img src="{{site.url}}/images/matrix/pintarweb.jpg" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Herramienta para pintar en la pantalla y ver lo que otros pintan</div>
</div>

<a name="codigo"></a>
<h2 class="title-big-seccion">Código</h2>

Parte del código ya lo hemos ido comentando, pero tenemos que hacer una mención especial al desarrollo realizado en AngularJS que lo usamos para poder pintar. Y el esquema de funcionamiento que sigue es similar al ya comentado en varias ocasiones, lo único que le hemos añadido ha sido una serie de funcionalidades para que emule una pizarra en la que pintar.


<div class="img-wrapper">
  <img src="{{site.url}}/images/matrix/pintar_interzonas_info.png" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Ejemplo de dibujo en la webapp pizarra </div>
</div>

La webapp también permite guardar y recuperar dibujos creados previamente como vemos en esta imagen:

<div class="img-wrapper">
  <img src="{{site.url}}/images/matrix/pintar_interzonas_detalle.png" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Ejemplo de gestión de dibujos con la webapp</div>
</div>

Todo el código del proyecto es accesible desde este [repositorio](https://github.com/karlosgliberal/matrixdrawing).

En el repositorio está el código de:

* Arduino
* Demonio nodejs
* Angularjs

Esto es un experimento y como tal lo tratamos en [interzonas](), faltan muchas piezas por mejorar pero tienes la posibilidad de comentarnos lo que encuentres raro tanto aquí como en el repositorio (haciendo pull-request) o usar nuestro [formulario de contacto de interzonas](http://interzonas.info/#contactar).

Con el experimento queríamos poder trabajar con nuevos soportes y este desarrollo nos permite abrir esas posibilidades. En esta ocasión lo hacemos con una pantalla de leds de 16x32 pero en otras ocasiones, quien sabe, ¿con una fachada de leds...?

También te puedes poner en [contacto](http://interzonas.info/#contactar) con nosotros si quieres que organicemos un taller o se te ocurre alguna idea donde te podríamos ayudar, por muy loca que sea.



<!--fin-->
