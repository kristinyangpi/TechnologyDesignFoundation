<img width="4284" height="5712" alt="IMG_0114" src="https://github.com/user-attachments/assets/d349300d-c6f8-42b1-b1b2-8fd52274fe57" /># Week 13 📅 Nov 16–20, 2026

---

# 🔌 Electronics 📟 Nov 3 — Expressive Mechanics Demo
**What we did**

- Went through the brief for our first foundational project, **Expressive Mechanics**
- Learned about gears and linkages as ways to create mechanical movement
- Looked at inspiration from artists, including [Neil Mendoza](https://www.neilmendoza.com/) and [Reuben Margolin](https://www.reubenmargolin.com/)
- Had a brief demo on Processing and p5.js, and how to connect them to Arduino along with computer vision

**Project brief: Expressive Mechanics**

| Item | Details |
|---|---|
| Length | 1.5 weeks |
| Connects | Arduino ↔ p5.js |
| Includes | Computer vision that triggers mechanical movement |
| Due | Nov 12 |


# Brainstorm & Ideation
Initially, I wanted to create something playful inspired by the occupied and vacant toilet sign you would see at public toilets.

**Early stage sketches**
<table width="100%">
<tr>
<td valign="top" width="50%">
<img width="4284" height="5712" alt="IMG_0097" src="https://github.com/user-attachments/assets/e2f555cf-fc23-432c-96f6-053774cb94ab" />

**Idea 1:** a slat window mechanism that shows vacant/occupied, triggered by waving to the camera

</td>
<td valign="top" width="50%">
<img width="3024" height="4032" alt="IMG_0099" src="https://github.com/user-attachments/assets/c628307f-2f10-4679-9a3a-a671d9beba29" />


**Idea 2:** vacant= eyes closed, occupied= eyes open

</td>
</tr>
</table>

<table width="100%">
<tr>
<td valign="top" width="50%">
<img width="4032" height="3024" alt="IMG_0101" src="https://github.com/user-attachments/assets/960e6db6-3881-46b5-90bb-96807bbfbfc8" />

**Idea 3:** Incorporating the 💩 from **Idea 2** and developed into a human figure with a hidden poop that would appear beneath its legs.

</td>
<td valign="top" width="50%">
<img width="4284" height="5712" alt="IMG_0123" src="https://github.com/user-attachments/assets/bf701263-f590-4b92-b347-9547352c785e" />

**Idea 4:** Made the human figure in a back faced squatting pose

</td>
</tr>
</table>
## How the idea developed

| Idea | Reason for exploring it |
| --- | --- |
| 1: Slats → rotating window | Simplify the mechanism. |
| 2: 💩 Poop with open/sleeping eyes | Communicate occupancy through an emoji |
| 3: Standing person with 💩 dropping |incorporate the 💩 emoji to an actual person|

I continued with **Idea 3** as it communicated the toilet scene the most and create a playful and straightforward interaction

## Mechanism concept
**Vacant:** The poop is hidden behind the person's face with just the person standing there.
<img width="1492" height="1076" alt="image" src="https://github.com/user-attachments/assets/6f05803e-184b-4ccc-80de-569a0603a8f5" />
**Occupied:** The servo motor controls the arm which allows the poop to swings down and stop between the legs
<img width="1492" height="1076" alt="image" src="https://github.com/user-attachments/assets/e837f6c8-cddc-4cf8-bf0b-18fae4df0e87" />

- the motion detection/computer vision part is not yet decided at this stage

## Building/Making
I wanted the physical design to remain compact and practical so I used the 1/8-inch plywood, with laser-cut parts wherever possible and minimal 3D printing. Only the 💩 part was 3D printed, the rest was built through laser cut plywood

**Adobe Illustrator file:**
<img width="9437" height="4883" alt="未命名-1" src="https://github.com/user-attachments/assets/ce6e0fa9-304c-46fe-b5a8-925a0e032f92" />
**Printed parts**
<img width="4284" height="5712" alt="IMG_0113" src="https://github.com/user-attachments/assets/9f19ae96-e352-4479-a33e-5e0892ffc27a" />

| Sandwiching M3 nuts between two plywoods | Assembling the servo arm to the servo and gluing the 💩 to one end |Securing the servo to the back of the box | Full interior of the mechanism |
| --- | --- | --- | --- |
| <img width="4284" height="5712" alt="IMG_0114" src="https://github.com/user-attachments/assets/44a01430-1fd0-4519-8bc1-4ff37a8437ef" />|<img width="4284" height="5712" alt="IMG_0116" src="https://github.com/user-attachments/assets/cde93035-2faf-4095-963a-ed5ae3e1e869" />|<img width="4284" height="5712" alt="IMG_0118" src="https://github.com/user-attachments/assets/d2cefeea-4a11-4044-b1e5-b5f09cdba2a8" />|<img width="4284" height="5712" alt="IMG_0129" src="https://github.com/user-attachments/assets/ba2efd16-593f-4c4d-98d5-6548d9e5dec2" />|


**Idea 2:** vacant= eyes closed, occupied= eyes open

</td>
</tr>
</table>

## Reflection / next step

My first servo arm felt too simple for the brief. I’m now exploring two coordinated outputs, with the 空 block removed. Next, I need to prototype the movement and check clearance inside the box.



**Key connections**

| Part | Pin | Connects to |
|---|---|---|
| [placeholder] | [placeholder] | [placeholder] |

**Key takeaways**
- [placeholder]

**Challenges**
- [placeholder]

---

# [emoji] [Project Name] [emoji]
**[placeholder: what the experiment combines]**

| Final Outcome! | Serial Monitor / Demo |
|---|---|
| [placeholder: drag video here] | [placeholder: drag video here] |

## 01 — Concept

[placeholder]

**Interaction:** [input] → [output]

## 02 — Components & Setup

| Components | Set Up |
|---|---|
| [placeholder] | [placeholder: drag setup photo here] |

## 03 — Coding the Interaction

[placeholder: how the program works]

**Code: [name]**

```cpp
// paste your Arduino code here
```

```javascript
// paste your p5.js code here, if this week uses it
```

## 04 — Experimentation & Troubleshooting

**Challenge 1: [placeholder]**

[placeholder]

**Takeaway:** [placeholder]

---

# 🥽 Fabrication & Prototyping 🛠 Nov 5 — [Topic/Title]

**What we did**
- [placeholder]

[placeholder: drag image here]

**Key learning**
- [placeholder]

**Challenges**
- [placeholder]

---

### 📋 Homework (due Tuesday, Nov 10)

  - [ ] Work on your Expressive Mechanics project
  - [ ] experiment with mechanisms
  - [ ] experiment with computer vision
  - [ ] PLAY!


### [Project Name] [emoji]

**Concept**

[placeholder]

---

### ✏️ Sketches / Brainstorm

<table width="100%">
<tr>
<td valign="top" width="50%">

[placeholder: drag sketch here]

<sub>Sketch 1: [placeholder]</sub>

</td>
<td valign="top" width="50%">

[placeholder: drag sketch here]

<sub>Sketch 2: [placeholder]</sub>

</td>
</tr>
</table>

---

### 🔁 Iterations

| Iteration | Material / settings | Image | How was it? |
|---|---|---|---|
| **V1** | [placeholder] | [placeholder] | [placeholder] |
| **V2** | [placeholder] | [placeholder] | [placeholder] |

**Outcome**

[placeholder: drag final image or video here]

**Moving Forward**
- [placeholder]

---

### 💡 Weekly Reflection

[placeholder]
