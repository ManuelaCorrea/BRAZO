# BRAZO
Brazo Robótico con 4 servos
Version 1.0
Manuela Correa López y Johan Perdomo, Estudiantes de Ingenieria Electronica de la Universidad del Quindio. 
El brazo robotico ha sido diseñado en base a su funcionalidad en la vida cotidiana y a su vez tambien ha sido 
diseñada una aplicación que permite su maneja por via bluetooth.

#include <SoftwareSerial.h>     // Esta libreria permite recibir datos externos "BLUETOOTH"
#include <Servo.h>

#define pinBase 3
#define pinArriba 5
#define pinAbajo 6        //Declaración de pines 
#define pinGarra 9
#define Angulo 

Servo Base;
Servo Arriba;
Servo Abajo;
Servo Garra ;
int bluetoothTx = 10; // El modulo bluetooth esta conectado en estos pines
int bluetoothRx = 11; // El modulo bluetooth esta conectado en estos pines
SoftwareSerial bluetooth(bluetoothTx, bluetoothRx);


void setup()                  // Corre una sola vez         

{      
Base.attach(pinBase);         // Utilizo es attach para poner a funcionar el servo
Arriba.attach(pinArriba);
Abajo.attach(pinAbajo);
Garra .attach(pinGarra );
Serial.begin(9600);           // Es la velocidad de los datos en Bits 
bluetooth.begin(9600);

}

void loop()
{
  if (bluetooth.available()>=2)        //si el modulo manda un dato es guarado en servopos y servopos1//
  {
  unsigned  int movimiento=bluetooth.read();   // Almacenamiento de datos en una variable entera sin signo
  unsigned int movimiento2=bluetooth.read();
  unsigned int SERVO=(movimiento2*256)+movimiento; // operacion de los datos obtenidos
  Serial.println(SERV,
  SERVO1= map(SERCO1, 1000,1180,O,180);    //Rango  de variación, donde se limita al servo hasta ciertos angulos o valores
  Base.Write(SERVO1);                                        // 
  Serial.println("Servo Base on");
  delay (10);
  
  if (SERVO>=1000&&SERVO<1180)   //El valor de SERVO se guarda en la variable SERVO1
  {
    int SERVO1= SERVO
  

