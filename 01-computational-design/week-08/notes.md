# Week 8 📅 Oct 12–16, 2026


### 🔧 Oct 13 — Digiphant Unity Game Presentation & Demo

**What we did**
- Before class, made final adjustments and iterations after combining each person's features into one DigiPhant Unity game
- Presented our DigiPhant Unity game as a group and demoed it live
- 🔗 [JCK_Digiphant Demo video🎪🐘🪽](https://drive.google.com/file/d/1nuq7_dsvGaAe9VmaOa4Y9Fo7RMF0Ze9G/view?usp=drive_link)


**Settings**

| Setting | Value |
|---|---|
| Agent model | gpt-6 astra |
| Effort | Medium |

**Adjustments**
| Area | Change |
|---|---|
| **Lollipop detection** | Retrained recognition for the printed image (previously lost track after combining features as a group) and made detection more forgiving, so showing the card for 1 second reliably triggers eating |
| **P3 tracking and flight** | Adjusted arm-flapping detection so P3 arm doesn't need to fully extend to trigger movement and split the flight controls: P1 steers and moves forward, P3 controls elevation and landing |
| **Drinking and spraying** | Made head gestures easier to trigger: neutral does nothing, nodding 3 degrees down drinks, tilting up 3 degress to spray. To reset: hold neutral head pose for 2 seconds, allowing user to re-calibrate if camera gets confused |
| **Flower garden** | Restored it(previously lost track after combining features as a group), so spraying water grows flowers on the wet ground |
| **Flight animation** | The elephant flaps its enlarged ears during flight instead of continuing its walking animation in air. |
| **Finish celebration** | Restored it, so crossing the finish line triggers the tutu ballet dance |
| **Camera** | Added a wider, higher third-person view that follows behind the elephant |
| **Audio** | Added casual background music and sound effects for eating, drinking, spraying, and reaching the finish, making gaming experience less awkward and more engaging |

| Drink water failed | Drink water fixed |
|---|---|
|https://github.com/user-attachments/assets/ed69e4c6-70aa-4b04-a59b-976d4e8b5276|https://github.com/user-attachments/assets/94d67da9-a2d8-435c-9393-7128edf7bc96|

**Challenges and takeaways**
- **Making detection reliable in real conditions:** The lollipop image was not consistently recognized at different sizes and positions. Retraining and adjusting detection showed us how much an interaction depends on camera distance, visibility, and framing.
- **Balancing sensitivity with intentional control:** Flapping and head gestures initially required movements that were too precise. We needed more forgiving thresholds while keeping drinking, spraying, and flying distinct enough to avoid accidental actions.
- **Coordinating three players through one elephant:** Individual controls had to work together without competing. Separating P1’s steering from P3’s flight elevation clarified each player’s role and made teamwork part of the gameplay.
- **Connecting recognition to visible results:** Detecting a gesture was only the first step—the elephant also needed to respond clearly. Missing flowers, flight animations, and the finish dance highlighted the importance of testing the complete sequence from player input to visual reward.
- **Keeping the experience readable during movement:** Flying made camera position and animation especially important. A wider, higher follow camera helped players judge direction, while flapping ears communicated flight more clearly than walking legs.
- **Preserving features during integration:** Previously working effects disappeared as the group version evolved. This taught us to recheck the full game after combining changes, including rewards, animations, and sound; not just the feature we had just fixed.


---

### 🔧 Oct 15 — Cross-Section Final Presentation

**What we did**
- Joined a cross-section review and presentation with classmates from the physical computing class and the digital computational design class
- Presented our DigiPhant Unity game, then had guests/classmates try it out
- Saw how differently each section approached its projects, from physical builds to digital and computational work

**Summary**
The review was a chance to see the course from the other side. The physical computation and digital computational design classes worked on very different projects with very different approaches, yet both were exploring how people interact with technology. Seeing so many approaches next to each other showed how many ways there are to solve a similar design problem, and having guests play our game turned it from a prototype we had only tested ourselves into something people could try.

**Key takeaway / challenge**
While guests tried our game, **many people were walking around in the camera's background, which made it hard to detect the player's pose.** The camera kept losing track of the player and picking up movement from people in the background, so the game felt less smooth than it did in our own testing. This is something we need to improve.

- This connects to what I found earlier in the course: a model only perceives what is in the frame, and it can't tell which person or object is the one that matters. Testing alone in a quiet space hid this problem completely, and a crowded room exposed it.
- It also echoes the Week 7 lollipop issue, where the person in the frame competed with the object I wanted detected.
- **ideas for how to fix:** tracking only the closest person, or adjusting the camera angle]


### ➡️ Next steps
- moving downstairs to physical computing!
