# Week 4 📅 Sept 15–18, 2026


### 🔧 Sept 15 — Vibe in VS Code + Agent, Publish it to GitHub, then deploy to Vercel.

**What we did**
- Set up VS Code and connected it to an AI coding assistant extension (I chose Claude Code)
- Used Claude to help log into VS Code through GitHub and Git, connecting our project
- Configured the project so it updates automatically once connected
- This set up an environment where the code assistant could help build, test, troubleshoot, and ultimately publish our prototype
<img width="1154" height="815" alt="截圖 2026-09-15 下午4 53 58" src="https://github.com/user-attachments/assets/eb085a1c-4011-4d3d-b1da-634a5f2a8f1f" />

**Settings**

| Setting | What it controls | How to use it |
|---|---|---|
| **Permission mode** | How much confirmation it needs before making changes | Use **Plan** mode to have it outline an approach and wait for approval, or **Manual** to approve each edit individually. Avoid **Edit automatically** or **Auto** while still learning the tool. |
| **Model** | Which AI model handles requests | Click the model name in the interface, or type `/model` |
| **Effort** | How much time it spends reasoning before responding — higher effort is slower but more thorough | Accessible through the mode menu, or type `/effort` |
| **CLAUDE.md (memory file)** | Project-specific context Claude automatically loads at the start of every session | Create a `CLAUDE.md` file in your project root describing your tech stack, conventions, or goals |



**Key takeaways**
- Having the AI assistant directly integrated into the code editor (rather than a separate chat window) streamlined the whole workflow: build, test, troubleshoot, and publish all happen in one connected environment
- Connecting GitHub/Git through the assistant itself simplified authentication and project syncing, rather than manually managing git commands

**Challenges**

### 💡 Reflection: Troubleshooting Before vs. After the VS Code Pipeline
---
During the previous week, I ran into trouble getting my API key to work with the letter-writing assistant. I tried troubleshooting by asking Claude directly, but since it wasn't connected to my project files, it couldn't go through the code firsthand — I had to manually explain everything, which made debugging slow and imprecise.

After learning how to connect everything into one pipeline (VS Code + Claude Code + GitHub + Vercel), I had Claude Code work directly within VS Code to help identify the API key issue. This time, it was able to find the bug and fix it directly — without me needing to describe the problem manually.

### 🔧 Sept 17 — [Topic/Title]

**What we did**

**Settings**

**Key takeaways**

**Challenges**


---

### 💡 Weekly Reflection

