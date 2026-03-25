# CS++ JavaScript — Assignment Workflow

> **This guide walks you through the complete workflow** for CS++ JavaScript assignments: accepting an assignment, writing code, previewing your page, committing, pushing, and checking your autograded score.

New to Git and GitHub? Start with the **[Getting Started Guide](https://github.com/cs-plus-plus/JS-Getting-Started)** first.

---

## Table of Contents

1. [Create a GitHub Account](#1-create-a-github-account)
2. [Accept an Assignment](#2-accept-an-assignment)
3. [Open in Codespaces](#3-open-in-codespaces)
4. [Understand the Project Structure](#4-understand-the-project-structure)
5. [Write Your Code](#5-write-your-code)
6. [Preview Your Page](#6-preview-your-page)
7. [Debug with the Browser Console](#7-debug-with-the-browser-console)
8. [Commit and Push Your Code](#8-commit-and-push-your-code)
9. [Check Your Autograded Score](#9-check-your-autograded-score)
10. [Practice Without Breaking Tests](#10-practice-without-breaking-tests)
11. [Using GitHub Desktop (Alternative)](#11-using-github-desktop-alternative)
12. [Tips for Success](#tips-for-success)
13. [Troubleshooting](#troubleshooting)
14. [FAQ](#faq)

---

## 1. Create a GitHub Account

If you don't have a GitHub account yet:

1. Go to [github.com](https://github.com/)
2. Click **Sign up** in the upper-right corner
3. Enter your email, create a password, and choose a username
4. Verify your email address
5. Sign in to GitHub

> 💡 **Tip:** Use a username you'd be comfortable putting on a resume — employers look at GitHub profiles!

---

## 2. Accept an Assignment

1. Your teacher will share an **assignment link** (usually in Google Classroom or your LMS)
2. Click the link — it opens in your browser
3. If prompted, **authorize GitHub Classroom** to access your GitHub account (first time only)
4. Click **"Accept this assignment"**
5. Wait a few seconds while GitHub creates your personal copy of the repository
6. Click the link to open your new repository

> 💡 **Tip:** Each student gets their own private copy. Your classmates can't see your code and you can't see theirs.

---

## 3. Open in Codespaces

1. From your assignment repository, click the green **"Code"** button
2. Select the **"Codespaces"** tab
3. Click **"Create codespace on main"**
4. Wait for the environment to load (1–2 minutes the first time)

You now have a full VS Code editor in your browser with everything pre-configured.

### What You'll See

```
📁 your-assignment/
├── 📄 index.html          ← open this to see the page structure
├── 📄 script.js           ← THIS is where you write your code
├── 📄 style.css           ← optional styling (not always present)
├── 📄 README.md           ← assignment instructions — READ THIS
├── 📁 .devcontainer/      ← Codespaces config (don't touch)
└── 📁 .github/workflows/  ← autograding tests (don't touch)
```

---

## 4. Understand the Project Structure

### Files You Edit

| File | Purpose | When to Edit |
|------|---------|-------------|
| `script.js` | Your JavaScript code — logic, functions, DOM manipulation | **Every assignment** |
| `index.html` | Page structure — HTML elements, IDs, buttons, inputs | Some assignments (check the README) |
| `style.css` | Visual styling — colors, layout, fonts | Optional / bonus |

### Files You Should NOT Edit

| File | Purpose | Why Not |
|------|---------|---------|
| `.github/workflows/classroom.yml` | Autograding test definitions | Editing this breaks your score |
| `.devcontainer/devcontainer.json` | Codespaces configuration | Editing this can break your environment |

> ⚠️ **Warning:** If you modify `classroom.yml`, your autograding will break and you'll get a 0. If this happens accidentally, you can revert the file from Git history.

---

## 5. Write Your Code

### Step-by-Step

1. **Read `README.md` first** — it describes exactly what your code should do
2. **Open `script.js`** — this is where most of your work goes
3. **Look for TODO comments or function stubs** — these tell you what to implement
4. **Write your code** following the instructions
5. **Save** (`Cmd+S` on Mac, `Ctrl+S` on Windows/Chromebook)

### Common Patterns You'll Use

**Getting an element by ID:**
```javascript
let element = document.getElementById("myElement");
```

**Changing text content:**
```javascript
document.getElementById("output").textContent = "Hello!";
```

**Reading input values:**
```javascript
let userInput = document.getElementById("myInput").value;
let number = parseInt(userInput);  // convert string to number
```

**Adding a click event listener:**
```javascript
document.getElementById("myBtn").addEventListener("click", function() {
    // code that runs when button is clicked
    document.getElementById("result").textContent = "Clicked!";
});
```

**Using prompt and alert (some assignments):**
```javascript
let name = prompt("Enter your name:");
alert("Hello, " + name + "!");
```

**Using console.log for debugging:**
```javascript
let x = 42;
console.log("x is:", x);  // shows in the browser console (F12)
```

> 💡 **Tip:** The README for each assignment tells you exactly what element IDs to use, what text to display, and what functions to write. Follow it precisely — the autograder checks for exact matches.

---

## 6. Preview Your Page

To see your page in action while you code:

### Option A: Live Server (Recommended)
1. Right-click `index.html` in the file explorer
2. Select **"Open with Live Server"**
3. A browser preview opens — it auto-refreshes when you save

### Option B: Terminal
```bash
npx live-server
```

### Option C: Simple Browser
1. Open the terminal (`Ctrl+`` `)
2. Run `npx live-server`
3. Codespaces will show a "Open in Browser" notification — click it

> 💡 **Tip:** Keep the preview open side-by-side with your code. Every time you save, the page updates instantly.

---

## 7. Debug with the Browser Console

The browser console is essential for finding bugs. It shows `console.log()` output, errors, and warnings.

### How to Open the Console
- Press **F12** or **Ctrl+Shift+J** (Windows/Chromebook) or **Cmd+Option+J** (Mac)
- Click the **"Console"** tab

### What to Look For
- **Red errors** — something crashed. Read the error message and line number.
- **Your `console.log()` output** — use this to check variable values.
- **Warnings** — yellow messages. Usually not critical but worth reading.

### Debugging Example

```javascript
function calculateTotal(price, quantity) {
    console.log("price:", price, "quantity:", quantity);  // check inputs
    let total = price * quantity;
    console.log("total:", total);  // check result
    return total;
}
```

> 💡 **Tip:** When a test fails, add `console.log()` statements around the relevant code to see what values your variables actually have. Compare them to what the test expects.

---

## 8. Commit and Push Your Code

This is how you submit your work. Every push triggers autograding.

### In Codespaces / VS Code (Recommended)

1. **Open Source Control** — click the branch icon in the left sidebar (or press `Ctrl+Shift+G`)
2. **Stage your changes** — click the **`+`** icon next to each changed file, or click **`+`** next to "Changes" to stage all
3. **Write a commit message** — type a short description (e.g., "completed iteration assignment")
4. **Click Commit** — the checkmark button
5. **Click Sync Changes** — this pushes your code to GitHub

### From the Terminal

```bash
git add .
git commit -m "completed iteration assignment"
git push
```

> 💡 **Tip:** Commit and push after completing each section, not just at the end. This way you can see your score building up incrementally.

### What Happens After You Push

1. GitHub receives your code
2. The autograding workflow starts automatically (takes 15–60 seconds)
3. Tests run against your code
4. Results appear in the **Actions** tab

---

## 9. Check Your Autograded Score

1. Go to your repository on **GitHub** (not Codespaces)
2. Click the **Actions** tab at the top of the page
3. Click the most recent workflow run (it will have your commit message as the title)
4. You'll see each test as a separate step:
   - ✅ **Green checkmark** = test passed (points earned)
   - ❌ **Red X** = test failed (click to see why)
5. Your total score is the sum of all green tests

### Reading a Failed Test

When a test fails, click on it to expand the details. You'll see:
- What the test expected
- What your code actually produced
- Sometimes a hint about what went wrong

### Example Output

```
✅ Required elements exist                  10/10
✅ Uses addEventListener (no onclick)        15/15
❌ Date format matches today                  0/20
✅ Timer runs and increments                 20/20
❌ Toggle button stops/resumes                0/20
                                   Total:   45/100
```

> 💡 **Tip:** Use the test names as a checklist. Work through them one at a time — get one passing before moving to the next.

---

## 10. Practice Without Breaking Tests

Want to experiment with JavaScript without affecting your assignment grade? Create practice files!

### Create Practice Files

In your Codespace, create two new files:

**`practice.html`:**
```html
<!DOCTYPE html>
<html>
<head>
    <title>My Practice Page</title>
</head>
<body>
    <h1 id="title">Practice Page</h1>
    <button id="myBtn">Click Me</button>
    <p id="output">Output goes here</p>
    <input type="text" id="myInput" placeholder="Type something...">

    <script src="practice.js"></script>
</body>
</html>
```

**`practice.js`:**
```javascript
// Practice file — experiment here without breaking tests!

// Example: Change text when button is clicked
document.getElementById("myBtn").addEventListener("click", function() {
    let input = document.getElementById("myInput").value;
    document.getElementById("output").textContent = "You typed: " + input;
});

// Example: Use console.log to see values
console.log("Practice file loaded!");
let x = 10;
let y = 20;
console.log("x + y =", x + y);
```

### Run Your Practice

- Right-click `practice.html` → **"Open with Live Server"** to see it in the browser
- Or run `node practice.js` in the terminal for console-only scripts

> 💡 **Tip:** Practice files (`practice.js`, `practice.html`) are ignored by the autograder — only `script.js` and `index.html` are tested.

---

## 11. Using GitHub Desktop (Alternative)

If you prefer to work on your own computer instead of Codespaces:

### Setup
1. Download [GitHub Desktop](https://desktop.github.com/)
2. Sign in with your GitHub account
3. Click **File** → **Clone Repository**
4. Paste your assignment repository URL
5. Choose a local folder and click **Clone**
6. Open the folder in **VS Code**

### Commit and Push
1. Open GitHub Desktop — your changes appear automatically
2. Type a commit message in the **Summary** field
3. Click **Commit to main**
4. Click **Push origin** to send to GitHub

### Local Requirements
- A modern web browser (Chrome, Edge, or Firefox)
- VS Code with the [Live Server extension](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer)
- [Node.js 18+](https://nodejs.org/) (only needed to run tests locally)

---

## Tips for Success

1. **📖 Read the README first** — seriously, read the whole thing before writing any code
2. **🆔 Check element IDs carefully** — `myBtn` is not the same as `mybtn` or `my-btn`
3. **🐛 Use `console.log()`** — it's the fastest way to find bugs
4. **💾 Save before pushing** — unsaved changes won't be committed
5. **🔄 Push early, push often** — don't wait until you're done to check your score
6. **📊 Use test names as a checklist** — tackle them one at a time
7. **🧪 Experiment in `practice.js`** — break things safely in a separate file
8. **📝 Write descriptive commit messages** — "finished functions" is better than "update"
9. **🎯 Match exact text** — if the test expects `"Child: $7"`, then `"child: $7"` will fail
10. **❓ Ask for help** — your teacher, classmates, and kevin@csplusplus.com are all resources

---

## Troubleshooting

| Problem | Solution |
|---------|----------|
| **Page doesn't update after saving** | Make sure Live Server is running. Try refreshing the browser manually. |
| **`console.log()` output not showing** | Open DevTools with **F12** → click the **Console** tab. |
| **Tests won't run after push** | Check the Actions tab. If the workflow failed, click on it for details. |
| **"Element not found" error in test** | Your HTML is missing an element with the expected ID. Check the README for required IDs. |
| **Score is 0 after push** | Make sure you didn't modify `classroom.yml`. Check that your code doesn't have syntax errors. |
| **Can't push — "Sync Changes" not working** | Make sure you committed first (step 4 in the commit section). |
| **Codespace won't load** | Try deleting the codespace and creating a new one. Your commits are safe on GitHub. |
| **`prompt()` or `alert()` causes test to hang** | The test mocks these functions. Make sure your code calls them correctly (exact prompt text matters). |
| **Code works in browser but fails test** | Tests run in a simulated environment. Make sure you use the exact IDs, text, and formatting from the README. |
| **`NaN` showing up in output** | You're doing math with a string. Use `parseInt()` or `parseFloat()` to convert input values to numbers. |
| **"Cannot read property of null"** | You're trying to access an element that doesn't exist. Check that the ID matches exactly. |
| **GitHub Desktop doesn't show the repo** | Make sure you're signed into the correct GitHub account. |

---

## FAQ

**Q: How many times can I push?**
As many as you want! Each push triggers autograding. Your most recent score is the one that counts.

**Q: Do I need to install anything?**
No — if you use Codespaces. Everything runs in your browser. If you prefer working locally, see [Section 11](#11-using-github-desktop-alternative).

**Q: What happens if I accidentally edit `classroom.yml`?**
Your autograding may break. To fix it, go to your repo on GitHub, find the file, click "History," and revert to the original version. Or ask your teacher for help.

**Q: Can I work on the assignment after the deadline?**
That depends on your teacher's policy. The autograder will still run, but your teacher decides whether to accept late work.

**Q: Why does my code work in the browser but fail the test?**
Common reasons:
- Wrong element ID (check capitalization and spelling)
- Wrong text format (tests check exact strings)
- Missing `.toFixed(2)` for decimal formatting
- Using `onclick` in HTML instead of `addEventListener` in JavaScript

**Q: Can I see what the tests are checking?**
Yes! Visit **[csplusplus.com/js-tests](https://csplusplus.com/js-tests)** to see every assignment's scoring breakdown, including what each test checks and how many points it's worth.

**Q: What if I want to start over?**
You can always revert to the original code using Git. In the terminal:
```bash
git checkout -- script.js
git checkout -- index.html
```
This resets those files to their original state. Then commit and push to re-run autograding.

**Q: Can I add extra files to my repo?**
Yes! Files like `practice.js`, `practice.html`, or `notes.txt` won't affect your grade. Only the files specified in the README are tested.

**Q: Where can I get help?**
- Read the assignment README carefully
- Check the scoring breakdown at [csplusplus.com/js-tests](https://csplusplus.com/js-tests)
- Ask your teacher or a classmate
- Email kevin@csplusplus.com

---

## Reference

For JavaScript fundamentals, data types, operators, and more examples, see the **[Getting Started Guide](https://github.com/cs-plus-plus/JS-Getting-Started)**.

📋 **View all assignments and scoring breakdowns at [csplusplus.com/js-tests](https://csplusplus.com/js-tests)**

---

*CS++ — AP Computer Science Principles — [csplusplus.com](https://csplusplus.com) — kevin@csplusplus.com*
