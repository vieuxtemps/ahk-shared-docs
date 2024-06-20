
# Shared AHK Documentation

This is the shared documentation page for all my AutoHotkey projects.

# Automatically running at startup (normal user privileges)

If you wish an application to run automatically at startup:

- Open the `Run` command window: Press `Win+R`, or type `Run` in the start menu
- Run `shell:startup`
- Create a shortcut there (for either the `.ahk` or `.exe` files)

# Automatically running at startup (elevated/administrator user privileges)

Some applications running with elevated privileges will completely ignore external input when being sent from an application being run with normal privileges. Examples: Task Manager, System settings and other System tools.

If you wish an application to run automatically at startup with elevated/administrator user privileges:

## Manually creating a task

- Open `Task Scheduler` by typing it in the start menu.
- Click `Task Scheduler Library`.
- Click `Create Task`.
- Tick `Run with highest privileges`.
- Triggers: `New` -> `Begin the task: at Startup`.
- Actions: `New` -> Choose program path (`.ahk` or `.exe`) and startup directory.

## Automatically creating a task

- Open the Command Prompt with administrator privileges.
- Modify `schtasks /create /tn "MyTaskName" /sc onlogon /tr "C:\Users\%USERNAME%\Documents\example.exe" /ru %USERNAME% /rl HIGHEST` with your custom application path and task name.
- Run it to create the task.

# Security and false positive issues

AutoHotkey has had issues for many years with multiple antivirus vendors, and will inevitably get flagged by some of them.

You can learn more about this on the official AutoHotkey discussion boards:

https://www.autohotkey.com/boards/viewtopic.php?f=17&t=62266

Some of the current AV vendors currently flagging AutoHotkey-compiled projects (independent of their content) are:

- Jiangmin, Bkav Pro, Cynet, Zillya

All my recent releases are compiled/bundled with AutoHotkey v1.1.37.01 (source: [GitHub](https://github.com/AutoHotkey/AutoHotkey/releases/tag/v1.1.37.01)), with the following SHA256 hashes:

- `AutoHotkey_1.1.37.01_setup.exe`: dbf3490648efe876bd9a98d53e4d9110bf5e02a3914c0dd4b2a48db4a09799b5
- `AutoHotkeyU64.exe`: 7d47220e8a09c113b82ba9f366ce2cbe5924b0cc661dc9df93c13e8dbfa1f254 
- `Ahk2Exe.exe`: (v1.1.37.01c) 73f4f00871ef2fd26c4592b0d921fcf682147b9062bffcf1279b1656260af2b4
