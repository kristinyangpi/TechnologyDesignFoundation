# Week 9 📅 Oct 19–23, 2026

---

# 🔌 Electronics 📟 Oct 20 — Introduction to Physical Computation and Arduino

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
     
# 👻 Shy Little Ghost 🎃
**Arduino Experiment:1 LED + 1 LDR**
<img width="770" height="427" alt="截圖 2026-10-27 下午3 49 17" src="https://github.com/user-attachments/assets/43e2e316-f0c4-48ef-b0cf-34f6f6c2bff3" />
| Final Outcome! | Serial Moniteor reporting LDR data |
|---|---|
| https://github.com/user-attachments/assets/07cc99d5-8c24-475a-9d9d-a5ad5cea8866| https://github.com/user-attachments/assets/97dd699f-e261-46a3-b432-8879554b417d|

## 01 — Concept: A Ghost That Lights Up in the Dark

Since Halloween is approaching, I came up with the idea of a shy little ghost that feels more comfortable in the dark. When exposed to light, the ghost stays unlit, almost as if it is hiding. When someone covers the light sensor with their hand, the ghost begins to glow.

The idea is to transform a simple input-output relationship into a small, playful interaction.

**Interaction:** Light → Ghost sleeps | Darkness → Ghost glows

## 02 — Components & Setup

I used the following components from the Arduino kit:
|Components|Set Up|
|---|---|
| Elegoo Arduino Uno R3, Breadboard and jumper wires, 1 LED, 1 LDR (light-dependent resistor), 1 × 10 kΩ resistor, 1 × 330 Ω resistor, USB cable |<img width="4284" height="5712" alt="IMG_9615" src="https://github.com/user-attachments/assets/bcaebcab-2aa6-4b82-ba16-bbaf60b8ac96" />|

The LDR senses changes in ambient light and sends an analog reading to the Arduino through pin A0. The Arduino compares this reading against a threshold and controls the LED through digital pin 9.

I initially planned the LED and LDR farther apart on the breadboard, but moved them closer together to accommodate the small size of the ghost.

**Key connections:**
- LDR → A0, using a 10 kΩ voltage divider
- External LED → D9, using a 330 Ω current-limiting resistor
- Onboard LED → built-in pin 13

*Documentation to add: Photo of the breadboard setup and wiring.*

## 03 — Coding the Interaction

The program combines two behaviours to meet the assignment requirements.

**Hello World:** The Arduino's built-in LED blinks every 500 milliseconds while "Hello World" and the current light reading are printed to the Serial Monitor.

**Ghost interaction:** The Arduino continuously reads the LDR using `analogRead()`. When the reading falls below a defined threshold, the external LED turns on. Otherwise, it remains off.

I used `analogWrite()` to control the LED brightness, allowing for a softer glow rather than an overly bright light.

**Code: Ghost LED + light sensor**

```cpp
const int ghostLED = 9;
const int lightSensor = A0;
const int threshold = 300;

unsigned long lastBlink = 0;
bool onboardState = false;

void setup() {
  pinMode(ghostLED, OUTPUT);
  pinMode(LED_BUILTIN, OUTPUT);

  Serial.begin(9600);
}

void loop() {
  // Read the light sensor
  int lightLevel = analogRead(lightSensor);

  // Ghost glows when it's dark!
  if (lightLevel < threshold) {
    analogWrite(ghostLED, 180);
  } else {
    analogWrite(ghostLED, 0);
  }

  // Blink onboard LED every 500ms
  if (millis() - lastBlink >= 500) {
    lastBlink = millis();

    onboardState = !onboardState;
    digitalWrite(LED_BUILTIN, onboardState);

    // Print Hello World
    Serial.print("Hello World | Light: ");
    Serial.println(lightLevel);
  }
}
```

## 04 — Experimentation & Troubleshooting

- One of the main challenges was learning how the components connect through the breadboard and understanding the relationship between the sensor readings and the LED's behavior

**Challenge 1 — Identifying components**

I learned to distinguish resistors by their color bands. I originally planned to use a 220 Ω resistor for the LED but used a 330 Ω resistor available in my kit instead.

**Challenge 2 — Calibrating the light sensor**

**Finding the ideal threshold:** 
Another challenge was finding the right LDR threshold before and after placing the ghost figure over the circuit. The ghost's material changes how much ambient light reaches the sensor, affecting its readings and the LED's behavior.

**Threshold Calibration: Before vs. After Assembly**

