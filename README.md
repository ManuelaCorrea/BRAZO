# BRAZO
/*Brazo Robótico con 4 servos
Version 1.0
Manuela Correa López y Johan Perdomo,
Estudiantes de Ingenieria Electronica de la Universidad del Quindio.
El brazo robotico ha sido diseñado en base a su funcionalidad en la vida
cotidiana. */

#include <Servo.h>

#define pinBase 9
#define pinArriba 11
#define pinAbajo 8                  //Declaración de pines
#define pinGarra 10
#define Angulo 30


Servo Base;                        //Declaracion de servos
Servo Arriba;
Servo Abajo;
Servo Garra;

void setup()
{
  Serial.begin(9600);            // Es la velocidad de los datos 
  Base.attach(pinBase);          // attach permite utilizar els Servo
  Arriba.attach(pinArriba);
  Abajo.attach(pinAbajo);
  Garra.attach(pinGarra);
}

void loop()
 {
   //Prueba base
    Base.write(80);      //Estos son los grados en los que se mueven los servos
    delay(500);
    Base.write(110);
    delay(500);
   // Base.write(180);
    //
    Arriba.write(120);
    delay(500);
    Arriba.write(160);
    delay(500);
    //
    Abajo.write(70);
    delay(500);
    Abajo.write(100);
    delay(500);
   //
    Garra.write(70);
    delay(500);
    Garra.write(50);
    delay(500);
}
