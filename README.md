###  DATE: 22.03.2024

###  NAME: RAGUL RAAJAN T
###  ROLL NO : 212223100043
###  DEPARTMENT: COMPUTER SCIENCE AND ENGINEERING [CYBER SECURITY]


# EXPERIMENT NO 05 INTERFACING ANALOG OUTPUT SERVO MOTOR WITH ARDUINO

### AIM
To interface an Analog output (servo motor) and modify the angular displacement of the servo using PWM signal .
COMPONENTS REQUIRED:
1.	Servo motor of choice (9v is preferred )
2.	1 KΩ resistor 
3.	Arduino Uno 
4.	USB Interfacing cable 
5.	Connecting wires 
6.	Servo rated power supply (dc source )


### THEORY
Servo motors and are constructed out of basic DC motors, by adding:
•	 gear reduction
•	 a position sensor for the motor shaft
•	 an electronic circuit that controls the motor's operation
Typically, a potentiometer (variable resistor) measures the position of the output shaft at all times so the controller can accurately place and maintain its setting.
Servo motors are used for angular positioning, such as in radio control airplanes.  They typically have a movement range of 180 deg but can go up to 210 deg.The output shaft of a servo does not rotate freely, but rather is made to seek a particular angular position under electronic control. 


![image](https://user-images.githubusercontent.com/36288975/163544439-1f477927-fcd4-42f0-9ce4-c863fdbf1210.png)



#### SERVO MOTOR SPLIT VIEW 
Control 
An external controller (such as the Arduino) tells the servo where to go with a signal know as pulse proportional modulation (PPM) or pulse code modulation (which is often confused with pulse width modulation, PWM). PWM uses 1 to 2ms out of a 20ms time period to encode its information.
 
 
 ![image](https://user-images.githubusercontent.com/36288975/163544482-3027136f-7135-4f3d-a23f-8dc2fe04194d.png)

### SERVO MOTOR PINS

 ![image](https://user-images.githubusercontent.com/36288975/163544513-ca497421-e6ba-4f91-871f-5cfba77f22a8.png)


###  SERVO MOTOR OVERVIEW 
CIRCUIT DIAGRAM
 
 
 ![image](https://user-images.githubusercontent.com/36288975/163544618-6eb8a7b5-7f1a-428a-8d9f-fd899b145efb.png)

### CIRCUIT DIAGRAM
![Screenshot 2024-03-22 104310](https://github.com/RAGULRAAJAN/EXPERIMENT-NO--05-INTERFACING-ANALOG-OUTPUT-SERVO-MOTOR-WITH-ARDUINO-/assets/147473144/c546e89f-9a9a-464a-b888-aa926d67caef)

### SCHEMATIC-DIAGRAM
![Screenshot 2024-03-22 103702](https://github.com/RAGULRAAJAN/EXPERIMENT-NO--05-INTERFACING-ANALOG-OUTPUT-SERVO-MOTOR-WITH-ARDUINO-/assets/147473144/f5456e47-bc11-4e3b-bb48-797a9e8594cf)
### GRAPHICAL REPRESENTATION:
![Screenshot 2024-03-22 104723](https://github.com/RAGULRAAJAN/EXPERIMENT-NO--05-INTERFACING-ANALOG-OUTPUT-SERVO-MOTOR-WITH-ARDUINO-/assets/147473144/67ecc11b-d906-46c0-9d48-de047eae2533)


### PROCEDURE:
1.	Connect the circuit as per the circuit diagram 
2.	Connect the board to your computer via the USB cable.
3.	If needed, install the drivers.
4.	Launch the Arduino IDE.
5.	Select your board (If you the board is arduino uno, select accordingly).
6.	Select your serial port, accordingly ( E.g. COM5 )
7.	Open the file of the program  and verify the error , clear if any errors that are existing 
8.	Upload the program and check for the physical working. 
9.	Ensure safety before powering up the device.


### PROGRAM :
 

```
#include<Servo.h>
Servo sr1;
int pos=0;
int red=9;
int green=8;

void setup()
{
  sr1.attach(6);
  Serial.begin(9600);
  pinMode(red,OUTPUT);
  pinMode(green,OUTPUT);
  
}

void loop()
{
  for(pos=0;pos<=180;pos+=5)
  {
    sr1.write(pos);
      delay(200);
    Serial.println(pos);
    if(pos>=120)
  {
    digitalWrite(red,HIGH);
      delay(200);
    digitalWrite(red,LOW);
      delay(200);
  }
  }
    

   for(pos=180;pos>=0;pos-=5)
 {
    sr1.write(pos);
       delay(200);
     Serial.println(pos);
      if(pos<=100)
  {
    digitalWrite(green,HIGH);
      delay(200);
    digitalWrite(green,LOW);
      delay(200);
    
  }
 }
  

}
```



### RESULTS: 
Arduino uno interfacing with servo motor is learned and angular position is controlled using PWM signal.
