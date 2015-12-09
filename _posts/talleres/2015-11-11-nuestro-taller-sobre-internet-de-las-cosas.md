---
layout: entrada
category: post
title: "Nuestro taller sobre internet de las cosas"
subtitulo: Interzonas / Iruña
date: 2015-11-11 11:11:11
tipo: blog
categories: blog
image: iot/cabeceraiot.jpg
published: true
big: 1
columna: 0
menu: "<div class=\"col-sm-3 hidden-xs columna-rigth\"> <div class=\"mon affix-top\" data-spy=\"affix\" data-offset-top=\"250\" data-offset-bottom=\"3000\"><div class=\"menu-lateral-wrapper\"><h3 class=\"title-menu-lateral\">Menú</h3><ul class=\"menu-lateral\"><li><a href=\"#antecedentes\">Antecedentes</a></li><li><a href=\"#esquema\">Esquema</a></li><li><a href=\"#definicion\">Definicion</a></li><li><a href=\"#lascosas\">Las cosas</a></li><li><a href=\"#eltransporte\">El transporte</a></li><li><a href=\"#elidioma\">El idioma</a></li><li><a href=\"#laspeleas\">Las peleas</a></li><li><a href=\"#laspracticas\">Practicas</a></li></ul></div><div class=\"wrapper-contacto\"><p>Si estas interesado en organizar un taller o tienes cualquier duda:</p><a class=\"btn btn-orange btn-primary\" href=\"mailto:hola@interzonas.info?subject=Contacto desde Interzonas-labs\" role=\"button\">Escríbenos</a></div></div></div>"
---

¿Quieres un taller (Interzonas style) sobre Internet de las Cosas? Nosotros estamos encantados de llevarlo donde nos digas. En este artículo recogemos lo que se cuenta en el taller. Es parte del material con el que trabajamos.

<!--mas-->

<div class="img-wrapper">
  <img src="{{site.url}}/images/iot/0.jpg" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Cartel presentación del taller en tabakalera</div>
</div>

