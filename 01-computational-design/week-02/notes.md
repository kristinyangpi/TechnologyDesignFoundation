# Week 2

📅 Sept 1–7, 2026

**[Sept 1 Part One: Self Exploration]**

### 🔧 What I did
The idea of an agent sandbox was completely new to me. Using [Agent Design Studio](https://agentstudio.aroughidea.com) was my first time to actually explore what it means to build my own agent. Rather than just interacting with an existing AI model, I could experiment with how the agent behaves by writing my own system instructions, giving it a knowledge base, and playing around with settings like temperature and switching between models.


### 🧪 Experiments
**Prompt 1: Dog Agent** 🐕

<sub>I was just curious how the agent would behave if I asked it to behave like a non-human organism, rather than the usual human-like persona prompts.</sub>
<table>
  <tr>
    <td><img width="1512" height="841" alt="first try" src="https://github.com/user-attachments/assets/6d307ca8-b7e3-4fcb-986e-21e63cdf2629" />
<sub>Stochastic (before)</sub></td>
    <td><img width="1512" height="848" alt="second try" src="https://github.com/user-attachments/assets/d9cbb7f4-5f84-4336-be0a-a6e145d17ca2" />
<sub>Deterministic (after)</sub></td>
  </tr>
</table>

| Setting | Value |
|---|---|
| Model | Meta: Llama 3.1 8B Instruct |
| System Instructions | 1. You are a dog, answer only in dog language <br> 2. Answer only questions related to animals |
| Temperature (1st attempt) | 1.2 Closer to stochastic |
| Temperature (2nd attempt) | 0.2 Closer to deterministic |

<sub>**Note:** First attempt(left image) with temperature closer to stochastic produced incoherent, unrelated word strings instead of dog-like responses. Switching temperature closer to deterministic fixed this(right image) — the model responded appropriately within the constraints. 
<br>**Takeaway:** Higher temperature at this model size can cause the response to lose coherence entirely rather than just adding variety, especially with unusual/creative constraints like "dog language."</sub>



<br> **Prompt 2: Private Chef** 👨‍🍳

<img alt="second attempt" src="https://github.com/user-attachments/assets/0d5889ac-c3be-419b-a645-33cf933ac236" />

| Setting | Value |
|---|---|
| Model | Meta: Llama 3.1 8B Instruct |
| System Instructions | 1. You are my sous chef who works with me to come up with interesting menus <br> 2. Not limited to pastry or savory dishes <br> 3. Be creative and draw new inspirations from all over the world <br> 4. Plan menu and dishes based on the background info of the person we are serving |
| Temperature | 0.5 (mid-range) |
| Test question | "What should I cook for Friendsgiving this year with friends from different cultural backgrounds including Taiwan, India and Canada? Out of the 10 two of them are gluten free" |

<sub>**Note:** The agent responded coherently and on-topic, suggesting a fusion menu (Korean-style tacos, Indian-style stuffed peppers, Taiwanese-style skewers) that incorporated each culture mentioned and accounted for the gluten-free constraint. Compared to the dog language test, this prompt was far more concrete and well-defined, which likely contributed to a much more usable, structured response even at a higher temperature.
<br>**Takeaway:** Comparing both experiments, the clearest factor in output quality wasn't just temperature — it was how **well-defined the system instructions were**. The "dog language" prompt was vague and abstract (what does "dog language" even mean to a model?), and even after lowering temperature to fix incoherence, the instruction itself left a lot open to interpretation. The "sous chef" prompt, by contrast, gave the agent a clear role, explicit scope ("not limited to pastry or savory"), and a concrete task structure ("plan based on background info") — and it produced a coherent, usable response even at a higher, more stochastic temperature (0.5).</sub>


**Prompt 2 Revisited: Temperature 0 vs. 0.5(previous attempt)**
*all setting kept the same except for the temperature*

<img width="1200" height="2342" alt="temp0_recipe_response" src="https://github.com/user-attachments/assets/0425bc38-e464-41ad-b19c-11609a5f43d8" />

<sub> **Result:** At temperature 0, the agent produced a single, highly detailed fusion recipe (Taiwanese beef noodle soup + Indian spices + Canadian bannock) rather than the multiple-option list format from the 0.5 test. The response was longer, more structured, and included extra sections (cultural significance, gluten-free tips) that weren't present before. 
<br>**Takeaway:** Interesting that lower temperature here produced *more* elaborate output, not less — contrary to what I initially assumed about determinism meaning "safer" or "shorter" answers.</sub>

### 🪞 Reflections
Temperature controls *how much randomness* the model introduces, but it can't compensate for ambiguous instructions — and conversely, a well-scoped prompt seems to tolerate more randomness without falling apart. Going forward, I want to prioritize instruction clarity first, then treat temperature as a secondary tuning knob rather than the main lever for getting reliable output.

Across all three experiments this week, the biggest factor in output quality wasn't any single setting — it was how **instructions and temperature interact**, rather than either one working alone.

With vague instructions ("answer in dog language") and higher temperature, the agent produced incoherent, unrelated output. Lowering temperature alone fixed this, suggesting that vague instructions need lower temperature to stay usable — there's less "room" for the model to interpret creatively before it breaks down.

With clear, specific instructions (the sous chef role), temperature didn't affect coherence at all — the agent stayed on-topic and useful at both 0 and 0.5. Instead, it shifted the *shape* of the response: lower temperature produced one deep, elaborated answer, while higher temperature produced a broader set of options.

### 💡 Overall Conclusion

- Instructions and temperature interact — neither one alone determines output quality
- **Vague instructions + high temperature** → incoherent output (dog language test); lowering temperature fixed it
- **Clear instructions (sous chef)** → stayed coherent at both temperature 0 and 0.5; temperature instead shifted response *shape* — one deep answer at 0, multiple broader options at 0.5
- **Main takeaway:** temperature shapes style/structure safely only when instructions are already clear. Vague instructions leave temperature to fill gaps that should've been specified upfront
- **Going forward:** prioritize instruction clarity first, treat temperature as a secondary tuning tool — not a fix for an underspecified task

### 🔗 Access

[My Agent Studio sandbox](https://agentstudio.aroughidea.com/a/LQlVjuHL43ykISHrlSEiBA)

---

**[Sept 3 Part Two: Group Project]**

## Apology Letter Agent — Role Card Exercise & Iteration Trials

---

### 🎭 Role-Play Exercise

Before training the agent, we performed the task manually within our group to understand the interaction firsthand:

- **User:** Missed a coffee chat with a friend (not very close, also elder) who works at a company the user wants to apply to
- **Writer's goal:** Help generate an apology letter
- **Observers:** Two group members recorded the interaction on post-it notes

### 👀 Observations
<img width="5712" height="4284" alt="IMG_7852" src="https://github.com/user-attachments/assets/3522bb63-4456-46e5-9f7f-8c61c1be99ff" />

- The writer immediately showed empathy — reassured the user it was okay and that they'd work out a solution together, before jumping into the task itself
- **Key human vs. LLM difference:** Partway through, the group nearly ran out of things to say since the situation wasn't especially serious — but instead of stopping, **they kept the conversation going by sharing personal past experiences.** This kind of tangential, relationship-building exchange likely wouldn't happen naturally with an LLM interaction. If the user didn't need further assistance, the agent wouldn't continue to generate text.

These observations helped us filled out the agent's role card. 

<img width="5712" height="4284" alt="IMG_7867 2" src="https://github.com/user-attachments/assets/47e22b34-90cf-4461-bed5-3153a47ba960" />

<sub>See the [attached Google Doc]([https://docs.google.com/your-actual-link](https://docs.google.com/document/d/1ZT3gkIhnpdw2IUk5aRNxzBUzQpIE4JA6idL8PPhDUVQ/edit?tab=t.in5usk5h0coj)) for full details.</sub>
---

### 🧪 Trial & Error: Agent Iterations

**Trial 1 — Google Gemma 3 12B**

| | |
|---|---|
| **Iteration points** | Words like "sincerest" felt overboard for a professional apology tone <br> 4th clarification question asked for the email's purpose, even though the initial prompt already stated wanting to reschedule <br> Tone was too agreeable — lacked reasoning behind word choices |
| **Good points** | Final reminders were reasonable and helpful |
| **Changes made** | Removed all "be friendly" instructions <br> Added to Interaction Loop: if user expresses worry/concern, give straightforward feedback <br> Added to Knowledge Base: identify context before giving personalized advice, without repeatedly asking what's already in the prompt <br> Temperature changed to 0.2 |

**Trial 2**

| | |
|---|---|
| **Iteration points** | "Sincerest" still felt overboard |
| **Good points** | Tone was more natural <br> Reflection and next-step suggestions were good and covered most situations |
| **Changes made** | Added tips for future reference after drafting, plus suggested next steps toward the broader goal <br> Removed the overly deferential opening tone — sincerity should come from briefly explaining the situation, not just stating "sincere apology" <br> Temperature changed to 0.3 |

**Trial 3**

| | |
|---|---|
| **Iteration points** | Didn't like the output, so moved to a tweaked version (Trial 4) <br> Agent gave feedback immediately after drafting, without waiting for user confirmation |
| **Changes made** | Added to Outputs: do not give feedback or future suggestions until the user confirms the draft |

**Trial 4 (Final Version)**

| | |
|---|---|
| **Iteration points** | N/A |

---

### 💡 Takeaway

The manual role-play exercise surfaced a subtle but important gap between human and AI interaction — humans naturally sustain low-stakes conversations through tangential, personal topics, which shaped how we scoped the agent's tone and pacing rather than trying to replicate that behavior directly. Iterating on temperature and instruction specificity (removing vague tone directives like "be friendly," adding explicit confirmation steps) got the agent from an overly formal, presumptuous first draft to a natural, appropriately paced final version by Trial 4.
