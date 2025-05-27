### Detailed Steps - Choose either one
**1. Using the dotnet-install script:**
- You can use the [dotnet-install script][1] to install the .NET SDK, which includes the .NET CLI and the shared runtime. 
- The script is available for both [Windows][1w] and [Linux/macOS][1l]. 
For Windows, you can use a PowerShell script. 
- Refer to the official documentation for specific installation instructions for your chosen script. 

**2. Downloading binaries:**
- Download the .NET SDK or Runtime binaries from the [Microsoft website][2]. 
  - [Windows Version][2w]
- Unzip the contents of the downloaded archive into a folder of your choice. 
- You will need to run the commands from within that folder.

**3. Using Windows Package Manager (winget):**
Open a Command Prompt or PowerShell window. 
- Run the following command to install .NET with winget: 
  ```bash
  winget install --id Microsoft.DotNet.Sdk --source online
  ```
- This method installs .NET as a user-level application, not requiring admin privileges. 


[1]:https://learn.microsoft.com/en-us/dotnet/core/tools/dotnet-install-script
[1w]:https://dot.net/v1/dotnet-install.ps1
[1l]:https://dot.net/v1/dotnet-install.sh

[2x]:https://learn.microsoft.com/en-us/dotnet/core/install/windows
[2]:https://dotnet.microsoft.com/en-us/download/dotnet
[2w]:https://dotnet.microsoft.com/en-us/download/dotnet/thank-you/sdk-8.0.410-windows-x64-binaries
