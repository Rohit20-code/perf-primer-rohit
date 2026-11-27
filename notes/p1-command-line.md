# P1.2 - Command Line Essentials (PowerShell & CMD)

Notes from practicing basic command line usage in PowerShell and CMD.

---

## Commands Practiced

- `pwd` (PowerShell) / `cd` (CMD): Displays the current working directory.
- `dir` / `ls`: Lists files and folders in the current directory.
- `cd <folder>`: Changes into a directory (`cd ..` to move one folder backwards).
- `mkdir <folder>`: Creates a new folder.
- `New-Item <file> -ItemType File`: Creates a new empty file in PowerShell.
- `copy <file> <destination>` / `Copy-Item`: Copies a file to another location or name.
- `move <file> <destination>` / `Move-Item`: Moves or renames a file.
- `del <file>` / `Remove-Item`: Deletes a file.
- `type <file>` (CMD) / `cat <file>` (PowerShell): Displays the contents of a file in the terminal.
- `Get-Content <file>`: Displays file contents in PowerShell.

---

## Environment Variables and PATH

Environment variables store configuration information that applications and processes can access.

Setting and checking environment variables:

**In PowerShell:**
```powershell
$env:GREETING = "hello"
echo $env:GREETING
```

**In CMD:**
```cmd
set GREETING=hello
echo %GREETING%
```

### What PATH Does

`PATH` is an environment variable containing a list of folder locations that Windows searches when a user runs a command without specifying its full path.

If an executable is not available in the directories listed in PATH, Windows may not recognise the command.

**Checking PATH in PowerShell:**
```powershell
$env:PATH
```

**Checking PATH in CMD:**
```cmd
echo %PATH%
```

**Checking whether a command is available:**
```powershell
Get-Command jmeter
```

**Temporarily adding a directory to PATH in PowerShell:**
```powershell
$env:PATH += ";C:\Tools\apache-jmeter\bin"
```

This change applies only to the current PowerShell session and its child processes.

---

## Programs, Flags, and Signals

- `python --version`: Displays the installed Python version.
- `git --help`: Displays Git help information and available commands.
- `java -version`: Displays the installed Java version.
- `node --version`: Displays the installed Node.js version.
- `npm --version`: Displays the installed npm version.
- `python hello.py`: Executes a Python script using the Python interpreter.

### Arguments and Flags

- Arguments provide information or files to a program.
- Flags or options modify how a program behaves or specify an action.
- Example: In `python hello.py`, `hello.py` is an argument.
- Example: In `python --version`, `--version` is an option.

### Stopping a Running Program

`Ctrl + C`: Sends an interrupt signal to stop a running program, script or development server in the terminal.

---

## Redirecting Output to a File

**Command:**
```powershell
dir > files.txt 2>&1
```

- `>` redirects standard output (stdout) to `files.txt`.
- `2>&1` redirects standard error (stderr) to the same destination as standard output.
- Both normal output and error messages are saved in `files.txt`.

### Other Redirection Operators

- `>`: Creates or overwrites a file with redirected output.
- `>>`: Appends redirected output to an existing file.

Example:
```powershell
"New entry" >> files.txt
```

---

## Running Two Terminals Side by Side

Having two terminal windows open simultaneously is useful for development and performance testing.

- **Terminal 1:** Runs the backend server or application using commands such as `npm run dev`. It keeps the application running and displays live logs and errors.
- **Terminal 2:** Runs the testing tool, such as JMeter or curl commands, to generate requests against the running application.

This allows the application and testing process to run independently without stopping either terminal.

---

## Self-Check

**Question:** You type `jmeter` in the terminal and get the error `'jmeter' is not recognized`. What two things do you check?

1. Check whether Apache JMeter is installed correctly and locate its installation directory. Verify that `jmeter.bat` exists inside the `bin` folder.
2. Check whether the JMeter `bin` directory is added to the Windows `PATH` environment variable. If PATH was recently modified, open a new terminal so that it loads the updated environment.

Additionally, verify that Java is installed and configured correctly, as Apache JMeter requires Java to run.

---

**End of P1.2 - Command Line Essentials**