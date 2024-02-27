---
{"dg-publish":true,"permalink":"/drexel-perforce/getting-started/installation-guide/"}
---

---
### P4V Client Installation

**P4V** is the Perforce Visual Client that provides a graphical interface for managing your files and repositories (depots) in Perforce. Here's how to install it:

1. **Download**:
    - Visit the official Perforce downloads page: [Download Helix Visual Client (P4V) | Perforce](https://www.perforce.com/downloads/helix-visual-client-p4v)
    - Select the version of P4V for your operating system (Windows, macOS, Linux).
    - Click the download button and save the installer to your computer.
2. **Install**:
    - Locate the downloaded installer and double-click to start the installation process.
    - Follow the on-screen instructions. Accept the license agreement, and continue with the default installation settings unless you have specific preferences.
    - Complete the installation. No initial configuration is needed during the install process.

---
### Setting Up Perforce Streams

Perforce Streams provide a structured way to manage branches in your projects, making it easier to handle merges and integrations.

**Accessing P4V**:
- **VPN Connection Required**: Before proceeding, ensure that you are logged in and connected to the [Drexel VPN using Cisco AnyConnect](https://drexel.edu/it/help/a-z/VPN/).
<img src="https://i.postimg.cc/7Y93gdd2/vpn-connect.gif" width="630" height="358" />

- Launch P4V from your applications or programs list.
- Connect to the Perforce server by entering the server address provided followed by the port number (the default is server port is 1666). 
		`perforce.westphal.drexel.edu:1666`
		![perforce_server_port.png](/img/user/Drexel%20Perforce/All%20Media/perforce_server_port.png)
- Log in with your provided credentials (username and password).


**Creating a Stream Depot** (**P4V Administrator**):
- **Pre-Check**: Verify if the required depot already exists or if there's a need to create a new one. Most course-related and project-specific depots are pre-established to facilitate immediate work.
- **Request Creation**: If a new depot is needed and you do not have administrative privileges, request its creation from your Perforce administrator. Provide them with the necessary details such as the preferred name for the depot and its intended use.
- **Administrative Creation**: If you have Perforce administrative privileges and need to create a new streams depot, follow these steps in the P4V Admin interface:
	- Right-click on the ***Depots*** area and select ***New Depot...***.
	- Choose ***Stream*** for the Depot Type. This is the preferred depot type for managing course and project work, offering structured branching and merging capabilities.
	- Name your depot (e.g., "GameDevProjects") with a clear, descriptive name that reflects its purpose or the course it's associated with.
		- For **Unity projects**, prefix the depot name with `N_`. For example, `N_GameDevProjects` for a Unity-based game development project.
		- For **Unreal projects**, prefix the depot name with `R_`. For example, `R_GameDevProjects` for an Unreal Engine-based game development project.
	- Provide a brief description of the depot's intended use or the course it supports to help users understand its role.
	- Retain the default settings for all other stream depot creation properties.
	- Click 'OK' to create the depot.
		<img src="https://i.postimg.cc/8PNdfNKG/p4admin-depot-new-Create.gif" width="685" height="351" />
- **Confirmation and Setup**: After creating the depot, ensure it's properly configured for the users. This might involve setting up access permissions and stream structures to align with the course or project requirements.


**Creating Your First Stream in P4V**:
- Navigate to the **Streams** tab:
  - This can be accessed through the menu by navigating to `View > Streams` or by using the shortcut `Ctrl + 7` (Windows/Linux) or `Cmd + 7` (macOS).
	  <img src="https://i.postimg.cc/gjqvtT01/p4v-streams-tab.gif" width="545" height="640" />
- Right-click in the window and select ***New Stream...***.
- Select ***Mainline*** as the stream type. This will be your project's main branch (also called the trunk).
- Name your stream (e.g., `main`) and provide a description if needed.
- Click 'OK' to create the stream.
		<img src="https://i.postimg.cc/T3HnsmR2/p4v-streams-new-Create.gif" width="601" height="979" />
- After this, other streams can be created either before or after populating the mainline. The standard stream depot setup includes:
	  **Mainline Stream (`//depot/mainline`)**: The project's backbone for stable code and assets. It's the top-level stream from which others branch off.
	  **Development Stream (`//depot/mainline/dev`)**: For ongoing development like new features and bug fixes, branching directly off the mainline.
	  **Art Asset Integration Stream (`//depot/mainline/dev/art`)**: Specialized for integrating and testing new art assets, it branches off from the development stream.
	  **Build (Release) Stream (`//depot/mainline/build`)**: Focused on preparing the project for release, directly branched from the mainline for easy merging of stable features and assets.
	
		![p4v_ideal_streams_setup.png](/img/user/Drexel%20Perforce/All%20Media/p4v_ideal_streams_setup.png)
		The Streams setup can be confirmed by accessing the ***Stream Graph Tab*** through the menu by navigating to `View > Streams Graph` or by using the shortcut `Alt + 7` (Windows/Linux) or `Opt + 7` (macOS).
---
### Configuring Your Workspace

A workspace is your local copy of files from the depot, where you can work on them before submitting changes back to the server.

### Creating a Workspace
- **Open Workspaces Tab**: In P4V, navigate to `View > Workspaces` or by using the shortcut `Ctrl + 5` (Windows/Linux) or `Cmd + 5` (macOS).
	<img src="https://i.postimg.cc/Y21fShx8/p4v-workspace-tab.gif" width="542" height="578" />
- **Create New Workspace**:
  - Click the 'New Workspace' button to open the dialog box.
  - **Name**: Assign a descriptive name, incorporating your Drexel ID, name or initials and the project or group (e.g., `abc123_GameDev`).
  - **Stream**: Select the previously created stream to link your workspace.
- **Root Directory**: Select a local directory for file storage, managed by P4V. This directory can be on your machine's main drive or an external drive. 

	<img src="https://i.postimg.cc/q7h2HRRs/p4v-workspace-new-Create.gif" width="720" height="966">

  - **External Drive Considerations**: If opting for an external drive, ensure it's an SSD with sufficient read/write speeds. Additionally, configure it according to [Perforce Recommendations](https://portal.perforce.com/s/article/2957) to ensure optimal performance and reliability.

### Populating Your Workspace
- **Switch to Workspace View**: After workspace creation, P4V automatically switches to the 'Workspace' view, provided the relevant checkbox is selected.
- **Get Latest Revision**:
  - To synchronize files from your stream to your local workspace, right-click in the workspace area and select 'Get Latest Revision'.
- **Initial Population**:
  - Should the chosen depot or stream be empty, a warning will appear in the console log, noting that no files have been populated.

For additional guidance on filling depots, initiating projects, and mastering Perforce workflows, refer to [[Drexel Perforce/Getting Started/First Steps in Perforce\|First Steps in Perforce]] for comprehensive insights and instructions.


---