| Setting | Before Ghost Assembly | After Ghost Assembly |
|---|---|---|
| LDR placement | Exposed to room lighting | Partially enclosed by ghost |
| Light reading (uncovered) | 370–501 | 230-250 |
| Light reading (covered) | 140-170 | 50-70 |
| Initial threshold | 500 <img width="233" height="87" alt="截圖 2026-10-27 上午11 01 35" src="https://github.com/user-attachments/assets/b97b993c-c90a-4643-9172-15138a0e8998" />| 300 |
| Adjusted threshold | 300 <img width="231" height="100" alt="截圖 2026-10-27 上午11 01 55" src="https://github.com/user-attachments/assets/990e087a-bc23-46c9-9255-974eeb93b62e" />| 200 |
| LED behavior | Often stays ON when uncovered| stays ON when surrounding is bright, OFF when surrounding is dark|
| Main challenge | Threshold too high | Ghost material may affect light detection |

| Before threshold adjustment | After adjustment |
|---|---|
| https://github.com/user-attachments/assets/c1b68330-9949-4774-bab6-827871670655| https://github.com/user-attachments/assets/d3d194bd-653c-4df5-a12d-9b97e9245b0e|

**Takeaway:** I learned that the physical form of an object can directly influence how its electronics behave. Sensor calibration needs to happen within the final physical prototype and the surrounding environment, not just on the breadboard.


---

# 🥽 Fabrication & Prototyping 🛠 Oct 20 — Introduction to Digital Fabrication: Laser Cutting

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

### The Snacker's Ring 🥔 💍

**Concept**

A ring that allows me to snack while I do work on my laptop without making my fingers dirty so my laptop can stay clean as well

---

### ✏️ Sketches/ Brainstorm

<table width="100%">
<tr>
<td valign="top" width="50%">

<img width="4284" height="5712" alt="design 1" src="https://github.com/user-attachments/assets/28ea1b1e-7836-46a7-8e16-e3750cf86ab6" />


<sub>Sketch 1: pinching mechanism controlled by the thumb</sub>

</td>
<td valign="top" width="50%">

<img width="5712" height="4284" alt="design 2 layout" src="https://github.com/user-attachments/assets/c7d98f63-b3f6-422c-b799-91a565ae3aea" />
<img width="5712" height="4284" alt="design 2" src="https://github.com/user-attachments/assets/72b475b2-8997-486b-8184-fcc574e0c94b" />


<sub>Sketch 2: pinching mechanism controlled by middle and index finger</sub>

</td>
</tr>
</table>

- Explored different ways to pick up the snack, trying to find the most ergonomic way
- ⬇️ decided to go with the second idea and designed the layout in adobe illustrator
<img width="1007" height="771" alt="截圖 2026-10-29 下午3 51 44" src="https://github.com/user-attachments/assets/2462bc92-178f-44e0-9ea4-b8fc4fe9c6ba" />

---

### 🔁 Iterations

| Iteration |material/thickness| Image | How was it? |
|---|---|---|---|
| **V1** |plywood/1/8 inch| <img width="2870" height="3827" alt="IMG_9604" src="https://github.com/user-attachments/assets/b95bdfb1-f874-4bca-8e11-cd5a0fb485f2" /><img width="4284" height="5712" alt="IMG_9606" src="https://github.com/user-attachments/assets/117962b0-25c9-4d45-af25-4d25cedc2700" />| The plywood used for cutting was too thick and the flexture design wasn't designed properly so it doesn't bend as I hope it would (it just breaks when you apply force) |
| **V2** | plywood/1/8 inch | <img width="4284" height="5712" alt="IMG_9626" src="https://github.com/user-attachments/assets/980a4a08-b21c-4e2e-98e6-69fed0de34f0" /><img width="5712" height="4284" alt="IMG_9609" src="https://github.com/user-attachments/assets/15003a95-8aba-4384-b5ce-a925fdd53901" />|I developed a completely new design that no longer required curling the plywood into a ring. Instead, this design used the plywood’s natural flexibility to create the pinching action. The prototype worked as I had hoped: the slender arms could bend enough to grip a chip without kerf cuts, hinges, or additional moving parts. This simplified the construction while preserving the intended function. |

**V2 layout design in Adobe Illustrator**
<img width="1052" height="732" alt="截圖 2026-10-29 下午4 13 25" src="https://github.com/user-attachments/assets/3acb893b-8e8c-42fb-91f5-533a348b1698" />
**Printing...**
https://github.com/user-attachments/assets/a65143f5-57ef-4c40-8a02-806c4217a1f0

**Outcome**
<img width="1535" height="1024" alt="木製指環夾取洋芋片拼貼人體藝術-1" src="https://github.com/user-attachments/assets/ba09a0d0-71cc-4537-b549-ea48f06d676a" />

### 💡 Weekly Reflection
- [placeholder]

### ➡️ Next steps
- Complete the homework above
- [placeholder]
