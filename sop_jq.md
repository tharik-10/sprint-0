# 📘 Standard Operating Procedure (SOP): Installing `jq` (Command-line JSON Processor)

| Author         | Created on     | Version         | Last updated by | Last edited on | Pre Reviewer | L0 Reviewer | L1 Reviewer | L2 Reviewer |
|----------------|----------------|-----------------|-----------------|----------------|---------------|-------------|-------------|-------------|
| Mohamed Tharik | 2025-04-16     |     Version 1         | Mohamed Tharik  | 2025-04-17     |Priyanshu | Khushi | Mukul Joshi|Piyush Upadhyay |

## 🎯 Purpose 

This guide explains how to install and use `jq`, a command-line tool for working with JSON data. It includes:

- ✅ What `jq` is used for.
- 🛠️ How to install it (using `apt` and manual method)  
- 🧹 How to uninstall and check the version  
- 🔍 Common `jq` commands to work with JSON

## ✨ Prerequisites

Before starting, make sure you have:

- A Linux-based OS (Ubuntu/Debian preferred for `apt` method)
- Terminal access with `sudo` privileges
- Internet connection (for downloading `jq` via `apt` or `wget`)
- Basic understanding of JSON format (optional but helpful)
- Installed `wget` if using the manual installation method

## 📑 Table of Contents

- [🔹 What is `jq`?](#-what-is-jq)
- [✅ Installation Methods](#-installation-methods)
  - [🛠️ Method 1: Install `jq` Using apt (Ubuntu)](#️-method-1-install-jq-using-apt-ubuntu)
    - [📋 Step-by-Step](#-step-by-step)
    - [🧹 Uninstall jq on Ubuntu](#-uninstall-jq-on-ubuntu)
  - [🧰 Method 2: Manual Installation of jq (Cross-platform)](#-method-2-manual-installation-of-jq-cross-platform)
    - [📋 Step-by-Step Installation](#-step-by-step-installation)
    - [🗑️ Remove the Manually Installed jq Binary](#️-remove-the-manually-installed-jq-binary-if-required)
    - [🧼 Clear the Shell Command Cache](#-clear-the-shell-command-cache)
- [📘 Simple jq Query Commands](#simple-jq-query-commands)
- [✅ Conclusion](#-conclusion)
- [📬 Contact Information](#-contact-information)
- [📚 Reference](#-reference)

## 🔹 What is `jq`?
`jq` is a lightweight and flexible command-line JSON processor. It allows you to slice, filter, map, and transform structured data with ease.

## ✅ Installation Methods

### 🛠️ Method 1: Install `jq` Using apt (Ubuntu)

#### 📋 Step-by-Step:

```bash
# Step 1: Update the package list
sudo apt update

# Step 2: Install jq using apt
sudo apt install jq -y

# Step 3: Verify installation
jq --version

```
#### 🧹 Uninstall jq on Ubuntu

If we wish to uninstall `jq` from your Ubuntu system, follow these steps:

```bash
# Step 1: Remove jq package but keep configuration files

sudo apt remove jq

# step 2: Completely remove jq (including configuration files)

sudo apt purge jq

```
### 🧰 Method 2: Manual Installation of jq (Cross-platform)

Follow the steps below to manually install `jq` on your system:

#### 📋 Step-by-Step Installation:

1. **Download the jq binary (64-bit Linux example):**
   Open your terminal and run the following command to download the jq binary:

   ```bash
   wget -O jq https://github.com/stedolan/jq/releases/download/jq-1.6/jq-linux64

2. **Make the binary executable:**

Next, you need to give executable permissions to the `jq` binary by running the following command:

```bash
chmod +x ./jq
```
3. **Move it to a location in your PATH:**

To make the `jq` command available globally, move it to a directory that is in your system's PATH (e.g., `/usr/local/bin`):

```bash
sudo mv jq /usr/local/bin
```
4. **Verify Installation:**

Finally, verify that `jq` has been installed successfully by checking its version:

```bash
jq --version
```
#### 🗑️ Remove the Manually Installed `jq` Binary if required 

To remove the old `jq` binary from `/usr/local/bin`:

```bash
sudo rm /usr/local/bin/jq
```
#### 🧼 Clear the Shell Command Cache 

fter removing the old binary, clear your shell's command cache to refresh the command path:
```bash
hash -r
```
This is manually downloading a precompiled binary for Linux 64-bit [jq GitHub Releases page](https://github.com/stedolan/jq/releases), binaries are provided for multiple platforms:

- `jq-linux64` → for **64-bit Linux**
- `jq-linux32` → for **32-bit Linux**
- `jq-win64.exe` → for **Windows**
- `jq-osx-amd64` → for **macOS**

This manual method is considered **cross-platform** because you can:

- ✅ Choose the binary for your specific operating system  
- 📥 Download it manually  
- 🔐 Make it executable (if required)  
- 🚀 Run it without needing to compile or use a package manager

This makes manual installation flexible and widely compatible across different systems.

## 📘 Simple jq Query Commands
jq is a powerful command-line JSON processor. Below are basic examples to help you get started with parsing and querying JSON data.

### 📂 Sample JSON (data.json)
```json
{
  "name": "Alice",
  "age": 30,
  "skills": ["Go", "Python", "Docker"],
  "active": true,
  "address": {
    "city": "New York",
    "zip": "10001"
  }
}
```
#### 1. Print Entire JSON
```bash 
jq '.' data.json
```
#### 2. Access a Specific Key
```bash
jq '.name' data.json
```
#### 3. Access Nested Object
```bash
jq '.address.city' data.json
```
#### 4. Access Array Elements
```bash
jq '.skills[0]' data.json
```
#### 5. Loop Through an Array
```bash  
jq '.skills[]' data.json
```
#### 6. Filter with select (Example with array of objects)
Sample JSON (users.json):
```bash 
{
  "users": [
    {"id": 1, "name": "Alice"},
    {"id": 2, "name": "Bob"}
  ]
}
```
Filter user with id 2:
```bash 
jq '.users[] | select(.id == 2)' users.json
```
## ✅ Conclusion

`jq` is a powerful and easy-to-use tool for handling JSON data in the terminal. It's especially helpful for tasks like:

- 📡 Reading and filtering API responses  
- ⚙️ Working with configuration files and logs  
- 🤖 Automating scripts that involve JSON  

With `jq`, you can quickly extract, transform, and analyze JSON data — making your terminal workflows faster and more efficient.

## 📬 Contact Information

| Name | Email address         |
|------|------------------------|
| Mohamed Tharik  | md.tharik.sanaatak@mygurukulam.co    |

## 📚 Reference

| Links                                                                                                                                                                                                                     | Descriptions                                                                                         |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------|
| [JQ Command for JSON Processing](https://www.baeldung.com/linux/jq-command-json)                                                                                                                                          | A complete guide on using the `jq` command in Linux to process and manipulate JSON data              |



