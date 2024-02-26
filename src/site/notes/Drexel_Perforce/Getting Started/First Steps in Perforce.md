---
{"dg-publish":true,"permalink":"/drexel-perforce/getting-started/first-steps-in-perforce/"}
---

Now that your workspace and streams are set up, let's delve into some practical tasks within the P4V client. This guide focuses on exploring your workspace and streams through common and useful tasks in P4V, helping you become proficient in managing and navigating your projects. While command-line operations offer additional power for advanced users, most day-to-day tasks can be efficiently handled through the P4V client.
## Order of Operations
1. **Managing `.p4ignore` Files**
2. **Navigating Your Workspace**
3. **Editing Files**
4. **Adding Files**
5. **Working with Streams**

---
### Managing .ignore Files in Perforce

An essential part of working efficiently with Perforce is managing which files and directories are versioned and which are ignored. This is particularly important in game development projects where build directories, temporary files, or third-party libraries should not be submitted to the Perforce server. Perforce uses `.p4ignore` files to specify patterns for files and directories to ignore. Let's go through setting up and using `.p4ignore` files in your project.

#### Setting Up `.p4ignore` Support

##### Enable `.p4ignore` Support
- **Perforce Environment Setup**: To use `.p4ignore`, you must first enable support by setting the `P4IGNORE` environment variable to `.p4ignore`.

    - **Windows**:
      - Open the Command Prompt.
      - Type `setx P4IGNORE .p4ignore` and press Enter.
      - **System GUI**:
        - Right-click `This PC` > `Properties` > `Advanced system settings`.
        - Under `System Properties`, click `Environment Variables`.
        - Click `New` under `User variables` or `System variables`.
        - Set `Variable name` to `P4IGNORE` and `Variable value` to `.p4ignore`.
        - Click `OK` to save.
        
    - **macOS/Linux**:
      - Open the Terminal.
      - Add `export P4IGNORE=.p4ignore` to your `.bashrc`, `.zshrc`, or equivalent.
      - **macOS System GUI**:
        - Go to `System Preferences` > `Users & Groups`.
        - Select your user and click `Login Items`.
        - Click the `+` button and navigate to your shell profile script to add it (additional steps may be required for direct environment variable setup via GUI).

*A Restart your machine may be required to activate the changes.*

---
#### Creating a `.p4ignore` File

- **Template Depots**: For courses and projects working from Template Depots, a `.p4ignore` file will be included, pre-populated with common patterns for Unity and Unreal projects.
- **Manual Creation**:
  - In your workspace's root directory, create a `.p4ignore` file.
  - Open this file in any text editor and define the patterns for files to ignore. For example:
  
    ```plaintext
    # Ignore all .tmp files
    *.tmp
    # Ignore build directory
    build/
    # Ignore all files in a temp directory
    temp/**
    ```

#### Applying `.p4ignore` Patterns

- With `.p4ignore` set, P4V and Perforce command line tools will ignore files matching these patterns when adding new files to version control.
- This file can be edited with any IDE or text editor to fit a project's specifics.

---
### Best Practices for .p4ignore Files

- **Commit .p4ignore**: While the `.p4ignore` file itself should be personal and not always shared across the team (as different developers might have different environments), it's often useful to have a team-standard `.p4ignore` file that's committed to the repository. This ensures consistent ignore rules across all team members' environments.
- **Specificity**: Be as specific as possible with your ignore patterns to avoid accidentally ignoring important files.
- **Regular Updates**: As your project evolves, regularly review and update your `.p4ignore` file to match new tools, directories, and file types that should be ignored.
---
### Navigating Your Workspace

Your workspace serves as a personal local copy of files from the server, customized for your individual tasks. Below are steps to efficiently navigate and manage your workspace in P4V:
#### Viewing Your Files
- Navigate to the 'Workspace' tab in P4V to view the files and folders within your local workspace. This allows you to explore the current structure and content you're working with.
#### Checking Out Files
- To modify any file, it must be checked out first. Right-click the desired file (or entire folder) in the ***Workspace tab*** and select ***Check Out***. This action locks the file for editing, signaling to your team that you are making changes.
#### Submitting Changes
- Upon completing your edits, right-click the modified file and select ***Submit.*** A dialog will prompt you to describe your changes. Completing this step commits your changes to the server, sharing them with your team.
#### Syncing to the Latest Version
- To ensure your work is based on the most recent file versions, right-click in your workspace and choose ***Get Latest***. This action synchronizes your workspace with the server's latest revisions.

---
### Editing Files
Editing involves checking out a file, making your changes, and then submitting those changes back to Perforce.

- **Check Out**: Right-click the file and select 'Check Out'.
- **Edit**: Make your changes using your preferred editor.
- **Submit**: Right-click the edited file and select 'Submit' to commit your changes, with a descriptive message of what was modified.

---
### Adding Files
Adding files to Perforce is a straightforward process, whether you're populating a new workspace for the first time or adding new assets to an ongoing project.
#### For First-Time Setup in an Empty Depot
If opening your workspace for the first time and your depot is empty, you'll need to add files to begin version control.

- **Create or Place Files**: In your local workspace directory, create new files or place existing ones that you wish to add to version control.
- **Add Files to Perforce**: In P4V, navigate to the root of your workspace or the directory where you have added files. Right-click and select ***Mark for Add***. Or, choose the individual files you wish to add, then click ***Add***.
- **Submit Changes**: After adding, a changelist will be created. Right-click this changelist and select 'Submit' to finalize adding your files to the depot.

---
### Working with Streams

Streams are branches defined with a purpose, making it easier to manage and integrate changes. Here’s how to work with them:

1. **Viewing Stream Structure**:
    - The 'Stream' tab in P4V gives you a graphical representation of your project's stream structure. Explore this view to understand how different streams relate to each other, such as mainline, development, and release streams.
2. **Switching Streams**:
    - If you need to work on a different part of the project, you can switch your workspace to another stream. Right-click your workspace name and choose 'Switch to Another Stream', then select the stream you wish to work on.
3. **Merging and Integrating Changes**:
    - Streams facilitate merging changes from one branch to another. To merge, right-click on the stream you want to integrate changes into and select 'Merge/Integrate'. Follow the prompts to select the source stream and resolve any conflicts that arise.

---

### Additional/Optional: Command Line Basics

For those interested in exploring beyond the P4V client, here are a few basic command-line operations. These are optional but can offer more control and flexibility:

- **Check Out a File**: `p4 edit <filename>`
- **Submit Changes**: `p4 submit -d "Description of changes" <filename>`
- **Sync Workspace**: `p4 sync`

These command-line operations are a glimpse into the power of Perforce from the terminal. They are particularly useful for advanced tasks or automation.