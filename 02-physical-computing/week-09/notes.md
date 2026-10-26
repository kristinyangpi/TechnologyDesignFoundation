# Week 9 📅 Oct 19–23, 2026

---

### 🔌 Electronics 📟 Oct 20 — Introduction to Physical Computation and Arduino

**Course agenda: two skill-building exercises (shorter projects) and two foundational projects**

| Project | Length | Focus | Due |
|---|---|---|---|
| **Foundational project 1: Expressive Mechanics** | 1.5 weeks | Arduino ↔ p5.js, computer vision, mechanical movement | Nov 12 |
| **Foundational project 2: Ambient Display** | 3 weeks | ESP32 ↔ web API; display through light, water, mechanical movement, etc.; museum quality | Dec 8 (Jacobs Design Showcase) |


**What we did**
- Received our Arduino kit!!! and went through what's inside
<img width="992" height="557" alt="截圖 2026-10-25 晚上11 24 56" src="https://github.com/user-attachments/assets/90ddd861-2904-46b1-9243-55ec971fd2f8" />

- Installed the Arduino software and learned how to write instructions and upload them to the board, following 🔗 [Dr.Sudhu's Arduino tutorial](https://github.com/loopstick/ArduinoTutorial)
- Learned what a resistor is, what it does, and how to tell resistors apart using the color code
- Hello, World!
<img width="816" height="840" alt="hello world" src="https://github.com/user-attachments/assets/7348e55e-f889-438a-a030-d2384c477489" />

- Successfully made the ✨First Blink✨🚨

**Setup: How to use Arduino to turn something ON and OFF**

| Item | Details |
|---|---|
| Board | Elegoo Arduino Uno R3 and breadboard |
| Software | Arduino |
| Components used | LED, resistor, jumper wires |
| code/instruction | **see following**

```cpp
/*
  Blink

  Turns an LED on for one second, then off for one second, repeatedly.

  Most Arduinos have an on-board LED you can control. 
  On the UNO it is attached to digital pin 13

  This example code is modified from.
  https://www.arduino.cc/en/Tutorial/BuiltInExamples/Blink
*/

int led = 13;  // define a variable to hold the pin number of the internal LED

// the setup function runs once when you press reset or power the board
void setup() {
  // initialize digital pin LED_BUILTIN as an output.
  pinMode(led, OUTPUT);
}

// the loop function runs over and over again forever
void loop() {
  digitalWrite(led, HIGH);   // turn the LED on (HIGH is the voltage level)
  delay(1000);               // wait for a second
  digitalWrite(led, LOW);    // turn the LED off by making the voltage LOW
  delay(1000);               // wait for a second
}
```
<table width="100%">
<tr>
<td valign="top" width="50%">

https://github.com/user-attachments/assets/ece36709-32d4-4435-a1c4-2e75742689ec

<sub>it blinked!yay!</sub>

</td>
<td valign="top" width="50%">

<img width="4284" height="5712" alt="IMG_9385" src="https://github.com/user-attachments/assets/2f3cdabc-f838-4a08-b8f5-3889ae9bb351" />

<sub>circuit setup</sub>

</td>
</tr>
</table>



**Key takeaways**
- I have very limited experience with Arduino and physical computing, but the tutorial was clear and easy to follow
- Reading the Hello World sketch showed me how an Arduino program is structured and what the basic terms mean:

| Term | What it means |
|---|---|
| `void` | The function doesn't return a value. It just does a job |
| `setup()` | Runs once, when the board powers on or resets. Used for one-time preparation |
| `loop()` | Runs over and over, forever, after `setup()` finishes |
| `Serial.begin(9600)` | Starts serial communication between the board and my computer at 9600 baud (the speed, which must match the Serial Monitor setting) |
| `Serial.println("Hello, world!")` | Sends the text to the Serial Monitor and moves to a new line |
| `delay(1000)` | Pauses the program for 1000 milliseconds (1 second) |
| `//` | A comment, which the computer ignores and is there for humans to read |

The code is split into two parts: preparation in `setup()` and the repeating action in `loop()`. That's why "Hello, world!" keeps appearing line after line in the Serial Monitor.

**Experimenting with `delay`**
- The number inside `delay()` controls how long the board waits before repeating, so it changes how fast the message prints
- `delay(1000)` prints one line per second (meaning the "Hello, world!" prints out new ones every second)
- A smaller number, like `delay(100)`, prints about ten lines per second
- A larger number, like `delay(5000)`, prints one line every five seconds

**Challenges**
- The last time I used Arduino was four years ago in uni, and it was only a brief introduction, so working with it again brought that memory back. This time was different: it was the first time I actually understood what the code meant, so I could play with it by changing variables and seeing how that showed up on the board.
- The main challenge was understanding the different components in the kit and what each one does, for example the resistor and the LDR (light-dependent resistor).

---

### 📋 Homework (due Tuesday, Oct 27)

- [ ] Review what we did in class, including the [Arduino Tutorial](https://github.com/loopstick/ArduinoTutorial)
- [ ] Write a program that flashes the onboard LED while printing "Hello World" to the serial monitor
- [ ] Write code and manipulate components. Experiment and play!
- [ ] Make something interesting happen with:
  - 1 LED + 1 LDR, or
  - 2 or more LEDs
- [ ] Document the work in this journal:
  - 1 video + some images (if relevant)
  - Code files + circuit diagrams
  - A short write-up of the experiments and results

---

### 🥽 Fabrication & Prototyping 🛠 Oct 20 — Introduction to Digital Fabrication: Laser Cutting

**Laser cutting Pros and Cons**

| Benefits | Limitations / risks |
|---|---|
| Saves time | High energy consumption |
| Works on a wide range of materials | Not universal: typical cutters only handle 2D sheet materials |
| Complex cut designs in a single cut | Some materials are dangerous to cut |
| One machine reduces the number of tools needed | |
| CAD files keep the workflow streamlined | |

**Joining techniques**

The right joint depends on the design and the material, and a good one makes the piece look neat and professional!
!!!!Make sure to sand all the edges of your product!!!!

| Joint | How it works | Notes |
|---|---|---|
| **Finger joint** | Interlocking rectangular teeth along 90° edges, held by press-fit or glue | The most used and the most abused. Use only when there's no other choice, with fewer tabs placed where they add to the look |
| **Mortise & tenon** | A tongue (tenon) fits tightly into a square hole (mortise) | Lets the top or bottom have a radius or other details |
| **Tusk tenon / pinned** | Mortise & tenon with an extra cross-hole through the tenon, locked with a wedge or pin | High mechanical strength and adjustable |
| **Snap-fit** | A cantilevered prong flexes past a ledge and locks into place | Relies on flexible materials like acrylic or plywood |
| **Slot hook & T-cutout** | Hooks or dog-bone tabs slide through slots and lock or twist into place | |
| **Fastener & hardware** | Captive nut joint: a slot holds a hex nut, and a bolt through the second part screws in | For frequent disassembly or heavy loads |

**Flexures & kerf bending**
Rigid sheets like wood or thick plastic don't normally bend. Cutting rows of alternating or staggered slits leaves small bridges of material that twist and flex.

**Key learning**
- Laser cutters only cut flat sheets, but joints and flexures turn 2D cuts into 3D objects
- Joint choice is a design decision about strength, appearance, and whether the piece needs to come apart
- [placeholder: your own takeaway]

---

### 📋 Homework: Ring 💍 (due Thursday, Oct 29)

**Brief:** Create a ring that describes a part of your personality or a cause you believe in. Make it bold, make it big, and have fun with it!

| Constraint | Details |
|---|---|
| **Make it your own** | A ring that reflects you or something you believe in |
| **Simplicity** | Rings are small, so there's little room for fine detail. Think big and outlandish |
| **Fit** | It must fit the finger it's designed for, so measure carefully |
| **Finish** | Sand to remove sharp edges and burnt edges |
| **Due** | Thursday, bring it to class and document it in the notebook |

- [ ] Decide on the personality trait or cause
- [ ] Measure the finger
- [ ] Design the ring in CAD
- [ ] Laser cut it
- [ ] Sand off sharp and burnt edges
- [ ] Bring it to class and document it in this journal

### 💡 Weekly Reflection
- [placeholder]

### ➡️ Next steps
- Complete the homework above
- [placeholder]
