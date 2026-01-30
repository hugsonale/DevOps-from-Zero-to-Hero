# Prerequisite for Learning DevOps

(Tools to Install Before You Continue)

Before you start learning DevOps concepts, pipelines, and cloud tools, there are a few basic tools you must have on your system. These tools will help you practice commands, understand how servers work, and follow along with real DevOps tasks.

At this stage, we are only installing essential tools. Advanced tools like Kubernetes, Terraform, or Jenkins will come later when they are truly needed.

A Computer (Basic Requirement)

To learn DevOps properly, you need a laptop or desktop computer. DevOps involves working with servers, commands, files, and configurations — a mobile phone will not work.

**Minimum recommendation:**
* At least 4GB RAM (8GB is better)
* Windows, macOS, or Linux
* Stable internet connection

DevOps is hands-on. You must be able to install software and run commands.

## Operating System (OS)

Your operating system is important because DevOps engineers mostly work with **Linux-based systems**.

### Options

- **Linux (Best choice)**  
  Ubuntu is highly recommended.

- **macOS**  
  Also good (already Unix-based).

- **Windows**  
  Works, but you must set it up properly.

If you are using **Windows**, don’t worry. You can still learn DevOps using:

- **Windows Subsystem for Linux (WSL)**

> We will **not install a full Linux OS yet**.  
> For now, **WSL is enough**.

## Terminal / Command Line (Very Important)

DevOps engineers work **inside the terminal** most of the time.  
This is where you run commands, manage servers, and automate tasks.

---

### What is a Terminal?

A terminal is a tool that allows you to communicate with your computer using **text commands** instead of clicking buttons.

---

### Based on Your Operating System (OS)

- **Linux** → Terminal is already installed  
- **macOS** → Terminal is already installed  
- **Windows** → You need to install:
  - Windows Terminal
  - WSL (Ubuntu)

---

### What to Install on Windows

1. Install **Windows Terminal** (from the Microsoft Store)
2. Install **WSL**
3. Install **Ubuntu inside WSL**

---

Once installed, you will be able to run **Linux commands** like a real DevOps engineer.

> **This is non-negotiable.**  
> DevOps without a terminal is impossible.


## Step-by-Step Installation Guide (Windows Users)

This guide will walk you through installing:
1. Windows Terminal  
2. Windows Subsystem for Linux (WSL)  
3. Ubuntu inside WSL  

Follow the steps **in order**. Do not skip any step.

---

## Step 1: Install Windows Terminal

Windows Terminal is the application that will allow you to open and manage command-line tools like PowerShell and Ubuntu (WSL).

### Steps:

1. Open the **Microsoft Store** on your Windows computer  
2. In the search bar, type **Windows Terminal**  
3. Click on **Windows Terminal** from the results  
4. Click **Install**  
5. Wait for the installation to finish  
6. Once installed, click **Open**

### Verify Installation:
- You should see a terminal window open
- By default, it opens with **PowerShell**

 Windows Terminal is now installed.

---

## Step 2: Install Windows Subsystem for Linux (WSL)

WSL allows you to run Linux directly on Windows without installing a full virtual machine.

### Steps:

1. Open **Windows Terminal**
2. Make sure it is using **PowerShell**
3. Type the command below and press **Enter**:

   ```bash
   wsl --install



## Step 4: Install Ubuntu Inside WSL
Ubuntu is the Linux distribution that will be used throughout this DevOps course.

### Steps
1. Open Windows Terminal

Type the command below and press Enter:

**wsl --install -d Ubuntu**

Wait while Ubuntu downloads and installs

Ubuntu will open automatically once installation is complete

## Step 5: Ubuntu First-Time Setup

When Ubuntu opens for the first time, complete the initial setup.

### Steps

1. Wait for the setup process to finish
2. Create a Linux username (This username is for Ubuntu only It does not have to match your Windows username)
3. Enter a password (Characters will not appear while typing)

This is normal behavior

4. Confirm the password

After setup, you will see a prompt similar to:

**username@computer-name:~$**

 Ubuntu is now ready for use. 💯

### Step 6: Verify Ubuntu Is Working

To confirm that Ubuntu is working correctly:

Inside the Ubuntu terminal, type:

**ls**

Press Enter

If the command runs without errors, Ubuntu is installed and functioning correctly.

 Your Linux environment is ready. 💯