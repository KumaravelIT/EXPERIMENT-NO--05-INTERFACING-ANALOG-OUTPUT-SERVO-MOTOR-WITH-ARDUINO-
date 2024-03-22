###  DATE: 22-03-2024

###  NAME: KUMARAVEL R
###  ROLL NO :212221220029
###  DEPARTMENT: INFORMATION TECHNOLOGY


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



#### Figure-01 SERVO MOTOR SPLIT VIEW 
Control 
An external controller (such as the Arduino) tells the servo where to go with a signal know as pulse proportional modulation (PPM) or pulse code modulation (which is often confused with pulse width modulation, PWM). PWM uses 1 to 2ms out of a 20ms time period to encode its information.
 
 
 ![image](https://user-images.githubusercontent.com/36288975/163544482-3027136f-7135-4f3d-a23f-8dc2fe04194d.png)

### Figure-02 SERVO MOTOR PINS

 ![image](https://user-images.githubusercontent.com/36288975/163544513-ca497421-e6ba-4f91-871f-5cfba77f22a8.png)


### Figure-03 SERVO MOTOR OVERVIEW 

 


 





CIRCUIT DIAGRAM
 
 
 ![image](https://user-images.githubusercontent.com/36288975/163544618-6eb8a7b5-7f1a-428a-8d9f-fd899b145efb.png)

### FIGURE 04 CIRCUIT DIAGRAM
<img width="686" alt="2024-03-22 (1)" src="https://github.com/KumaravelIT/EXPERIMENT-NO--05-INTERFACING-ANALOG-OUTPUT-SERVO-MOTOR-WITH-ARDUINO-/assets/117756569/44c9d9ad-5718-4120-b91f-521105529c8e">


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
Servo s1;
int po=0;
int red=9;
int green=8;
void setup()
{
  s1.attach(6);
  Serial.begin(9600);
  pinMode(red,OUTPUT);
  pinMode(green,OUTPUT);
}
void loop()
{
  for(po=0;po<=180;po+=5)
  {
    s1.write(po);
    delay(200);
    Serial.println(po);
    if(po>=120)
    {
      digitalWrite(red,HIGH);
      delay(200);
      digitalWrite(red,LOW);
      delay(200);
  }
  
}
for(po=180;po>=0;po-=5)
{
  s1.write(po);
    delay(200);
    Serial.println(po);
  if(po<=100)
  {
      digitalWrite(green,HIGH);
      delay(200);
      digitalWrite(green,LOW);
      delay(200);
  }
}  
  
  
  
  
   
    
 
}
```


### schematic diagram
![Web capture_22-3-2024_161543_www tinkercad com](https://github.com/KumaravelIT/EXPERIMENT-NO--05-INTERFACING-ANALOG-OUTPUT-SERVO-MOTOR-WITH-ARDUINO-/assets/117756569/cc9f9756-253c-4638-8deb-4e9db5db7b1a)

### output:
### graphical representation of angle:
![Web capture_22-3-2024_161516_www tinkercad com](https://github.com/KumaravelIT/EXPERIMENT-NO--05-INTERFACING-ANALOG-OUTPUT-SERVO-MOTOR-WITH-ARDUINO-/assets/117756569/45022cde-ece6-4375-a9b6-37e7963f2607)





### RESULTS: 
Arduino uno interfacing with servo motor is learned and angular position is controlled using PWM signal.
