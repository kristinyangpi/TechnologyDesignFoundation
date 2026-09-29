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


motion classifier training test 1: [here](https://teachablemachine.withgoogle.com/models/LpMLrX4Y5/)


**Key takeaways**
- [placeholder]

**Challenges**
- [placeholder]

---

### 💡 Weekly Reflection
- [placeholder]

### ➡️ Next steps
- [placeholder]
