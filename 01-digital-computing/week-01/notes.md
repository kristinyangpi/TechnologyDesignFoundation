# Week 1

📅 Sept 1–7, 2026



### 🔧 What I did
- The idea of an agent sandbox was completely new to me. Using [Agent Design Studio](https://agentstudio.aroughidea.com) was my first time to actually explore what it means to build my own agent. Rather than just interacting with an existing AI model, I could experiment with how the agent behaves by writing my own system instructions, giving it a knowledge base, and playing around with settings like temperature and switching between models.

### 🧪 Experiments
First Attempt: Dog Agent 🐕

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
| Temperature (1st try) | 1.2 Closer to stochastic |
| Temperature (2nd try) | 0.2 Closer to deterministic |

<sub>**Note:** First try(left image) with temperature closer to stochastic produced incoherent, unrelated word strings instead of dog-like responses. Switching temperature closer to deterministic fixed this(right image) — the model responded appropriately within the constraints. <br>**Takeaway:** Higher temperature at this model size can cause the response to lose coherence entirely rather than just adding variety, especially with unusual/creative constraints like "dog language."</sub>



Second Attempt: Private Chef 👨‍🍳
<img width="1512" height="841" alt="second attempt" src="https://github.com/user-attachments/assets/0d5889ac-c3be-419b-a645-33cf933ac236" />

| Setting | Value |
|---|---|
| Model | Meta: Llama 3.1 8B Instruct |
| System Instructions | 1. You are my sous chef who works with me to come up with interesting menus <br> 2. Not limited to pastry or savory dishes <br> 3. Be creative and draw new inspirations from all over the world <br> 4. Plan menu and dishes based on the background info of the person we are serving |
| Temperature | 0.5 (mid-range) |
| Test question | "What should I cook for Friendsgiving this year with friends from different cultural backgrounds including Taiwan, India and Canada? Out of the 10 two of them are gluten free" |

<sub>**Note:** The agent responded coherently and on-topic, suggesting a fusion menu (Korean-style tacos, Indian-style stuffed peppers, Taiwanese-style skewers) that incorporated each culture mentioned and accounted for the gluten-free constraint. Compared to the dog language test, this prompt was far more concrete and well-defined, which likely contributed to a much more usable, structured response even at a higher temperature.</sub>

### Lesson Learned

Comparing both experiments, the clearest factor in output quality wasn't just temperature — it was how **well-defined the system instructions were**. The "dog language" prompt was vague and abstract (what does "dog language" even mean to a model?), and even after lowering temperature to fix incoherence, the instruction itself left a lot open to interpretation. The "sous chef" prompt, by contrast, gave the agent a clear role, explicit scope ("not limited to pastry or savory"), and a concrete task structure ("plan based on background info") — and it produced a coherent, usable response even at a higher, more stochastic temperature (0.5).

### 🪞 Reflections
Temperature controls *how much randomness* the model introduces, but it can't compensate for ambiguous instructions — and conversely, a well-scoped prompt seems to tolerate more randomness without falling apart. Going forward, I want to prioritize instruction clarity first, then treat temperature as a secondary tuning knob rather than the main lever for getting reliable output.


### ➡️ Next steps
- 

---
