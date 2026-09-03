# Week 1

📅 Sept 1–7, 2026



### 🔧 What I did
The idea of an agent sandbox was completely new to me. Using [Agent Design Studio](https://agentstudio.aroughidea.com) was my first time to actually explore what it means to build my own agent. Rather than just interacting with an existing AI model, I could experiment with how the agent behaves by writing my own system instructions, giving it a knowledge base, and playing around with settings like temperature and switching between models.

### 🧪 Experiments
Prompt 1: Dog Agent 🐕

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



Prompt 2: Private Chef 👨‍🍳

<img alt="second attempt" src="https://github.com/user-attachments/assets/0d5889ac-c3be-419b-a645-33cf933ac236" />

| Setting | Value |
|---|---|
| Model | Meta: Llama 3.1 8B Instruct |
| System Instructions | 1. You are my sous chef who works with me to come up with interesting menus <br> 2. Not limited to pastry or savory dishes <br> 3. Be creative and draw new inspirations from all over the world <br> 4. Plan menu and dishes based on the background info of the person we are serving |
| Temperature | 0.5 (mid-range) |
| Test question | "What should I cook for Friendsgiving this year with friends from different cultural backgrounds including Taiwan, India and Canada? Out of the 10 two of them are gluten free" |

<sub>**Note:** The agent responded coherently and on-topic, suggesting a fusion menu (Korean-style tacos, Indian-style stuffed peppers, Taiwanese-style skewers) that incorporated each culture mentioned and accounted for the gluten-free constraint. Compared to the dog language test, this prompt was far more concrete and well-defined, which likely contributed to a much more usable, structured response even at a higher temperature.
<br>**Takeaway:** Comparing both experiments, the clearest factor in output quality wasn't just temperature — it was how **well-defined the system instructions were**. The "dog language" prompt was vague and abstract (what does "dog language" even mean to a model?), and even after lowering temperature to fix incoherence, the instruction itself left a lot open to interpretation. The "sous chef" prompt, by contrast, gave the agent a clear role, explicit scope ("not limited to pastry or savory"), and a concrete task structure ("plan based on background info") — and it produced a coherent, usable response even at a higher, more stochastic temperature (0.5).</sub>

<table>
<tr>
<td valign="top" width="40%">


**Sous Chef Revisited: Temperature 0 vs. 0.5(previous attempt)**

<table>
<tr>
<td valign="top" width="50%">

**Agent Studio settings**

| Setting | Value |
|---|---|
| Model | Meta: Llama 3.1 8B Instruct |
| System Instructions | 1. You are my sous chef who works with me to come up with interesting menus <br> 2. Not limited to pastry or savory dishes <br> 3. Be creative and draw new inspirations from all over the world <br> 4. Plan menu and dishes based on the background info of the person we are serving |
| <span style="color:red">**Temperature**</span> | <span style="color:red">**0 (fully deterministic)**</span> |
| Test question | What should I cook for Friendsgiving this year with friends from different cultural backgrounds including Taiwan, India and Canada? Out of the 10 two of them are gluten free |

</td>
<td valign="top" width="50%">

Considering the diverse cultural backgrounds and dietary restrictions, I'd suggest a dish that's both delicious and inclusive. Here's a recipe that combines elements from Taiwan, India, and Canada, and is gluten-free:

Gluten-Free Taiwanese-Style Beef Noodle Soup with Indian-Style Spices and Canadian-Style Bannock

This dish is a creative fusion of flavors and textures that will surely impress your friends. The Taiwanese-style beef noodle soup is a nod to the Taiwanese influence, while the Indian-style spices add a warm and aromatic flavor. The Canadian-style bannock is a fun twist on traditional bread.

Ingredients:

1 pound of beef (such as flank steak or beef short ribs), sliced into thin strips
2 tablespoons of gluten-free soy sauce
1 tablespoon of Indian-style garam masala
1 tablespoon of ground cumin
1 tablespoon of coriander
1 teaspoon of cayenne pepper
1/4 cup of gluten-free beef broth
1/4 cup of water
1 tablespoon of vegetable oil
1 onion, diced
2 cloves of garlic, minced
1 cup of gluten-free noodles (such as rice noodles or corn noodles)
1 cup of Canadian-style bannock (see below for recipe)
Fresh cilantro or scallions for garnish
Instructions:

Cook the gluten-free noodles according to the package instructions.
In a large pot, heat the oil and sauté the onion and garlic until softened.
Add the beef and cook until browned, then set aside.
Add the garam masala, cumin, coriander, and cayenne pepper to the pot and cook for 1-2 minutes.
Add the beef broth and water to the pot and bring to a boil.
Add the cooked noodles and beef to the pot and simmer for 5-7 minutes.
Serve the soup hot, topped with Canadian-style bannock and garnished with cilantro or scallions.
Canadian-Style Bannock Recipe:

2 cups of gluten-free all-purpose flour
1/4 cup of sugar
1/2 teaspoon of salt
1/4 teaspoon of baking powder
1/2 cup of vegetable oil
1 cup of warm water
Mix the dry ingredients together, then add the oil and water. Knead the dough for 5-7 minutes until smooth. Divide the dough into 8-10 pieces and shape into balls. Flatten each ball into a disk shape and fry in hot oil until golden brown.

Gluten-Free Tips:

Use gluten-free soy sauce and beef broth to ensure that the dish is gluten-free.
Be sure to check the ingredients of the gluten-free noodles to ensure that they're gluten-free.
If using store-bought broth, look for a brand that's certified gluten-free.
Cultural Significance:

Taiwanese-style beef noodle soup is a popular comfort food in Taiwan, often served with a variety of toppings.
Indian-style spices, such as garam masala and cumin, add a warm and aromatic flavor to the dish.
Canadian-style bannock is a traditional bread that's often served with soups and stews.
This dish is a delicious and inclusive option that will surely impress your friends from different cultural backgrounds. The gluten-free ingredients ensure that the two friends with dietary restrictions can enjoy the dish as well. Happy cooking!

</td>
</tr>
</table>

### 🪞 Reflections
Temperature controls *how much randomness* the model introduces, but it can't compensate for ambiguous instructions — and conversely, a well-scoped prompt seems to tolerate more randomness without falling apart. Going forward, I want to prioritize instruction clarity first, then treat temperature as a secondary tuning knob rather than the main lever for getting reliable output.


### ➡️ Next steps
- 

---
