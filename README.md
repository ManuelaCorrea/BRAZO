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
  
  if(bluetooth.available()>=2)  //si el modulo manda un dato es guarado en servopos y servopos1//
  {
    unsigned int servopos=bluetooth.read();                        //almacenamineto de datos en una variable entera sin signo//
    unsigned int servopos1=bluetooth.read();
    unsigned int realservo=(servopos1 *256)+servopos;             //operacion de los datos obtenidos
    Serial.println(realservo);                                    //impresion del resultado obtenido
    }
      if(realservo>=1000&&realservo<1180) //decision
      {
          int servo1=realservo;  //el valor de realservo se guarda en la variable entera servo1
          servo1=map(servo1,1000,1180,0,180); //rango de variacion, donde se limita al servo hasta ciertos angulos o valores
          Base.write(servo1);          //angulo al cual se mueve el servo 
          Serial.println("Servo Base ON"); //impresion de que el servo esta funcionando 
          delay(10);                   //retardo de 10 milisegundos
      }
            if(realservo>=2000&&realservo<2180)
                {
                  int servo2=realservo;
                  servo2=map(servo2,2000,2180,0,180);
                  Arriba.write(servo2);
                  Serial.println("Servo Arriba ON");
                  delay(10);
                }
                      if(realservo>=3000&&realservo<3180)
                    {
                      int servo3=realservo;
                      servo3=map(servo3,3000,3180,0,180);
                      Abajo.write(servo3);
                      Serial.println("Servo Abajo ON");
                      delay(10);
                    }
                           if(realservo>=4000&&realservo<4180)
                        {
                          int servo4=realservo;
                          servo4=map(servo4,4000,4180,0,180);
                          Garra.write(servo4);
                          Serial.println("Servo Garra ON");
                          delay(10);
                        }
                    

}












