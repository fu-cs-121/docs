## Using the Visual Studio Code Interface

1. **Stage Changes**
   - Click on the Source Control icon in the left sidebar (looks like a branch)
   - Hover over the file you want to stage and click the '+' icon
2. **Commit Changes**
   - Enter a commit message in the text box at the top of the Source Control panel
   - Click the checkmark icon (✓) above the message box or press Ctrl+Enter (Cmd+Enter on Mac)
3. **Push Changes**
   - Click on the '...' (ellipsis) next to the Source Control title
   - Select 'Push' from the dropdown menu
   - Alternativelly, you can click the “Sync Changes” button

## Using the Terminal (pro mode)

1. **Stage Changes**
   - To stage all changes: `git add .`
   - To stage specific file: `git add filename`
2. **Commit Changes**
   - `git commit -m "Your commit message here"`
3. **Push Changes**
   - `git push`

## Verify Your Push

- In the terminal, type: `gh repo view --web`
- This opens your GitHub repository in a web browser
- Check that your latest changes are visible in the repository

Remember: Always write clear, descriptive commit messages to explain your changes!
