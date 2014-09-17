---
layout: entrada
category: post
title: Taller Tiras de Leds direccionables con Arduino
subtitulo: Hirikilabs / Donostia
date: 2014-07-25 11:21:04
tipo: talleres
categories: talleres
image: leds2.jpg
published: true
big: 1
columna: 0
menu: "<div class=\"col-sm-3 hidden-xs columna-rigth\"> <div class=\"mon affix-top\" data-spy=\"affix\" data-offset-top=\"250\" data-offset-bottom=\"300\"><div class=\"menu-lateral-wrapper\"><h3 class=\"title-menu-lateral\">Menú</h3><ul class=\"menu-lateral\"><li><a href=\"#componentes\">Componentes</a></li><li><a href=\"#codigo\">Código</a></li><li><a href=\"#fotos\">Presentación y fotos</a></li></ul></div><div class=\"wrapper-contacto\"><p>¿Estás interesado en organizar un <strong>taller</strong> o tienes cualquier duda?</p><a class=\"btn btn-orange btn-primary\" href=\"mailto:hola@interzonas.info?subject=Contacto desde Interzonas-labs\" role=\"button\">Escríbenos</a></div></div></div>"
---

Desde Interzonas preparamos este taller para una introducción de Arduino que realizamos en Hirikilabs y esta es la relación de ejercicios.

<!--mas-->

Para el taller usamos una tira de leds direccionables rgb con el chip ws2811 este es el producto:
[https://www.sparkfun.com/products/12028](https://www.sparkfun.com/products/12028)

Información técnica de como funciona la tira de led rgb [https://learn.sparkfun.com/tutorials/ws2812-breakout-hookup-guide/addressable-led-strips](https://learn.sparkfun.com/tutorials/ws2812-breakout-hookup-guide/addressable-led-strips)

Aunque la idea final del taller es controlar este tipo de leds, el taller se convierte en una herramienta ideal para entender los conceptos básicos de la programación. Que es una variable, que es un array, que es un loop, es mucho mas fácil de comprender viéndolo y eso lo hace a la perfección la tira de led.

<!--Componentes-->
<a name="componentes"></a>
<h2 class="title-big-seccion">Componentes</h2>

* Placa protoboard
* Jumppers (varios)
* Interruptor
* resistencia de 470 omhios
* Potenciómetro 1k omhios
* Tira de 16 leds rgb

*Nota la tira de led el puerto de datos lo conectamos en todos lo ejercicios al pin 4*

Presentación de la charla: http://slides.com/interzonas/taller-arduino-tiras-de-led-rgb-direccionables

<a name="codigo"></a>
<h2 class="title-big-seccion">Código</h2>
Para poder realizar el taller hemos programado una serie de código de ejemplo ordenados por dificultad, el código esta accesible desde un repositorio este [repositorio en github](https://github.com/karlosgliberal/Taller_arduino_tira_led) o puedes descargarlo desde [aquí](https://github.com/karlosgliberal/Taller_arduino_tira_led/archive/master.zip)


<a name="componentes"></a>
<h2 class="title-big-seccion">Fotos y presentación</h2>

Aquí una serie de fotos que hicimos en el taller de [hirikilabs](http://hirikilabs.tabakalera.eu)
<script type="text/javascript" src="https://apis.google.com/js/plusone.js"></script>


<div class="g-post" data-href="https://plus.google.com/105484933848505786542/posts/DpgrZACmg83"></div>


Tenemos esta pequeña presentación que utilizamos a modo de introducción del taller
<iframe src="//slides.com/interzonas/taller-arduino-tiras-de-led-rgb-direccionables/embed" width="576" height="420" scrolling="no" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>


<!--fin-->
