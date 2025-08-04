# 🖥️ IT-Refresh PowerShell App
# 📌 Summary
This PowerShell-based GUI application serves as a centralized control hub for the IT Refresh team. It provides a single interface to organize, manage, and execute daily-use PowerShell scripts. In addition to script management, the application includes integration with a knowledge base (via SharePoint-exported Excel tables) and will support basic user account handling for permission-restricted features.

Whether you're retiring machines, imaging systems, or referencing data from ServiceNow, this app aims to be your daily dashboard for getting it all done.

# 📁 Project Structure (Planned)
IT-Refresh-PowerShell-App/
│
├── /UI/                  # Forms and layout for the GUI (Windows Forms)
├── /Scripts/             # Folder where user-added scripts can be stored
├── /Backend/             # Script runner, input handler, and logic controller
├── /Data/                # Excel or table-based reference data (from SharePoint or ServiceNow)
├── /Accounts/            # Optional: Config or credential store for user logins
├── /Config/              # JSON files to store user script paths and GUI bindings
└── Main.ps1              # Entry point that launches the GUI
# 🚀 Features
📂 Dynamic Script Management
Add PowerShell scripts to the GUI on the fly by selecting a path and defining required input types (e.g., TextBox, ComboBox). These are saved in a config file and persist between sessions.

📚 Knowledge Base Integration
Import and manipulate Excel files (exported from SharePoint/ServiceNow) to track devices, tickets, or workflows.

🔐 User Role & Credential Handling
(Planned) Optional Windows-authenticated or local account system to store admin credentials for elevated tasks or permission-restricted tools.

🔍 Search & Filter
Powerful filtering and searching of the imported knowledge base, especially for tasks like device lookup or record validation.

# ⚙️ Technologies Used
Windows.Forms (for GUI)

ImportExcel (for handling Excel files) — Optional

ConvertFrom-Json / ConvertTo-Json (for script storage and config)

Start-Process (for script execution)

Get-Credential, New-Object System.Security.SecureString (for account management)

SharePoint (manual Excel export)

# 🧠 In Depth: Modules
Module	Description
UI	Windows Form GUI with dynamic tab/page creation for each script
Backend	Script runner, argument parser, account manager, JSON handlers
Scripts	Folder or registry for user-added scripts, dynamically loaded
Data	SharePoint/ServiceNow Excel table import, parsing, and filtering
Accounts	(Optional) Local or Windows-user credential binding
Config	JSON-based config file storing script metadata and GUI input mappings

# ✅ Prerequisites
PowerShell 5.1+

Access to SharePoint (for exporting Excel data)

Administrator privileges (for some script execution)

# 🔧 Setup
Clone or download the repository.

Open Main.ps1 in PowerShell ISE or VS Code.

Run the script:

Set-ExecutionPolicy Bypass -Scope Process
.\Main.ps1
Begin adding scripts via the GUI or by editing the JSON config.

# 🔧 How to Add a Script
Click "Add New Script" in the GUI.

Provide:

Path to the script

Inputs needed (text fields, dropdowns, checkboxes, etc.)

Optional admin requirement flag

Script metadata will be stored in config/scripts.json.

A new page will be generated in the GUI with proper input fields.

# ❓ Help / FAQ
Q: Can I run scripts that require elevation?
A: Yes — you’ll be prompted for credentials if needed. In the future, admin credentials may be securely stored per user.

Q: Can I edit my Excel data in the GUI?
A: Yes. Once imported, the app will let you search, filter, and even edit data in a temporary grid.

Q: Will this work without Excel installed?
A: Yes. As long as you export Excel data from SharePoint and use PowerShell to parse it (using ImportExcel or CSV fallback), no full Excel install is needed.

Q: Can I use this from the shared drive?
A: That’s the plan. Just launch Main.ps1 from the drive with appropriate permissions.

# 🧭 Future Roadmap
 JSON-based export/import for script configs

 Windows account binding and secure credential vault

 Drag-and-drop script loader

 Searchable script library

 GUI settings config (color theme, font size, etc.)

 Optional .exe packaging using PS2EXE

# 👥 Credits & Contributions
Developed by and Maintained by: Riley Thompson
Open to collaboration — feel free to fork and build!
