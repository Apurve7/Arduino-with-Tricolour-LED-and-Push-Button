Arduino Tricolor LED with Push Button Control 

This project shows you how to control a common cathode Tricolor (RGB) LED with an Arduino. Initially, the LED cycles through red, green, and blue. A push button is then added to let you change the color manually with each press. It's a great starting point for learning about digital outputs (digitalWrite()) and inputs (digitalRead()).

Hardware Requirements 🔩
You'll need the following components:

An Arduino board (e.g., Arduino Uno)

1 x Common Cathode Tricolor LED

3 x 100Ω Resistors (for the LED)

1 x 100Ω Resistor (for the push button)

1 x Push Button

1 x Breadboard

Jumper Wires

Workflow & Instructions 🛠️
1. Understand the Circuit
Common Cathode LED: This LED has four pins. The longest pin is the common cathode, which connects to Ground (GND). The other three pins (Red, Green, Blue) connect to digital output pins on the Arduino. Sending a HIGH signal to a color pin turns it on.

Push Button with Pull-Down Resistor: The button acts as a digital input. A pull-down resistor ensures a stable reading. When the button isn't pressed, the resistor pulls the input pin to GND, making the Arduino read a reliable LOW. When pressed, the button connects the input pin to 5V, so the Arduino reads HIGH.

2. Assemble the Circuit
Connect the components on the breadboard as follows:

Tricolor LED:

Connect the longest pin (cathode) of the LED to GND on the Arduino.

Connect the Red pin to a 100Ω resistor, then connect the resistor to Digital Pin 12.

Connect the Green pin to a 100Ω resistor, then connect the resistor to Digital Pin 11.

Connect the Blue pin to a 100Ω resistor, then connect the resistor to Digital Pin 10.

Push Button:

Connect one leg of the push button to 5V on the Arduino.

Connect the opposite leg to Digital Pin 4.

On the same leg connected to Pin 4, add the 100Ω resistor and connect its other end to GND.

3. Understand and Upload the Program
The code makes the LED cycle through colors only when the button is held down.

void setup():

Sets the LED pins (10, 11, 12) as OUTPUT.

Sets the button pin (4) as INPUT.

void loop():

The action is wrapped in an if (digitalRead(4) == HIGH) statement. This means the code inside only runs when the button is being pressed.

While the button is pressed, the Arduino cycles through blue (pin 10), green (pin 11), and red (pin 12).

4. Compile and Test
Connect your Arduino to your computer via USB.

In the Arduino IDE, paste your code and select the correct board and port.

Click the Verify button to compile the code.

Click the Upload button to send the program to your Arduino.

Press the push button. The LED should cycle through blue, green, and red.

Release the button. The blinking should stop immediately.
