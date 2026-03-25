# GitHub Workflow for JavaScript Students

This guide walks you through the complete workflow for CS++ JavaScript assignments: accepting an assignment, writing code, running tests, and submitting your work.

To learn more about the tools we use, head to the [Getting Started Repo](https://github.com/cs-plus-plus/JS-Getting-Started).

## 1. Creating a GitHub Account

1. Go to [GitHub](https://github.com/)
2. Click **Sign up** in the upper-right corner
3. Enter your email address, create a password, and choose a username
4. Follow the on-screen instructions to complete setup (you may need to verify your email)
5. Sign in to GitHub

## 2. Accepting an Assignment

1. Your instructor will post an assignment link in **Google Classroom**
2. Click the link to open it in your browser
3. If prompted, authorize GitHub Classroom to access your GitHub account
4. Click **Accept this assignment**
5. GitHub Classroom will create a personal repository for you with the assignment files
6. Click the link to your new repository to view it on GitHub

## 3. Opening Your Assignment (Recommended: GitHub Codespaces)

GitHub Codespaces gives you a full development environment in your browser — no installation required.

1. From your assignment repository on GitHub, click the green **"Code"** button
2. Select the **"Codespaces"** tab
3. Click **"Create codespace on main"**
4. Wait for the environment to load (this may take a few minutes the first time)
5. You now have a full VS Code editor in your browser with Node.js and all extensions pre-installed

## 4. Writing Your Code

1. Open **`script.js`** — this is where you write your JavaScript
2. Read the **README.md** for the assignment — it describes what each function or feature should do, with exact expected inputs and outputs
3. Some assignments also require editing **`index.html`** — the README will tell you if this is needed
4. Write your code, save (`Cmd+S` or `Ctrl+S`), and preview in the browser

### Tips for Writing Code
- **Read the README carefully** — it tells you the expected behavior, element IDs, and exact text to match
- **Start simple** — get one function or feature working before moving to the next
- **Use `console.log()`** to debug — open the browser console (`F12`) to see your output
- **Check element IDs** — the autograder looks for specific IDs in your HTML (e.g., `#myDate`, `#feedback`)
- **Save your file** (`Cmd+S` or `Ctrl+S`) before testing

### Previewing Your Page
1. Right-click `index.html` in the file explorer
2. Select **"Open with Live Server"** (if available), or:
3. Open the terminal and run:
   ```bash
   npx live-server
   ```
4. Your page will open in a browser preview — it refreshes automatically when you save

## 5. Running Tests Locally (Optional)

The autograder runs tests automatically when you push, but you can also run them locally to check your work before pushing.

### From the Terminal in Codespaces
```bash
# Install test dependencies (first time only)
npm install --save-dev jest@29 jest-environment-jsdom@29

# Run all tests
npx jest --verbose
```

> **Note:** Not all assignments include a local test file. Some tests are embedded directly in the GitHub Actions workflow. You can always push your code and check the Actions tab for your score.

## 6. Saving Your Work (Committing and Pushing)

### In Codespaces / VS Code
1. Click the **Source Control** icon (branch icon) in the left sidebar, or press `Ctrl+Shift+G`
2. You'll see your changed files listed under "Changes"
3. Click the **`+`** icon next to each file to stage it, or click **`+`** next to "Changes" to stage all
4. Type a commit message (e.g., "Completed iteration assignment")
5. Click the **Commit** button (checkmark)
6. Click **Sync Changes** to push your code to GitHub

### Using GitHub Desktop (if working locally)
1. Open GitHub Desktop — your changes will appear automatically
2. Write a short summary of what you changed in the **Summary** field
3. Click **Commit to main**
4. Click **Push origin** to send your changes to GitHub

## 7. Checking Your Score (Autograding)

When you push your code, GitHub automatically runs the tests and assigns points.

1. Go to your assignment repository on GitHub
2. Click the **Actions** tab at the top
3. Click on the most recent workflow run
4. Each test shows as a separate step with its point value
5. Green checkmarks = points earned, red X = points not earned
6. Your total score is the sum of all passing tests

> **Tip:** You can push as many times as you want! Each push triggers autograding, so keep improving your code until all tests pass.

## Alternative Setup: GitHub Desktop + Local Editor

If you prefer to work locally instead of using Codespaces:

1. Download and install [GitHub Desktop](https://desktop.github.com/)
2. Open GitHub Desktop and sign in with your GitHub account
3. Click **File** > **Clone Repository**
4. Select the **URL** tab and paste your assignment repository URL
5. Choose a local path and click **Clone**
6. Open the cloned folder in **VS Code**

### Local Requirements
- A modern web browser (Chrome, Edge, or Firefox)
- VS Code with the Live Server extension
- Node.js 18+ ([Download](https://nodejs.org/)) — needed to run tests locally

## Troubleshooting

| Problem | Solution |
|---------|----------|
| Page doesn't update after saving | Make sure Live Server is running, or refresh the browser manually |
| `console.log()` output not showing | Open the browser console with `F12` or `Ctrl+Shift+J` |
| Tests won't run locally | Run `npm install --save-dev jest@29 jest-environment-jsdom@29` first |
| "File not found" errors | Check that `script.js` is in the root directory (not inside a folder) |
| Can't push changes | Make sure you committed first, then click "Sync Changes" |
| Element not found by test | Check that your HTML element IDs match exactly what the README specifies |
| `prompt()` / `alert()` not working in tests | Tests mock these functions — your code should still use them normally |

## Need Help?

- Check the **README.md** in each assignment repo for detailed instructions and examples
- Review the **scoring breakdown** on [csplusplus.com/js-tests](https://csplusplus.com/js-tests) to understand what each test checks
- Ask a classmate or visit office hours
- Contact Mr. Hare at kevin@csplusplus.com
