# Bash script for creating a folder in the current working directory

- Make batch script for making folders
```
@echo off
setlocal

:: Check if an argument was passed
if "%1"=="" (
    echo Usage: mkfolders [full|retest]
    exit /b 1
)

:: Normalize argument to lowercase for comparison
set "arg=%1"
set "arg=%arg:"=%"  :: remove quotes

if /I "%arg%"=="full" (
    mkdir "Checklist"
    mkdir "Draft Report"
    mkdir "Final Report"
    mkdir "Misc"
    mkdir "POCs"
    mkdir "Issues"
    mkdir "Scan Files"
    dir
    echo.
    echo All folders created for 'full' test.
    exit /b 0
)

if /I "%arg%"=="retest" (
    mkdir "Draft Report"
    mkdir "Final Report"
    mkdir "Misc"
    mkdir "POCs"
    mkdir "Issues"
    mkdir "Scan Files"
    dir
    echo.
    echo All folders created for 'retest'.
    exit /b 0
)

:: If the argument is invalid
echo Invalid argument: %arg%
echo Usage: mkfolders [full|retest]
exit /b 1
```

- Make alias using the below command:
```
doskey mkfolders = "C:\Users\MuraliRaviNarayan\Documents\mkfolders.bat"
```

- Close and open cmd again and run the command "mkfolders"

