# Week 7 📅 Oct 5–9, 2026


### 🔧 Oct 6 — Intro to Digital Twins

**What we did**
- Started with a class discussion on what a Digital Twin actually is. Opinions varied widely, from things like Fitbits to information models
- Learned that the data is the important part, and that the process behind a digital twin is fairly straightforward:

| Observe | → Interpret | → Translate | → Simulate | → Test |
|---|---|---|---|---|

<img width="799" height="448" alt="截圖 2026-10-17 凌晨1 10 34" src="https://github.com/user-attachments/assets/4a382784-79e2-428b-8c34-d96c2a9a1d90" />

My definition: A digital twin is a **virtual counterpart** that responds to a person’s movements and intentions in real time, turning physical actions into **meaningful** digital experiences.

**Key takeaways**
- A digital twin is built through a repeatable process rather than a single tool, and the quality of the data drives everything after it
- This maps onto our elephant project: the camera observes a performer, pose or face detection interprets the movement, the signals are translated into controls, Unity simulates the elephant, and we(user) test how it responds

---

### 🔧 Oct 8 — DigiPhant Group Project: Roles & Game Environment Set Up

**What we did**
- Continued working on our group DigiPhant Unity game, where the goal is to guide the elephant through Candy Wonderland: eat treats, grow a flower garden, fly across the course, and reach the finish for a tutu ballet celebration
- Assigned each person a part of the controls, each driven by a different kind of detection:

| Player | Role | What they control | Detection |
|---|---|---|---|
| **P1: Junling** | Drive & Steer | Moving the elephant forward and backward, turning left and right, and stopping | Pose detection |
| **P2: Celena** | Eat & Splash | Eating watermelon, and drinking and splashing water through the trunk | Facial expression: mouth open, head nod and tilt |
| **P3: Kristin (me)** | Treats & Flight | Eating lollipops by showing a lollipop image to the camera. After 2 lollipops, flight unlocks and flapping both arms makes the elephant rise | Object detection (plus arm pose for flight) |

**Problem 1: Tree too tall, lollipop not in reach**
<table width="100%">
<tr>
<td valign="top" width="50%">

**Before Adjustment: pick up fail**
<img width="1505" height="738" alt="截圖 2026-10-17 凌晨1 19 12" src="https://github.com/user-attachments/assets/b4bedaec-0f3a-47b3-9185-cc3445e2fd5f" />


</td>
<td valign="top" width="50%">

**After Adjustment: pick up and ate the lollipop --> triggers birthday hat**
<video src="../assets/hat_success_compat.mov" width="100%" controls></video>




</td>
</tr>
</table>

**Settings**


**Key takeaways**
- Splitting the controls by detection type (pose, face, object) lets each person build and test one part independently
- Flight is a shared action: I control the height, and P1 steers during flight, so the elephant can't fly without teamwork
- The lollipop works as a reward system: 1 lollipop grows a birthday hat, and 2 lollipops give big ears and unlock flight
- [placeholder: what worked or didn't when testing your lollipop detection]

**Challenges**
- [placeholder]

---

### 💡 Weekly Reflection
- [placeholder]

### ➡️ Next steps
- [placeholder]
