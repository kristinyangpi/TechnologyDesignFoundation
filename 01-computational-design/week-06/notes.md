# Week 6 📅 Sept 28- Oct 2

---

### 🔧 Sept 29 — Machine Learning Methods in Computer Vision- Virtual Environments

**What we did**
- Learned the difference between two kinds of virtual environments (VEs):
  - **Software VE:** a controlled computing environment that manages dependencies and organizes the system through code (Python, packages, model files, APIs)
  - **Simulated VE:** a closed digital world that recreates things like terrain, camera, lighting, agents, and physics
- Both act as containers for testing computer vision models, and they can talk to each other through APIs and messaging formats (JSON, REST, CSV, WebSocket, OSC, Python scripts)
- Set up Unity, the main simulated VE software for this class: installing Unity Hub and Unity, creating a project, connecting GitHub, and making a sandbox to experiment in

<img width="663" height="372" alt="截圖 2026-10-06 下午3 32 43" src="https://github.com/user-attachments/assets/1f1e357f-06de-405b-ba8b-eefadb143dad" />
<img width="799" height="449" alt="截圖 2026-10-06 下午3 26 57" src="https://github.com/user-attachments/assets/7635dd30-e942-4d20-b826-0c2bd760644c" />

**Software VE vs. Simulated VE**

| | Software VE | Simulated VE |
|---|---|---|
| **Main purpose** | A controlled computing environment where code and models run | A digital world where agents, objects, and physics interact |
| **Typical components** | Python, packages (pip/conda), model files, APIs | Terrain, camera, lighting, agents, physics |
| **What it controls** | Computing resources, libraries, model loading, API execution | World state, scene objects, sensors, agent behavior, time |
| **Example outputs** | Model predictions, analysis results, API responses | Rendered scenes, sensor data (images, depth), animations, interaction outcomes |

**Key takeaways**
- One manages computation; the other manages a world
- Because the two can exchange data through APIs and messaging, a model running in a software VE can drive what happens inside a simulated VE
- [placeholder: your own takeaway]

---

### 🔧 Oct 1 — MediaPipe Tutorial and Unity Setup

**What we did**
- Explored Google MediaPipe, which offers many ready-made vision "tasks" that can be used as prototyping tools: face landmarker, gesture recognizer, holistic landmarker, and image segmenter (plus others like object detector and pose landmarker)
- Took a crash course in Unity: opening and interacting with the elephant simulation VE
- Formed groups: Our task is to use MediaPipe to figure out how to move and control the simulated elephant movement in Unity

<table width="100%">
<tr>
<td valign="top" width="50%">

<img width="1430" height="773" alt="截圖 2026-10-01 下午3 27 32" src="https://github.com/user-attachments/assets/bf4da653-dc40-488f-855a-cc4a52eabdea" />


<sub>face landmarker</sub>

</td>
<td valign="top" width="50%">



<img width="1429" height="768" alt="截圖 2026-10-01 下午3 29 37" src="https://github.com/user-attachments/assets/22753753-4839-44c4-bf9e-382f861c3a39" />

<sub>gesture recognizer</sub>

</td>
</tr>
<tr>
<td valign="top" width="50%">

<img width="1423" height="764" alt="截圖 2026-10-01 下午3 32 41" src="https://github.com/user-attachments/assets/f453cabd-c6d3-48aa-9ab9-1a4fc1e049a9" />

<sub>holistic landmarker</sub>

</td>
<td valign="top" width="50%">

<img width="1429" height="769" alt="截圖 2026-10-01 下午3 35 17" src="https://github.com/user-attachments/assets/adee65b1-8bd1-4100-8253-d4a50518e137" />

<sub>image segmenter</sub>

</td>
</tr>
</table>

--

**Unity setup with the Codex agents**

🔗 [DigiPhant student starter](https://github.com/kommanderpi/studentstarter): the setup guide we gave our coding agents

- Used the Codex agents I set up earlier in week 5(explorer, builder, reviewer, documenter) in VS Code to run the Unity installation, rather than following a fixed list of manual commands
- The guide breaks down into three steps:
  1. Create a Unity project in Unity Hub (Universal 3D / URP is the easiest starting point)
  2. Clone the starter repo into the project root, beside `Assets` and not inside it, as `DigiPhantStarter`
  3. Open the agent in the Unity project root and prompt it to inspect my project, computer setup, and the cloned repo, then integrate the elephant and motion tracking, verify what it can, and record the setup in `DIGIPHANT_SETUP.md`
- The same prompt also asks the agent to set up performance recording (`RECORDING.md`) and a lightweight Git repo for my own project (`STUDENT_GIT.md`)

**Controlling the Elephant🐘**

| Component | Contents |
|---|---|
| `Elephant/` | Rigged elephant, animations, textures, prefab, and demo scene |
| `DigiPhant/` | Reference scene, receiver, camera preview, calibration, mapping, rig control, and locomotion |
| `Tracking/bridge.py` | Webcam capture, MediaPipe pose tracking, performer assignment, movement signals, and local UDP output |
| `INTEGRATION.md` | Message format, ports, signals, calibration, and tracking behavior |


https://github.com/user-attachments/assets/79a00527-90d4-413f-9334-7ae6159fae6a


**Challenges**
- When following the instructions to control the elephant, I realized the entire arm needs to be visible on screen. If part of it falls outside the frame, pose detection loses track, and the model doesn't predict anything beyond the edge of the camera view.

**Key takeaways**
- Pose tracking only works on what the camera can see. It estimates from visible body parts and doesn't fill in what's cropped out, so camera framing is part of the control design.
- This is consistent with the starter guide, which notes that full-body mode needs hips and feet visible, while seated mode relies on shoulders and hands. Choosing a mode amounts to deciding which body parts must stay in frame.
- It echoes my Week 5 pose detection findings: the model only perceives what's actually detectable, so the interaction has to be designed around that limit rather than what feels natural to me as a human.

---

### 💡 Weekly Reflection

This week moved from training small models to thinking about the environments they live in. Learning the difference between software VEs (where code and models run) and simulated VEs (where a world with physics, cameras, and agents exists) gave me a clearer picture of how computer vision actually gets used. The pose tracking happens in one place, and the thing it controls happens in another, with messages passing between the two. Setting up Unity and the elephant project made that concrete, since a Python tracking bridge was feeding movement signals into a simulated world.

Having my Codex agents run the Unity installation was a good test of the workflow I set up earlier. Instead of following a fixed list of commands, the instructions gave the agent a goal and a set of rules about inspecting first, preserving my existing work, and documenting what it did. That felt closer to directing a collaborator than operating a tool, and it reinforced how much the quality of the instructions shapes the result, the same lesson I learned from writing role cards.

**The most useful discovery came while controlling the elephant:** pose detection loses track as soon as part of my arm leaves the frame, and it doesn't guess what's out of view. This connects directly to last week's pose detection work, where I found the model could only perceive large, clear features like face and arm position. Both times, the lesson was that I have to design around what the system can actually perceive rather than what feels natural to me. Camera framing turned out to be part of the interaction design, not just a technical setup step.

### ➡️ Next steps
- Continue working with our group: (Junling, Celena, Kristin) on mapping MediaPipe tasks to elephant controls
