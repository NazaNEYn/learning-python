## How a Beginner Should Start Any New Project

The most effective way to start a new software project is to shift your mindset from "knowing everything" to "discovering problems step-by-step."

### The Core Mindset Shift (Very Important)

You don't start a project by knowing all the problems; **you start by discovering them.**

* **Beginners think:** "I need to know everything before I start."
* **Experienced developers think:** "I'll start simple and let problems show themselves."

This approach removes a lot of unnecessary pressure.

---

### Step 1: Define the Smallest Useful Version

Before thinking about complex concepts, ask: **What is the simplest version of this project that is still useful?**

* **Example (Duplicate File Finder):** The smallest useful version is: Scan one folder, detect duplicates, and print them.
* *No GUI. No performance optimization. No edge cases.*

This minimal goal gives you a clear and achievable **target**.

### Step 2: Describe the Program in Plain English

Write down the program's intended function using simple, non-technical words.

* **Example:** Ask user for a folder, look at every file inside, decide which files are the same, and show the duplicates.

If you can't explain it in plain English, you're not ready to code it yet.

### Step 3: Turn English Into Questions

Now, take your simple description and transform it into technical questions.

* "How do I look at every file in a folder?"
* "How do I decide two files are the same?"
* "How do I store what I've seen already?"
* "What do I show at the end?"

These questions define the actual problems. You don't need answers yet—just good questions.

### Step 4: Map Questions → Concepts

This step organically dictates what concepts you need to learn.

| Question | Concept |
| :--- | :--- |
| How do I go through folders? | File system traversal (`os.walk`) |
| How do I compare files? | File size, **hashing** |
| How do I group duplicates? | Dictionaries / Hash maps |
| How do I handle many files? | Loops |
| How do I deal with errors? | Error handling (`try/except`) |

You didn't guess concepts—the problem demanded them.

### Step 5: Accept That Unknowns Are Normal

At this point, you will likely encounter unknowns: "I don't know how to traverse folders," or "I don't know how hashing works."

* That is **not failure**; that is perfect project design.
* Each unknown becomes: **"One specific thing to learn next."**

### Step 6: Solve One Tiny Question at a Time

**Do NOT** try to solve the whole project at once.

* **Today:** "How do I list files in a folder?"
* **Tomorrow:** "How do I compare two files?"
* **Next:** "How do I store duplicates?"

Projects grow by stacking small, solved problems.

### Step 7: Expect Your Plan to Change (This Is Key)

Your first plan is almost always wrong. You'll discover things like: "Some files can't be read," or "Some comparisons are slow."

* **Instead of thinking:** "I planned badly."
* **Think:** "Now I know what the real problem is."

This is what "the problem teaches you" means.

### Step 8: Write a Very Rough Algorithm (No Code)

Create a high-level roadmap of the steps.

* **Example:** Get folder path, walk through files, group by size, compare matching sizes, store duplicates, print results.

This is your roadmap, not a contract.

### Step 9: Learn Concepts Just-in-Time

You don't pre-learn every chapter of every book.

* **Need to walk folders** → learn `os.walk` documentation.
* **Need to compare content** → learn file hashing principles.
* **Need to store groups** → learn better use of dictionaries.

This focused approach helps you avoid "tutorial hell."

### Step 10: Reflect After Each Small Win

After solving a tiny problem, take a moment to ask:

* What worked?
* What surprised me?
* What should the UI show because of this? (Even if you don't have a UI yet)

This reflection is the mechanism by which beginners become strong, self-sufficient developers.

---

### The Most Important Truth (Read This Twice)

You don't define all problems first. **You define the next smallest problem.**
