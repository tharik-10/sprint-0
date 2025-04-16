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
