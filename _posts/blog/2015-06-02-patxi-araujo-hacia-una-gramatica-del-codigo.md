---
layout: entrada
category: post
title: "¿Te vienes a escuchar a Patxi Araujo hablar sobre la gramática del código? 4ª reunión Código Creativo el jueves 11 Junio"
subtitulo: Hirikilabs / Donosti
date: 2015-06-01 12:22:00
tipo: post
categories: post
image: amari01.png
published: true
big: 1
columna: 0
menu: "<div class=\"col-sm-3 hidden-xs columna-rigth\"></div>"
---

<script type="text/javascript" src="http://interface.khm.de/wp-content/plugins/processingjs/js/processing.min.js?ver=4.0.1"></script>

¿Y si el código no es más que la excusa? Hablaremos con Patxi Araujo sobre vvv, código y arte.

<!--mas-->

El jueves día 11 a las 18:30 en [Hirikilabs](http://hirikilabs.tabakalera.eu) nos volveremos a juntar el grupo de Código Creativo. Esta vez lo hacemos con [Patxi Araujo](http://patxiaraujo.com/) camarada del metal con el que comparto, entre otras cosas, la pasión por el código. 

Patxi Araujo nos hablará de [vvvv](http://vvvv.org) y de la relación de sus proyectos con el Arte y con la Universidad.

Pero para que entendáis por qué no os podéis perder esta reunión os voy a contar una historia. Una historia que por la cantidad de veces que la cuento se convertirá en leyenda o fábula.

En el 2012 el grupo [teknotrakitana](http://www.teknotrakitana.com/) organizamos el Encounter (en el [2014](http://www.teknotrakitana.com/) se repitió) e invitamos a un colega de Patxi de la universidad, [Augusto Zubiaga](http://www.augustozubiaga.com/web/). Augusto estuvo hablándonos sobre un sistema neuronal con el que estaba trabajando, y a partir de esa conversación Patxi inició un trabajo personal. 

El sistema neuronal basado en las investigaciones de Shun-Ichi Amari (Amari 1977) (posiblemente desfasadas con las teorías actuales) son la pieza que Patxi utilizó como base. Lo interesante de estos osciladores neuronales es que permiten crear un comportamiento rítmico de una manera muy elegante. Son dos ecuaciones matemáticas que describen el comportamiento de los dos sistemas acoplados entre sí en el tiempo.

Podemos ver más abajo una representación gráfica de este sistema, e interactuar en la excitación con el slider. En este [post](http://interface.khm.de/index.php/research/experiments/netze-networks-neural-oscillators/) tenemos la explicación técnica y ejemplos en pure data, processing, etc


<div id="javascriptad" >
<script type="application/processing">
/***********************************************************************************************
 *   amari oscillator based on the mutual copling of an excitatory and an inhibitory neuron.
 ***********************************************************************************************/

AmariNeuron u, v;
HScrollbar hs1;
HScrollbar hs2;

float weight;

void setup ()
{
  size(200, 100);
  //initialize the excitatory neuron
  u = new  AmariNeuron(0, 300, -.0155, 10.905, 1.5, .18, 50, 60, 50, "u");
  //initialize the inhibitory neuron
  v = new  AmariNeuron(0, 300, -1, 10.905, 0, .18, 150, 60, 120, "v");
  background( 255 );
  //inhibitory connection from v->
  u.setAfferentConnection(v, -1.5);
  //excitatory connection from u->v
  v.setAfferentConnection(u, 1.5);  
  //hs1 = new HScrollbar(0, 14, width, 16, 16,150);
  hs1 = new HScrollbar(0, 14, width, 16, 16,width);
 
}

void draw ()
{
  noStroke();
  background( 255 );
  u.computeOutput();
  v.computeOutput();
  u.compute();
  v.compute();
  u.drawConnections();
  v.drawConnections();
  u.drawActivation();
  v.drawActivation();
  hs1.update();
  hs1.display();
  //hs2.update();
  //hs2.display();
  //u.tau = hs1.getPos() + 50;
  //v.tau = hs1.getPos() + 50;
  weight = hs1.getPos()/width;
  //text("set frequency", 8, 12);
  text("set weight"   , 8, 12);
  u.setWeight(weight);
  v.setWeight(weight);
}


/*************************************************
 * AamariNeuron is a class to compute and to visualize the dynamical equation for the 
 * temporal evolution of the activation variable of a neuron.
 *
 */
class AmariNeuron
{
  //activation variable u
  float u;
  //rate of change of u
  float u_dot;
  //
  float output;
  //list of afferent neuron
  ArrayList afferent_neurons;
  //array of afferent weights
  float [] afferent_weights;
  //parameter section
  //timescale \tau
  int tau;
  //resting level
  float h;
  //slope \beta of sigmoid function
  float beta;
  //self excitation
  float c_uu;
  //noise strength
  float c_n;
  //drawing parameters
  int pos_x, pos_y;
  int gray_value;
  //internal variables for time measurement 
  int t, dt, ot; 
  String name;
  //constructor
  AmariNeuron(float u_0, int tau, float h, float beta, float c_uu, float c_n, int pos_x, int pos_y, int gray_value, String name)
  {
    //copy paramter values
    this.tau=tau;
    this.h=h;
    this.pos_x=pos_x;
    this.pos_y=pos_y;
    this.gray_value=gray_value;
    this.beta=beta;
    this.c_uu=c_uu;
    this.c_n=c_n;
    this.name=new String(name);
    float weight=1;
    //initialize activation 
    u=u_0;
    output=sigmoid(u, beta);
    afferent_neurons=new ArrayList(); 
    afferent_weights=new float[0];
    randomSeed(0);
  }
  void setAfferentConnection(AmariNeuron afferentNeuron, float c_afferent)
  {
    this.afferent_neurons.add(afferentNeuron);
    this.afferent_weights=append(this.afferent_weights, c_afferent);
  }
  void computeOutput()
  {
    output=sigmoid(u, beta);
  }
  void compute()
  {
    //measure time
    t=millis();
    //time difference -> how long takes a single step through the loop
    dt=t- ot;
    //keep last time measurement
    ot=t;
    //check that delta time is not larger than relaxation time, if d_t>tau, the system becomes unstable
    if (dt>tau)
    {
      dt=tau/2;
    }
    //sum input from all afferent connections
    float s=0;
    for (int i=0;i<afferent_neurons.size();i++)
    {
      AmariNeuron afferent_neuron= (AmariNeuron) afferent_neurons.get(i);
      s+=afferent_weights[i]*weight*afferent_neuron.output;
    }
    //compute noise
    float n=random(-1, 1);
    // amari equation 
    u_dot=1.*dt/tau * (-u  + c_uu*output + s + c_n*n + h);
    //integration
    u+=u_dot;
  }


  void setWeight(float weight)
  {
    this.weight=weight;
  }
  //drawing methods
  void drawConnections()
  { 
    for (int i=0;i<afferent_neurons.size();i++)
    {   
      AmariNeuron afferent_neuron= (AmariNeuron) afferent_neurons.get(i);
      //line(afferent_neuron.pos_x, afferent_neuron.pos_y, pos_x, pos_y);
      int distance_x=(pos_x-afferent_neuron.pos_x);
      int distance_y=(pos_y-afferent_neuron.pos_y);
      float distance=sqrt(pow(distance_x, 2)+pow(distance_y, 2));
      float direction=atan2(distance_y, distance_x);
      noFill();
      strokeWeight(weight*2*abs(afferent_weights[i]));  
      stroke((1-afferent_neuron.output)*200); 
      float intermediate_point_x1=afferent_neuron.pos_x+distance/3*cos(direction) -  distance/3*sin(direction);
      float intermediate_point_x2=afferent_neuron.pos_x+2*distance/3*cos(direction) -  distance/3*sin(direction);
      float intermediate_point_y1=afferent_neuron.pos_y+distance/3*sin(direction) + distance/3*cos(direction);
      float intermediate_point_y2=afferent_neuron.pos_y+2*distance/3*sin(direction) +  distance/3*cos(direction);

      bezier(afferent_neuron.pos_x, afferent_neuron.pos_y, intermediate_point_x1, intermediate_point_y1, intermediate_point_x2, intermediate_point_y2, pos_x, pos_y);
      float bezier_x = bezierPoint(afferent_neuron.pos_x, intermediate_point_x1, intermediate_point_x2, pos_x, .8);
      float bezier_y = bezierPoint(afferent_neuron.pos_y, intermediate_point_y1, intermediate_point_y2, pos_y, .8);

      fill((1-afferent_neuron.output)*200);
      if (afferent_weights[i]<0)
      {
        direction=atan2( pos_y-bezier_y, pos_x-bezier_x);
        float elipse_x=pos_x-(10+30*output)/2*cos(direction);
        float elipse_y=pos_y-(10+30*output)/2*sin(direction);
        ellipse(elipse_x, elipse_y, 10, 10);
      }
      else
      {
        direction=atan2( pos_y-bezier_y, pos_x-bezier_x);
        pushMatrix();  
        float elipse_x=pos_x-(10+30*output)/2*cos(direction);
        float elipse_y=pos_y-(10+30*output)/2*sin(direction);

        translate(elipse_x, elipse_y);
        rotate(direction+PI/4);
        rectMode(CENTER);
        rect(0, 0, 8, 8);
        popMatrix();
      }
    }
    if (c_uu!=0)
    {
      stroke((1-output)*200);      
      fill((1-output)*200);
      float bezier_x = bezierPoint(pos_x, pos_x-50, pos_x-50, pos_x, .8);
      float bezier_y = bezierPoint(pos_y, pos_y+50, pos_y-50, pos_y, .8);
      float direction=atan2( pos_y-bezier_y, pos_x-bezier_x);
      pushMatrix();  
      float rect_x=pos_x-(10+30*output)/2*cos(direction);
      float rect_y=pos_y-(10+30*output)/2*sin(direction);
      translate(rect_x, rect_y);
      rotate(direction+PI/4);
      rectMode(CENTER);
      rect(0, 0, 8, 8);
      popMatrix();
      noFill();
      bezier(pos_x, pos_y, pos_x- 50, pos_y + 50, pos_x-50, pos_y-50, pos_x, pos_y);
    }
  }
  void drawActivation()
  {
    noStroke();
    fill(gray_value);
    ellipse(pos_x, pos_y, 15+25*output, 15+25*output);
    fill(10);
    text(name, pos_x, pos_y-25);
  }
  float sigmoid(float x, float beta)
  {
    return 1./(1+exp(-beta*x));
  }
}

class HScrollbar {
  int swidth, sheight;    // width and height of bar
  float xpos, ypos;       // x and y position of bar
  float spos, newspos;    // x position of slider
  float sposMin, sposMax; // max and min values of slider
  int loose;              // how loose/heavy
  boolean over;           // is the mouse over the slider?
  boolean locked;
  float ratio;

  HScrollbar (float xp, float yp, int sw, int sh, int l,int pos) {
    swidth = sw;
    sheight = sh;
    int widthtoheight = sw - sh;
    ratio = (float)sw / (float)widthtoheight;
    xpos = xp;
    ypos = yp-sheight/2;
    spos = pos;
    newspos = spos;
    sposMin = xpos;
    sposMax = xpos + swidth - sheight;
    loose = l;
  }

  void update() {
    if (overEvent()) {
      over = true;
    } else {
      over = false;
    }
    if (mousePressed && over) {
      locked = true;
    }
    if (!mousePressed) {
      locked = false;
    }
    if (locked) {
      newspos = constrain(mouseX-sheight/2, sposMin, sposMax);
    }
    if (abs(newspos - spos) > 1) {
      spos = spos + (newspos-spos)/loose;
    }
  }

  float constrain(float val, float minv, float maxv) {
    return min(max(val, minv), maxv);
  }

  boolean overEvent() {
    if (mouseX > xpos && mouseX < xpos+swidth &&
       mouseY > ypos && mouseY < ypos+sheight) {
      return true;
    } else {
      return false;
    }
  }

  void display() {
    noStroke();
    fill(204);
    rect(xpos, ypos, swidth*2, sheight);
    if (over || locked) {
      fill(0, 0, 0);
    } else {
      fill(102, 102, 102);
    }
    rect(spos, ypos, sheight, sheight);
  }

  float getPos() {
    // Convert spos to be values between
    // 0 and the total width of the scrollbar
    return spos * ratio;
  }
}


</script><canvas width="200" height="100" tabindex="0" id="__processing0" style="image-rendering: -webkit-optimize-contrast !important;"></canvas><br>
<div style="width: 210px" class="wp-caption alignleft"> <p class="wp-caption-text"><strong>Oscilador Neural:</strong> <i>u</i> es la neurona excitatoria (tono más oscuro) y la v es la neurona inhibitoria. Su nivel de activación se muestra por su tamaño. La conexión inhibitoria va de v a u que está marcada por un círculo, las conexiones excitadoras están marcados con un triángulo.</p>
</div></div>

 
Sobre esta <a href="http://patxiaraujo.com/portfolio/amari">base</a> Patxi inició su proceso creativo, que consistió en comprender e interpretar el <strong>código</strong>, para crear una narrativa sobre él. Desde mi visión externa, viendo como Patxi avanzaba en el proyecto, extraía de la base del código un significado, pero es un significado al margen de la propuesta matemática. 
Un primer resultado de este significado es el Patch(código[vvvv]) donde une 81 osciladores entre si.

<div class="img-wrapper">
  <img src="{{site.url}}/images/amari01.png" class="img-responsive" alt="Responsive image">
  <div class="img-footer">Desde este <a href="http://patxiaraujo.com/wp-content/uploads/2013/11/Amari01.png">enlace</a> podéis ver la imagen en su tamaño real.</div>
</div>

 Esta basta red de conexiones generan una red, una red en el sentido matemático, pero también un sentido narrativo. Cada una de esas líneas es conectada a mano, de la misma forma que lo hacen las rederas gallegas con los aparejos de la mar. Patxi con este patch no sólo programa, también dota de significado al código y a la matemáticas de Amari.

Y en este proceso creativo de extracción de significado es donde nos queremos mover a la hora de pensar sobre  código creativo.

[Abelardo Gil Fournier](http://abelardogfournier.org/texts/notas-presentacin-teknotrakiana--diciembre-2014) comenta que esta relación entre el código, el proceso y el resultado es muy interesante porque muestra cómo el código, para crecer en complejidad, sus resultados, necesita de nosotros, en tanto que fuentes de datos y de complejidad y que esto no ocurre solamente en los experimentos con código creativo, ocurre con sistemas computacionales en general. 

Y estamos llegando al final de la historia. Final que lo cuenta directamente Patxi en estos dos vídeos. El primero donde se puede ver la conducta de este conjunto complejo en red.
 
<iframe src="https://player.vimeo.com/video/79181133" width="660" height="495" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe> <p><a href="https://vimeo.com/79181133">Neural Network Amari (Simulation)</a> from <a href="https://vimeo.com/user1789947">patxi araujo</a> on <a href="https://vimeo.com">Vimeo</a>.</p>

Y en este segundo vídeo es donde el código ya muta y pasa a segundo plano, la metáfora se adueña del proyecto y aparece la Turba. Pero lo dicho, mejor escuchar a Patxi contándolo en directo.

Nos vemos el Jueves día 11 a las 18:30 en Hirikilabs donde hablaremos con Patxi Araujo de esto y mucho más.


<iframe src="https://player.vimeo.com/video/103224167" width="660" height="371" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe> <p><a href="https://vimeo.com/103224167">TURBA by Patxi Araujo. Concert in 15 movements for 64 neural oscillators</a> from <a href="https://vimeo.com/user1789947">patxi araujo</a> on <a href="https://vimeo.com">Vimeo</a>.</p>




