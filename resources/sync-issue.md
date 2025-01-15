# Git (Source Control) Sync Issue Troubleshooting

If you run into an error message syncing your code, follow the instructions below to see if they resolve your issue:

**Step 1: Commit Any Local Changes Using the Source Control Panel**

_If you don't see any changes in the Source Control panel, skip to Step 2._

1. Look for the **Source Control** icon on the left (it looks like three branches connecting).
2. If you see a list of files under **Changes**, click the **+** (plus) sign next to each file or right-click and select **Stage All Changes**.
3. Type a short message in the textbox (for example, “Initial commit”).
4. Click the checkmark or **Commit** button.

---

**Step 2: Pull With `--no-rebase` in the Terminal**

1. At the top menu of your Codespace, click **Terminal** → **New Terminal**.
2. In the terminal that appears, type:
   ```bash
   git pull --no-rebase
   ```
3. Press **Enter**.
   - This command downloads and merges any commits GitHub Classroom added to your repository (like a “Codespaces” button in your README).

---

**Step 3: Push Your Changes**

1. Return to the Source Control panel.
2. Click **Push** (or **Sync Changes**, if that’s what you see).
   - This sends your merged, updated code back to GitHub.

---

**That’s It!**

You’ve now pulled any new commits without rebasing and pushed your own changes to GitHub. You shouldn’t see the “pull.rebase” prompt again for this assignment. If you run into any issues, ask for help or check for prompts in the Source Control panel that might guide you further.
