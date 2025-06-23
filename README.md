# AIT Installer Build Instructions
## Using WiX Toolset

This project uses the WiX Toolset to create Windows installation packages. WiX provides a powerful set of tools for building Windows Installer (.msi) packages from XML source code. For more information and documentation on how to use WiX, visit the [WiX Toolset Documentation](https://docs.firegiant.com/wix/).

## Requirements

To create your first installation package with the WiX Toolset, you only need a text editor and the [.NET SDK](https://dotnet.microsoft.com/en-us/download). If you have Visual Studio 2022, you have both.

## Build Commands

Set the environment and build for each configuration. Run commands in PowerShell.

### CI Environment

```powershell
$env:EnvironmentName = "CI"
dotnet build -p:TargetName="AIT CI installer" --no-incremental
```

### Demo Environment

```powershell
$env:EnvironmentName = "Demo"
dotnet build -p:TargetName="AIT Demo installer" --no-incremental
```

### Qed Environment

```powershell
$env:EnvironmentName = "Qed"
dotnet build -p:TargetName="AIT Qed installer" --no-incremental
```

### Prod Environment

Build with default settings:

```powershell
Remove-Item Env:EnvironmentName
dotnet build --no-incremental
```