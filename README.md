# Fokus

Fokus ist ein einfacher Seitenblocker für Windows 11, macOS und iOS. Gesperrte
Domains landen in der hosts-Datei, das Entsperren ist bewusst umständlich: nach
dem Blocken bleiben nur 60 Sekunden zum Rückgängigmachen, danach ist die Sperre
dauerhaft. Ein Werkzeug zur Selbstbindung gegen Ablenkung. Adminrechte braucht
nur die Installation; blocken kann danach jedes Benutzerkonto, auch ohne
Adminrechte.

![Die Fokus-App mit einer geblockten Seite](docs/app.png)

## Download

Ein Klick auf den Link deiner Plattform lädt die aktuelle Installationsdatei
direkt herunter:

| Plattform | Direkt-Download | Anleitung |
|-----------|-----------------|-----------|
| **Windows** 10/11 (Intel/AMD, 64 Bit) | **[⬇ Fokus-Setup-x64.exe (v1.0.2)](../../releases/download/v1.0.2/Fokus-Setup-x64.exe)** | [Windows-Anleitung](#windows-installation-in-drei-schritten) |
| **macOS** | **[⬇ Fokus-1.0.0.pkg](../../releases/download/macos-v1.0.0/Fokus-1.0.0.pkg)** | [macOS-Anleitung](#macos-mac) |
| **iOS** (iPhone) | [⬇ Fokus-1.0.0-unsigned.ipa](../../releases/download/ios-v1.0.0/Fokus-1.0.0-unsigned.ipa) | [iOS-Hinweise](#ios-iphone) – **nicht** direkt installierbar |

Die Links zeigen immer auf die neueste Version (werden bei jedem Release
automatisch aktualisiert). Ältere Versionen und Prüfsummen (`SHA256SUMS`):
[alle Releases](../../releases).

Für Windows auf ARM gibt es letztmalig bei [v1.0.0](../../releases/tag/v1.0.0)
einen Installer; neuere Versionen erscheinen nur noch für x64.

## Windows: Installation in drei Schritten

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

## macOS (Mac)

**Fokus-<Version>.pkg** aus der Release-Reihe `macos-v<Version>` laden und
öffnen. Das Paket ist nicht notarisiert, deshalb blockt macOS den ersten
Doppelklick: **Rechtsklick (ctrl-Klick) auf die .pkg → „Öffnen“** und
bestätigen (alternativ Systemeinstellungen → Datenschutz & Sicherheit →
„Dennoch öffnen“). Dann den Assistenten durchklicken und einmal Adminrechte
bestätigen.

Der Installer legt die App für alle Benutzer in /Applications ab und richtet
den Hintergrund-Dienst ein. Beim ersten Start fragt macOS ggf. einmal um
Freigabe für die App sowie für die Safari-Steuerung (offene Tabs einer frisch
geblockten Seite werden sofort umgeleitet) – beides erlauben. Auch hier
bleiben die Sperren in /etc/hosts nach einer Deinstallation absichtlich
bestehen.

## iOS (iPhone)

In der Release-Reihe `ios-v<Version>` liegt
**Fokus-<Version>-unsigned.ipa** – die iOS-Version (eigene Versionsstände;
Windows-/Mac-Fixes ändern sie nicht). Der Filter läuft dort als
Netzwerk-Extension systemweit (alle Browser und Apps) und wird über ein
Konfigurationsprofil verankert, das App und Filter ohne Passwort unlöschbar
macht. Die IPA ist unsigniert: iOS installiert sie nur nach Signierung mit
einem eigenen Apple-Developer-Account (Details in den Release-Notes).
Zusätzlich nötig: beaufsichtigtes iPhone (Apple Configurator) und das selbst
erzeugte Konfigurationsprofil.

## Hinweise

Privates Projekt, unsigniert, ohne Gewähr. Der Quellcode ist nicht öffentlich;
hier liegen nur die fertigen Installer.
