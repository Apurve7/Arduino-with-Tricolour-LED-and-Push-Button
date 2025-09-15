# Arduino-with-Tricolour-LED-and-Push-Button
This project demonstrates how to control a common cathode Tricolor (RGB) LED using an Arduino. The LED is programmed to cycle through its primary colors—red, green, and blue. A push button is then integrated to allow manual control, changing the color with each press. This is an excellent introductory project for learning about digital outputs (digitalWrite()) and digital inputs (digitalRead()) on the Arduino platform. 

Hardware Requirements 
You'll need the following components for this experiment:

An Arduino board (e.g., Arduino Uno)

1 x Common Cathode Tricolor LED

3 x 1000Ω Resistors (for limiting current to the LED pins)

1 x 100Ω Resistor (as a pull-down resistor for the push button)

1 x Push Button

1 x Breadboard

Jumper Wires

Workflow & Instructions
1. Understand the Connection Circuit
Common Cathode LED: This type of LED has four pins. The longest pin is the common cathode, which must be connected to Ground (GND). The other three pins correspond to Red, Green, and Blue and are connected to digital output pins on the Arduino. We send a HIGH signal to a color pin to turn it on.

Push Button with Pull-Down Resistor: The push button is used as a digital input. To ensure a stable reading, we use a pull-down resistor. When the button is not pressed, the resistor connects the input pin to GND, making the Arduino read a reliable LOW signal. When the button is pressed, it connects the input pin to 5V, making the Arduino read a HIGH signal.

2. Connect the Circuit
Assemble the components on the breadboard according to the pin numbers used in your code:

Tricolor LED:

Connect the longest pin (cathode) of the LED to a GND pin on the Arduino.

Connect the Red pin of the LED to one end of a 100Ω resistor. Connect the other end of the resistor to Digital Pin 10.

Connect the Green pin of the LED to one end of a 100Ω resistor. Connect the other end of the resistor to Digital Pin 11.

Connect the Blue pin of the LED to one end of a 100Ω resistor. Connect the other end of the resistor to Digital Pin 12.

Push Button:

Connect one leg of the push button to the 5V pin on the Arduino.

Connect the opposite leg to Digital Pin 4 on the Arduino.

Connect that same leg (the one connected to Pin 4) to one end of the 100Ω resistor. Connect the other end of the resistor to GND.

3. Understand and Upload the Program
Your code makes the blinking sequence dependent on holding the button down.

The void setup() function:
Sets the LED pins (10, 11, 12) as OUTPUT.

Sets the button pin (4) as INPUT.

The void loop() function:
The entire action is wrapped in an if (digitalRead(4) == HIGH) statement. This means the code inside the curly braces will only run when the button is actively being pressed.

If the button is pressed, the Arduino quickly blinks pin 10 (red), then pin 11 (green), and finally pin 12 (blue).

The loop() function repeats this check. As long as you hold the button down, the if condition remains true, and the R-G-B blinking sequence will repeat continuously. When you release the button, the condition becomes false, and the LEDs turn off.

4. Compile and Test
Connect your Arduino to your computer via USB.

In the Arduino IDE, paste your code, and select the correct board and port.

Click the Verify button to compile the code.

Click the Upload button to send the program to your Arduino.

Press the push button. The LED should begin blinking cycle of red, green, and blue with each press

Release the button. The blinking should stop immediately.
