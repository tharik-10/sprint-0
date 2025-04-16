# 📘 Standard Operating Procedure (SOP): Installing `jq` (Command-line JSON Processor)

## 🔹 What is `jq`?
`jq` is a lightweight and flexible command-line JSON processor. It allows you to slice, filter, map, and transform structured data with ease.

---

## ✅ Installation Methods

---

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

