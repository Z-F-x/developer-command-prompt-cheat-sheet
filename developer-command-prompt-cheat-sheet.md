# Developer Command Prompt

## Create a new empty file in current directory

```cmd
type nul > fileName.txt
```

## Output all files of specific extension from current directory and subdirectories (replace \*.exe with your file extension).

```cmd
dir /s /b *.c
```

## Delete file in current directory

```cmd
del fileName.txt
```

## Delete a folder and all it's content

```cmd
rd /s /q folderName
```

or

```cmd
rmdir /s /q folderName
```

Note: `"C:\path\to\folderName"` works also.

## Directory Operations

Create a new directory

```cmd
mkdir NewFolder
```

Remove a directory and everything inside it (use with care)

```cmd
rd /s /q OldFolder
```

## Copy & Move

Copy a file

```cmd
copy source.txt destination.txt
```

Move or rename a file

```cmd
move source.txt NewFolder\source.txt
```

Copy a folder with it's content
```cmd
Xcopy C:\source D:\source /E /H /C /I
```
Note:
`/E` – Copies all subdirectories, including any that are empty. 
`/H` – Copies hidden and system files as well. 
`/C` – Continues copying even if errors occur. 
`/I` – Treats the destination as a directory if it’s unclear. 

## Search for specific file type in current folder recursively (checking every subfolder in current folder).

```cmd
dir /S /B *.ext
```

## Search

Search for text inside files, recursively and case-insensitive

```cmd
findstr /s /i "searchTerm" *.c
```

## Batch Processing

Run a command on every .c file

```cmd
for /r %f in (*.c) do @echo %~ff
```

## Build & Compile

Build a Visual Studio solution

```cmd
msbuild MySolution.sln /m
```

Compile a single C source file with the Microsoft C/C++ compiler

```cmd
cl /EHsc source.c
```

## Environment Helpers

List all environment variables (handy to see VS variables)

```cmd
set
```

Show full path to an executable found in PATH

```cmd
where cl
```

## rd

`rd /?` (or the synonym `rmdir /?`) tells **cmd.exe** to print the built-in help for the **remove-directory** command. You’ll see usage syntax and the available switches—most notably:

```
RD [/S] [/Q] <folder>

  /S  Removes all files and subfolders (recursive delete).
  /Q  Quiet mode—no “Are you sure?” prompt.
```

# Developer Command Prompt Cheat Sheet

Note on `REM`:

```cmd
REM This line is just a comment
copy source.txt destination.txt  REM still a comment after the command
```

So that little `/ ?` suffix is a handy way to get on-demand documentation for almost any Command-Prompt command.
The preceding `REM Example` line is just a comment explaining that the line below is an example of using the `/ ?` help trick.

## Quick Help

Get syntax help for any command

```cmd
<command> /?
```

## Navigation

Navigate to root directory of current drive

```cmd
cd \
```

## Syntax to run a PowerShell script from cmd`

```cmd
powershell -ExecutionPolicy Bypass -File "path\to\your-script.ps1"
```

**Note:** `-ExecutionPolicy Bypass:`
This flag allows the script to run even if your system has restricted execution policies (common on corporate machines). It does not permanently change system settings.
