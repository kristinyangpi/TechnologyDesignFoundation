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
| **P3: Kristin (me)** | Treats & Flight | <img alt="pink lollipop" src="https://github.com/user-attachments/assets/a36c66f7-6995-4da4-9154-b6a1d9163941" width="20%"/>Eating lollipops by showing a lollipop image to the camera. After 2 lollipops, flight unlocks and flapping both arms makes the elephant rise | Object detection (plus arm pose for flight) |

**Adjustment 1: Tree too tall, lollipop not in reach**
<table width="100%">
<tr>
<td valign="top" width="50%">

**Before Adjustment: pick up fail**
<img width="1505" height="738" alt="截圖 2026-10-17 凌晨1 19 12" src="https://github.com/user-attachments/assets/b4bedaec-0f3a-47b3-9185-cc3445e2fd5f" />


</td>
<td valign="top" width="50%">

**After Adjustment: pick up and ate the lollipop --> triggers birthday hat**

https://github.com/user-attachments/assets/5df1c8d3-bd04-45fc-9901-dd858ab63d30

</td>
</tr>
</table>

**Adjustments 2,3,4,5:**
| Problem/Adjustment | vs Code Codex iteration input | Output/Adjustment |
|---|---|---|
| **Camera game angle follows the side of the elephant, making it difficult to see obstacles ahead** <img width="1508" height="740" alt="截圖 2026-10-18 晚上7 31 24" src="https://github.com/user-attachments/assets/e37e2914-aeb5-4c9e-9a29-76622ead49cd"/> | make camera game angle third person pov, always following elephant's back. Also, not too close to the elephant to allow a wider perspective of the environment | <img width="1505" height="736" alt="截圖 2026-10-18 晚上7 29 31" src="https://github.com/user-attachments/assets/1a7d01fe-b401-4f5c-943f-5181e6a590de"/> |
| **Elephant is penetrating through threes and obstacles** | elephant should be blocked from running over obstacles and user should control to bypass | elephant cannot penetrate through obstacles|
| **Dumbo-like Large ear instead of wings when second lollipop is eaten** <img width="960" height="720" alt="second-lollipop-wings" src="https://github.com/user-attachments/assets/3c21a87b-e907-4553-a530-e9ca847a71e5" />| When second lollipop is eaten, make elephant ear enlarged like dumbo to unlock flying feature instead of growing wings | https://github.com/user-attachments/assets/d0f55cd8-bff0-427f-9448-a582bf607a8e |
| **Elephant finishing dance** | When elephant passes finishing line, create confetti effect and trigger a victory ballet dance with elephant dressing in tutu | https://github.com/user-attachments/assets/40352e6d-4c43-418d-9298-821bebc224b0|


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
- Learning the digital twin process (observe, interpret, translate, simulate, test) gave me a way to describe what our elephant project is doing. Each performer's movement becomes data that is interpreted and translated into the elephant's behavior.

### ➡️ Next steps
- [placeholder]
