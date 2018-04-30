# BRAZO
Brazo Robótico con 4 servos


Manuela Correa López,Estudiante de Ingenieria Electronica de la Universidad del Quindio. 
El brazo robotico ha sido diseñado en base a su funcionalidad en la vida cotidiana.

#include <Servo.h>
#define pinBase = (); // Debo colocarle el pin donde estará este servo
#define pinDerecho = ();
#define pinIzquierdo = ();
#define pinPinzas = ();

Servo Base;
Servo Derecho;
Servo Izquierdo;
Servo Pinzas;

void setup()                        // Corre una sola vez
{
Base.attach(pinBase);               // Utilizo es attach para poner a funcionar el servo
Derecho.attach(pinDerecho);
Izquierdo.attach(pinIzquierdo);
Pinzas.attach(pinPinzas);

Serial.begin(9600);                // Es la velocidad de los datos en Bits 
}













