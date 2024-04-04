![image](https://github.com/vasanthkumarch/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/36288975/739cc470-48c8-4873-a730-6319b4afc602)
###  DATE: 04-04-2024

###  NAME: ETTA SUPRAJA
###  ROLL NO :212223220022
###  DEPARTMENT:INFORMATION TECHNOLOGY
# Experiment-no-6-DC-Motor-Speed-Control-Using-Arduino
### AIM : To control the speed and the direction of a DC motor using L293D driver ic( H- bridge)

### Components Required:
•	Arduino UNO board
•	L293D driver
•	12V DC motor
•	10K ohm potentiometer
•	Pushbutton
•	12V source
•	Breadboard
•	Jumper wires
### THEORY 
The L293D quadruple half-H drivers chip allows us to drive 2 motors in both directions, with two PWM outputs from the Arduino we can easily control the speed as well as the direction of rotation of one DC motor. (PWM: Pulse Width Modulation).
Arduino DC motor control circuit:
Project circuit schematic diagram is the one below.

![image](https://user-images.githubusercontent.com/36288975/167763051-b230c183-afc5-46f2-ba95-0f95e10dd6c9.png)
FIGURE-01 H BRIDGE CIRUCIT INTERFACE 
 
The speed of the DC motor (both directions) is controlled with the 10k potentiometer which is connected to analog channel 0 (A0) and the direction of rotation is controlled with the push button which is connected to pin 8 of the Arduino UNO board. If the button is pressed the motor will change its direction directly.
The L293D driver has 2 VCCs: VCC1 is +5V and VCC2 is +12V (same as motor nominal voltage). Pins IN1 and IN2 are the control pins where:
![image](https://user-images.githubusercontent.com/36288975/167763120-1421c2c5-8381-49eb-b376-03f6e1113b7a.png)
TABLE-01 EXITATION TABLE FOR H BRIDGE 

As shown in the circuit diagram we need only 3 Arduino terminal pins, pin 8 is for the push button which toggles the motor direction of rotation. Pins 9 and 10 are PWM signal outputs, at any time there is only 1 active PWM, this allows us to control the direction as well as the speed by varying the duty cycle of the PWM signal. The active PWM pin decides the motor direction of rotation (one at a time, the other output is logic 0).

### PROGRAM 
int enable=6;
int input1=3;
int input2=4;


void setup()
{
  pinMode(enable, OUTPUT);
   pinMode(input1, OUTPUT);
   pinMode(input2, OUTPUT);
}

void loop()
{
  analogWrite(enable, 80);
  delay(1000); 
  digitalWrite(input1, HIGH);
  digitalWrite(input2, LOW);
  delay(7000);
  digitalWrite(input1, LOW);
  digitalWrite(input2, HIGH);
  delay(7000);
}

### OUTPUT
![Screenshot 2024-04-04 142035](https://github.com/vasanthkumarch/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/151641352/536e1243-f8d3-43de-9c64-be5d698745c5)

![Screenshot 2024-04-04 142048](https://github.com/vasanthkumarch/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/151641352/98ac0781-5099-4312-9eb8-9b1fd2891f6b)


### GRAPH AND TABULATION 

![Screenshot 2024-04-04 142100](https://github.com/vasanthkumarch/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/151641352/1bae202c-bb38-4f7d-8914-5c8dcf3d5828)

![Screenshot 2024-04-04 142109](https://github.com/vasanthkumarch/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/151641352/20523a1d-36af-4419-957b-c9c6868ab0d2)


### RESULTS AND DISCUSSION 
Thus we have controled the speed and the direction of a DC motor using L293D driver ic(H-bridge).

