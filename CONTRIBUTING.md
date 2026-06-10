# TankFlare Contributing Guide

Thanks for trying to contribute to TankFlare! Here's a step-by-step, easy to follow, process for contributing:

<details>
<summary><strong>Step 0 - Prerequisites</strong></summary>
1. **Computer**: Windows, macOS, or a Linux computer with a recommended minimum of 8GB RAM.
2. **Internet**: A stable internet to make sure GitHub and Git run smoothly.
3. **Email Account**: Needed to sign up for GitHub.
4. **GitHub Account**:
   - Go to https://github.com/join.
   - Fill in username, email, password. Verify your email.
5. **Install Git**:
   - Windows: Download from https://git-scm.com/download/win, run installer, accept defaults.
   - macOS: Install Xcode Command Line Tools by running `xcode-select --install` in Terminal, or download from https://git-scm.com.
   - Linux: Use your package manager, e.g. `sudo apt install git`.
6. **Install a Code Editor**: We recommend [VS Code](https://code.visualstudio.com/download). Download, run installer, accept defaults.
> **Check setup**: Open Terminal/PowerShell and run git --version and node --version. Both should print versions. If not, reinstall.
</details>

## Step 1 - Fork the TankFlare Repository

1. Go to the project page: [TankFlare](https://github.com/Omo-star/tankflare-community).
2. Click the **Fork** button in the top-right corner, right in-between the **Watch** and **Star** buttons.
3. Choose your account and create the fork (no need to change settings). This creates your own copy of TankFlare under `https://github.com/YOUR_USERNAME/tankflare-community`.

## Step 2 - Create an Issue or Fix an Issue

<details>
<summary><strong>Fix an Issue</strong></summary>
1. Go to [Issues](https://github.com/Omo-star/tankflare-community/issues) in a new tab.
2. Choose an existing issue that you want to fix. Beginner-friendly issues are kept [here](https://github.com/Omo-star/tankflare-community/issues?q=state%3Aopen%20label%3A%22good%20first%20issue%22).
3. Scroll down and click the instructions link. Read these instructions carefully!
</details>

<details>
<summary><strong>Create an Issue</strong></summary>
1. Go to [Issues](https://github.com/Omo-star/tankflare-community/issues) in a new tab.
2. Click **New Issue**, then choose one of the templates.
3. Fill out the template, and follow the instructions.
</details>

## Step 3 - Choose your workflow

### 3A - Direct Edits

> This will be good enough for most tasks, as all tasks are primarily devoted to editing JSON files.

1. Open your fork (at https://github.com/YOUR_USERNAME/tankflare-community).
2. Create the file(s), and follow the issue's instructions.
3. Write directly into the GitHub editor, and use the **File Upload** feature to add images.
4. Save the file with a short commit message of what you did, like "Added Neon Tetra species".

Skip to [step 10](#step-10---open-a-pull-request-pr).

<details>
<summary><strong>3B - Local Edits</strong></summary>
  
> **Beginners beware!** This is for more advanced users.

## Step 4 - Clone Your Fork Locally

You now have a fork on GitHub. Pull it into your computer:

1. Copy the **HTTPS** URL (https://github.com/YOUR_USERNAME/tankflare-community.git
2. Open your terminal and run:
```sh
git clone https://github.com/YOUR_USERNAME/tankflare-community.git
cd tankflare-community
```
3. Add the upstream/original repository so you can sync it later:
```sh
git remote add upstream https://github.com/Omo-star/tankflare-community.git
```

## Step 5 - Create a New Branch for Your Work

Always keep `main` clean. Create a branch:

```bash
git checkout -b your-issue-short-name
```

Example: `git checkout -b add-neon-tetra-species`.

## Step 6 - Make the Changes

1. Open the project in VS Code: either run `code .` (if the command is installed) or open VS Code and choose **File → Open Folder…**.
2. Follow the instructions in your chosen issue:
   - Modify files.
   - Keep your changes focused on your single issue.
3. Save files. Use VS Code’s Git sidebar to see changed files.

## Step 7 - Install and Use Python

To check whether a JSON file is formatted correctly, you need Python installed.

### Windows

1. Go to [Python Downloads](https://www.python.org/downloads/).
2. Download the latest Python installer for Windows.
3. Open the installer.
4. Before clicking **Install Now**, check this box:

   **Add python.exe to PATH**

5. Click **Install Now**.
6. When it finishes, close and reopen your terminal.

Check that Python works:

```powershell
python --version
```

If that does not work, try:

```powershell
py --version
```

### Mac

1. Go to [Python Downloads](https://www.python.org/downloads/).
2. Download the latest Python installer for macOS.
3. Open the installer and follow the steps.
4. Close and reopen your terminal.

Check that Python works:

```sh
python3 --version
```

### Linux

Many Linux computers already have Python installed.

Check with:

```sh
python3 --version
```

If Python is not installed, install it with your Linux package manager:

**Ubuntu/Debian**:

```sh
sudo apt update
sudo apt install python3
```

**Fedora**:

```sh
sudo dnf install python3
```

**Arch Linux**:

```sh
sudo pacman -S python
```

## Check a JSON File

Once Python is installed, run:

```sh
python -m json.tool package.json
```

On Mac or Linux, you may need to use:

```sh
python3 -m json.tool package.json
```

If the JSON is valid, Python will print a formatted version of the file.

If the JSON is broken, Python will show an error message telling you where the problem is.

## Step 7 - Commit Your Changes

1. See what changed:

   ```sh
   git status
   ```

2. Stage files:

   ```sh
   git add path/to/changed-file.tsx
   ```

   Or add everything: `git add .` (only if you’re sure).

3. Commit with a descriptive message (use lower-case conventional style):

   ```sh
   git commit -m "fix: update onboarding copy"
   ```

If Git asks for your name/email, set them once:

```sh
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```
**Windows**:

```sh
python --version
```

**macOS/Linux**:

```sh
python3 --version
```

If that does not work, try:

```sh
py --version
```

## Step 8 - Sync With Upstream

If time passed since you forked:

```sh
git fetch upstream
git checkout main
git merge upstream/main
git checkout your-branch
git rebase main   # optional, keeps history clean
```

Fix conflicts if Git reports any (VS Code highlights them). Save, stage, continue with `git rebase --continue`.

## Step 9 - Push to Your Fork

```bash
git push origin your-branch
```

The first push may prompt you to sign in to GitHub via browser—follow the prompts.

</details>

## Step 10 - Open a Pull Request (PR)

1. Visit your fork on GitHub. You’ll see a banner suggesting to create a PR.
2. Click **Compare & pull request**.
3. Ensure base repository is `Omo-star/tankflare-community` and base branch is `main`.
4. Fill in the PR template:
   - **Title**: short summary (`Added Neon Tetra species`).
   - **Description**: what you changed and why.
   - **Linked issue**: type “Closes #ISSUE_NUMBER”.
5. Click **Create pull request**.


## Step 11 - After Opening the PR

1. The CI runs automatically (shows as status checks).
2. Maintainers may request changes. To update:
   - Make edits locally.
   - Run ```python -m json.tool package.json``` again.
   - Commit additional changes.
   - ```git push origin your-branch``` (push adds to same PR automatically).
3. Celebrate when it’s merged 🎉

- [ ] Created GitHub account + installed Git, Node.js, VS Code
- [ ] Forked repository
- [ ] Chose a [good first issue](https://github.com/Omo-star/tankflare-community/issues?q=state%3Aopen%20label%3A%22good%20first%20issue%22)
- [ ] Cloned fork locally (```git clone```) _(skip if using GitHub-only workflow)_
- [ ] Created branch (```git checkout -b ...```)
- [ ] Made change + ran ```python -m tools.json package.json```
- [ ] Committed (```git commit -m ...```)
- [ ] Pushed (```git push origin ...```)
- [ ] Opened PR and filled template
- [ ] Responded to review feedback

Congratulations, you’ve now officially contributed to TankFlare. Thanks so much! 🐟
