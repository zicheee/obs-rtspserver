![Latest Release](https://img.shields.io/github/v/release/iamscottxu/obs-rtspserver.svg)
![CI Release](https://github.com/iamscottxu/obs-rtspserver/workflows/CI%20Release/badge.svg)
![Contributors](https://img.shields.io/github/contributors/iamscottxu/obs-rtspserver.svg)
![Total Downloads](https://img.shields.io/github/downloads/iamscottxu/obs-rtspserver/total.svg)
![License](https://img.shields.io/github/license/iamscottxu/obs-rtspserver.svg)


🇨🇳 [简体中文](//github.com/iamscottxu/obs-rtspserver/blob/master/README_zh-CN.md)
🇭🇰 [繁體中文](//github.com/iamscottxu/obs-rtspserver/blob/master/README_zh-TW.md)
🇯🇵 [日本語](//github.com/iamscottxu/obs-rtspserver/blob/master/README_ja-JP.md)
🇰🇷 [한국어](//github.com/iamscottxu/obs-rtspserver/blob/master/README_ko-KR.md)
🇪🇦 [Español](//github.com/iamscottxu/obs-rtspserver/blob/master/README_es-ES.md)
🇫🇷 [Français](//github.com/iamscottxu/obs-rtspserver/blob/master/README_fr-FR.md)
🇮🇹 [Italiano](//github.com/iamscottxu/obs-rtspserver/blob/master/README_it-IT.md)
🇩🇪 [Deutsch](//github.com/iamscottxu/obs-rtspserver/blob/master/README_de-DE.md)
🇳🇱 [Nederlands](//github.com/iamscottxu/obs-rtspserver/blob/master/README_nl-NL.md)
🇷🇺 [Русский](//github.com/iamscottxu/obs-rtspserver/blob/master/README_ru-RU.md)

<font size="5">[Helfen Sie bei der Übersetzung von obs-rtspserver!](https://www.transifex.com/scott-xu/obs-rtspserver)</font>

# OBS-RTSPServer

Dies ist ein Plugin für obs-studio, das die Ausgabe codiert und ein RTSP-Stream veröffentlicht.

**Unterstützte Betriebssysteme** : Windows 10, Windows 11, Linux und macOS

**Unterstützte OBS Studio Version**: 30.0.0+

[![Paketstatus](https://repology.org/badge/vertical-allrepos/obs-rtspserver.svg)](https://repology.org/project/obs-rtspserver/versions)

# Installation
## Windows
Der Installer kann auf der [Release-Seite](https://github.com/iamscottxu/obs-rtspserver/releases) gefunden werden.

Wenn Sie eine komprimierte Datei verwenden möchten, um manuell zu installieren, können Sie sie entpacken (z.B.: obs-rtspserver-v2.0.5-windows.zip) und in den Installationsordner von obs-studio legen.

### winget Paket
Wenn die Betriebssystemversion Windows 10 1709 oder neuer ist und [app-installer](https://www.microsoft.com/store/productId/9NBLGGH4NNS1) installiert wurde, führen Sie einfach Folgendes aus, um es zu installieren:

```powershell
winget install iamscottxu.obs-rtspserver
```

## MacOS
Sie können den .pkg-Installer verwenden, um zu installieren, und der Installer kann unter [Release-Seite](https://github.com/iamscottxu/obs-rtspserver/releases) gefunden werden, wenn macOS verwendet wird.

## Linux (Nur x64)
### Ubuntu/Debian DEB-Paket
Laden Sie das deb-Paket von der [Release-Seite](https://github.com/iamscottxu/obs-rtspserver/releases) herunter und installieren Sie es.

```bash
wget -O obs-rtspserver-linux.deb https://github.com/iamscottxu/obs-rtspserver/releases/download/{version}/obs-rtspserver-{version}-linux.deb
apt install -y obs-rtspserver-linux.deb
```
* Ersetzen Sie {version} durch die letzte Veröffentlichungsversion, z.B.: v2.2.0

### Red-Hat RPM-Paket
Laden Sie das RPM-Paket von der [Release-Seite](https://github.com/iamscottxu/obs-rtspserver/releases) herunter und installieren Sie es.

```bash
wget -O obs-rtspserver-linux.rpm https://github.com/iamscottxu/obs-rtspserver/releases/download/{version}/obs-rtspserver-{version}-linux.rpm
rpm -ivh obs-rtspserver-linux.rpm
```
* Ersetzen Sie {version} durch die letzte Veröffentlichungsversion, z.B.: v2.2.0

### ArchLinux AUR-Paket
obs-rtspserver ist auch als [AUR-Paket](https://aur.archlinux.org/packages/?O=0&K=obs-rtspserver) verfügbar. Wenn Sie [yay](https://github.com/Jguer/yay) verwenden, führen Sie einfach Folgendes aus, um es zu installieren:

```bash
yay -S obs-rtspserver
```

### Andere
Laden Sie das tar.gz-Archiv von der [Release-Seite](https://github.com/iamscottxu/obs-rtspserver/releases) herunter und entpacken Sie es in "/".

```bash
wget -O obs-rtspserver-linux.tar.gz https://github.com/iamscottxu/obs-rtspserver/releases/download/{version}/obs-rtspserver-{version}-linux.tar.gz
#For all user
tar -xzvf obs-rtspserver-linux.tar.gz -C /
#For local user
mkdir -p ~/.config/obs-studio/plugins/obs-rtspserver/bin/64bit/
mkdir -p ~/.config/obs-studio/plugins/obs-rtspserver/data/
mkdir -p ~/obs-rtspserver-linux
tar -xzvf obs-rtspserver-linux.tar.gz -C ~/obs-rtspserver-linux/
mv ~/obs-rtspserver-linux/usr/lib/obs-plugins/obs-rtspserver.so ~/.config/obs-studio/plugins/obs-rtspserver/bin/64bit/obs-rtspserver.so
mv ~/obs-rtspserver-linux/usr/share/obs/obs-plugins/obs-rtspserver/locale ~/.config/obs-studio/plugins/obs-rtspserver/data/locale
rm -rf ~/obs-rtspserver-linux
```
* Ersetzen Sie {version} durch die letzte Veröffentlichungsversion, z.B.: v2.2.0


# Bauen
* Install cmake, visual studio(only windows) and qt.
* Laden Sie den Quellcode von obs-studio herunter und konfigurieren Sie ihn.
* Kopieren Sie den Quellcode in (obs-studio Quellcode)/plugins/obs-rtspserver/
* Fügen Sie `add_subdirectory(obs-rtspserver)` zu (obs-studio Quellcode)/plugins/CMakeLists.txt hinzu.
* Build obs-rtspserver.

# Verwendung
## RTSP Server starten
1. OBS Studio öffnen und im Menü: Tools → RTSP Server
2. Server Einstellungen konfigurieren (Port, Authentifizierung, etc.)
3. Start klicken um den RTSP server zu starten

### Achtung!: Stream automatisch aktiv
Der RTSP stream ist automatisch aktiv, sobald der RTSP server gestartet ist. Sie müssen NICHT den OBS Studio's "Start Streaming" Button verwenden. Der stream ist automatisch verfügbar, basierend auf der aktuellen Szene und Einstellungen

### Den Stream abrufen
```
rtsp://{server-ip}:{port}/{path}

## if all defaults:
rtsp://{server-ip}:554/live
```
Der Stream kann mit VLC, FFmpeg oder jedem anderen RTSP Client getested werden

### Hinweise
* Der RTSP server läuft unabhängig von OBS Studio's eingebauter streaming Funktionalität
* Der stream beinhaltet direkt was in dem OBS Vorschaufenster gezeigt wird (aktive Szene)
* Der server läuft so lange, bis OBS Studio geschlossen wird oder der server gestoppt wird

# FAQ
* [Kann das Plugin im Menü nicht finden](https://github.com/iamscottxu/obs-rtspserver/wiki/FAQ#cant-find-the-plugin-in-the-menu)

# Lizenz
* [RtspServer](https://github.com/PHZ76/RtspServer/) - [MIT License](https://github.com/PHZ76/RtspServer/blob/master/LICENSE)
* [Qt5](https://www.qt.io/) - [GPL version 2](https://doc.qt.io/qt-5/licensing.html)
* [libb64](https://sourceforge.net/projects/libb64/) - [Public domain dedication](https://sourceforge.net/p/libb64/git/ci/master/tree/LICENSE)
