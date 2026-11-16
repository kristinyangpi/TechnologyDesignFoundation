# Week 10 📅 Oct 26–30, 2026

---

# 🔌 Electronics 📟 Oct 27 — More ArduinoOOoOOOoooOOOooo

**What we did**
- Learned what others made with their LED, LDR kit
- Self-study/work time
- Matching the correct color-coded jump wire with the correct space in the breadboard

| Wire color | Meaning |
|---|---|
| 🔴 **RED** / 🟠 **ORANGE** | Positive voltage, power |
| ⚫ **BLACK** / 🟢 **GREEN** | Ground (GND), negative voltage |

<img width="837" height="332" alt="截圖 2026-11-03 下午1 15 31" src="https://github.com/user-attachments/assets/35c575d7-cdce-402e-a841-d2ba96c937a0" />

---

### 📋 Homework (due Tuesday, Nov 3)

- [ ] Review what we did in class, including the [Arduino Tutorial](https://github.com/loopstick/ArduinoTutorial)
- [ ] Write code and manipulate components. Experiment and play!
- [ ] Make something interesting happen with:
  - Servo motor
  - Ultrasonic or PIR sensor
- [ ] Document the work in this journal:
  - 1 video + some images (if relevant)
  - Code files + circuit diagrams
  - A short write-up of the experiments and results

# 🪦 Peeka-BOO! 🎃👻🍬🦇💀🧡
**Arduino Experiment: Serbvo motor + ultrasonic sensor**

## 01 — Concept
A tiny ghost hides behind a tombstone. When someone gets close, it peeks out to say BOO! When they leave, it hides again.
**Mechanism:** Attach a paper ghost directly to the servo wing, hidden behind the tombstone(ultrasonic sensor).
<img width="733" height="413" alt="截圖 2026-11-03 下午1 25 57" src="https://github.com/user-attachments/assets/9921eb43-0156-4afd-a5b1-0c63e6f19967" />

| Final Outcome! | Serial Monitor displays the ultrasonic sensor’s distance readings |
|---|---|
| https://github.com/user-attachments/assets/64feca16-9afe-4908-a38d-3545caa612e7 | https://github.com/user-attachments/assets/9ac4dbf9-45f7-499c-8f60-0aaf059bdfb7 |

**Interaction:** hand distance <35cm → servo turns from 90° to 150° and reveals the little ghost

## 02 — Components & Setup

| Components | Outcome |
|---|---|
| servo motor x1, ultrasonic sensor x1, breadboard, jumper wire, Arduino Uno | https://github.com/user-attachments/assets/71290139-6668-4c10-a73b-637d3925fd79 |

**Key connections:**

**The part that took the longest to troubleshoot:** figuring out where each wire should connect to the sensor's four pins (1–4). I eventually realized that each wire has to go into the same breadboard column as its sensor pin. The holes in a column are connected to each other, so a wire placed in a different column isn't connected to that pin at all, even if it looks like it's right next to it.
| # | Sensor pin | Function | Arduino pin |
|---|---|---|---|
| 1 | 🔴 **Vcc** | Power (5V) | from d12 to j12 |
| 2 | 🟠 **Trig** | Trigger: tells the sensor to send out a sound pulse | from d11 to j11 |
| 3 | 🟣 **Echo** | Echo: reports how long the pulse took to bounce back | from d10 to j10 |
| 4 | ⚫ **Gnd** | Ground | from d9 to j9 |

<img width="2556" height="1180" alt="IMG_0043" src="https://github.com/user-attachments/assets/9512e6c5-69b7-4a5b-b837-fe4186a3d89b" />

## 03 — Coding the Interaction

[placeholder: how the program works]

**Code: [name]**

```cpp

#include <Servo.h>

Servo plantServo;

// Pin connections
const int servoPin = 9;
const int trigPin = 10;
const int echoPin = 11;

// Ghost personality
const int normalAngle = 90;
const int shyAngle = 150;

bool isShy = false;

void setup() {
  Serial.begin(9600);

  pinMode(trigPin, OUTPUT);
  pinMode(echoPin, INPUT);

  plantServo.attach(servoPin);
  plantServo.write(normalAngle);

  Serial.println("Judgmental Plant is awake!");
}

void loop() {
  // Send ultrasonic pulse
  digitalWrite(trigPin, LOW);
  delayMicroseconds(2);
  digitalWrite(trigPin, HIGH);
  delayMicroseconds(10);
  digitalWrite(trigPin, LOW);

  // Measure reflected pulse
  long duration = pulseIn(echoPin, HIGH, 25000UL);

  // No echo: return to normal
  if (duration == 0) {
    isShy = false;
    plantServo.write(normalAngle);
    Serial.println("No echo - looking forward");
  } else {
    float distance = duration * 0.0343 / 2.0;

    Serial.print("Distance: ");
    Serial.print(distance);
    Serial.println(" cm");

    // Someone approaches
    if (!isShy && distance < 25) {
      isShy = true;
      plantServo.write(shyAngle);
      Serial.println("Ugh, a human! Turning away!");
    }

    // Someone leaves
    else if (isShy && distance > 35) {
      isShy = false;
      plantServo.write(normalAngle);
      Serial.println("Finally, some peace.");
    }
  }

  delay(100);
}

```

## 04 — Experimentation & Troubleshooting

**Challenge 1 — Breadboard Connections & Ultrasonic Sensor**
Initially, the ultrasonic sensor kept displaying No echo in the Serial Monitor, meaning it wasn't detecting any objects. After troubleshooting, I realized that although the sensor and jumper wires were placed in the same numbered rows, they were on opposite sides of the breadboard's center gap and therefore weren't electrically connected. Moving the jumper wires to the same connected side resolved the issue.

**Challenge 2 — Integrating Electronics into the Physical Design**
Another challenge was figuring out how to hide the servo, ultrasonic sensor, and wiring inside the Halloween tombstone without affecting their functionality. The ultrasonic sensor needed an unobstructed view to detect approaching hands, while the servo needed enough clearance to rotate the ghost. I explored different placements and designed cutouts for the sensor, keeping the moving mechanism behind the tombstone.
| Before | After |
|---|---|
| <img width="1645" height="2193" alt="IMG_9643" src="https://github.com/user-attachments/assets/e326064b-9444-4f9a-a740-a978ebac8d35" /> | https://github.com/user-attachments/assets/24445125-3e90-4753-84a5-0984017b9a53|

**Takeaway:** I learned that physical computing goes beyond programming and wiring. It also involves understanding how physical structures influence sensor performance and mechanical movement, and more importantly, how to transform simple movements into meaningful, expressive interactions rather than just mechanical actions.

---

# 🥽 Fabrication & Prototyping 🛠 Oct 29 — Prototyping and Fabrication- 3D printing & Fusion 360

**What we learned**
- Started by looking at everyone's laser-cut rings from the previous exercise. It was nice to see how each ring reflected a part of its maker
- Learned about CAD and 3D printing as a powerful prototyping tool for different stages of the prototyping process
- Had a quick intro and crash course on setting up Fusion
**Key learning**
- 3D printing can serve different stages of prototyping, from quick rough models to more refined versions. 
<img width="902" height="507" alt="截圖 2026-11-05 中午12 55 59" src="https://github.com/user-attachments/assets/770a2720-9f6f-465c-828b-4ead2ba46ce5" />

- Setting up Fusion was the first step toward modeling parts in 3D, compared with the flat 2D Adobe Illustrator files I used for laser cutting

---

### 📋 Homework: 3D printed Rings (due Thursday,Nov 5)

- [ ] 3D print your rings!
- [ ] Bring your working Arduino + servo (or motor) + computer vision assembly:
  - [p5.js Web Editor: TDF_ComputerVision_HeadPositionControlsServo](https://editor.p5js.org/loopstick/sketches/5DSqlJBWt)
- [ ] Document the work in this journal:
  - 1 video + some images (if relevant)
  - Code files + circuit diagrams
  - A short write-up of the experiments and results

### The Sushi NFC Ring 🍣 💍

**Concept**
I wanted to make a ring with an NFC sticker built in, so it becomes a useful everyday tool: a tap that could serves as a door key fob or open my Instagram profile. Since I love sushi, I designed the ring in the shape of sushi to make a functional object feel playful and personal.
**Interaction:** Tap the ring to a my apartment front door → door unlocks

---

### ✏️ Sketches / Brainstorm
**Design features**
I wanted the to make the sushi flavors changeable, so the ring itself is designed as a separate component from the rice, which could be slided and clicked on to secure
- **Modular design:** the ring base and the sushi pieces are separate parts
- **Slide-and-click fit:** the rice slides onto the ring and clicks to lock in place
- **Changeable parts:** different sushi toppings can be swapped on the same ring
- **NFC sticker:** built in so the ring works as a tap tool

<table width="100%">
<tr>
<td valign="top" width="50%">

<img width="1800" height="1400" alt="Tamago_v1" src="https://github.com/user-attachments/assets/f19512c6-285b-41c3-b97b-8349bb0e1f52" />

idea visualization: tamago sushi

</td>
<td valign="top" width="50%">

<img width="5712" height="4284" alt="IMG_0286" src="https://github.com/user-attachments/assets/52289621-3450-4524-9fda-fb2d57490907" />
**outcome: first print**
The first version is printed in single grey color for testing to see if each components fits well and if the NFC is detectable/scannable within the designated slot.
</td>
</tr>
</table>

---

### 🔁 Iterations

| Iteration | Material / thickness | Image | How was it? |
|---|---|---|---|
| **V1** | grey filament (test) | <img width="4284" height="5712" alt="IMG_0283" src="https://github.com/user-attachments/assets/75de9492-047b-4064-8414-83489b778790" /> | each components are compatible and fits securely, so it would be good to print the official version with separate color filaments |
| **V2** | white(rice), yellow(tamago), dark green (seaweed wrap) filament | <img width="798" height="669" alt="截圖 2026-11-16 下午2 21 36" src="https://github.com/user-attachments/assets/d7df84b8-32f0-4e68-b0e0-c629e12d159e" /> | i like it! |

**Outcome**
<table width="100%">
<tr>
<td valign="top" width="50%">
<img width="1086" height="1448" alt="tamago photoshoot2" src="https://github.com/user-attachments/assets/feff2486-efac-4c7c-a1be-2061c8fb4d35" />

</td>
<td valign="top" width="50%">

<img width="1086" height="1448" alt="tamago photoshoot 3" src="https://github.com/user-attachments/assets/482b1f4b-fa7f-4235-adfd-7bfb6a0c26ea" />

</td>
</tr>
</table>


**Moving Forward**
- I could create a series of personalized tools, each designed around something I enjoy, with a practical function built in.
- Since the ring and the sushi are separate parts, the same base could hold other designs, not just sushi flavors. [placeholder: your ideas]

