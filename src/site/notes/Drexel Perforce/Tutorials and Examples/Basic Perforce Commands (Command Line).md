---
{"dg-publish":true,"permalink":"/drexel-perforce/tutorials-and-examples/basic-perforce-commands-command-line/"}
---

## Overview

This section provides an introduction to basic Perforce commands, distinguishing between those commonly used by general users and those intended for admins or super users. It also explains how to access and use the command line interface on Windows and Mac systems.

## Introduction to Perforce Command Types

In Perforce, commands are executed through a command-line interface (CLI) like `Terminal`. However, there are two versions of commands, those that connect with the Perforce Server/Depot directly (p4) and those that connect with the Perforce Visual Client (p4vc). Understanding the difference between these command types is crucial.

- **`p4` Commands:** These are executed in the command-line environment and are ideal for scripting, automation, and flexibility.
    
- **`p4vc` Commands:** When these commands are executed, they affect the P4V GUI (Graphical User Interface).
    

***This document focuses on `p4` command-line operations, providing a guide for both general users and administrators***

## Accessing the Command Line

### Windows
1. **Using CMD (Command Prompt):**
   - Press `Win + R`, type `cmd`, and press `Enter`.
   - Alternatively, search for "Command Prompt" in the start menu.

2. **Using PowerShell:**
   - Search for "PowerShell" in the start menu and select it.

### macOS
1. **Using Terminal:**
   - Open Finder, go to Applications > Utilities, and double-click on Terminal.
   - Alternatively, use `Cmd + Space` to open Spotlight Search, type "Terminal", and press `Enter`.

## Basic Commands for P4V Users

For basic users, the focus is on daily tasks such as checking files in and out, viewing file histories, and managing personal workspaces.

- **Check Out Files:**
  ```
  p4 edit <file-path>
  ```
  Marks files for open as being edited.

- **Submit Changes:**
  ```
  p4 submit -d "description of changes"
  ```
  Submits changes to the depot.

- **Get Latest Version:**
  ```
  p4 sync
  ```
  Synchronizes workspace with the latest files from the depot.

- **View File History:**
  ```
  p4 filelog <file-path>
  ```
  Shows the revision history of a file.

## Advanced Commands for Admins/Super Users

Admins or super users need to manage user permissions, server configurations, and more complex depot operations.

- **Create User:**
  ```
  p4 user -f <username>
  ```
  Force-creates a new user or edits an existing user configuration.

- **Manage User Permissions:**
  ```
  p4 protect
  ```
  Edits the protection table for controlling user access.

- **Depot Management:**
  ```
  p4 depot _depotname_
  ```
  Displays or edits a depot.

- **Server Health Check:**
  ```
  p4 pull
  ```
  Displays information about file transfers.

### Tips for Using Perforce Commands
- Always verify your current workspace and ensure it is set to the correct stream or branch before performing operations.
- Use `p4 help <command>` to get more detailed information on specific commands.

---

**There are many more p4 commands that can be used to manage a project or a server that simply cannot be shown here. To find a list of commands and their descriptions/use case, follow the link below to the official Helix Core docs on the topic.**

---

**Official Helix Core Documentation: P4 Command Line by Area** - https://www.perforce.com/manuals/cmdref/Content/CmdRef/Commands%20by%20Functional%20Area.html 