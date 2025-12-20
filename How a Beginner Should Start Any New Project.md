## How a Beginner Should Start Any New Project

The most crucial skill in starting a project is **problem decomposition**—breaking a big, scary task into small, solvable steps.

### The Core Mindset Shift (Very Important)

You don't start by knowing all the problems; you start by **discovering** them.

* **Beginners think:** "I need to know everything before I start."
* **Experienced devs think:** "I'll start simple and let problems show themselves."

This mindset removes a lot of pressure.

---

### Step 1: Define the Smallest Useful Version

Before thinking about concepts, ask: **What is the simplest version of this project that is still useful?**

* **Example (Duplicate File Finder):**
    * Scan one folder.
    * Detect duplicates.
    * Print them.
* *No GUI. No performance optimization. No edge cases.* This gives you a clear, achievable target.

### Step 2: Describe the Program in Plain English

Explain the project's logic without using any technical words.

* **Example:**
    * Ask user for a folder.
    * Look at every file inside.
    * Decide which files are the same.
    * Show the duplicates.

> If you can’t explain it in plain English, you’re not ready to code it yet.

### Step 3: Turn English Into Questions

Convert the plain-English steps into specific technical questions.

* "How do I look at every file in a folder?"
* "How do I decide two files are the same?"
* "How do I store what I’ve seen already?"
* "What do I show at the end?"

These questions define the actual problems you need to solve. You don't need answers yet—just good questions.

### Step 4: Map Questions → Concepts

This step shows you *exactly* what concepts you need to learn.

| Question | Concept |
| :--- | :--- |
| How do I go through folders? | File system traversal |
| How do I compare files? | File size, hashing |
| How do I group duplicates? | Dictionaries |
| How do I remember results? | Data structures |
| How do I handle many files? | Loops |
| How do I deal with errors? | Error handling |

You didn't guess concepts—the problem demanded them.

### Step 5: Accept That Unknowns Are Normal

When you identify unknowns ("I don’t know how to traverse folders," or "I don’t know how hashing works"), treat this not as a failure, but as **perfect project design**.

Each unknown becomes: **"One thing to learn next."**

### Step 6: Solve One Tiny Question at a Time

Do **NOT** try to solve the whole project at once.

* **Today:** "How do I list files in a folder?"
* **Tomorrow:** "How do I compare two files?"
* **Next:** "How do I store duplicates?"

Projects grow by stacking small, solved problems.

### Step 7: Expect Your Plan to Change (This Is Key)

Your first plan is always wrong, because you can't foresee real-world issues until you hit them.

* **You'll discover:** Some files can’t be read, some folders are huge, some comparisons are slow.
* **Instead of thinking:** "I planned badly."
* **Think:** "Now I know what the real problem is."

This is what "the problem teaches you" means.

### Step 8: Write a Very Rough Algorithm (No Code)

Create a simple, non-technical roadmap of the steps.

* **Example:**
    * Get folder path
    * Walk through files
    * Group by size
    * Compare matching sizes
    * Store duplicates
    * Print results

This is your roadmap, not a contract.

### Step 9: Learn Concepts Just-in-Time

Avoid "tutorial hell" by learning concepts only when the project *demands* them.

* **Need to walk folders** → learn `os.walk` or `pathlib`.
* **Need to compare content** → learn file hashing.
* **Need to store groups** → learn dictionaries better.

### Step 10: Reflect After Each Small Win

After solving a tiny problem, take a moment to ask:

* What worked?
* What surprised me?
* What should the UI/output show because of this?

This reflection is how beginners become strong developers.

---

### How This Applies Beyond This Project

This approach works for any type of development—automation scripts, GUIs, APIs, games, or data projects—because you’re not just learning a language; you’re learning **problem decomposition**.

### The Most Important Truth (Read This Twice)

You don’t define all problems first. **You define the next smallest problem.**
