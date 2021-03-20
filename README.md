# Matriz-led-con-arduino

#include "LedControl.h"    

LedControl lc=LedControl(11,12,10,1); 

int sleep = 200;  

byte L_1[8] = {  
  B00000000,
  B00000000,
  B00100000,
  B00010000,
  B00001111,
  B00010000,
  B00100000,
  B00000000
};

void setup() {
  lc.shutdown(0,false);     
  lc.setIntensity(0,4);    
  lc.clearDisplay(0);     
}

void loop(){
  def_1();   
  delay(sleep);     
 
}

void def_1(){
  for (int i = 0; i < 8; i++)   
  {
    lc.setRow(0,i,L_1[i]);  
  }
}
