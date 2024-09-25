---
{"dg-publish":true,"permalink":"/drexel-perforce/getting-started/first-steps-in-perforce/"}
---

<iframe src="https://1drv.ms/v/s!AqQzGx8l4o2wk-syAmTvlqQr5q2YpA?embed=1" width="640" height="320" frameborder="0" scrolling="no" allowfullscreen></iframe>

---

# 🚀 First Steps in Perforce: A Beginner's Guide

Welcome to your journey with Perforce! This guide will walk you through the essential tasks you'll perform using the P4V client. *Let's dive in!*

## 📋 Table of Contents

1. [Managing .p4ignore Files](#managing-p4ignore-files)
2. [Navigating Your Workspace](#navigating-your-workspace)
3. [Editing Files](#editing-files)
4. [Adding Files](#adding-files)
5. [Deleting Files](#deleting-files)
6. [Working with Streams](#working-with-streams)
7. [Best Practices](#best-practices)

---

## 🛠 Managing .p4ignore Files

> [!important] Why Use .p4ignore?
> `.p4ignore` files help manage which files are versioned in your project. This is crucial for game development, where you often have build directories, temporary files, or third-party libraries that shouldn't be in version control.

### Setting Up .p4ignore Support

1. **Enable .p4ignore Support**:
   - Open Command Prompt as administrator
   - Type `setx P4IGNORE .p4ignore` and press Enter

2. **Create a .p4ignore File**:
   - In your workspace root, create a file named `.p4ignore`
   - Add patterns for files to ignore, for example:

```plaintext
# Ignore temporary files
*.tmp

# Ignore build directory
build/

# Ignore all files in temp directories
temp/**
```

> [!tip] Pro Tip
> For Unity or Unreal projects, check if a template `.p4ignore` file is provided in your depot. It's a great starting point!

---

## 🗺 Navigating Your Workspace

Your workspace is your local copy of files from the server. Here's how to navigate it efficiently:

### 👀 Viewing Your Files

1. Open the **Workspace Tree** tab:
   - Menu: `View > Workspace Tree`
   - Shortcut: `Ctrl + 0` (Windows) or `Cmd + 0` (macOS)

   ![Workspace Tree](https://i.postimg.cc/k43L3FzN/p4v-workspace-Tree-tab.gif)

### 🔄 Syncing to the Latest Version

- Right-click your workspace and choose **Get Latest Revision**
- Shortcut: `Ctrl + Shift + G` (Windows) or `Cmd + Shift + G` (macOS)

   ![Get Latest](https://i.postimg.cc/QdzRSrqy/p4v-get-Latest.gif)

### 🔒 Checking Out Files

- Right-click a file and select **Check Out**
- Shortcut: `Ctrl + E` (Windows) or `Cmd + E` (macOS)

   ![Check Out](https://i.postimg.cc/j5HmsnYp/p4v-check-Out.gif)

### 📤 Submitting Changes

1. Go to the **Pending** tab
2. Right-click your changelist and select **Submit**
3. Enter a detailed description
4. Click **Submit**

   ![Submit Changes](https://i.postimg.cc/SRVP90sV/p4v-submit.gif)

---

## ✏️ Editing Files

1. **Check Out**: Right-click the file and select 'Check Out'
2. **Edit**: Make your changes using your preferred editor
3. **Submit**: Right-click the edited file and select 'Submit'

> [!warning] Remember
> Always provide a clear, descriptive message when submitting changes!

---

## 📁 Adding Files

1. **Create or Place Files** in your workspace
2. In P4V, right-click and select **Mark for Add**
3. **Submit** the changelist to add files to the depot

   ![Adding Files](https://i.postimg.cc/HL7FhPZs/p4v-add.gif)

---

## 🗑 Deleting Files

> [!caution] Important
> Always use P4V to delete files. Don't delete directly from your file system!

1. **Locate Files**: In the Depot tab, find the file(s) you want to delete
2. **Mark for Deletion**: Right-click and choose "Delete"
3. **Submit the Change**:
   - Go to the Pending tab
   - Right-click the changelist and select "Submit"
   - Enter a description explaining the deletion
4. **Verify**: Check both the Depot tab and your local workspace to ensure the files are gone

> [!tip] Tip
> If files persist locally after deletion, try refreshing your workspace or syncing to the latest revision.

---

## 🌊 Working with Streams

Streams are purpose-defined branches that make managing changes easier.

1. **View Stream Structure**:
   - Open the Stream Graph tab: `View > Stream Graph` or `Alt + 7`

2. **Switch Streams**:
   - Right-click your workspace, choose "Edit Workspace"
   - Select the desired stream
   - Or drag the computer icon in the Stream Graph

   ![Switch Streams](https://i.postimg.cc/Lsbj02CG/p4v-stream-Graph-switch.gif)

3. **Merge Changes**:
   - Right-click the target stream and select 'Merge/Integrate'
   - Follow prompts to resolve conflicts

   ![Merge Streams](https://i.postimg.cc/FRk3M8wz/p4v-stream-Graph-merge.gif)

> [!attention] Also see: 
> [[Drexel Perforce/Perforce Streams/Branching, Merging, and Copying with Streams\|Branching, Merging, and Copying with Streams]]

---

## 💡 Best Practices

1. **Sync Frequently**: Get the latest version before starting work
2. **Check Out Wisely**: Only check out necessary files
3. **Review Changes**: Use "Revert If Unchanged" before submitting
4. **Descriptive Submissions**: Always provide clear commit messages
5. **Communicate**: Keep your team informed about significant changes
6. **Regular Syncs**: Update your workspace often to minimize conflicts

---

> [!note] Want to Learn More?
> Check out the [Official Helix Core Documentation](https://help.perforce.com/helix-core/quickstart/Content/quickstart/end-user-reference.html) for in-depth information and advanced techniques!