//WRITTEN BY TINKERER 

#include<Servo.h>
Servo servo1, servo2, servo3, servo4;
const int pot1 = 0, pot2 = 1, pot3 = 2, pot4 = 3;
int pot1val, pot2val, pot3val, pot4val, i = 0;
int pot1angle, pot2angle, pot3angle, pot4angle;
const int button1 = 12;
const int button2 = 13;
int button1presses = 0;
boolean button2pressed = false;
int servo1pos[] = {1, 1, 1, 1}, servo2pos[] = {1, 1, 1, 1}, servo3pos[] = {1, 1, 1, 1}, servo4pos[] = {1, 1, 1, 1};      //To save more positions change the size of the arrays 
void setup()
{
  Serial.begin(9600);
  servo1.attach(9);
  servo2.attach(6);
  servo3.attach(5);
  servo4.attach(3);
  pinMode(button1, INPUT);
  pinMode(button2, INPUT);
}
void loop()
{
  pot1val = analogRead(pot1);
  //Serial.println(pot1val);
  pot1angle = map(pot1val, 0, 1023, 0, 90);
  servo1.write(pot1angle);
  pot2val = analogRead(pot2);
  //Serial.println(pot2val);
  pot2angle = map(pot2val, 0, 1023, 0, 180);
  servo2.write(pot2angle);
  pot3val = analogRead(pot3);
  //Serial.println(pot3val);
  pot3angle = map(pot3val, 0, 1023, 0, 120);
  servo3.write(pot3angle);
  pot4val = analogRead(pot4);
  //Serial.println(pot4val);
  pot4angle = map(pot4val, 0, 1023, 60, 180);
  servo4.write(pot4angle);
  if (digitalRead(button1) == HIGH)
  {
    button1presses++;
    for (i = 0; i < 1; i++)
    {
      servo1pos[ button1presses - 1] = pot1angle;
      servo2pos[button1presses - 1] = pot2angle;
      servo3pos[button1presses - 1] = pot3angle;
      servo4pos[button1presses - 1] = pot4angle;
      Serial.println("position saved");
    }
  }
  if (digitalRead(button2) == HIGH)
  {
    button2pressed = true;
  }
  if (button2pressed == true)
  {
    for (int i = 0; i <= 3; i++)
    {
      Serial.println("Moving...");
      servo1.write(servo1pos[i]);
      servo2.write(servo2pos[i]);
      servo3.write(servo3pos[i]);
      servo4.write(servo4pos[i]);
      delay(500);
    }
  }
  delay(100);
}
