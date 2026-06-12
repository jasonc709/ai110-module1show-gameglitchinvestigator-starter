# 💭 Reflection: Game Glitch Investigator

Answer each question in 3 to 5 sentences. Be specific and honest about what actually happened while you worked. This is about your process, not trying to sound perfect.

## 1. What was broken when you started?

- What did the game look like the first time you ran it?
- List at least two concrete bugs you noticed at the start  
  (for example: "the hints were backwards").

The show hint button didnt work and the new game button doesn't work after you win.
**Bug Reproduction Log**

Document at least 3 bugs you found. Add rows as needed.

| Input | Expected Behavior | Actual Behavior | Console Output / Error |
|-------|-------------------|-----------------|------------------------|
| 10,20 | Hint should say higher, Hint said lower N/A
| 90,99 |Hint should say lower but hint said higher
| 55.   |I did win the game but I couldn't start a new game without refreshing

---

## 2. How did you use AI as a teammate?

- Which AI tools did you use on this project (for example: ChatGPT, Gemini, Copilot)?
- Give one example of an AI suggestion that was correct (including what the AI suggested and how you verified the result).
- Give one example of an AI suggestion that was incorrect or misleading (including what the AI suggested and how you verified the result).
I used Claude Code. It correctly found that the New Game button never reset the game status, so it stayed on "won" and wouldn't let me replay. I verified this by replaying in the browser and it worked. It also deleted one of my comments during a refactor without telling me, so I learned to check its edits. 
---

## 3. Debugging and testing your fixes

- How did you decide whether a bug was really fixed?
- Describe at least one test you ran (manual or using pytest)  
  and what it showed you about your code.
- Did AI help you design or understand any tests? How?
 knew a bug was fixed when I reran the game and the behavior actually changed, like New Game letting me start over. I ran pytest on test_game_logic.py and the old tests failed at first because they compared a tuple to a string, then passed after the fix. AI also helped by writing tests for the high and low hints and explaining why the old ones were broken.
---

## 4. What did you learn about Streamlit and state?

- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?
Streamlit reruns the wholescript from top to bottom each time you click something. This allows your history to get wiped. Session state saves things that stays the same after the rerun so things like secret number are saved.
---

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects?
  - This could be a testing habit, a prompting strategy, or a way you used Git.
- What is one thing you would do differently next time you work with AI on a coding task?
- In one or two sentences, describe how this project changed the way you think about AI generated code.
One habit I want to reuse is writing small pytest tests to actually prove a bug is fixed instead of just assuming it works. Next time I would check the AI's edits more carefully, since it once deleted a comment without telling me. This project made me realize AI generated code can look finished but still have hidden bugs, so I should always test it myself before trusting it.