# Robotics-LED-blink-
# LED Blinking Using Push Button (Arduino):
## Objective:
Turns on and blinks a light emitting diode(LED) connected to digital pin 13, when pressing a pushbutton attached to pin 2.
## Components:
1. Arduino Uno
2. LED
3. Push Button
4. 220Ω Resistor
5. Breadboard
6. Connecting Wires
7. ## Process:
8. We first initialize the LED pin as output and button pin as output.
   - Inside the void loop, we check if the button is pressed. If yes, the button state is high and the LED blinks. 
   - Blinking speed is controlled by delay(100).
     Blinking happens by setting the pin to high for 100ms and then setting it to low by dropping voltage to 0V.
     It again waits for 100ms and then the loop continues.
  -  When the button is not pressed, the LED is turned off.

## Code:
// set pin numbers:
const int buttonPin = 2;  // number of button pin
const int ledPin = 13;    // number of the LED pin
int buttonState = 0;  // variable for reading the pushbutton status

void setup() {
  pinMode(ledPin, OUTPUT);
  pinMode(buttonPin, INPUT);
}

void loop() {
  // read the state of the pushbutton value:
  buttonState = digitalRead(buttonPin);

  if (buttonState == HIGH) {
    // turn LED on:
    digitalWrite(ledPin, HIGH);
    delay(100);
    digitalWrite(ledPin, LOW);
    delay(100);
  } else {
    // turn LED off:
    digitalWrite(ledPin, LOW);
  }
}
