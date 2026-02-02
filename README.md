[![DS Code Logo](./media/ds-code-logo.png)](https://ds-code.ca)
[Visit my Site](htps://ds-code.ca)

# The Great LLM Paint-Off: Who Codes the Best Canvas?

### The Following post was written in response to this project. The main app is the ChatGPT coded paint. 

As a developer, I’m constantly looking for the "ceiling" of current Large Language Models. We use them for snippets and debugging every day, but how do they handle a full-stack front-end task with specific state-management requirements?

To find out, I staged a **"Paint App Contest."** I gave four of the heavy hitters—ChatGPT-5, Gemini Flash 2.5, Claude 4.5, and Grok 4—the exact same prompt: build a single-file, MS Paint-style web app with custom textures, undo/redo functionality, and canvas resizing.

Here is how the experiment went down and why one model emerged as the clear "Senior Architect" of the group.

---

## The Experiment Parameters

> **The Prompt:**
> "Objective: An extremely simplified version of Microsoft Paint as a web app using html, javascript, and css. Method: Single html document... HTML canvas for the drawing surface. Specifications: Three paintbrush textures, color menu, eraser, sizing controls, resize canvas, and undo/redo actions."

---

## 1st Place: ChatGPT-5 (The Senior Architect)

**Score: A+** ChatGPT was the slowest to generate, but the wait was worth it. It didn't just write code; it designed a system.

* **The "Winning" Logic:** Instead of using the standard (and often limiting) `lineTo` method for everything, ChatGPT implemented a **Primitive-Based Drawing** pattern. It calculates points along a stroke and calls a separate `drawDot` function for each. This made implementing complex textures like "Splatter" and "Chalk" incredibly easy and scalable.
* **Scalability:** High. Adding a new texture is as simple as adding a case to the abstracted drawing function.
* **Polish:** It was the only model to provide a truly modern, dark-themed UI that felt like a real application rather than a coding exercise.
* **The Catch:** It did require one minor manual fix to get the canvas running, but the architectural superiority made it the clear winner.

👉 [Check out the polished ChatGPT version here](./index.html)

---

## 2nd Place: Gemini Flash 2.5 (The Modern Professional)

**Score: B** Gemini produced very "clean" code. It felt like it was written by a developer who loves modern ES6 syntax and documentation.

* **Pros:** Excellent use of utility functions like `saveState()` and `applySettings()`. The use of destructuring (e.g., `[lastX, lastY] = [x, y]`) made the code concise and readable.
* **Cons:** The "Square" brush was notably choppy. While the code was organized, the visual output was a bit boring and lacked the "flair" found in ChatGPT’s textures. It’s solid, professional, but lacked inspiration.

👉 [View Gemini's entry here](./other-pages/gemini.html)

---

## 3rd Place: Claude 4.5 (The Creative Specialist)

**Score: B** Claude took an interesting approach to textures, particularly the "Sketch" brush, but the underlying structure was a bit "spaghetti-ish."

* **The Issue:** Claude crammed the logic for all textures into one massive `draw` function. As a dev, this is a red flag for scalability. If I wanted to add five more brushes, that function would become a nightmare to maintain.
* **Inconsistency:** It used standard line drawing for "Solid" but shifted to direct pixel manipulation (`fillRect`) for "Spray." It worked, but it wasn't elegant.

👉 [View Claude's entry here](./other-pages/claude.html)

---

## 4th Place: Grok 4 (The Speedster)

**Score: Low B / C** Grok was the fastest to finish, but it cut far too many corners.

* **The Critique:** The code was monolithic and lacked comments. It used `alert()` and `prompt()` boxes for canvas resizing—a big "no-no" for user experience in 2026.
* **Fragility:** The undo/redo stack felt fragile and the drawing logic was coupled too tightly with state management. It’s the kind of code you’d write for a hackathon at 3:00 AM—it works, but you wouldn’t want to show it to a lead dev.

👉 [View Grok's entry here](./other-pages/grok.html)

---

## Final Thoughts

While all models successfully created a functional drawing tool, ChatGPT-5 demonstrated a superior understanding of software architecture. It built a foundation that allowed for "Splatter" and "Chalk" textures to feel like natural extensions of the system, rather than hard-coded hacks.

When you're looking for an AI to act as a pair programmer, look for the one that thinks about how the code will grow, not just if it runs.

**Which version do you prefer?** I've hosted the original outputs for each model so you can test the "feel" of the brushes yourself.


<a href="https://www.flaticon.com/free-icons/question" title="question icons">Question icons created by juicy_fish - Flaticon</a>