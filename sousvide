#include "Adafruit_LEDBackpack.h"

Adafruit_7segment led_display1 = Adafruit_7segment();

const int sensorPin = A2;
float temperatura = 0; 
float leituraSensor = 0;
               
void setup(){
  Serial.begin(9600);
  pinMode(3, OUTPUT);
  
  led_display1.begin(112);
}
 
void loop(){
 
   leituraSensor = (analogRead(sensorPin));
   temperatura = map(leituraSensor,20.5,357.4,-40,125);
   /* Map entre 0,1023, lê entre 0 e 5V.
      Map entre 20.5,357.4, lê entre 0.1 e 1.75V */
                  
  if(temperatura > 32){
    digitalWrite(3, HIGH);
  }
  else if (temperatura < 28) {
    digitalWrite(3, LOW);
  }
  
  led_display1.println(temperatura);
  led_display1.writeDisplay();
  
  
   Serial.println((String)"temperatura = " + temperatura);
   
   delay(100); //INTERVALO DE 2 SEGUNDOS
 }
