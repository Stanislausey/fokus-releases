# Fokus

Fokus ist ein einfacher Seitenblocker für Windows 11 und iOS. Gesperrte Domains landen
in der hosts-Datei, das Entsperren ist bewusst umständlich: nach dem Blocken
bleiben nur 60 Sekunden zum Rückgängigmachen, danach ist die Sperre dauerhaft.
Ein Werkzeug zur Selbstbindung gegen Ablenkung.

![Die Fokus-App mit einer geblockten Seite](docs/app.png)

## Download

Die neueste Version liegt unter **[Releases](../../releases/latest)**.

| Datei | Für wen |
|-------|---------|
| **Fokus-Setup-x64.exe** | Windows-PCs mit Intel oder AMD (64 Bit) |

Für Windows auf ARM gibt es letztmalig bei [v1.0.0](../../releases/tag/v1.0.0)
einen Installer; neuere Versionen erscheinen nur noch für x64.

## Installation in drei Schritten

**1. Installer herunterladen** und doppelklicken.

**2. Windows-Warnung wegklicken.** Beim ersten Start erscheint diese Meldung:

![SmartScreen-Warnung mit Schaltfläche Trotzdem ausführen](docs/smartscreen.png)

Das ist **kein Virus**. Die Meldung kommt nur, weil die App privat und nicht
teuer signiert ist. Auf **„Weitere Informationen"** klicken, dann auf
**„Trotzdem ausführen"**. Danach kommt sie nie wieder.

> Auf einem deutschen Windows heißen die Schaltflächen „Weitere Informationen"
> und „Trotzdem ausführen"; auf Englisch „More info" und „Run anyway".

**3. Adminrechte bestätigen** und den Assistenten durchklicken. Fertig.

![Der Installations-Assistent](docs/wizard.png)

## Prüfsumme prüfen (optional)

Wer sichergehen will, dass die Datei unverändert ist, vergleicht die Prüfsumme
in PowerShell mit dem Wert aus der Datei `SHA256SUMS` beim
[Release](../../releases/latest):

```powershell
Get-FileHash .\Fokus-Setup-x64.exe -Algorithm SHA256
```

## Deinstallation

Über „Apps und Features" wie jedes andere Programm. **Wichtig:** die von Fokus
gesetzten Sperren in `C:\Windows\System32\drivers\etc\hosts` bleiben
**absichtlich bestehen**, auch nach der Deinstallation. Genau das ist der Sinn
der App: der Selbstbindungs-Effekt steckt in der hosts-Datei, nicht im Programm.
Wer die Sperren doch entfernen will, bearbeitet die hosts-Datei von Hand.

## iOS (iPhone)

Unter [Releases](../../releases) liegt zusätzlich
**Fokus-x.y.z-unsigned.ipa** – die iOS-Version (aktuell im Release v1.0.0;
die iOS-App hat eigene Versionsstände, Windows-Fixes ändern sie nicht). Der Filter läuft dort als
Netzwerk-Extension systemweit (alle Browser und Apps) und wird über ein
Konfigurationsprofil verankert, das App und Filter ohne Passwort unlöschbar
macht. Die IPA ist unsigniert: iOS installiert sie nur nach Signierung mit
einem eigenen Apple-Developer-Account (Details in den Release-Notes).
Zusätzlich nötig: beaufsichtigtes iPhone (Apple Configurator) und das selbst
erzeugte Konfigurationsprofil.

## Hinweise

Privates Projekt, unsigniert, ohne Gewähr. Der Quellcode ist nicht öffentlich;
hier liegen nur die fertigen Installer.