Si estas interesado en un taller teórico/político/práctico sobre Internet de las Cosas [ponte en contacto con nosotros/as](http://interzonas.info/#contactar).


En Interzonas usamos este laboratorio para poder experimentar con tendencias (en la mayoría tecnológicas, pero no siempre). Estos experimentos nos aportan unos conocimientos y experiencia que luego usamos de distintas maneras. Una de estas maneras es la creación de un taller donde aplicamos lo aprendido y lo testeamos con más personas. Esto ya lo hemos realizado en otras ocasiones un ejemplo sería este taller: [Como montar tu propia arcade con Raspberry Pi y MAME](http://labs.interzonas.info/articles/talller-de-pi-mame/).

Este artículo recoge el material tanto teórico como práctico de nuestro taller sobre "Internet de las Cosas", también llamado IoT del inglés "Internet of Things".

<!--Antecedentes-->
<a name="antecedentes"></a>
<h2 class="title-big-seccion">Antecedentes del taller</h2>

En Interzonas somos conscientes que desde hace unos años nuevos actores han aparecido en escena: Big data, smartcity, cloud computing, o como en el caso de este artículo "Internet de las cosas". De cada uno de estos términos se puede sacar muchas visiones. En Interzonas queremos tener nuestra propia visión, y a poder ser una visión crítica.

Allá por el 2013/14 apareció uno de esos proyectos que nos llamó la atención: [Spark Core](https://www.kickstarter.com/projects/sparkdevices/spark-core-wi-fi-for-everything-arduino-compatible?ref=discovery). Según lo que se contaba del proyecto, era la forma simple de hacer prototipos para el tan comentado "Internet de las Cosas". Vimos mucho potencial con spark y fuimos dando forma a un taller.

<div class="img-wrapper">
  <img src="{{site.url}}/images/iot/2.jpg" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Presentación del Grupo de Código Creativo de Hirikilabs</div>
</div>

Desde [Hirikilabs](http://hirikilabs.tabakalera.eu/) y desde [el Grupo de Código Creativo](http://hirikilabs.tabakalera.eu/blog/category/grupos-de-trabajo/codigo-creativo/) planteamos un taller sobre el Internet de las Cosas que no sólo fuese práctico. Queríamos un taller que diera pie a la especulación, no quedarnos solamente en lo tecnológico o práctico. Y así lo hicimos.

El planteamiento del taller es que sea accesible para todo el mundo, pero dependiendo de los conocimientos será mas fácil seguir la parte práctica.


<!--Esquema -->
<a name="esquema"></a>
<h2 class="title-big-seccion">Esquema del taller</h2>

El esquema del taller es algo revisable, ya que dependiendo del lugar y el tiempo disponible la propuesta puede cambiar. La primera vez lo realizamos en dos días diferentes en Hirikilabs, donde el primer día fue la parte más teórica y una primera aproximación práctica, y el segundo día donde hubo una parte de introducción al [Photon de particles](https://store.particle.io/) y una segunda de experimentación libre en grupo.

Para poder hacer un proyecto concreto se necesita una visión más o menos completa de cómo se hacen la cosas con este componente, ya que es la manera de poder luego proponer algo en un formato tipo Open Space.

<h3 class="title-post-seccion">Esquema</h3>

* Día 1
  * Presentación
  * Dinámica de grupo: ¿Qué es el Internet de las Cosas?
  * Dinámica de grupo: ¿Para qué el Internet de las Cosas?
  * Charla Internet de las Cosas.
  * Dinámica de grupo: Una historia de terror
  * Photon configuración
  * El hola mundo con el photon
* Día 2
  * Introducción al photon, entorno desarrollo, api etc
  * Open space ¿Qué proyectos hacemos?


<!--Definicón-->
<a name="definicion"></a>
<h2 class="title-big-seccion">Definición</h2>

Tenemos muchas definiciones posibles de "Internet de las Cosas". La más simple pero que abarca la mayor de sus posibilidades es esta:

<BLOCKQUOTE><strong>Internet de las Cosas</strong> es un concepto que se refiere a la interconexión digital de objetos cotidianos con Internet.</BLOCKQUOTE>

Hasta ahora entendíamos que a Internet se conecta personas, que en la mayoría de los casos lo hará con un ordenador, móvil/tablets, (televisión en menos casos) y luego los servidores entre sí. Pero la realidad es otra, cada vez mas "cosas", objetos, sensores, máquinas se conectan a Internet. Y esto está creciendo de forma brutal e irá a más.

Por lo tanto, la realidad es que los objetos, las cosas, van a tener la posibilidad de estar conectados y por lo tanto recibiendo/enviando información a través de Internet.

Otra posible definición es la creada por Bruce Sterling hace ya algunos años y que para ello acuñó el término de Spime:

<BLOCKQUOTE><strong>Spime</strong> para definir aquellos objetos físicos tan informacionalmente significados que informan sobre la línea temporal de su vida como productos (sus materiales, sus autores, sus dueños actuales y pasados, sus orígenes, su diseño, su entorno…)</BLOCKQUOTE>

Bruce Sterling imagina un mundo donde los objetos tiene la posibilidad de significar su existencia. Es una visión mas posibilista, donde la propia idea del objeto es algo más y ese más puede ser revisado.

Aunque para ser sinceros, la realidad encaja mejor en la primera definición, estará en nuestras manos especular como hace Bruce en el Internet de las Cosas que queremos.

<div class="img-wrapper">
  <img src="{{site.url}}/images/iot/cisco.jpg" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Cosas</div>
</div>

Lo que si está claro es que el impacto del IoT es algo real. Se calcula que para el 2020 habrá 37 millones de objetos "inteligentes" conectados a Internet. En cantidad de datos generados podemos decir que en el 2013 fueron 4ZB (1 zetabyts es igual 1 billón de gigabyts) y en el 2020 serán 44ZB.

El impacto es tal, que no sólo lo podemos contemplar en términos tecnológicos, también tenemos que hacerlo en términos, políticos, económicos y sociales. El cloud computing, el big data y la smart city, forman parte de un todo, y el Internet de las Cosas es la pieza fundamental.
¿Qué supondrá tener todas estas cosas conectadas a nuestro alrededor? ¿y nuestra privacidad se verá afectada? ¿y el control social? ¿y el impacto medio ambiental? ¿energético? Surgen muchas preguntas que sería interesante pararse un rato y responderlas.

<!--Las cosas-->
<a name="lascosas"></a>
<h2 class="title-big-seccion">Las cosas</h2>


<h3 class="title-post-seccion">¿Pero qué cosas?</h3>

El término "cosas" tan ambiguo y sugerente que nos propone un mar de posibilidades, pero ¿estamos preparados?

<div class="img-wrapper">
  <img src="{{site.url}}/images/iot/cosas.png" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Cosas</div>
</div>


En este futuro cercano los objetos conectados serán muchos, los habrá en forma de productos, hardware específico, suites verticales, y mucho desarrollo a medida que cubra necesidades específicas. Lo que es seguro es que vamos a estar rodeados de ojos, oídos, narices, cámaras, luces, cuantificadores, lanzadores... que van a conectar nuestra vida a una red informacional demasiado basta y dispersa como para controlarla.


<h3 class="title-post-seccion">Productos</h3>


<div class="img-wrapper">
  <img src="{{site.url}}/images/iot/productos_photon.png" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Productos creado con photon de particles </div>
</div>

Cada día están saliendo productos nuevos, algunos con una propuesta muy clara, pero otros pierden todo el sentido. Son ya varias webs las que están recogiendo estos productos, como es el caso de [iolist](http://iotlist.co/). Otro lugar que se ha convertido en el valedor de estos productos es [Kickstarter](https://www.kickstarter.com/discover/advanced?ref=nav_search&term=iot), una plataforma de crowdfunding que está permitiendo testar productos tecnológicos de una forma colectiva y que en caso del IoT están permitiendo sacar productos de éxito como por ejemplo la bombilla [lifx](http://www.lifx.com/)

<h3 class="title-post-seccion">Hardware</h3>

<div class="img-wrapper">
  <img src="{{site.url}}/images/iot/hardware.png" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Cosas</div>
</div>

Pero en el hardware también está habiendo una gran revolución, tanto en componentes electrónicos, como en hardware multipropósito. Por supuesto la estela de Arduino ha sido fundamental, muchos proyectos han seguido esa estela añadiendo sus innovaciones específicas.

En nuestro caso optamos por el producto [Photon](https://store.particle.io/) de [Particle](http://www.particle.io/) como hardware para nuestro taller. Aunque es cierto que cada día sale un hardware nuevo con propuestas completamente diferentes.

Lo cierto es que con una raspberry-pi y un módulo wifi, podremos montar un dispositivo IoT sin problemas, aunque los hardware específicos están aportando elementos que simplifican sobre todo la fase de prototipado.

Photon, el hardware que usamos en el taller, se basa en tecnología Arduino, de manera que si sabes programar en esta plataforma lo sabes en el producto estrella de Particles. La ventaja de Photon es que viene con un chip wifi integrado y una app que simplifica mucho la configuración de este chip. A esto le han añadido una plataforma en su propia nube, que permite programar los photones y flashear los que tengas a tu cargo. También proporciona una [api](https://docs.particle.io/reference/api/) que da acceso a cada uno de tus dispositivos. Seguiremos hablando de Photon más adelante.


<!--El transporte -->
<a name="eltransporte"></a>
<h2 class="title-big-seccion">El transporte</h2>

La capa de comunicación es una de las piezas claves del Internet de las Cosas. Como estos objetos se conectan a Internet es parte de la revolución y como en toda revolución hay peleas. En el listado de abajo comentamos las opciones más conocidas, dependiendo del proyecto algunas no encajarán y otras sí. Estos son los lugares comunes. Otra opción son los desarrollos a medida. Muchas empresas están innovando dentro de su casa, creando la ingeniería necesaria para conectar dispositivos, pero no están usando estándares públicos como los que veremos a continuación.

* **Wifi**: Un medio común con limitaciones como el consumo de batería, y la complejidad de conexión
* **GSM**: Convertir el hardware en un nodo conectado a la red de telefonía inalámbrica
* **6LoWPAN**: Posibilita el uso de Ipv6 en wifi. Hace posible que dispositivos puedan comunicarse directamente con otros dispositivos IP (con las nuevas direcciones, que no serán escasas como las actuales) [[enlace]](http://datatracker.ietf.org/wg/6lowpan/charter/).
* **SigFox**: Conectividad celular global para Internet de las Cosas. Otra red privada para el IoT [[enlace]](http://www.sigfox.com/es/)
* **Bluetooth LTE**: El clásico método revisado en su versión 4.0 con un gran ajuste en consumo
* **ZigBee**: También sobre el estándar ieee 802.15.4 pero ajustando el consumo de batería

El proyecto será el que determine la elección, en nuestro caso Photon que es un Arduino con un chip wifi y una serie de utilidades que simplifican la configuración del wifi (mediante una app, o con nodejs). Además es un proyecto surgido de una campaña de kickstarter y que son muy respetuosos, liberando la gran mayoría del código necesario para implementarlo por tu cuenta.


<!--El idioma-->
<a name="elidioma"></a>
<h2 class="title-big-seccion">El idioma</h2>

El protocolo de comunicación o el idioma será la manera de como enviamos y recogemos los datos en nuestros dispositivos IoT. No siendo algo tan diverso y privado como en la capa de transporte, también hay una serie de discusiones que hacen estar atentos a la elección elegida. Aquí ponemos una lista.

* **REST**: La Transferencia de Estado Representacional (Representational State Transfer) para describir cualquier interfaz entre sistemas que utilice directamente HTTP para obtener datos o indicar la ejecución de operaciones sobre los datos. Está muy de moda en todas las APIs web ya que ha simplificado mucho el crear un capa de aplicación con el estilo http. [[Rest]](https://es.wikipedia.org/wiki/Representational_State_Transfer)
* **MQTT**: Message Queue Telemetry Transpor un protocolo usado para la comunicación machine-to-machine, es uno de los clásicos, pero tiene su complejidad, se requiere de un broker ([mosquitto](http://mosquitto.org/) es uno opensource famoso) y no es sencillo poner todo en orden.[MQTT](http://mqtt.org/)
* **CoAP**: Es una versión REST con soporte UDP y reducción de cabeceras. Es una de las esperanzas, sigue siendo igual de simple y estándar que REST (incluso compatible) pero consume menos. [coap](http://coap.technology/)
* **Websockets**: El sistema de sockets basado en tecnología web, permite abrir sockets entre navegadores o hard que lo permita, tiene muchas posibilidades en su relación con la web [websocket](http://www.html5rocks.com/es/tutorials/websockets/basics/)
* **iBeacon**: Sistema de posicionamiento en interiores mediante balizas liderado por Apple [iBeacon](https://developer.apple.com/ibeacon/)
* **Eddystone**: También sobre el estándar ieee 802.15.4 y también pensado para las balizas pero ajustando el consumo de batería [Eddystone](https://github.com/google/eddystone)


<!--Las Peleas-->
<a name="laspeleas"></a>
<h2 class="title-big-seccion">Las peleas</h2>

<blockquote> <p>Y en este galimatías de sistemas de comunicación, protocolos de red, productos, negocios, y la mala tendencia del capitalismo de generar violencia, no podían faltar las peleas. </p></blockquote>

<h3 class="title-post-seccion">Forzando el estándar</h3>

Una de las tecnologías que hemos comentado es el Bluetooth LTE (Low energy). Es una nueva especificación que permite otra forma de usar las conexiones bluethooth. Donde se le ha visto potencial es en las balizas para el posicionamiento en interiores. El GPS no entra en los edificios y un aeopuerto o museo no tiene una forma simple de identificar donde estás. Aquí es donde entran en juego estas dos tecnologías enfrentadas: [iBeacon](https://developer.apple.com/ibeacon/) y [Eddystone](https://github.com/google/eddystone)

El planteamiento es simple, un pequeño hardware con una batería (puede ser una pila de botón) que emite una serie de datos y lo hace por este nuevo formato (Bluetooth LTE Low energy). Nuestro móvil es reactivo a estas balizas y reaccionará, dependiendo de las circunstancias (tener una app es una de ellas), abriéndote una app y en ella indicando la información asociada a la baliza, por ejemplo, el cuadro que estás viendo o la oferta del zapato en la estantería frente a la que estás.

Pero ¿dónde está la pelea? Pues en el intento de forzar el estándar. Apple con los iBeacon quiere que las balizas solo manden tres valores, UUID, mayor, y minor. Y con una serie de restricciones que ellos consideran necesarias y que en IOS, pueden forzar de forma simple.
Mientras tanto, los señores de google han sacado recientemente la especificación abierta de Eddyston. Este manda un uid, unos datos telemétricos, y lo más importante, una url. Por lo tanto, la baliza te manda una url, el móvil es reactivo y abrirá la url. Ya hay un proyecto llamado [physical-web](http://google.github.io/physical-web/) que es interactivo con estas urls.

Son dos visiones completamente distintas y una pelea por forzar un estándar. El capitalismo tiende al monopolio y lo suele hacer de forma violenta y estos dos grandes tecnológicos están en una pelea por decidir cuál es el sistema de balizas del futuro cercano.


<!--La parte práctica-->
<a name="laspracticas"></a>
<h2 class="title-big-seccion">La parte práctica</h2>


Como hemos comentado más arriba, este taller tiene unas partes prácticas, dinámicas de grupo, primeros pasos con Photon y un Open Space para trastear y crear un proyecto entorno a estas tecnologías. En esta serie de fotos vamos a intentar explicar qué cosas se hicieron en los distinto apartados prácticos.

La primera parte, presentación de [Interzonas](http://labs.interzonas.inf), el [Grupo de Código Creativo](http://codigocreativo.info/tributo/) e [Hirikilabs](http://hirikilabs.tabakalera.eu/)

<div class="img-wrapper">
  <img src="{{site.url}}/images/iot/1.jpg" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Presentación del taller y explicación de las dinámicas </div>
</div>

<div class="img-wrapper">
  <img src="{{site.url}}/images/iot/2.jpg" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Presentación de Grupo de Código creativo e Hirikilabs</div>
</div>

Nada más empezar y hacer las presentaciones pertinentes iniciamos una dinámica en grupo, respondiendo entre todos y todas dos preguntas: ¿Qué es el Internet de las Cosas? ¿Para qué es el Internet de las Cosas?

<div class="img-wrapper">
  <img src="{{site.url}}/images/iot/4.5.jpg" class="img-responsive" alt="Responsive image">
  <div class="img-footer"> Jaime de [Arteklab](http://www.arteklab.org/) e Ibai de Hirikilabs respondiendo a las preguntas de la dinámica ¿qué y para qué es el Internet de las Cosas? </div>
</div>

Fuimos haciendo una ronda y poniendo en común lo que cada uno entendía o sabía sobre el IoT. Hubo mucho consenso, pero también ideas originales. 

<div class="img-wrapper">
  <img src="{{site.url}}/images/iot/4.jpg" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Resultado de la dinámica</div>
</div>

Realizada la puesta en común teníamos preparada esta presentación:

<iframe src="//slides.com/interzonas/deck-15-16/embed" width="660" height="495" scrolling="no" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>

<div class="img-wrapper">
  <img src="{{site.url}}/images/iot/3.jpg" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Charla teórica</div>
</div>

Como hemos comentado más arriba la idea no sólo es usar un dispositivo y entender más menos lo que es esto del IoT. Queremos especular, ver más allá del prospecto feliz donde un licenciado en publicidad startapil nos quiere vender.

Por eso la segunda dinámica fue la de que todos escribiéramos una historia de terror. Que pensáramos algo que nos genere inquietud o miedo al respecto de IoT. 

<div class="img-wrapper">
  <img src="{{site.url}}/images/iot/5.jpg" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Segunda dinámica, cuéntanos una historia de terror </div>
</div>

Salieron muchas historias pero rescato una, que es realmente inquietante: una fábrica de frigoríficos que se alía con la red de supermercados para apagar los frigos y así se ponga malos los productos. 

<div class="img-wrapper">
  <img src="{{site.url}}/images/iot/6.jpg" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Material de las dinámicas</div>
</div>

A partir de aquí, empezamos a trabajar con la placa Phonton de Particles:

<div class="img-wrapper">
  <img src="{{site.url}}/images/iot/7.jpg" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Primera toma de contacto con el hardware Photon, configuración, pasándole el passs y contraseña de la wifi</div>
</div>

<div class="img-wrapper">
  <img src="{{site.url}}/images/iot/8.jpg" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Configurando</div>
</div>

<div class="img-wrapper">
  <img src="{{site.url}}/images/iot/9.jpg" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Viendo la documentación de Photon en la web de Particles</div>
</div>

<div class="img-wrapper">
  <img src="{{site.url}}/images/iot/10.jpg" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Comprobando el circuito para el "hola mundo"</div>
</div>

<div class="img-wrapper">
  <img src="{{site.url}}/images/iot/11.jpg" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Interfaz de gestión de photones en la web de Particles </div>
</div>

Si estás interesado en este taller ponte en contacto con nosotros. <a class=\"btn btn-orange btn-primary\" href=\"mailto:hola@interzonas.info?subject=Contacto desde Interzonas-labs\" role=\"button\">Escríbenos</a>



