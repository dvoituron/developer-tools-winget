# Developer Tools (winget)

This article lists all tools installed on my machine, using [WinGet](https://github.com/microsoft/winget-cli) to simplify the installation.

## Prerequisites

  1. To install or update WinGet, go to the **Microsoft Store** 
     and install or update the [App Installer](https://www.microsoft.com/store/productId/9NBLGGH4NNS1).
     
  2. To authorize installations from the Microsoft Store, you must be logged in (with a personal email address).
  
  3. Open a **Windows Terminal** and run `winget` command to display the documentation.

## Windows Tools

Run these lines one by one.

```
winget install 7zip.7zip
winget install DeepL.DeepL
winget install Elgato.StreamDeck
winget install Git.Git
winget install GitHub.GitHubDesktop
winget install Microsoft.AzureCLI
winget install Microsoft.AzureDataStudio
winget install Microsoft.Edge.Dev
winget install Microsoft.PowerToys
winget install Microsoft.VisualStudioCode
winget install Notepad++.Notepad++
winget install OpenJS.NodeJS
winget install SlackTechnologies.Slack
winget install 9WZDNCRDMDM3                  -- NuGet Package Explorer
winget install 9NBHCS1LX4R0                  -- Paint.Net (Paid)
winget install 9WZDNCRF0083                  -- Facebook Messenger
```

## Windows Configurations

### Windows 11 Explorer - Classic Contextual Menu

1. Open the Registry Editor and go to `Computer\HKEY_CURRENT_USER\SOFTWARE\CLASSES\CLSID\`.
2. Add this new key:`{86ca1aa0-34aa-4e8b-a509-50c905bae2a2}`.
3. Add this new sub-key: `InprocServer32`.
4. Open the value `(Default)` and click on OK (without value data).
4. Logoff / login your session.

### Use Sounds when build failed

1. Open the **Sound** dialog box running this command line: `control mmsys.cpl sounds`
2. Go to the Sounds tab and collapse the Windows events in the list to display the **Microsoft Visual Studio** events.
3. Set these sounds:
    - Build failed: `Windows Critical Stop.wav`
    - Build Succeeded: `Windows Exclamation.wav`
    - Test Run failed: `Windows Critical Stop.wav`
    - Test Run Succeeded: `Windows Exclamation.wav`
    
## Visual Studio Extensions

- [Output enhancer](https://github.com/MykolaBalakin/VSOutputEnhancer)
- [Open Command Line](https://github.com/madskristensen/OpenCommandLine)
- [File Differ](https://github.com/madskristensen/FileDiffer)
- [Add Any File](https://github.com/madskristensen/AddAnyFile)

## VSCode Extensions

- [Visual Studio Keymap](https://marketplace.visualstudio.com/items?itemName=ms-vscode.vs-keybindings)
- [C#](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp)
- [MongoDB for VSCode](https://marketplace.visualstudio.com/items?itemName=mongodb.mongodb-vscode)
- [REST Client](https://marketplace.visualstudio.com/items?itemName=humao.rest-client)
- [Sql Server](https://marketplace.visualstudio.com/items?itemName=ms-mssql.mssql)
- [VSCode Icons](https://marketplace.visualstudio.com/items?itemName=vscode-icons-team.vscode-icons)
- [XML Tools](https://marketplace.visualstudio.com/items?itemName=DotJoshJohnson.xml)
