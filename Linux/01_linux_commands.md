# 🧠 Linux & Terminal: General Knowledge (ثقافة عامة)

### 1. What is Linux?
* **The Kernel (The Engine):** Technically, Linux is not a full operating system; it is just the **Kernel** (created by Linus Torvalds in 1991). The Kernel is the core software that allows your applications (Software) to talk directly to your computer's hardware (CPU, RAM, Keyboard).
* **Open Source:** It is free and open-source, meaning anyone can view, modify, and distribute its code.

---

### 2. What are Linux Distributions (Distros)?
Since Linux is open-source, different companies and communities take the Linux Kernel, package it with their own desktop designs and software, and release them as different "Distros" (Distributions):
* **Linux Mint:** Super stable, beginner-friendly, and has a familiar interface similar to Windows.
* **Ubuntu:** The most famous distro, widely used by developers and enterprise servers.
* **Fedora:** Always features the latest software updates and cutting-edge technologies.
* **Arch Linux:** Built for advanced users who want to assemble and configure their OS piece-by-piece.

---

### 3. What is the Terminal (CLI)?
* **Command Line Interface (CLI):** It is the oldest and most powerful way to interact with a computer using text commands instead of pointing-and-clicking with a mouse.
* **Why Developers Use It:** It is incredibly fast, allows automate repetitive tasks, and gives you absolute control over system configuration files.

---

### 4. Why C and Not PHP?
* **C Language:** The Linux Kernel, Bash, and core system utilities are written in **C/C++** because it runs extremely fast, directly manages system memory, and has no overhead.
* **The `echo` Origin:** The `echo` command was born in the Unix/Linux Terminal decades before **PHP** existed. PHP simply "borrowed" the name and variable styles (like using `$`) to make web backend development feel familiar and easy for Linux system administrators.


## 🐧 Essential Linux Terminal Commands Cheat Sheet

Here is a list of all the basic commands we used and configured today:

---

## 1. Directory Navigation & Location
* **`pwd`** (Print Working Directory): Shows the absolute path of your current location in the file system.
* **`cd [directory]`** (Change Directory): Moves you into a specific folder (e.g., `cd Documents`).
* **`cd ..`**: Moves you one step backward to the parent directory.
* **`cd ~`**: Instantly takes you back to your Home directory (`/home/nora`).

---

## 2. Listing Files & Folders
* **`ls`** (List): Displays the files and folders in your current directory.
* **`ls -la`**: Lists all files in a long format with details (permissions, size, owner) including hidden files starting with a dot (`.`).

---

## 3. Creating & Managing Files
* **`mkdir [folder_name]`** (Make Directory): Creates a new folder (e.g., `mkdir Dev-Notebook`).
* **`touch [file_name]`**: Creates a new empty file (e.g., `touch 01_linux_commands.md`).
* **`cp [source] [destination]`** (Copy): Copies a file to a new name or location.
* **`mv [source] [destination]`** (Move/Rename): Renames a file or moves it to another directory.
* **`rm [file_name]`** (Remove): Deletes a file permanently. *Warning: It bypasses the trash bin!*

---

## 4. Reading & Writing File Content
* **`cat [file_name]`**: Displays the entire content of a file directly in the terminal.
* **`echo "[text]" >> [file_name]`**: Appends a line of text to the end of a file without overwriting it.
* **`nano [file_name]`**: Opens a lightweight terminal text editor to edit files directly.

---

## 5. Terminal Control & Shortcuts
* **`clear`** (or `Ctrl + L`): Clears the terminal screen.
* **`Ctrl + C`**: Cancels or stops any currently running command or process.
* **`Tab` (Key ↹)**: Autocomplete feature. Type the first few letters of a file/folder and press Tab to complete the name.
* **`code .`**: Opens the current directory directly inside VS Code.

---

## 6. System Configurations & Custom Aliases
* **`xmodmap -e "keycode 49 = less greater less greater bar backslash"`**: Re-maps the key below Esc (keycode 49) to write `<` and `>`.
* **`nano ~/.bashrc`**: Opens your terminal configuration file to add, edit, or delete custom shortcuts (Aliases).
* **`source ~/.bashrc`**: Refreshes the terminal configurations to apply any new changes instantly.
* **`alias`**: Lists all active shortcuts (aliases) currently running on your system.