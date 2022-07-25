# Developer Tools (winget)

This article lists all tools installed on my machine, using [WinGet](https://github.com/microsoft/winget-cli) to simplify the installation.

## 👉 Prerequisites

  1. To install or update WinGet, go to the **Microsoft Store** 
     and install or update the [App Installer](https://www.microsoft.com/store/productId/9NBLGGH4NNS1).
     
  2. To authorize installations from the Microsoft Store, you must be logged in (with a personal email address).
  
  3. Open a **Windows Terminal** and run `winget` command to display the documentation.

## 👉 Windows and Developer Tools

Run these lines one by one.

```
winget install 7zip.7zip
winget install DeepL.DeepL
winget install Elgato.StreamDeck
winget install Git.Git
winget install GitHub.GitHubDesktop
winget install Microsoft.AzureCLI
winget install Microsoft.AzureDataStudio
winget install Microsoft.dotNetFramework
winget install Microsoft.DotNet.SDK.6
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

## 👉 Windows Configurations

### Windows 11 Explorer - Classic Contextual Menu

1. Open the Registry Editor and go to `Computer\HKEY_CURRENT_USER\SOFTWARE\CLASSES\CLSID\`.
2. Add this new key:`{86ca1aa0-34aa-4e8b-a509-50c905bae2a2}`.
3. Add this new sub-key: `InprocServer32`.
4. Open the value `(Default)` and click on OK (without value data).
4. Logoff / login your session.

> You can run copy this content in a **.reg** file and execute it.
> And next, logoff / login your session.
> ```
> Windows Registry Editor Version 5.00
> [HKEY_CURRENT_USER\Software\Classes\CLSID\{86ca1aa0-34aa-4e8b-a509-50c905bae2a2}]
> @=""
> [HKEY_CURRENT_USER\Software\Classes\CLSID\{86ca1aa0-34aa-4e8b-a509-50c905bae2a2}\InprocServer32]
> @=""
> ``` 

### Use Sounds when build failed

1. Open the **Sound** dialog box running this command line: `control mmsys.cpl sounds`
2. Go to the Sounds tab and collapse the Windows events in the list to display the **Microsoft Visual Studio** events.
3. Set these sounds:
    - Build failed: `Windows Critical Stop.wav`
    - Build Succeeded: `Windows Exclamation.wav`
    - Test Run failed: `Windows Critical Stop.wav`
    - Test Run Succeeded: `Windows Exclamation.wav`
    
## 👉 Visual Studio Extensions

- [Output enhancer](https://github.com/MykolaBalakin/VSOutputEnhancer)
- [Open Command Line](https://github.com/madskristensen/OpenCommandLine)
- [File Differ](https://github.com/madskristensen/FileDiffer)
- [Add Any File](https://github.com/madskristensen/AddAnyFile)
- Download the [JetBrains Mono font](https://www.jetbrains.com/lp/mono/), install TTF files (right-click + Install) and, in Visual Studio, open Tools / Options / Fonts and Colors and select **Jetbrains Mono Medium** in the font list.

## 👉 VSCode Extensions

- [Visual Studio Keymap](https://marketplace.visualstudio.com/items?itemName=ms-vscode.vs-keybindings)
- [C#](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp)
- [MongoDB for VSCode](https://marketplace.visualstudio.com/items?itemName=mongodb.mongodb-vscode)
- [REST Client](https://marketplace.visualstudio.com/items?itemName=humao.rest-client)
- [Sql Server](https://marketplace.visualstudio.com/items?itemName=ms-mssql.mssql)
- [VSCode Icons](https://marketplace.visualstudio.com/items?itemName=vscode-icons-team.vscode-icons)
- [XML Tools](https://marketplace.visualstudio.com/items?itemName=DotJoshJohnson.xml)
- **JetBrains Mono Font** 
   1. Download the [font](https://www.jetbrains.com/lp/mono/).
   2. Extract the ZIP file, and install the TTF Files (right-click + Install).
   3. Set Jetbrain Mono Font in Visual Studio Code:
      ```json
      "editor.fontFamily": "'JetBrains Mono', Consolas, 'Courier New', monospace",
      "editor.fontLigatures": true,
      "editor.fontWeight": "bold"
      ```

## 👉 Windows Terminal - GIT colorized

To configure the Windows Terminal with colorization of GIT, all details are [here](https://docs.microsoft.com/windows/terminal/tutorials/custom-prompt-setup).

1. Install a Nerd Font
   - Download the [Caskaydia Cove Nerd Font](https://github.com/ryanoasis/nerd-fonts/releases/download/v2.1.0/CascadiaCode.zip).
     Extract the ZIP file and install the fonts (right-click / install).
   - Open **the Windows Terminal**, go to the Settings / Windows Powershell profile and set
      - The **Starting directory** to **Use parent process directory**
      - The **Font face** to **Caskaydia Nerd Font**
3. Install Oh My Posh for PowerShell: `winget install JanDeDobbeleer.OhMyPosh`
4. Choose and apply a PowerShell prompt theme
   - Open you profile file: 
     `notepad C:\Users\<USER_NAME>\Documents\WindowsPowerShell\profile.ps1`
   - Add the following to the end of your PowerShell profile file to set the [paradox theme](https://ohmyposh.dev/docs/themes)
     `oh-my-posh --init --shell pwsh --config "C:\Users\<USER_NAME>\AppData\Local\Programs\oh-my-posh\themes\amro.omp.json" | Invoke-Expression`
   - Allow to execute this script
     `Set-ExecutionPolicy -ExecutionPolicy Unrestricted -Scope CurrentUser`
> If the starting time of a Powershell Session is very slow, you can add this file to your anti-virus exclusion list.
> `C:\Users\<USER_NAME>\AppData\Local\Programs\oh-my-posh\bin\oh-my-posh.exe`

To configure the Windows Terminal features, add or update these parameters in **settings.json* file.
```json
{
  "confirmCloseAllTabs": false,
  "centerOnLaunch": true,  
}
```

## 👉 SQL Server Local DB

LocalDB is a feature you select during SQL Server Express installation, and is available when you download the media.

0. Check if you installed .NET Framework 4.8: `winget install Microsoft.dotNetFramework`.
1. Start the setup [SQL Server Express](https://docs.microsoft.com/en-us/sql/database-engine/configure-windows/sql-server-express-localdb).
2. Select **Download Media** and choose **LocalDB** (~55 MB).
3. Start `SqlLocalDB.msi` file.
4. Create an instance MyServer using this command: `SqlLocalDb create MyServer`.
5. Open VSCode and the **SQL Server (mssql)**.

