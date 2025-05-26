### VSCode Global Settings
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

```
`.vscode/launch.json`
```json

```
```
HKEY_CURRENT_USER\Software\Microsoft\Command Processor\DefaultColor
HKEY_LOCAL_MACHINE\Software\Microsoft\Command Processor\DefaultColor
color 0a
@reg add "hkcu\software\microsoft\command processor" /v defaultcolor /t reg_dword /d 0xa /f
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Console\TrueTypeFont\
Name: 00
Data: Consolas

reg query "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Console\TrueTypeFont"
reg query "HKEY_LOCAL_MACHINE\Software\Microsoft\Command Processor" /v DefaultColor

reg query "HKEY_CURRENT_USER\Software\Microsoft\Command Processorr" /v DefaultColor
reg query HKLM\Software\Microsoft\ResKit /v Version

```


