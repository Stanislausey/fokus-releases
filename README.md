# Fokus für Windows

Fokus ist ein einfacher Seitenblocker für Windows 11. Gesperrte Domains landen
in der hosts-Datei, das Entsperren ist bewusst umständlich (60 Sekunden Undo,
danach bleibt die Sperre). Ein Werkzeug zur Selbstbindung gegen Ablenkung.

## Download

Die neueste Version liegt unter [Releases](../../releases/latest).

- **Fokus-Setup-x64.exe** für normale Windows-PCs (Intel oder AMD, 64 Bit).

## Installation

1. Installer herunterladen.
2. Beim ersten Start zeigt Windows „Der Computer wurde durch Windows geschützt"
   mit „Unbekannter Herausgeber". Das ist **kein Virus**, sondern normal bei
   privaten, nicht signierten Apps. Auf „Weitere Informationen" und dann
   „Trotzdem ausführen" klicken.
3. Der Installer fragt nach Adminrechten und richtet Dienst und Tray-App ein.

Optional die Datei vor dem Start prüfen (PowerShell), die Prüfsumme steht bei
jedem Release:

```powershell
Get-FileHash .\Fokus-Setup-x64.exe -Algorithm SHA256
```

## Deinstallation

Über „Apps und Features" wie jedes andere Programm. Wichtig: die von Fokus
gesetzten Sperren in `C:\Windows\System32\drivers\etc\hosts` bleiben
**absichtlich bestehen**, auch nach der Deinstallation. Genau das ist der Sinn
der App. Wer sie doch entfernen will, bearbeitet die hosts-Datei manuell.

## Hinweise

Privates Projekt, unsigniert, ohne Gewähr. Der Quellcode ist nicht öffentlich;
hier liegen nur die fertigen Installer.
