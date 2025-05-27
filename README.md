## Tools Needed
1. [VSCode][1]
1. [git][2]

### Installing VSCode
1. Download [VSCode][1] windows .zip version 
![](img\vscode-zip.png)
1. Extract to c:\sw\code
1. Add c:\sw\code\bin to [path](#adding-to-path)

### Installing Git

1. Download [git][2] portable
![](img\git-portable.png)
1. Extract to C:\sw\PortableGit
1. Add C:\sw\PortableGit and C:\sw\PortableGit\bin to [path](#adding-to-path)
1. configure git in VS Code

### Configure git in VSCode
`file->prefernce->setting or ctrl + ,`

1. keyin git.path
2. Click Edit in settings.json  
![git.path][3] ![settings.json][4]

`"git.path": "C:\\sw\\PortableGit\\bin\\git.exe"`

3. save and re-open git
> User manager for login on 1st use


### Adding to path
> Using CMD, keyin
```bash
rundll32 sysdm.cpl,EditEnvironmentVariables
```
> Add these entries
```
C:\sw\PortableGit
C:\sw\PortableGit\bin
C:\sw\code\bin
```
[1]:https://code.visualstudio.com/download
[2]:https://git-scm.com/downloads/win
[3]:img/vsc-git-path.png
[4]:img/vsc-git-path-save.png
