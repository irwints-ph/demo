### Installing VSCode
1. Download [VSCode][1] windows .zip version 
  ![](img\vscode-zip.png)
1. Extract to c:\sw\code
1. Add c:\sw\code\bin to [path](#adding-to-path)

### Installing Git
1. Download [git][2] portable
  ![](img\git-portable.png)
1. Extract to C:\sw\PortableGit
1. Add C:\sw\PortableGit and C:\sw\PortableGit\bin to [path](#setup-environment-variables)
1. configure git in VS Code

### Configure git in VSCode
`file->prefernce->setting or ctrl + ,`
> or copy the VSCode configuration below
1. keyin git.path
2. Click Edit in settings.json  
  ![git.path][3] 
  ![settings.json][4]

  `"git.path": "C:\\sw\\PortableGit\\bin\\git.exe"`
4. save and re-open git
> User manager for login on 1st use

## VSCode configuration for all projects
`%userprofile%\AppData\Roaming\Code\User\settings.json`
```json
{
  "git.path": "C:\\sw\\PortableGit\\bin\\git.exe",                 //Git Executable Path
  "editor.fontSize": 18,                                           //Editor Font Size
  "terminal.integrated.defaultProfile.windows": "Command Prompt",  //Default Terminal - CMD
  "terminal.integrated.fontSize": 18,                              //Terminal Font Size
  "editor.tabSize": 2,                                             //Default Editor space tab size
  "workbench.colorCustomizations": {                               //Color Customization
    "terminal.foreground" : "#1AFF01",                             //Terminal Text Color
    "terminal.background" : "#000000"                              //Terminal Background Color
  },
  "terminal.integrated.cursorBlinking": true,                      //Terminal Corsor
  "editor.minimap.enabled": false,                                 //Hide Minimap
  "hediet.vscode-drawio.resizeImages": null,                       //Drwa IO Extsion resize image
}
```

## Install VSCode extensions
```bash
code --install-extension humao.rest-client
code --install-extension shd101wyy.markdown-preview-enhanced
code --install-extension ms-python.debugpy
code --install-extension ritwickdey.liveserver
code --list-extensions
```

# Setup environment Variables
```bash
setx PATH "%PATH%;C:\sw\PortableGit;C:\sw\PortableGit\bin;C:\sw\code\bin;"
```

## DOTNET
```bash
setx DOTNETBIN C:\sw\dotnet-sdk-8.0.410-win-x64
setx PATH "%PATH%;%DOTNETBIN%;"
```

## Color and Prompt
```
reg add "HKCU\Software\Microsoft\Command Processor" /v DefaultColor /t REG_DWORD /d 0x0a /f

SETX PROMPT $+$M$_$P$_$$$S
```


## Others

### Open Environment Variable for user
```bash
rundll32 sysdm.cpl,EditEnvironmentVariables
```

### Set Powershell Propmt
```ps
function prompt {
  Write-Host ("PS`n" + $(Get-Location) +"`n$") -NoNewline
  return " "
}
```
### Install NVM
```bash
start chrome https://github.com/coreybutler/nvm-windows/

nvm install 10.15.3
sudo nvm use 10.15.3
npm install -g json-server@0.16.3
npm install -g @angular/cli@7.3.5
```

[1]:https://code.visualstudio.com/download
[2]:https://git-scm.com/downloads/win
[3]:img/vsc-git-path.png
[4]:img/vsc-git-path-save.png
