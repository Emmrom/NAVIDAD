Coloca aqui tu codigo processing de muestra
/* 31 agosto  */
/* Islas Romero Jose Emmanuel */
/* Progrma que muestra Autos*/

Auto tsuru;//se instancia a un objeto de la clase auto
Auto vocho;
Auto mustang;

void setup() {
  size(200, 200);
  //crea un auto llamdo tsuru de color azul en x=0 y y=125
  tsuru = new Auto(color(255,255,0),0,50,1);// se declara un objeto de la clase auto llamda vocho
  //crea un auto llamdo vocho de color amarillo en x=0 y y=50
  vocho = new Auto(color(0,0,255),0,125,1);
  mustang = new Auto(color(255,0,0),0,175,2);
}

class Auto {//se define una clase llamada auto
  color c;// variables
  int posx;// variables
  int posy;// variables
  int velocidad;// variables
  
  /*constructor de la clase auto. Recibe como parametros
  el color, la posicion x y la posicion y del objeto a construir*/
  
  Auto(color temporalC, int temporalPosx, int temporalPosy, int temporalVel) {// constructor de la clse 
    c = temporalC;
    posx = temporalPosx;
    posy = temporalPosy;
    velocidad = temporalVel;
  }
  
  void despliega() {//metodo (funcion)
    rectMode(CENTER);
    fill(c);
    rect(posx, posy, 20, 10);
  }
  
  void conduce() {//metodo (funcion)
    posx = posx + velocidad;
    if (posx > width) {
      posx = 0;
    }
  }
}

void draw() {
  background(255);
  tsuru.despliega();//se opera el objeto vocho al llamar a sus metodos
  tsuru.conduce();

  vocho.despliega();
  vocho.conduce();

  mustang.despliega();
  mustang.conduce();
}
