# Week 5 📅 Sept 21-25

---

### 🔧 Sept 22 — Open Your Eyes 👀: Intro to Computer Vision

**What we did**
- Learned what is "computer vision" training the computer to see and make sense of the world we see
<img width="796" height="447" alt="截圖 2026-09-29 下午1 19 42" src="https://github.com/user-attachments/assets/42bafcd6-f490-4de9-9687-abb1122cfcf7" />
<img width="800" height="445" alt="截圖 2026-09-29 下午1 20 52" src="https://github.com/user-attachments/assets/45228eb0-1d48-42d2-ac7d-6465330212c2" />

- exercise: pretending to be the transmitter of Convolutional Neural Networks (CNNs) in translating each stage of computational representations
<img width="657" height="535" alt="截圖 2026-09-29 下午1 39 38" src="https://github.com/user-attachments/assets/3af526b8-b2c6-4a79-a5b4-aa94b58c6c0a" />

---

**Assignment: Set up projects workspace with coding agents in VS Code**

- Set up a VS Code project workspace, following the guide: 🔗 [OYE workspace setup guide](https://github.com/kommanderpi/OYE)
- Chose **Codex** over Claude Code for this setup, due to its higher token limits
- Configured four specialized agent roles, each with distinct responsibilities, models, and reasoning effort:

| Agent | Responsibility | Model | Reasoning Effort |
|---|---|---|---|
| **Explorer** | Investigates the project — files, dependencies, code — before any changes are made. Reports findings and recommended approach; does not build | gpt-5.6-luna | Low |
| **Builder** | Implements the approved work; only begins after findings are explained and the user approves | gpt-5.6-terra | Medium |
| **Reviewer** | Checks the Builder's work for bugs, unclear logic, unnecessary complexity, and missing requirements | gpt-5.6-sol | High |
| **Documenter** | Documents what was built, how it's structured, and how to use it | gpt-5.6-luna | Low |

- Workflow enforced across all agents: **Explore → Explain Findings → Ask Permission → Build → Review → Document**
- Set up `AGENTS.md` to define shared workflow instructions, and individual `.toml` config files per agent under `~/.codex/agents/` to define each agent's model and behavior

**Key takeaways**
- Model/effort assignment isn't uniform — lighter, faster models (Luna, low effort) are used for investigation and documentation, while the Reviewer intentionally gets the strongest model and highest reasoning effort, since its job is to critically evaluate rather than just produce more code
- The Explorer is explicitly restricted from making changes — exploration only authorizes explaining findings and requesting permission, never skipping straight to building
- 🌟Separating responsibilities this way mirrors a real team structure (research → build → QA → docs) rather than treating the AI as one undifferentiated assistant

**Challenges**
- Understanding file path notation like `~/.codex/config.toml` — specifically what `~` means (a shortcut for the home folder aka **[your home folder]/.codex/config.toml**) and why the `.codex` folder needed to stay at the home folder level rather than inside the `Projects` folder


---

### 🔧 Sept 24 — Machine Learning Methods in Computer Vision
Focus: Object Detection and Pose Estimation

**What we did**
- Object detection: How it works, what a good dataset looks like, real-life application, train model in Teachable Machine
<img width="798" height="450" alt="good eg obj detection" src="https://github.com/user-attachments/assets/a4d44039-8ff1-499d-8e14-7fcde5e0a769" />

- Pose estimation: How it works, what a good dataset looks like, real-life application, train model in Teachable Machine
<img width="799" height="450" alt="pose estimation data training" src="https://github.com/user-attachments/assets/cc4b4f11-ddf5-4265-ba13-e420eddede05" />

---

**Settings**
### Object Detection Training — Test 1

🔗 [Teachable Machine Model](https://teachablemachine.withgoogle.com/models/icHSrioDc/)

| Sample | Image | Object |
|---|---|---|
| Sample 1 | <img width="339" height="612" alt="截圖 2026-09-24 下午4 48 22" src="https://github.com/user-attachments/assets/da9a4ed1-0cf0-4131-bfcf-423dffbd539e" /> | Peanut butter pretzel |
| Sample 2 | <img width="323" height="598" alt="截圖 2026-09-24 下午4 49 03" src="https://github.com/user-attachments/assets/46bc0759-fdd4-4f93-bee1-806004b136b4" /> | Watch |

**Problem**

It was difficult to show the object without also showing my hand, which made detection confusing for the model. Since my hand was present in the training data for the watch dataset, the model started detecting a bare hand (with no watch) as a "watch" — it had learned to associate the hand itself with that class, rather than the watch specifically.
<table width="100%">
<tr>
<td valign="top" width="50%">

**false detection mixing hand with watch:**
<img width="326" height="597" alt="截圖 2026-09-24 下午4 49 25" src="https://github.com/user-attachments/assets/4788de3b-8189-4264-81e2-279804ec0c39" />


</td>
<td valign="top" width="50%">

**training datasets**
<img width="1457" height="754" alt="training in progress" src="https://github.com/user-attachments/assets/99eba7fc-2073-4a68-95dc-ded5e38b1cc4" />



</td>
</tr>
</table>

### Motion Classifier Training — Test 1

🔗 [Teachable Machine Model](https://teachablemachine.withgoogle.com/models/LpMLrX4Y5/)

<table width="100%">
<tr>
<td valign="top" width="50%">

**Sample 1:** Kristin
**Sample 2:** Vicky

<img width="1467" height="756" alt="截圖 2026-09-24 下午5 06 57" src="https://github.com/user-attachments/assets/5fa73a7c-29f9-4795-9007-9fb0bd5cc548" />


</td>
<td valign="top" width="50%">

**Detects me as Vicky when I do the same pose**
<img width="1458" height="805" alt="截圖 2026-09-24 下午5 11 28" src="https://github.com/user-attachments/assets/95af872d-47da-4a30-9347-6585f137f04b" />


</td>
</tr>
</table>

**Observation**

This shows **the model only detects pose, not facial expression or identity** — when I did the same pose as Vicky, it classified me as "Vicky" instead of "Kristin." This means the classes should be labeled based on the pose itself (e.g. "hands down" vs. "hand raised") rather than by person, since the model is learning body position, not who's in frame.


**Key takeaways**

Both tests point to the same underlying lesson: 
A model only learns what's actually distinguishable in the training data, not what the label implies. The object detection test learned "hand + watch = watch," so a bare hand alone triggered a false positive — and the motion classifier learned "this specific pose = Kristin," so the same pose performed by someone else got misclassified. In both cases, the labels I chose ("watch," "Kristin") suggested a much narrower, more specific concept than what the model was actually able to isolate from the images. Going forward, class labels should describe exactly what's visually consistent and controllable in the training data — the pose, the object in isolation — rather than a broader category (a name, an object class) that depends on things the dataset doesn't actually hold constant.

**Assignment**

### A trained object classifier 🔗 [here](https://teachablemachine.withgoogle.com/models/2JCa_NSyv/)
## Object Detection Training — Peach & Soda Dataset 🍑 🥤

**What I did**

Applying the takeaway from the previous test, I built a more varied training set for peach and soda — capturing each object in different settings: on a plain table background, held in my hand, close-up, farther from the camera, and inside a bowl. The goal was to help the model generalize "peach" and "soda" across different contexts rather than tying the label to one specific setup.

**Observation**

The first round of training still sometimes struggled to differentiate between the two classes. Accuracy improved once I added a **"no food" class** — a plain table, background, and empty bowl with no food or object present at all. This gave the model an explicit "nothing" reference point to compare against, rather than forcing it to classify every frame as either peach or soda by default.

**Before & After: Peach & Soda Dataset**

| | Before | After |
|---|---|---|
| **Training classes** | Peach, Soda, snack, egg | Peach, Soda, **Blank (no object)** |
| **Image variety** | Object in different settings (table, hand, close-up, far, bowl) <img width="224" height="224" alt="1" src="https://github.com/user-attachments/assets/e57282d9-d318-45f0-8faa-0b3c78a9fb5e" /><img width="224" height="224" alt="78" src="https://github.com/user-attachments/assets/900515cb-b23b-4a0a-8fdf-30010d72e515" /><img width="224" height="224" alt="174" src="https://github.com/user-attachments/assets/6beb539e-b379-458b-8b04-a69df81ffdb3" /><img width="224" height="224" alt="430" src="https://github.com/user-attachments/assets/1f799320-b59e-4311-8110-38f7746f8012" /> | Same variety, plus a blank/empty version of each setting<img width="224" height="224" alt="98" src="https://github.com/user-attachments/assets/f92a1f67-5ea6-4df4-b40a-64ac65f3c415" />
<img width="224" height="224" alt="41" src="https://github.com/user-attachments/assets/ea57bf72-ca29-4ffc-a79e-de10eaa5411c" />
<img width="224" height="224" alt="3" src="https://github.com/user-attachments/assets/cc21063c-2fa7-49e7-8d35-8362280803d2" />
 |
| **Result** | Sometimes difficult to differentiate between peach and soda | Differentiated properly — model had a clear "nothing" reference to contrast against |
| **Key change** | — | Added a negative/blank class so the model wasn't forced to guess between only two positive labels |

**Takeaway**

Diversifying the training images across settings (distance, context, close-up) helped the model generalize the object itself — but just as important was giving it a negative class (empty scene) so it had something to contrast against. Without a "nothing" example, the model may default to guessing between the only two labels it knows, even when neither is actually present.

## A trained pose classifier 🔗 [here](https://teachablemachine.withgoogle.com/models/CmWSWobAH/)


---

### 💡 Weekly Reflection
- [placeholder]

### Something Funny

The model thinks I'm an egg loll (not sure what to think about that)
<img width="1512" height="639" alt="thinks im egg" src="https://github.com/user-attachments/assets/ee89480d-c5e1-4839-a388-430f3c95b87c" />

