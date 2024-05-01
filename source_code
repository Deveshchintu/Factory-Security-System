#include <LiquidCrystal.h>
int mot=5;
int pot=A0;
int echo=2;
int trigg=3;
long time;
float distance;
LiquidCrystal lcd = LiquidCrystal(6,7,8,9,10,11);// Create an LCD object. Parameters: (RS, E, D4, D5, D6, D7):
void setup(){Serial.begin(9600);
lcd.begin(16, 2); // Specify the LCD's number of columns and rows.And this is 16x2 LCD so here(16,2)
pinMode(mot,OUTPUT);  // It simply specify the pin to behave either as an input or an output
pinMode(pot,INPUT);
pinMode(trigg,OUTPUT);
pinMode(echo,INPUT);}
void loop(){
  digitalWrite(trigg,LOW); // It is used to write a HIGH or a LOW value to a digital pin
  delayMicroseconds(5);
  digitalWrite(trigg,HIGH);
  delayMicroseconds(10);
  digitalWrite(trigg,LOW);
  time=pulseIn(echo,HIGH);
  distance=(0.017*time);
  delay(500);
  Serial.println("distance=");
  Serial.print(distance);
  Serial.println("cm");
  if (distance>=150){        // here we use if else condition for danger situation
   nodanger();}
  else if(distance<150){
   danger();}

}
void nodanger(){lcd.clear();  //  clears the LCD screen 
  lcd.print("NO DANGER");
                delay(2000);  // delay of some time
                
  int c=1024-analogRead(pot);     // It reads the value from the specified analog pin
  analogWrite(mot,c);     // It writes an analog value(PWM wave) to a pin
}
void danger(){lcd.clear();
  lcd.print("!!!DANGER!!!");
              delay(2000);         
analogWrite(mot,30);         // It writes an analog value(PWM wave) to a pin
             }
