---
layout: entrada
category: post
title: Experimentos con una fachada de leds y webRTC
subtitulo: Interzonas / Etopia - Zaragoza
date: 2015-01-26 10:46:04
tipo: experimentos
categories: experimentos
image: post-led1.png
published: true
big: 1
columna: 0
menu: "<div class=\"col-sm-3 hidden-xs columna-rigth\"></div>"

---

Tuvimos la oportunidad de experimentar con la fachada de leds del Centro de Arte y Tecnología Etopia en Zaragoza

<!--mas-->

<h2 class="title-big-seccion">Antecedentes</h2>

Post a post vamos llenando este laboratorio de "cosicas" interesantes. Hace poco publicamos el tutorial ["Construye tu pizarra de leds colaborativa"](http://labs.interzonas.info/articles/contruye_tu_pizarra_de_leds_colaborativa/), invento que nos llevamos al Centro de Arte y Tecnología [Etopia](http://www.zaragoza.es/ciudad/etopia/), donde Jaime de los Rios de [Arteklab](http://www.arteklab.org/) nos invitó a pasar un día y conocer el espacio. 

Esa primera sesión fue muy interesante, primero porque conocimos las instalaciones de la mano de Juan Pradas uno de los responsables de Etopia. Y segundo porque nos dejaron usar su fachada de leds donde usamos el software que habíamos programado para la pizarra colaborativa. 

El resultado de esta sesión lo podéis ver en este vídeo resumen. 

<iframe width="660" height="500" src="//www.youtube.com/embed/GSXqhJlsykU" frameborder="0" allowfullscreen></iframe>

La verdad es que poder pintar varias personas al mismo tiempo con nuestro software en la fachada de leds fue muy guapo. 

La fachada se controla desde un ordenador conectado a la misma. Ese ordenador considera la fachada como si de un monitor auxiliar se tratara, pero con un detalle importante, que sólo pinta los primeros 263 pixeles de ancho por 68 de alto. Lo que se muestra en ese espacio es lo que se ve en la fachada. 

Y aquí surgió el reto **¿Cómo se podría hacer para poder pintar de forma remota en la fachada?**. Y por supuesto, hacerlo simple en lo que a las plataformas y sistema de instalación se refiere.

**WebRTC** fue la palabra que nos vino a la cabeza. En Interzonas somos fervientes defensores de la web y de las tecnologías que les rodean. Vivimos un momento dulce respecto a la web y sus tecnologías, son libres y estándares. 

Por supuesto aceptamos el reto. Este fue el plan: nosotros le dábamos una vuelta a ver si era posible la solución basada en webRTC y después en un par de sesiones/talleres lo poníamos en común y lo terminábamos. El día 22 y 23 de enero nos fuimos a Zaragoza para contarles nuestro plan.

Podéis ver el código del prototipo en este [repositorio](https://github.com/karlosgliberal/screeCaptureWebRTC). 
Y la solución propuesta se basa en la tecnología webRTC, como intuíamos.

<h2 class="title-big-seccion">¿Qué es webRTC?</h2>
___Conocido como Web Real-Time Communications (Comunicación en tiempo real para la web), es un proyecto de código abierto – promovido por Google, Mozilla y otros – que permite comunicaciones en tiempo real sin plug-ins a través de una API Javascript.___

[Esta presentación](http://io13webrtc.appspot.com/#1) podría ser la mejor forma de entender esta prometedora tecnología. O en este post de [cristobalmedinalopez](http://www.cristobalmedinalopez.es/28-webrtc-comunicacion-en-tiempo-real-sin-plugin) también tenemos una introducción muy accesible del potencial del webRTC

<div class="img-wrapper">
  <img src="{{site.url}}/images/webrtc/signaling.png" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Una propuesta para el proceso de señalización</div>
</div>

En el esquema de arriba se muestran los elementos que conforman una conexión básica basada en webRTC. Para conseguir conectar los peer (o pares) es necesario intercambiar un objeto 'session description' (SDP) y esta es parte de la locura del webRTC. Como se ve en el esquema los datos fluyen entre los peer pero antes has tenido que ponerlos en relación y para eso hay un montón de estrategias diferentes. Sea como sea, al final vamos a terminar haciendo uso de ICE (Interactive Connectivity Establishment) que nos ayudará a buscar la mejor ruta para entablar la conexión con nuestro peer (o par) ¿Cómo? Pues con cosas como stun, turn o host candidates. 
 
Nosotros todo esto lo hemos resuelto haciendo uso de [peerjs](http://peerjs.com/), un servicio/librería que simplifica mucho este tema tanto el uso como su implementación.

<h2 class="title-big-seccion">El desarrollo</h2>
Lo primero de todo fue ponernos a investigar. Al principio fue un tanto frustrante, la web webrtc-experiment tiene copada la mayoría de los artículos técnicos pero es un pozo oscuro y poco útil. Una vez superado este escollo vimos claramente las piezas que necesitábamos.

* Chrome apps (o extensión)
* Cliente webRTC
* Peerjs

Chrome apps es la encargada de permitir la selección de la pantalla que se quiere compartir e iniciar el envío mediante webRTC al peer que está esperando la llamada. 

Decidimos crear la Chrome app, ya que Google pone una restricción para usar "desktopCapture" y es que sólo se puede hacer sus capturas de pantalla con la API de Google chrome mediante una extensión o app (o unos parámetros en el arranque). Tiene sentido, permitir compartir cualquier pantalla de tu ordenador es algo delicado y añadiendo esta restricción pones un paso de decisión al usuario. 

<div class="img-wrapper">
  <img src="{{site.url}}/images/webrtc/appwebstore.jpg" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Aplicación en la webstore de Google Chrome</div>
</div>

Otra de las ventajas de crear una app es que le da un icono cuando la arrancas y queda claro que es algo distinto de navegador, aparte de que el sistema operativo lo considera una aplicación independiente. 

<div class="img-wrapper">
  <img src="{{site.url}}/images/webrtc/iconos.jpg" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Aplicación en la webstore de Google Chrome</div>
</div>

La verdad que crear y publicar una webapp es simple, un fichero manifest.json y, en función de las necesidades, incorporar alguna directiva al mismo. Y luego llamamos al index.html donde podemos usar la API extendida de chrome.

<script src="https://gist.github.com/karlosgliberal/3eac80da9c81e6116a54.js"></script>

Nosotros en este manifest.json hemos añadido la directiva ```permissions``` añadiendo ```desktopCapture``` como un permiso necesario. Este permiso es el necesario para poder capturar la pantalla seleccionada por el usuario.

<script src="https://gist.github.com/karlosgliberal/4a71a2ae6fd6d99b3fb1.js"></script>

Sencillo ¿no? Una vez le das al botón lanza la ventana y después procesamos el resultado recogiendo en ```chromeMediaSourceId``` el id de la ventana, que lo necesitamos para crear un stream mediante ```webkitGetUserMedia```. El gestor de medias de chrome permite añadir una serie de restricciones, frames, aspect ratio, y como se ve en el código, ajuste de tamaños, esto lo hacemos con las propiedades ```mandatory```. En [este enlace](http://googlechrome.github.io/webrtc/samples/web/content/manual-test/constraints/) os dejo un ejemplo con las distintas posibilidades de la propiedad mandatory.

Antes de seguir vamos a ver como funciona todo junto. 

<iframe width="660" height="500" src="//www.youtube.com/embed/u0ijkOhIpbo" frameborder="0" allowfullscreen></iframe>

En el vídeo se ve todo el proceso. Por un lado, desde una url específica asociada a un dominio accedemos a lo que hemos llamado cliente webRTC, el cual es el responsable de hacer la llamada y quedarse en espera. Seguidamente, en el vídeo se ve como abrimos un pequeño sketch en processing con las dimensiones adecuadas para que encaje en la fachada, que sería la obra a mostrar en la fachada. Una vez tenemos la ventana a publicar, arrancamos la app de google chrome y le damos al botón que nos permite seleccionar entre las ventanas que tenemos abiertas en nuestro ordenador, donde nosotros elegimos la ventana de processing. La propia app tiene una ventana de preview. Lo que ha ocurrido cuando arrancamos la app es que ha comprobado si tiene alguna llamada entrante, y en caso de ser así, iniciará el proceso que veíamos en el esquema de arriba. Cuando ya se ha generado el stream y ya se tiene el canal entre peer (pares) creados se inicia la retransmisión y en el dominio específico se ve en formato vídeo la captura de pantalla. 

Para simplificar todo este proceso hemos usado [Peerjs](http://peerjs.com/). Como ellos dicen, peerjs simplifica las llamadas de vídeo, audio y datos entre pares con webRTC.

Peerjs ofrece un servicio en la nube para gestionar toda la parte de las firmas y la verdad es que simplifica mucho la implementación. 


Como hemos comentado todo el código (es purito prototipo) se puede ver en [github](https://github.com/karlosgliberal/screeCaptureWebRTC/).

Nuestro proyecto es un tanto especial ya que webRTC admite múltiples forma de conectar los peer/pares y nosotros hemos cerrado esta posibilidad, de manera que sólo puede haber un cliente y una app al mismo tiempo, ya que en nuestro caso sólo un artista puede emitir en la fachada. 

Por nuestra parte, en [Interzonas](http://interzonas.info) nos hemos quedado muy contentos, tanto con el resultado como con la forma de llevarlo a cabo. Poder ofrecer soluciones concretas para espacios tan especiales tiene mucho potencial. Y una vez más demostramos que las tecnologías web son un lugar de confluencia.

Muchas gracias a Néstor y Guillermo, artistas residentes de Etopia, por todo el curro y la atención recibida.



