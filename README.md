# color-sensor-LDR
Colour Sensor that is LDR (light dependent resistor) based and identify three primary colours Red, Green, Blue.
 
 Components used:
 1) LDR.
 2) RGB LED(2 in number)
 3) NodeMCU and USB 
 4) Jumper wires
 
 
 DESIGN::
 
    Hardware:
  RGB LED connections to NodeMCU ---> connect the negative of LED to ground and the other lines of LED to three digital pins ,say D1,D3,D5,of the NodeMCU.Similarly connect the other RGB LED to the digital pins D0,D4,D6.
  LDR connections to NodeMCU---> connect one line of terminal of LDR to GND and the other to analog pin A0 of the NodeMCU.Also make sure to surround the LDR with insulating tape so that no other light interferes(refer figure attached).
  
    Design flow and Arduino IDE:
   here first we use one of the RGB with the LDR we read and store the value of red,green and blue light emiited into variables defined.
  
  digitalWrite(rled,HIGH);//red color value detection
  delay(40);
red=analogRead(ldrValue);
Serial.print('r');
Serial.println(red);
delay(10);
digitalWrite(rled,LOW);

digitalWrite(bled,HIGH);//blue color value detection
delay(40);
blue=analogRead(ldrValue);delay(10);
Serial.print('b');
Serial.println(blue);
digitalWrite(bled,LOW);

digitalWrite(gled,HIGH);//green color value detction
delay(40);
green=analogRead(ldrValue);delay(10);
Serial.print('g');
Serial.println(green);
digitalWrite(gled,LOW);
   
   Now on placing the red/green/blue coloured object over the LDR(surrounded by insulating tape) we run a comparison instruction to compare the already stored values and emit the light accordingly the second (main) output RGB LED.
    if (red>green&&red>blue)
   { 
  rvalue=HIGH;
  
Serial.println('r');
        
   }
   else 
    rvalue=LOW;
 
   
   if (green>red&&green>blue)
   { 
  gvalue=HIGH;
  
Serial.println('g');
        
   }
    else 
    gvalue=LOW;
   
   
   if (blue>red&&blue>green)
   {
bvalue=HIGH;
Serial.println('b');
        
   }
   else 
  bvalue=LOW;
 
   digitalWrite(gout,gvalue);
  digitalWrite(bout,bvalue);
  digitalWrite(rout,rvalue);
  
  
  GO check out the entire code and images to understand better.
 
   
  
 
  
 

  
  
