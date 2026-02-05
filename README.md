# 2FA Einrichtungshilfe - Deployment

Dieses Repository enthält die gepackte Edge-Erweiterung für die Unternehmensverteilung.

## Dateien

| Datei | Beschreibung |
|-------|-------------|
| `2fa-guide.crx` | Gepackte Extension (automatisch generiert) |
| `updates.xml` | Update-Manifest für Edge-Policy |
| `extension-id.txt` | Extension-ID als Referenz |

## Installation auf Zielrechnern

Die Extension wird per Registry-Policy force-installiert. Folgenden Schlüssel setzen (als Administrator):

```
HKLM:\SOFTWARE\Policies\Microsoft\Edge\ExtensionInstallForcelist
```

Neuer Wert (String):
```
<Extension-ID>;<Update-URL>
```

Beispiel:
```
kjglglbcjfigdjkckcfpdaeilodhhdlp;https://raw.githubusercontent.com/Zuescho/regioit-2fa-guide-extension-publish/main/updates.xml
```

Nach einem Neustart von Edge wird die Extension automatisch installiert (Enterprise Policy, Benutzer kann sie nicht entfernen).

## Updates

Wenn eine neue Version in dieses Repository gepusht wird, erkennt Edge das Update automatisch über `updates.xml` und installiert die neue CRX-Datei.

## Deinstallation

Den Registry-Eintrag unter `ExtensionInstallForcelist` entfernen und Edge neu starten.
