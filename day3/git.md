# Installing Git on Windows (Step-by-Step Guide)

This guide walks you through **installing Git on a Windows laptop using the terminal**, explained clearly and step by step. It is beginner-friendly and suitable for DevOps learners.

---

## Prerequisites

Before you begin, make sure:

* You are using a **Windows laptop**
* You have an **active internet connection**
* You have **basic knowledge of using a browser and terminal**

---

## Step 1: Download Git for Windows

1. Open your web browser

2. Visit the official Git website:

   ```
   https://git-scm.com
   ```

3. Click **Download for Windows**

4. The download will start automatically (`Git-xx.x.x-64-bit.exe`)

---

## Step 2: Run the Git Installer

1. Go to your **Downloads** folder
2. Double-click the Git installer file
3. If Windows shows a permission prompt:

   * Click **Yes**

---

## Step 3: Installation Configuration (Important)

Follow these steps carefully. If unsure, **stick to the recommended options below**.

---

### 1. Select Destination Location

* Leave the default path unchanged
* Click **Next**

---

### 2. Select Components

* Leave all options as default
* Ensure **"Git Bash Here"** is checked
* Click **Next**

---

### 3. Select Start Menu Folder

* Leave default settings
* Click **Next**

---

### 4. Choose Default Editor for Git

Choose one:

* **Visual Studio Code** (recommended if installed)
* Or leave default (**Vim**) if unsure

Click **Next**

---

### 5. Adjusting PATH Environment (Very Important)

Select:

>  **Git from the command line and also from 3rd-party software**

This allows Git to work in:

* Command Prompt
* PowerShell
* VS Code Terminal

Click **Next**

---

### 6. Choose HTTPS Transport Backend

* Select **Use the OpenSSL library** (default)
* Click **Next**

---

### 7. Configure Line Ending Conversions

Choose:

>  **Checkout Windows-style, commit Unix-style line endings**

Click **Next**

---

### 8. Configure the Terminal Emulator

Choose:

>  **Use MinTTY (the default terminal of Git Bash)**

Click **Next**

---

### 9. Configure Extra Options

* Leave all options as default
* Click **Next**

---

### 10. Experimental Options

* Leave all options unchecked
* Click **Install**

Wait for the installation to complete, then click **Finish**.

---

## Step 4: Verify Git Installation

You can verify Git installation using any terminal.

---

### Option A: Using Git Bash (Recommended)

1. Right-click anywhere on your Desktop
2. Click **Git Bash Here**
3. Run the command:

```bash
git --version
```

Expected output:

```
git version 2.xx.x.windows.x
```

---

### Option B: Using Command Prompt or PowerShell

1. Open **Command Prompt** or **PowerShell**
2. Run:

```bash
git --version
```

If a version number appears, Git is installed successfully.

---

## Step 5: Basic Git Configuration (Required)

Set your Git username:

```bash
git config --global user.name "Your Name"
```

Set your Git email:

```bash
git config --global user.email "youremail@example.com"
```

Verify configuration:

```bash
git config --list
```

---

## What You Have Achieved

* Git installed on Windows
* Git Bash terminal available
* Git accessible from CMD, PowerShell, and VS Code
* Ready for GitHub, DevOps, and CI/CD workflows

---


Happy building 🚀
