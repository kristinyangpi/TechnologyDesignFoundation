
# Week 4 📅 Sept 15–18, 2026


### 🔧 Sept 15 — Vibe in VS Code + Agent, Publish it to GitHub, then deploy to Vercel.

## What we did
- Set up VS Code and connected it to an AI coding assistant extension (I chose Claude Code)
- Used Claude to help log into VS Code through GitHub and Git, connecting our project
- Configured the project so it updates automatically once connected
- This set up an environment where the code assistant could help build, test, troubleshoot, and ultimately publish our prototype
<img width="1154" height="815" alt="截圖 2026-09-15 下午4 53 58" src="https://github.com/user-attachments/assets/eb085a1c-4011-4d3d-b1da-634a5f2a8f1f" />

## Settings
| Mode | Behavior |
|---|---|
| **Plan** | Describes a plan and waits for your approval before acting |
| **Manual** | Asks for approval before each individual edit |
| **Auto / Edit automatically** | Makes changes without asking first — avoid while still learning the tool |

**💭 Notes on Permission Modes**

I find **Plan mode** works really well for me since I'm new to this — it lets me understand the reasoning behind each decision it makes before anything happens. Whereas for simpler, more specific changes (like adjusting typography or layout), **Manual mode** allows a faster workflow while still keeping my permission in the loop.

## Challenges

During the previous week, I ran into trouble getting my API key to work with the letter-writing assistant. I tried troubleshooting by asking Claude directly, but since it wasn't connected to my project files, it couldn't go through the code firsthand — I had to manually explain everything, which made debugging slow and imprecise.
<img width="1362" height="812" alt="截圖 2026-09-15 中午12 49 17" src="https://github.com/user-attachments/assets/0a0f08e6-07d0-4ac6-bc08-8793ec07ba33" />
⬆️ Didn't have the exact screenshot of letter-writing assistant reporting API error, but I had to go back and forth between Claude and AI Studio and fix errors one by one.
After learning how to connect everything into one pipeline (VS Code + Claude Code + GitHub + Vercel), I had Claude Code work directly within VS Code to help identify the API key issue. This time, it was able to find the bug and fix it directly — without me needing to describe the problem manually.
<img width="1256" height="716" alt="截圖 2026-09-21 晚上8 46 23" src="https://github.com/user-attachments/assets/f6453462-55a1-4250-837e-5c02bbf65000" />
⬆️ Had Claude doublecheck and confirmed API is working!

## Key takeaways

- Having the AI assistant directly integrated into the code editor (rather than a separate chat window) streamlined the whole workflow: build, test, troubleshoot, and publish all happen in one connected environment
- Connecting GitHub/Git through the assistant itself simplified authentication and project syncing, rather than manually managing git commands

### 🔧 Sept 17 — Mini-Me Prototype & Process Presentation

**What we did**
- An individual presentation wrapping up our progress so far working with AI agents
- Each of us shared our own design journey exploring these tools, and listened to how classmates approached the same challenge differently.

**Key takeaways**
- Many classmates created interesting apps based on their personal interests. One that stood out was an app that lets users capture beautiful views along a hike, tracking the trail so it can be stored on a map — allowing family and friends to share and revisit core memories together.
- Although having a working prototype is the goal, process documentation is just as important. It lets us look back and understand our learning curve, and helps us see how and why we made each decision along the way.

---

### 💡 Overall Reflection
- My thoughts on AI-assisted design have changed over these past couple weeks. With the help of AI agents, I was able to create apps and websites that I used to think would be impossible without a fundamental coding background. While this opened so many doors and possibilities, it also made me more conscious of the design decisions I make throughout the process. I kept asking myself: is this feature, type, or layout my own decision, or the AI's idea? Is it actually good to adopt, or was I choosing it out of convenience?
- While working and interacting with AI agents has become a big part of the design journey, it made user testing and user feedback even more important! It allows designers to catch problems and pain points that AI might not have taken into consideration. It reminded me the fact that we are designing *with* our users, rather than *for* them.
