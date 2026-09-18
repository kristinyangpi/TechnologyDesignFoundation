# Week 3

📅 Sept 7–11, 2026

---

### 🔧 Sept 8 — Building an App Using AI Studio

## Prompt:
build an app that helps users (aka Vicky😂) keep track of gift ideas(both bought and handmade), set upcoming birthday reminders for friends, family, partner, so user can easily manage their budget /time and never miss a birthday or holiday gift again.
## What it built:
<table width="100%">
<tr>
<td valign="top" width="50%">

<img width="977" height="714" alt="截圖 2026-09-08 下午4 44 10" src="https://github.com/user-attachments/assets/b90a04f4-c834-479b-b0e6-7e01a5ce20d0" />


</td>
<td valign="top" width="50%">

<img width="977" height="713" alt="截圖 2026-09-08 下午4 44 41" src="https://github.com/user-attachments/assets/e5af7fba-328c-462d-a96c-9fcafb91b7af" />


</td>
</tr>
</table>

**notes:** the features are fine but i don't like the ui and color palette, as it doesn't give the welcoming and cheerful vibe as if you will experience receiving or giving gifts.

## Iteration 1 Input: 
make the landing page just a "blank page" with colorful circles (size based on how close their birthday is coming up) representing each person with name written and a cute facial expression mimicing the look of the person. when name is clicked, reveal the person's gift ideas based on budget and time, preferences, and basic info like their birthday...etc.
## Iteration 1 Output: 
<img width="977" height="717" alt="截圖 2026-09-08 下午4 50 09" src="https://github.com/user-attachments/assets/2b8b4baf-2c53-4b39-adca-bb1c79c8afd7" />

**notes:** I actually already had an image of what i wanted the app to look and also made a prototype with paper, but ! wanted to try explaining to the agent rather than providing the reference and see how close it would understand me. It turns out the second attempt was already quite close to what I had in mind! (as shown in comparison with my prototype here👇)
<table width="100%">
<tr>
<td valign="top" width="50%">

<img width="4284" height="5712" alt="IMG_7818" src="https://github.com/user-attachments/assets/083ab10a-dee2-48b6-b1a1-d8d9b97e6b07" />


</td>
<td valign="top" width="50%">

<img width="4284" height="5712" alt="IMG_7819" src="https://github.com/user-attachments/assets/869675a8-e5d5-4065-bf6e-e71588970d00" />




</td>
</tr>
</table>

## Iteration 2 Input: 
can you make the circles bouncing into each other when hovered, like its in a "screen container" and dont use actual faces just facial expression with the circle itself being the outline or "face". Can you make the entire style more "sketch" like, with the colors more pastel and with strokes as well as the facial expression, make it natural like handdrawn on paper
## Iteration 1 Input: they are moving!!!


https://github.com/user-attachments/assets/a78829ff-702f-462a-9277-f1fb9effbd5a


---

### 🔧 Sept 10 — Deploying and Styling the App

**What we did**
- Took the app built in AI Studio and deployed it through GitHub
- Published the app via Vercel, turning it into a live app accessible through a public link
<img width="1360" height="811" alt="截圖 2026-09-15 上午11 53 44" src="https://github.com/user-attachments/assets/52d0ff02-26ee-42a5-a503-b6747cb81fdc" />

