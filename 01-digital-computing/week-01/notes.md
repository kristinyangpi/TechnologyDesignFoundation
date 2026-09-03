# Week 1

📅 Sept 1–7, 2026



### 🔧 What I did
- The idea of an agent sandbox was completely new to me. Using [Agent Design Studio](https://agentstudio.aroughidea.com) was my first time to actually explore what it means to build my own agent. Rather than just interacting with an existing AI model, I could experiment with how the agent behaves by writing my own system instructions, giving it a knowledge base, and playing around with settings like temperature and switching between models.

### 🧪 Experiments
First Attempt: Dog Agent 🐕
<sub>I was just curious how the agent would behave if I asked it to behave like a non-human organism, rather than the usual human-like persona prompts.</sub>
<table>
  <tr>
    <td><img width="1512" height="841" alt="first attempt" src="https://github.com/user-attachments/assets/6d307ca8-b7e3-4fcb-986e-21e63cdf2629" />
<sub>Stochastic (before)</sub></td>
    <td><img width="1512" height="848" alt="second attempt" src="https://github.com/user-attachments/assets/d9cbb7f4-5f84-4336-be0a-a6e145d17ca2" />
<sub>Deterministic (after)</sub></td>
  </tr>
</table>

| Setting | Value |
|---|---|
| Model | Meta: Llama 3.1 8B Instruct |
| System Instructions | 1. You are a dog, answer only in dog language <br> 2. Answer only questions related to animals |
| Temperature (1st try) | 1.2 Closer to stochastic |
| Temperature (2nd try) | 0.2 Closer to deterministic |

<sub>**Note:** First attempt(left image) with temperature closer to stochastic produced incoherent, unrelated word strings instead of dog-like responses. Switching temperature closer to deterministic fixed this(right image) — the model responded appropriately within the constraints. Takeaway: higher temperature at this model size can cause the response to lose coherence entirely rather than just adding variety, especially with unusual/creative constraints like "dog language."</sub>
 

### 💡 Key takeaways
- 

### 🚧 Challenges
- 

### 🪞 Reflections
- 

### ➡️ Next steps
- 

---
