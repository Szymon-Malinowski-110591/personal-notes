#### Step-by-step Guide to Create a Local Repository(in VS Code):

- Use VS Code in order to see the changes visually.
- Make sure you sign in to GitHub in VS Code.
- Follow these steps:

1. Open your interested directory in VS Code (`it should have at least one markdown file in it`. This is because Git does not track empty directories).
2. Open the terminal in VS Code (`ctrl + J`)
3. Initialize a new Git repository **`(do this only once per project)`**:
   ```bash
   git init
   ```
   - This creates a `.git` folder in your project directory.
   - You will see that all files are now green with a U (untracked) symbol in the Source Control tab.
   - This means that Git is tracking these files but they are not yet staged for commit.
4. Stage the files for commit:
   ```bash
   git add .
   ```
   - The `.` after `git add` means `PLEASE ADD ALL FILES` in the current directory.
   - The `U` symbols will change to `A` (added) in the Source Control tab.
   - Optionally, you can stage specific files by replacing `.` with the file name. For example if you want to stage only `README.md`, you would run:
     ```bash
     git add README.md
     ```
5. Commit the staged files with a message:
   ```bash
   git commit -m "Initial commit"
   ```
   - The `-m` flag allows you to add a commit message to your changes.
6. At this point we will use the `source control` tab in VS Code to connect to a remote repository on GitHub.
   - Click on the `Publish to GitHub` button.
   - In the search box, type the name of your new repository (if required).
   - Choose the visibility of your repository (public or private).
   - Click on `Publish Repository`.
   - VS Code will automatically add the remote URL and push your changes.
7. Verify that your changes are pushed to GitHub by visiting your repository on the GitHub website.