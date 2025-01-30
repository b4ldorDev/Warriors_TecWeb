#include <SoftwareSerial.h>

int STBY =A2;
char instruccion;

//Motores
int PWMA = 11;
int MOTORA1 = 2;
int MOTORA2 = 4;

int PWMB =3;
int MOTORB1 =A3;
int MOTORB2 =5;


SoftwareSerial blue(3,2);
void setup()  
{
  Serial.begin(9600);
  blue.begin(9600);
  pinMode(MOTORB1, OUTPUT);
  pinMode(MOTORB2, OUTPUT);
  pinMode(STBY, OUTPUT); 
  pinMode(PWMB, OUTPUT);
  pinMode(PWMA, OUTPUT);
  pinMode(MOTORA1, OUTPUT);
  pinMode(MOTORA2, OUTPUT);

  //
  digitalWrite(STBY,1);

}

void loop() 
{
  while(blue.available())
  {
    instruccion = blue.read(); 
    Serial.println(instruccion);
    switch(instruccion){
      case 'a':
      GiroI();
      break;
      case 'w':
      avanzar();
      break;
      case 's':
      retroceder();
      break;      
      case 'd':
      GiroD();
      break;    
    }
  }

}

void retroceder(){
   digitalWrite(MOTORB1, 1);
   digitalWrite(MOTORB2, 0);
   analogWrite(PWMB, 150);
   digitalWrite(MOTORA1, 1);
   digitalWrite(MOTORA2, 0);
   analogWrite(PWMA, 150);
}


void avanzar(){
   digitalWrite(MOTORB1, 0);
   digitalWrite(MOTORB2, 1);
   analogWrite(PWMB, 150);
   digitalWrite(MOTORA1, 0);
   digitalWrite(MOTORA2, 1);
   analogWrite(PWMA, 150);
}


void GiroD(){
   digitalWrite(MOTORB1, 0);
   digitalWrite(MOTORB2, 1);
   analogWrite(PWMB, 70);
   digitalWrite(MOTORA1, 0);
   digitalWrite(MOTORA2, 1);
   analogWrite(PWMA, 200);
}


void GiroI(){
   digitalWrite(MOTORB1, 0);
   digitalWrite(MOTORB2, 1);
   analogWrite(PWMB, 70);
   digitalWrite(MOTORA1, 0);
   digitalWrite(MOTORA2, 1);
   analogWrite(PWMA, 200);
}
