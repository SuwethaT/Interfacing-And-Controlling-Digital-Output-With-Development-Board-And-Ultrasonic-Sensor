# Interfacing-And-Controlling-Digital-Output-With-Development-Board-And-Ultrasonic-Sensor
Interfacing And Controlling Digital Output With Development Board And Ultrasonic Sensor
AIM :
 To Interface And Control Digital Output With Development Board And Ultrasonic Sensor
 
COMPONENTS REQUIRED:
  1. Ultrasonic Sensor
  2. 1 KΩ resistor
  3. Arduino Uno
  4. USB Interfacing cable

Procedure:

Open Tinkercad → Circuits and create a new circuit.

Place an Arduino Uno R3 in the workspace.

Add a breadboard.

Add an HC-SR04 ultrasonic sensor.

Connect the VCC pin of the sensor to Arduino 5V.

Connect the GND pin to Arduino GND.

Connect TRIG to Arduino digital pin 9.

Connect ECHO to Arduino digital pin 10.

Add an LED to the breadboard.

ALGORITHM – Ultrasonic Sensor with Digital Output
Start

Connect the HC-SR04 ultrasonic sensor to the Arduino.

Connect the LED to digital pin 7.

Set TRIG as an output pin.

Set ECHO as an input pin.

Send a short pulse through the TRIG pin.

Receive the reflected signal through the ECHO pin.

Calculate the distance of the object using the echo time.

Check whether the distance is less than the specified limit (for example, 20 cm).

If the distance is less than 20 cm, turn ON the LED.

Otherwise, turn OFF the LED.

Repeat steps 6–11 continuously.

Stop.

Program:

const int trigPin = 9;
const int echoPin = 10;

void setup() {
  pinMode(trigPin, OUTPUT);
  pinMode(echoPin, INPUT);
  Serial.begin(9600);
}

void loop() {
  digitalWrite(trigPin, LOW);
  delayMicroseconds(2);
  
  digitalWrite(trigPin, HIGH);
  delayMicroseconds(10);
  digitalWrite(trigPin, LOW);
  
  long duration = pulseIn(echoPin, HIGH);
  int distance = duration * 0.0343 / 2; // Speed of sound wave divided by 2 (to and fro)
  
  Serial.print("Distance: ");
  Serial.print(distance);
  Serial.println(" cm");
  
  delay(500);
}

OUTPUT :

<img width="1512" height="715" alt="image" src="https://github.com/user-attachments/assets/d7d42747-ffae-4137-98fa-ac532402432e" />

Result:

The HC-SR04 ultrasonic sensor was successfully interfaced with the Arduino Uno in Tinkercad. The sensor detected the distance of an object, and the LED was controlled based on the detected distance.

When the object was less than 20 cm, the LED turned ON. When the object was more than 20 cm, the LED turned OFF.

Connect the LED anode to digital pin 7 through a 220 Ω resistor.

Connect the LED cathode to GND.