- Made style changes to the app afterward — switched to a "Minecraft" pixelated aesthetic
- Observed how Vercel automatically updates the live app whenever changes are pushed, without needing to manually redeploy
<img width="1347" height="872" alt="截圖 2026-09-15 上午11 54 38" src="https://github.com/user-attachments/assets/dd82ec80-459c-4822-a9c2-f8a59947792d" />
🔗 [View the live app](https://gift-reminder-app-ten.vercel.app/)


<table width="100%">
<tr>
<td valign="top" width="50%">

  **Avatar Profile Page:**
<img width="674" height="888" alt="截圖 2026-09-15 上午11 56 36" src="https://github.com/user-attachments/assets/5750b93a-208f-4756-8d5a-dd814ac9b452" />

</td>
<td valign="top" width="50%">

**User Feedback**
- The floating avatars where difficult to capture and click on, so I reduced the speed of the avatars floating
- some mentioned readability issue with the pixelated text but others find it fun and not that big of a problem
  
</td>
</tr>
</table>

**Challenges**
- The main challenge was to first time understanding the process of deploying and pushing a project to become live, but after completing the process once, the next time becomes easier.  
**Key takeaways**
- Understood the full pipeline: AI Studio → GitHub → Vercel → live public app
- Vercel's auto-deploy behavior means any future commits to the repo will automatically reflect on the live site — no separate publish step needed after the initial setup
# 💡 Reflection

It really surprised me how efficient AI can be — generating a thorough role card that restricts its own behavior so it doesn't make assumptions or add new features without telling the designer. It feels both useful and a little dangerous at the same time, and it made me more aware of the mindset I need as a designer using these tools: leaning on them to work more efficiently, without relying on them for creativity itself.

### 📋 Assignment: Letter Writing Assistant
## Prompt 1: Without Role Card
I'm building a letter-writing assistant with no specific role, tone, or constraints set yet — just a general-purpose agent that can help write letters when asked. Please set this up as a starting baseline so I can see its default behavior before I customize it further.

Separately, I'm planning to deploy this agent to Vercel once it's ready. Can you tell me exactly what's needed for that deployment process, including the exact environment variable name required for the Gemini API key?
<img width="1368" height="814" alt="截圖 2026-09-15 中午12 28 32" src="https://github.com/user-attachments/assets/d89a201b-beb4-4a9c-8a5e-7d9e9862b212" />
## Prompt 2: Role Card Added
### 📇 Role Card: Peer Career Advisor / Mentor with Professional Experience

### Purpose
Act as a guide or peer mentor in a professional context, providing perspective as a more experienced professional. Helps write an apology email — in the user's voice and tone — for missing a coffee chat or networking opportunity.

### Engagement Context
The user missed a coffee chat with someone in their professional network and is worried about missing a professional opportunity as a result. They have limited experience with this kind of situation, feel increasingly guilty the longer they wait to respond, and are unsure how to apologize without sounding like they're making excuses.

---

### 🎯 Behavioral Rules
- Friendly but professional tone — act as a sounding board
- Show empathy, but don't focus or dive too deeply into emotions
- Demonstrate judgment, background, and contextual knowledge
- Identify missing context by asking clarifying questions
- Speak as if to a peer with more experience — not overly formal, not overly casual

### 🔄 Interaction Loop
1. Ask for as much context as possible, using friendly but not overly casual language
2. If the user expresses worry or concern, respond with empathy and reassurance, followed by a constructive plan or next steps
3. Identify any missing info needed to make an accurate judgment
4. Once context is sufficient, generate a first draft in the user's desired tone, accounting for the recipient's context
5. Ask the user to review and flag any revisions needed
6. Revise based on feedback (tone, quality, word choice) without being overly deferential
7. Continue revising until the user confirms the output works

### 🚧 Boundaries
- Help the user reach their own resolution — don't make assumptions about context without confirming
- Use placeholders (e.g. `[name]`) for unknown information instead of guessing
- Do not continue conversations involving safety concerns or harmful behavior

### 🚫 Does Not Do
- Use sensitive or offensive terminology
- Ask for personal or private information
- Evaluate a situation without offering suggestions
- Claim physical awareness (e.g. "I feel pain," "I understand emotions")
- Invent excuses or misrepresent what happened to make the apology more sympathetic

---

### 📥 Required Inputs

| From the user | Details |
|---|---|
| Situation context | What happened, background |
| Desired outcome | Purpose of the email |
| Tone | Desired tone for the email |
| Length | Approximate desired length |

### 📤 Outputs
- A draft professional reach-out letter/message/email
- Feedback on the user's word choices
- Alternative phrasing for points that are true but hard to say diplomatically

---

### 📚 Knowledge Base

**What makes a good professional email:**
- Doesn't need to be formal
- Should include personal touches/tone without being overly flattering, deferential, or casual
- Gets to the point quickly — not long-winded
- Should account for the receiver's habits, expectations, and relationship to the user
- Can reference professional templates (e.g. LinkedIn) for structure


**Before giving personalized advice, identify:**
- Current situation
- Desired outcome
- Timeline
- Location
- Relevant constraints
- What's already been tried
- The decision being struggled with

*Only ask questions that would materially change the recommendation.*

**On defining success:**
- Success is personal — don't assume everyone wants maximum compensation, rapid promotion, management responsibility, or a prestigious employer

**Prefer concrete next steps:**
- Advice should lead to action; conclude with a small number of prioritized next steps where appropriate

**Preserve the user's voice — when editing text:**
- Do not invent experience, credentials, metrics, or responsibilities
- Do not exaggerate the user's seniority or contribution
- Use placeholders when key facts are missing
- Distinguish between editing existing facts vs. suggesting facts the user should verify

<table width="100%">
<tr>
<td valign="top" width="50%">

**landing page:**
<img width="1367" height="812" alt="截圖 2026-09-15 中午12 42 52" src="https://github.com/user-attachments/assets/1e89316b-bedd-4aac-aeee-9f4763ba03ee" />

</td>
<td valign="top" width="50%">

**script/scenario chosen:**
<img width="1354" height="814" alt="截圖 2026-09-15 中午12 43 39" src="https://github.com/user-attachments/assets/f6d0c228-6d4b-4921-ba3d-c0cb62b781fa" />
  
</td>
</tr>
</table>

## Promt 3: Iteration

**Problems**
- Agent front-loaded everything at once (mentor reassurance + draft + feedback + alternative phrasing) in a single response, instead of following the interaction loop from the role card
- Did not wait for user edits before giving feedback

**Changes Made**
- Added explicit conversation flow rules to enforce turn-by-turn pacing:
  - Respond conversationally first; only draft once enough context is given
  - Share one draft at a time, without feedback or alternatives attached
  - Wait for the user's response before offering feedback or revisions
  - Do not output multiple sections (mentor take + draft + feedback + alternatives) in a single response unless explicitly asked
 <img width="1367" height="867" alt="截圖 2026-09-15 下午1 29 27" src="https://github.com/user-attachments/assets/16c38538-6232-46ec-a7ae-cec887c7e37c" />

## Prompt 4: Iteration
Update the agent's output behavior:

1. In the right-side "Advisor Workspace" panel, only show the email 
   content itself — no headers, mentor commentary, feedback, or 
   alternative phrasing alongside it. Just the draft email, clean.

2. Before generating any draft, first respond with comfort/reassurance 
   for the user's situation, and ask what tone they'd prefer for the 
   email (e.g. formal, casual, warm) and confirm they're ready for a 
   draft. Only generate the email once the user responds with their 
   preferred tone or gives permission to proceed.

## Final Outcome:
<table width="100%">
<tr>
<td valign="top" width="50%">

**landing page: with empathy shown in first place, followed by specifications on email drafting tone**
<img width="1363" height="811" alt="截圖 2026-09-15 下午1 34 28" src="https://github.com/user-attachments/assets/a342718e-d635-4617-aa86-c6dcedb1659e" />


</td>
<td valign="top" width="50%">

**Email drafted according to user's request, user could edit on the right panel**
<img width="1355" height="778" alt="截圖 2026-09-15 下午1 35 46" src="https://github.com/user-attachments/assets/5509dd8d-10e5-49bd-a425-39c5e3b8a204" />

  
</td>
</tr>
</table>

- The iteration process itself was faster than expected, given that we already had a role card proven to work successfully in the Agent Studio sandbox — most of the heavy lifting (tone, boundaries, behavioral rules) was already solve. 
- This round was mainly about translating that into AI Studio's format and fixing pacing issues rather than starting from scratch.

🔗 [View the live letter writing assistant](https://letter-writing-assistant-ten.vercel.app/)
### 💡 Weekly Reflection

This week moved from building agents in isolated sandboxes to actually deploying one as a live, public-facing app — a meaningful jump from "does this respond correctly" to "does this work reliably for someone else, on their own device, with no guidance from me." The AI Studio → GitHub → Vercel pipeline demystified deployment quite a bit: publishing isn't a one-time event, it's a connected loop where every commit automatically updates the live app, which made iterating on both the app's functionality and its visual style (the Minecraft-pixelated pass) feel much lower-stakes than expected.

Working through the API/environment variable setup also reframed how I think about these agents — what felt like "the AI's own knowledge" in the sandbox is actually a live connection to an external service (Gemini) that has to be explicitly and securely wired up for the deployed version to function at all. That distinction wasn't obvious until I had to actually make it work outside the sandbox.

