# 2FA Guide Extension - Deployment Package

This repository contains the packed Edge extension for enterprise deployment.

## Files

| File | Description |
|------|-------------|
| `2fa-guide.crx` | Packed extension (auto-generated) |
| `updates.xml` | Update manifest for Edge policy |
| `extension-id.txt` | Extension ID reference |
| `Deploy-2FAExtension.ps1` | PowerShell deployment script |

## Deploy via PowerShell (SCCM/GPO)

```powershell
.\Deploy-2FAExtension.ps1 -ExtensionId "<id from extension-id.txt>" -UpdateUrl "https://raw.githubusercontent.com/OWNER/regioit-2fa-guide-extension-publish/main/updates.xml"
```

This sets an Edge enterprise policy to force-install the extension. Requires admin privileges.

## Uninstall

```powershell
.\Deploy-2FAExtension.ps1 -ExtensionId "<id>" -Uninstall
```

## How Updates Work

When a new version is pushed to this repository, Edge will automatically detect the update via `updates.xml` and install the new CRX.
