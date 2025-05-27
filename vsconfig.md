### VSCode Global Settings
`%userprofile%\AppData\Roaming\Code\User\settings.json`
```json
{
  "terminal.integrated.defaultProfile.windows": "Command Prompt",
  "terminal.integrated.fontSize": 18,
  "editor.tabSize": 2,
  "workbench.colorCustomizations": {
      "terminal.foreground" : "#1AFF01",
      "terminal.background" : "#000000"
  },
  "terminal.integrated.cursorBlinking": true,
  "editor.minimap.enabled": false,
}
```

### CMD Propmt
```bash
PROMPT=$+$M$_$P$_$$$S
code --list-extensions
```
`%userprofile%\.vscode\extensions`

### VSCode basic extensions
```bash
code --install-extension humao.rest-client
```
### Python
`Extensions`
```
ms-python.debugpy
ms-python.python
ms-python.vscode-pylance
```
`Debug Settings`
`.vscode/settings.json`
```json
{
  "rest-client.environmentVariables": {
    "$shared": {
      "host": "http://localhost:2000",
      "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiJ1MkBtYWlsLmNvbSIsImV4cCI6MTc0ODMzOTAyM30.pVWY-0TZxxl25RjqlQVmhF6GTP2RniGMboeTUVpfcx0"
    }
  },
  "python.defaultInterpreterPath":"~/.venv/flask/Scripts/python.exe"
}
```
`.vscode/launch.json`
```json
{
  "version": "0.2.0",
  "configurations": [
    {
      "name": "Flask App",
      "type": "debugpy",
      "request": "launch",
      "module": "flask",
      "cwd": "${workspaceFolder}/",
      // args per command separated by space indicated by comma      
      "args": [
        "run",
        "-h",
        "0.0.0.0",
        "-p",
        "2000",
        "--debug"
      ]
    },
    {
      "name": "Refresh Data",
      "type": "debugpy",
      "request": "launch",
      "program": "seeder.py",
      "console": "integratedTerminal"
    }
  ]
}
```
### Disable from Microsoft Store App Installer python and pyhton3
```
Python was not found; run without arguments to install from the Microsoft Store, or disable this shortcut from 
Settings > Apps > Advanced app settings > App execution aliases.
```

### Install [pyenv-win](https://github.com/pyenv-win/pyenv-win)
```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser

Invoke-WebRequest -UseBasicParsing -Uri "https://raw.githubusercontent.com/pyenv-win/pyenv-win/master/pyenv-win/install-pyenv-win.ps1" -OutFile "./install-pyenv-win.ps1"; &"./install-pyenv-win.ps1"
```

```bash
pyenv install 3.13.3
pyenv global 3.13.3
pyenv version
```
### CMD Color
```
reg add "HKCU\Software\Microsoft\Command Processor" /v DefaultColor /t REG_DWORD /d 0x0a /f
setx PROMPT $+$M$_$P$_$$$S
setx PATH "%PATH%;C:\sw\PortableGit;C:\sw\PortableGit\bin;C:\sw\code\bin;"
```
> `Restart CMD`

`Others`
```
color 0a

reg add "HKCU\Control Panel\Desktop" /v LogPixels /t REG_DWORD /d 96 /f
mode con: cols=130 lines=32766

reg query "hkcu\console" /S | more


@reg add "HKEY_CURRENT_USER\Software\Microsoft\Command Processorr" /v defaultcolor /t reg_dword /d 0xa /f

HKEY_CURRENT_USER\Software\Microsoft\Command Processor\DefaultColor
HKEY_LOCAL_MACHINE\Software\Microsoft\Command Processor\DefaultColor

HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Console\TrueTypeFont\
Name: 00
Data: Consolas

reg query "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Console\TrueTypeFont"
reg query "HKEY_LOCAL_MACHINE\Software\Microsoft\Command Processor" /v DefaultColor

reg query "HKEY_CURRENT_USER\Software\Microsoft\Command Processorr" /v DefaultColor
reg query HKLM\Software\Microsoft\ResKit /v Version

```


