# Week 12 📅 Nov 9–13, 2026

# 🔌 Electronics 📟 Nov 10 — Self-study (Continue to work on our Expressive Mechanics project)

## Project: Expressive Mechanics — Iteration

**01 Concept**
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

**02 Mechanism & Setup**

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
https://github.com/user-attachments/assets/c45f8202-82aa-4931-8e42-30b2e5191422
</td>
</tr>
</table>

**03 Coding**
- Connected the code and computer vision with Arduino, so a detected motion now triggers the servo
- [placeholder: how you sent the signal from p5.js to Arduino, e.g. serial]
- [placeholder: which pose or motion triggers the movement]

[placeholder: drag video of the game triggering the mechanism here]

**04 Experimentation**
- [placeholder: what worked, what didn't, any tuning you did]

**Key takeaways**
- A more natural pose makes the visual easier to read
- [placeholder: what you learned from connecting CV, p5.js and Arduino]

**Moving Forward**
- [placeholder]

# 🥽 Fabrication & Prototyping 🛠 Nov 12 — Expressive Mechanics Crit Day!
