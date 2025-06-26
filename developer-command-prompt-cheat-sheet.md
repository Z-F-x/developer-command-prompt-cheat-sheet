# Developer Command Prompt Cheat Sheet

## Create a new empty file in current directory
```type nul > fileName.txt```

## Output all files of specific extension from current directory and subdirectories (replace *.exe with your file extension).
```dir /s /b *.c```

## Delete file in current directory
```del fileName.txt```

## Directory Operations
```cmd
REM Create a new directory
mkdir NewFolder

REM Remove a directory and everything inside it (use with care)
rd /s /q OldFolder
```

## Copy & Move
```cmd
REM Copy a file
copy source.txt destination.txt

REM Move or rename a file
move source.txt NewFolder\source.txt
```

## Search
```cmd
REM Search for text inside files, recursively and case-insensitive
findstr /s /i "searchTerm" *.c
```

## Batch Processing
```cmd
REM Run a command on every .c file
for /r %f in (*.c) do @echo %~ff
```

## Build & Compile
```cmd
REM Build a Visual Studio solution
msbuild MySolution.sln /m

REM Compile a single C source file with the Microsoft C/C++ compiler
cl /EHsc source.c
```

## Environment Helpers
```cmd
REM List all environment variables (handy to see VS variables)
set

REM Show full path to an executable found in PATH
where cl
```

## Quick Help
```cmd
REM Get syntax help for any command
<command> /?

REM Example
rd /?
```
