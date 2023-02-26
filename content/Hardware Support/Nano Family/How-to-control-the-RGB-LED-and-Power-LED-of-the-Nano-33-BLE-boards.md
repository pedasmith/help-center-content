---
title: "How to control the RGB LED and Power LED of the Nano 33 BLE boards?"
id: 360016724140
---

The [Nano 33 BLE Sense](https://store.arduino.cc/products/arduino-nano-33-ble-sense) board has an inbuilt RGB LED which is connected to pin 22, 23, 24.

This information is available on the Nano 33 BLE's boards [variant file](https://github.com/arduino/ArduinoCore-nRF528x-mbedos/blob/master/variants/ARDUINO_NANO33BLE/pins_arduino.h#L54).

```arduino
#define RED 22     
#define BLUE 24     
#define GREEN 23
#define LED_PWR 25
```

Below is the general sketch to play around with the RGB led on the Nano 33 BLE boards and user can modify the sketch according to the requirements.

```arduino
/// How to control the RGB Led and Power Led of the Nano 33 BLE boards.  

 #define RED 22     
 #define BLUE 24     
 #define GREEN 23
 #define LED_PWR 25
 // Declare the function ahead of time with the arguments.
void SetLedColor(PinStatus red, PinStatus green, PinStatus blue);

void setup() {

 // initialize the digital Pin as an output
  pinMode(RED, OUTPUT);
  pinMode(BLUE, OUTPUT);
  pinMode(GREEN, OUTPUT);
  pinMode(LED_PWR, OUTPUT);
}

// the loop function runs over and over again
// It will turn the lights from red to green to blue
// and then white (along with the power) and then off,
// and then do it all over again.
void loop() {
  SetLedColor(LOW, HIGH, HIGH);   // Red=LOW=ON, Green and Blue both HIGH=OFF
  delay(1000);                    // wait for a second
  SetLedColor(HIGH, LOW, HIGH);
  delay(1000);                    // wait for a second
  SetLedColor(HIGH, HIGH, LOW);   // Green
  delay(1000);  
  SetLedColor (LOW, LOW, LOW);    // "White"
  digitalWrite(LED_PWR, HIGH);
  delay(1000);  
  SetLedColor (HIGH, HIGH, HIGH); // "Off"
  digitalWrite(LED_PWR, LOW);
  delay(1000);  
}

// Function to set the color of the RGB LED on the 
// Nano 33 BLE. The LED is controlled by three pins
// LEDR, LEDG, LEDR for Red, Green, and Blue; each 
// can be ON or OFF.
// Unusually, the pins are "Active Low", meaning that
// to turn the color ON your need to set the pin LOW.
void SetLedColor(PinStatus red, PinStatus green, PinStatus blue)
{
      digitalWrite(LEDR, red);
      digitalWrite(LEDG, green);
      digitalWrite(LEDB, blue);
}

```
