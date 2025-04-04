# GitHub for Complete Beginners

This guide will help you create a new project on GitHub and learn how to save your changes. Don't worry if you've never used GitHub before - we'll explain everything step by step using simple language.

## What You'll Need

- A computer with internet access
- A GitHub account (we'll show you how to create one)
- Git installed on your computer (we'll explain how to install it)

## Part 1: Creating a GitHub Account

1. Go to [https://github.com](https://github.com) in your web browser
2. Click the "Sign up" button in the top right corner
3. Enter your email address
4. Create a password
5. Choose a username (this will be visible to others)
6. Solve the puzzle to verify you're human
7. Click "Create account"
8. Check your email and verify your account by clicking the link GitHub sent you

## Part 2: Installing Git on Your Computer

### For Windows:

1. Go to [https://git-scm.com/downloads](https://git-scm.com/downloads)
2. Click on "Windows"
3. The download should start automatically
4. Open the downloaded file and follow these steps:
   - Click "Next" through the license screen
   - Click "Next" on the destination location screen
   - Click "Next" on the components screen
   - Click "Next" on the Start Menu folder screen
   - On the "Choosing the default editor" screen, select "Notepad" (easiest for beginners) and click "Next"
   - On the next screen, select "Use Git from the Windows Command Prompt" and click "Next"
   - On the HTTPS transport screen, select "Use the OpenSSL library" and click "Next"
   - On the line ending conversions screen, select "Checkout Windows-style, commit Unix-style line endings" and click "Next"
   - On the terminal emulator screen, select "Use MinTTY" and click "Next"
   - On the extra options screen, make sure "Enable file system caching" and "Enable Git Credential Manager" are selected and click "Next"
   - Click "Install"
   - When it's done, click "Finish"

### For Mac:

1. Open the "Terminal" app (you can find it using Spotlight Search - press Command+Space and type "Terminal")
2. Type this command and press Enter:
   ```
   xcode-select --install
   ```
3. A pop-up window will appear asking you to install the developer tools. Click "Install"
4. Wait for the installation to complete (this might take a few minutes)
5. When it's done, type this command to check if Git was installed:
   ```
   git --version
   ```
6. You should see a message telling you what version of Git is installed

## Part 3: Creating a New Repository on GitHub

1. Log in to your GitHub account
2. Click the "+" sign in the top right corner, then select "New repository"
3. Give your repository a name (for example, "my-first-project")
4. (Optional) Add a description to help remember what your project is about
5. Choose "Public" if you want anyone to see your project, or "Private" if you only want it visible to you and people you invite
6. Check the box that says "Add a README file"
7. Click the green "Create repository" button

Congratulations! You've created your first GitHub repository.

## Part 4: Getting Your Project on Your Computer

Now let's download your project to your computer so you can work on it:

1. On your repository page, click the green "Code" button
2. Make sure "HTTPS" is selected
3. Click the clipboard icon to copy the link

Now open the command line:
- On Windows: Press the Windows key, type "cmd" and press Enter
- On Mac: Open the Terminal app

Then follow these steps:

4. Navigate to where you want to save your project. For example, to save it on your Desktop:
   - On Windows, type: `cd Desktop`
   - On Mac, type: `cd ~/Desktop`
   - Press Enter

5. Type the following command to download your repository (replace the URL with the one you copied):
   ```
   git clone https://github.com/your-username/my-first-project.git
   ```
   - Press Enter

6. You should see a message that your repository is being cloned (downloaded)

7. When it's done, move into your project folder by typing:
   ```
   cd my-first-project
   ```
   - Press Enter

## Part 5: Making Changes and Saving Them

Now that you have your project on your computer, let's make some changes and save them to GitHub:

### Step 1: Make a change

1. Open the project folder on your computer
2. Open the README.md file in any text editor (like Notepad on Windows or TextEdit on Mac)
3. Add some text, like "This is my first GitHub project!"
4. Save the file and close it

### Step 2: Tell Git about your changes

Go back to your command line window and make sure you're in your project folder. Then:

1. Check what files you've changed by typing:
   ```
   git status
   ```
   - Press Enter
   - You should see README.md listed in red as a modified file

2. Add your changes to a "staging area" (think of this as a shopping cart before checkout):
   ```
   git add README.md
   ```
   - Press Enter

   To add all changed files at once, you can use:
   ```
   git add .
   ```
   - Press Enter

3. Save your changes with a message describing what you did:
   ```
   git commit -m "Updated README with a description"
   ```
   - Press Enter

### Step 3: Send your changes to GitHub

1. Upload your changes to GitHub:
   ```
   git push origin main
   ```
   - Press Enter

2. If asked for your GitHub username and password:
   - Type your username and press Enter
   - For the password, you'll need to use a "personal access token" instead of your regular GitHub password. If you don't have one:
     - Go to GitHub.com → click your profile picture → Settings → Developer settings → Personal access tokens → Generate new token
     - Give it a name, set an expiration date, check the "repo" box
     - Click "Generate token" and copy it
     - Use this token as your password when prompted

3. Once the command completes, your changes are now on GitHub!

## Part 6: Getting Updates from GitHub

If you're working on multiple computers, or if other people are also working on your project, you'll want to get the latest changes from GitHub:

1. Make sure you're in your project folder in the command line
2. Get the latest changes:
   ```
   git pull origin main
   ```
   - Press Enter

## Part 7: Creating a Branch and Merging Changes

Branches let you work on new features without affecting the main project until you're ready.

### Creating a new branch:

1. Make sure you're in your project folder in the command line
2. Create and switch to a new branch:
   ```
   git checkout -b my-new-feature
   ```
   - Press Enter
   - This creates a branch called "my-new-feature" and switches to it

3. Make your changes as described in Part 5
4. When you're ready to save your changes to this branch:
   ```
   git push origin my-new-feature
   ```
   - Press Enter

### Merging your branch into the main project:

1. Go to your repository on GitHub.com
2. You should see a message about your recently pushed branch
3. Click the "Compare & pull request" button
4. Add a title and description explaining your changes
5. Click "Create pull request"
6. On the next page, if there are no conflicts, click "Merge pull request"
7. Click "Confirm merge"
8. Your changes are now part of the main project!

## Common Issues and Solutions

### "I made a mistake in my commit message"

If you haven't pushed your changes yet:
```
git commit --amend -m "New correct message"
```

### "I want to undo my last commit but keep the changes"

```
git reset --soft HEAD~1
```

### "I want to completely undo my last commit and all changes"

```
git reset --hard HEAD~1
```

### "I can't push because there are changes on GitHub I don't have"

First, get the latest changes:
```
git pull origin main
```

Then try pushing again:
```
git push origin main
```

## Remember:

The basic workflow is:
1. Make changes to your files
2. `git add .` (add changes to staging)
3. `git commit -m "Describe what you did"` (save your changes)
4. `git push origin main` (send to GitHub)

If you're working with others:
1. `git pull origin main` (get latest changes)
2. Make your changes
3. Add, commit, and push as above

## Need Help?

- Ask a friend who knows GitHub
- Search for your issue on [Google](https://www.google.com)
- Check [GitHub's help documentation](https://docs.github.com/en/github/getting-started-with-github)

Happy coding!