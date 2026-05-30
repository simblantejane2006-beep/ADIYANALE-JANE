# ADIYANALE
|DISCRIPTION|
|-----------|
|This prototype based on Arduino is designed to track soil health by utilizing an NPK (Nitrogen, Phosphorus, and Potassium) sensor.|
We refer to it as adiyanale since it draws inspiration from the agricultural goddess in Pre-Colonial Philippine mythology called "adinayale". The NPK sensors connect to the analog input pins of the Arduino to gather soil nutrient information. As the system starts operating, the Arduino persistently monitors the nitrogen, phosphorus, and potassium readings from the sensors. The LCD screen shows these readings alongside their related units in milligrams per kilogram (mg/kg).|
|The Idiyanale prototype acts as an intelligent agricultural device that integrates sensor technology and microcontroller programming for assessing soil fertility. By monitoring nutrients in real-time and providing future crop suggestions, the project seeks to aid farmers in enhancing crop yields, maximizing fertilizer efficiency, and encouraging sustainable farming methods.|





























# CODE
#include <Wire.h>
#include <LiquidCrystal_I2C.h>

LiquidCrystal_I2C lcd(0x27, 20, 4);

int button = A3;
int menuCounter = 0;

int nitrogenPin = A0;
int phosphorusPin = A1;
int potassiumPin = A2;


int nitrogen;
int phosphorus;
int potassium;

void setup(){
 Display_Lcd();
  delay(2000);
   Serial.begin(9600);


}
void loop(){
  
Npk_Show();

}

void Npk_Show(){
   nitrogen = analogRead(nitrogenPin);
  phosphorus = analogRead(phosphorusPin);
  potassium = analogRead(potassiumPin);
   int Value_button = analogRead(button);
    Serial.println(Value_button);


 
    lcd.clear();
    lcd.print("Nitrogen:"); lcd.print(nitrogen); lcd.print(" mg/kg");
    lcd.setCursor(0, 1);
     lcd.print("Phosphorus:"); lcd.print(phosphorus); lcd.print(" mg/kg");
    lcd.setCursor(0, 2);
    lcd.print("Potassium:");   lcd.print(potassium);   lcd.print(" mg/kg");
  
 
  if(nitrogen >= 60 && nitrogen <= 100 &&
         phosphorus >= 40 && phosphorus <= 60 &&
         potassium >= 200 && potassium <= 300)
      {
         lcd.setCursor(0, 3);
        lcd.print("HEALTHY SOIL");
      }
      else
      {
         lcd.setCursor(0, 3);
      lcd.print("UNHEALTHY SOIL");
        
      }

      
     

delay(2000);

}

void Display_Lcd(){
  lcd.init();
  lcd.backlight();

  lcd.setCursor(0,0);
  lcd.print("NPK System Ready");
 
}
void Eggplant(){
   if(nitrogen >= 60 && nitrogen <= 100 &&
         phosphorus >= 40 && phosphorus <= 60 &&
         potassium >= 200 && potassium <= 300)

} 
void Pechay(){
   if(nitrogen >= 60 && nitrogen <= 100 &&
         phosphorus >= 40 && phosphorus <= 60 &&
         potassium >= 200 && potassium <= 300)

}
void Ampalaya(){
   if(nitrogen >= 60 && nitrogen <= 100 &&
         phosphorus >= 40 && phosphorus <= 60 &&
         potassium >= 200 && potassium <= 300)

}
void BellPepper(){
   if(nitrogen >= 60 && nitrogen <= 100 &&
         phosphorus >= 40 && phosphorus <= 60 &&
         potassium >= 200 && potassium <= 300)

}
void Kamatis(){
   if(nitrogen >= 60 && nitrogen <= 100 &&
         phosphorus >= 40 && phosphorus <= 60 &&
         potassium >= 200 && potassium <= 300)

}
