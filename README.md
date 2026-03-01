Hi, I'm Frostbyte, and this is a project on how to make a Light-Emitting Diode.

Materials you will need in the Arduino Kit:
	1. Arduino Uno
	2. Breadboard
	3. Jumper Wires
	4. LED
	5. Fixed Resistor

Procedure:
	1. Assemble the circuit similar to something shown in Figure A. The wire connecting the LED to the UNO should be at Pin 9 (Digital). Also, ensure that the wire connecting the 	resistor to the UNO should be at GND Pin (Power).
	2. Follow the code as follows:

	int led = 9;         // the PWM pin the LED is attached to
int brightness = 0;  // how bright the LED is
int fadeAmount = 5;  // how many points to fade the LED by

// the setup routine runs once when you press reset:
void setup() {
  // declare pin 9 to be an output:
  pinMode(9, OUTPUT);
}

// the loop routine runs over and over again forever:
void loop() {
  // set the brightness of pin 9:
  analogWrite(9, brightness);

  // change the brightness for next time through the loop:
  brightness = brightness + fadeAmount;

  // reverse the direction of the fading at the ends of the fade:
  if (brightness <= 0 || brightness >= 255) {
    fadeAmount = -fadeAmount;
  }
  // wait for 30 milliseconds to see the dimming effect
  delay(30);
}

3: Run the program and se it go!
