# Week 12 📅 Nov 9–13, 2026

# 🔌 Electronics 📟 Nov 10 — Self-study (Continue to work on our Expressive Mechanics project)

## Project: Expressive Mechanics — Iteration

### **01 Concept**
- I changed the **human figure from standing to squatting** because the pose communicates the toilet scene more naturally.
- I then developed the rear-facing character into someone who could turn around with an angry expression when their privacy was interrupted.
- **This led to a motion-controlled game:** the player holds a squat to keep the toilet door closed. Standing too early opens the door, and the physical character turns to look at them.

<table width="100%">
<tr>
<td valign="top" width="50%">

Before:
<img width="4284" height="5712" alt="IMG_0122" src="https://github.com/user-attachments/assets/cab9bcf7-d629-4abd-b164-345633684e6f" />

</td>
<td valign="top" width="50%">

After:
<img width="4284" height="5712" alt="IMG_0145" src="https://github.com/user-attachments/assets/17a9aebb-6ade-4c2a-8836-b6dddc9b4213" />

</td>
</tr>
</table>

### **02 Mechanism & Setup**

| Part | Role |
|---|---|
| Computer vision | Detects the player's pose / motion |
| p5.js | Reads the detection and sends a signal |
| Arduino | Receives the signal and drives the servo |
| Mechanism | Moves the squatting figure |

- I added a circular opening where the head would be. Behind it, a connected plate carries two drawings: the back of the head and an angry face. A servo moves the plate across the opening, creating the impression that the character turns around while the body stays still.
- The mechanism developed from a larger half-turn movement into a 45° V-shaped arm, then a double-V arm that carries both the head plate and the lower pieces.

<table width="100%">
<tr>
<td valign="top" width="50%">

Sketch:
<img width="4284" height="5712" alt="IMG_0123" src="https://github.com/user-attachments/assets/668bb890-e9a1-4cf9-8634-920a090b0db6" />
<img width="5712" height="4284" alt="IMG_0136" src="https://github.com/user-attachments/assets/771daa4f-2dc3-4c03-a9c3-079fd92198b9" />


</td>
<td valign="top" width="50%">

Lasercut:
<img width="4284" height="5712" alt="IMG_0170" src="https://github.com/user-attachments/assets/77066115-3be2-4436-a2c1-9cd8aff45de6" />

https://github.com/user-attachments/assets/37f30d08-62f9-4b42-9e79-6b9de8f804c6

</td>
</tr>
</table>

### **03 Game Implementation**

After having the physical part set, I decided to connect the mechanism to a toilet game, giving the character a setting and a reason to turn around. The player helps the character poop in peace by holding a squat to keep the toilet door closed. Standing up too early interrupts his privacy, making him turn around angrily.

| Player action | On-screen response | Physical mechanism |
|---|---|---|
| Squat and hold | Door stays closed; squat time accumulates | Character faces away |
| Stand up too early | Door opens; progress pauses | Angry face moves into view |
| Squat again | Door closes; progress resumes | Character turns back |

<table width="100%">
<tr>
<td width="50%" valign="top">

Game Interface Sketch in Illustrator:
<img width="677" height="477" alt="截圖 2026-11-24 中午12 55 19" src="https://github.com/user-attachments/assets/0ddbdd29-6658-46f3-9000-98810c10e29a" />


</td>
<td width="50%" valign="top">

  **Prompt for Codex**

instruction: this is a toilet with doors open and close controlled by motion
1. he needs to go to the toilet, help him walk over (motion: detects person mimicing walking with arms swinging )
2. knock to open the door (motion: detects person using either left or right hand to knock back and forth 2 times)
3. Come on in
4. Squat to lock the door! STAY IN POSITION UNTIL HE'S DONE! Or else the door will open (motion: detects user squating, door stays locked and triggers the pooping mechanism in arduino, the person will be done in 10 sec, if detects the user stand up within the 10 sec range, make door open and the person pooping shock and angry, until the user goes back to squating, door close again and time continues to count, if user stays squat for 10 sec, see instruction 5.)
5. He's done! Give him a thumbs up! (motion: detects user giving either left or right hand thumbs up, door opens and the person walks out. and triggers arduino to return to the 空 sign.
6. thanks for helping: your pooping score is: (depedning on how accurate the squat position is and if the person stopped squating in between , give a score from 1-100)
7. restart again

the style of the interface make it mimic the laser cutting wood and engraving style with simple line drawing and typography, show me a visualization before continueing

</td>
</tr>
</table>

**Codex Output:**
<img width="1156" height="675" alt="截圖 2026-11-24 下午1 02 16" src="https://github.com/user-attachments/assets/baa2a2b8-63d4-4d83-b787-4a8d200048fb" />

### **04 Coding and Iteration**

I connected the browser game to Arduino through Web Serial over USB. MediaPipe detects the player’s movement, JavaScript decides what should happen, and Arduino receives a command to move the servo.

| Part | Role |
|---|---|
| Webcam + MediaPipe | Detect the player's pose |
| Browser JavaScript | Run the game and decide when to trigger a reaction |
| USB serial connection | Send commands from the computer to Arduino |
| Arduino Uno + MG90S servo | Move between calibrated positions |
| Laser-cut plywood mechanism | Reveal the different head and lower-display states |

**Circuit**


1. **Calibration**
I updated the Arduino program for a 45° movement and recalibrated the two stopping positions. The program saved these positions so I could reuse them after reconnecting the board.

https://github.com/user-attachments/assets/e9bff186-5b14-4274-81d0-7a232aafb60f

2. Simplifying the game play and user journey


```Arduino Code:
// paste your Arduino code here
```

[placeholder: drag video of the game triggering the mechanism here]

### **05 Experimentation**
- [placeholder: what worked, what didn't, any tuning you did]

**Key takeaways**
- A more natural pose makes the visual easier to read
- [placeholder: what you learned from connecting CV, p5.js and Arduino]

**Moving Forward**
- [placeholder]

# 🥽 Fabrication & Prototyping 🛠 Nov 12 — Expressive Mechanics Crit Day!
