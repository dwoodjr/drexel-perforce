---
{"dg-publish":true,"permalink":"/drexel-perforce/tutorials-and-examples/p4-admin-bulk-add/"}
---

# Integration of the Bulk Add Tool into P4 Admin

In situations where the Bulk Add or Bulk Project Creator Tool is absent from P4 Admin, it is necessary to engage a Perforce administrator for its inclusion. Alternatively, if possessing the role of a P4 Admin Super User, the tool can be integrated by adhering to the installation instructions detailed in the repository found [here](https://github.com/vertigojc/p4_bulk_project_creator).

**Installation Steps:**
1. **Repository Cloning:** Initiate by cloning the tool's repository to a local directory.
2. **Tool Creation in P4 Admin:**
   - Navigate to `Tools > Manage Tools > Custom Tools...` after logging into P4 Admin with super user credentials.
3. **Tool Registration:**
   - Within the Custom Tools window, opt for `New > Tool...`.
4. **Tool Configuration:**
   - In the ensuing Add Local Tool window, provide the necessary details for:
     - **Name:** Assign a name to the tool.
     - **Application:** Specify the path to the tool's executable file (.exe).
     - **Start In:** Designate the path where the tool's configuration file (.ini) resides.
     - Ensure the option `Refresh Helix Admin upon completion` is selected.
5. **Finalization:**
   - Confirm the settings by clicking `OK`, followed by applying the changes across all dialogue windows.

# Preparing the Project Details CSV

The Bulk Add Tool requires a CSV (comma delimited) file for parsing new users, groups, and depots. This file must adhere to a specific format to facilitate the creation of all new project components. An example CSV can be found here: [good_example_list.xlsx](https://1drv.ms/x/s!AqQzGx8l4o2wk-U7Mr4SqcDrzKJSuQ?e=jYTQVq)
- ### Components Explained
	- **Name**: The student's full name.
	- **Drexel ID/Email**: The student's Drexel email, typically in the format `abc123@drexel.edu`.
	- **Group Name**: A unique identifier for the student group, formatted as `Year_Quarter_ProjectType_GroupName`. Project types are categorized as either Unity (`N_`) or Unreal (`R_`).
	- **Owner**: Indicates the group depot owner. Mark one student (ideally the project lead or lead developer) as the Owner with `TRUE`. This student will have administrative responsibilities for the group's depot. 
		- If a Student is not an owner, leave the cell blank. 
		- It is a good idea to place the Owner as the *first* group member.

| Name         | E-mail                 | Group_Name       | Owner |
| ------------ | ---------------------- | ---------------- | ----- |
| John Doe     | jdoe123@drexel.edu     | 2024_FA_N_GroupA | TRUE  |
| Jane Smith   | jsmith456@drexel.edu   | 2024_FA_N_GroupA |       |
| Mike Brown   | mbrown789@drexel.edu   | 2024_FA_R_GroupB | TRUE  |
| Alex Johnson | ajohnson012@drexel.edu | 2024_FA_R_GroupB |       |

# Utilizing the Bulk Add Tool in P4 Admin

For Super Users within P4 Admin, the Bulk Add Tool facilitates the mass creation of users, groups, and depots across numerous projects efficiently.

### Execution Instructions:

1. **Initiation:**
   - Access the tool via `Tools > Bulk Add` from the main menu.

![](https://i.imgur.com/hWP4MMr.png)


2. **CSV Importation:**
   - Utilize the `Load CSV file...` option to locate and upload the CSV file containing project details.
     - Post-upload, the interface displays a list of users including their Name, Email, Group, and Owner Status.
3. **Template Selection:**
   - Choose a template project for depot setup, typically `Template_Unity` or `Template_Unreal`.
     - *Note:* These templates correspond to Streams Depot Templates.
4. **Navigation to Creation Page:**
   - Click on `Go to Creation Page` to proceed.

![](https://i.imgur.com/Wk7aCUa.png)

5. **Project Creation:**
   - The Creation Page provides details on output paths/locations for commands and log files, along with a count of Users to be created and available server seats. Follow the sequence to execute tasks by clicking the corresponding buttons:
     1. `Users` - Initiates user creation.
     2. `Groups` - Begins group formation.
     3. `Permissions` - Assigns appropriate permissions.
     4. `Depots` - Starts depot creation.
     5. `Populating Depots` - Fills depots with necessary data.

![](https://i.imgur.com/ZvrtoKN.png)

6. **Completion:**
   - Upon successful execution of all tasks, close the tool. Refresh P4 Admin to view the newly added users, groups, and depots.

#  Passwords

By default, the initial password for all users will be `ChangeMe123!`. New users will be required to **reset** their password on first login.

If a new default password is desired, the `config.ini` can be changed to update the default passwords.
```JSON
[DEFAULT]
EMAIL_DOMAIN = myuniversity.edu
DEFAULT_PASSWORD = myUniversitySecret#45
REQUIRE_PASSWORD_RESET = false
```

---
Link to Bulk Add GitHub Repo: https://github.com/vertigojc/p4_bulk_project_creator
