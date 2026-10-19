# Week 8 📅 Oct 12–16, 2026


### 🔧 Oct 13 — Digiphant Unity Game Presentation & Demo

**What we did**
- Before class, made final adjustments and iterations after combining each person's features into one DigiPhant Unity game
- Presented our DigiPhant Unity game as a group and demoed it live
- 🔗 [JCK_Digiphant Demo video🎪🐘🪽]([https://drive.google.com/file/d/1nuq7_dsvGaAe9VmaOa4Y9Fo7RMF0Ze9G/view?usp=drive_link])


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
- [placeholder]

**Settings**

| Setting | Value |
|---|---|
| [placeholder] | [placeholder] |
| [placeholder] | [placeholder] |

**Key takeaways**
- [placeholder]

**Challenges**
- [placeholder]

---

### 💡 Weekly Reflection
- [placeholder]

### ➡️ Next steps
- [placeholder]
