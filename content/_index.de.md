---
title: Einführung
type: docs
bookToc: false
---

# Die Regolith Desktop Umgebung

![](/regolith-empty.png)

{{< columns >}}

### Produktivität steht an erster Stelle

Regolith verwendet [i3](https://i3wm.org/): ein beliebter, schneller und konfigurierbarer Kachelfenster-Manager, der sich hervorragend für schnelle tastaturgesteuerte Arbeitsabläufe eignet. Regolith integriert i3 mit anderen Desktop-Komponenten wie z.B. `i3bar`, `rofication`, `gnome-flashback`, und [`ilia`](https://github.com/regolith-linux/ilia#readme), um eine vollständige Desktop-Oberfläche zu bieten.

<--->

### GNOME System Management

Durch die Bereitstellung einer Gnome-Sitzung mit [`gnome-flashback`](https://wiki.gnome.org/Projects/GnomeFlashback), umgeht Regolith einen Großteil der Komplexität einer typischen `gnome-shell`-basierten Umgebung und bietet gleichzeitig
einfache und konsistente Systemverwaltungsmöglichkeiten.

{{< /columns >}}

***

# Regolith 2.2 installieren

{{< hint warning >}}
UPDATE: The Regolith repository key has changed.  Update it by re-running the first step for your distro/version from below. [More Details](https://github.com/orgs/regolith-linux/discussions/888)
{{< /hint >}}

{{< tabs "uniqueid" >}}
{{< tab "Ubuntu 22.10" >}}

Regolith kann als Systempaket installiert werden. Dies macht das Aktualisieren und Entfernen einfach und konsistent. Die folgenden Schritte beschreiben, wie Sie Ihr System so konfigurieren, dass es Pakete aus dem Regolith-Paket-Repository liest und das Desktop-Paket installiert.

1. Registrieren Sie den öffentlichen Schlüssel von Regolith in Ihrem lokalen `apt`:

   ```console
   wget -qO - https://regolith-desktop.org/regolith.key | \
   gpg --dearmor | sudo tee /usr/share/keyrings/regolith-archive-keyring.gpg > /dev/null
   ```

1. Fügen Sie den Repository-URL zu Ihrem lokalen `apt` hinzu:

   ```console
   echo deb "[arch=amd64 signed-by=/usr/share/keyrings/regolith-archive-keyring.gpg] \
   https://regolith-desktop.org/release-ubuntu-kinetic-amd64 kinetic main" | \
   sudo tee /etc/apt/sources.list.d/regolith.list
   ```

1. Aktualisieren Sie `apt` und installieren Sie Regolith

   ```console
   sudo apt update
   sudo apt install regolith-desktop regolith-compositor-picom-glx
   sudo apt upgrade
   ```

1. System-Neustart

Der Login-Manager muss neu gestartet werden, damit die neue Desktop-Sitzung erkannt wird. Der einfachste Weg, ihn neu zu starten, ist ein Neustart des Systems.

{{< hint info >}}
Ersetzen Sie `arm64` mit `amd64` an den beiden Stellen in der obigen Zeile, um auf ARM-basierten Systemen zu installieren.
{{< /hint >}}

{{< hint info >}}
The `regolith-compositor-picom-glx` compositor should work on most computers. If you experience driver or visual issues, [try another compositor](docs/howtos/customize-compositor).
{{< /hint >}}

{{< /tab >}}

{{< tab "Ubuntu 22.04" >}}

Regolith kann als Systempaket installiert werden. Dies macht das Aktualisieren und Entfernen einfach und konsistent. Die folgenden Schritte beschreiben, wie Sie Ihr System so konfigurieren, dass es Pakete aus dem Regolith-Paket-Repository liest und das Desktop-Paket installiert.

1. Registrieren Sie den öffentlichen Schlüssel von Regolith in Ihrem lokalen `apt`:

   ```console
   wget -qO - https://regolith-desktop.org/regolith.key | \
   gpg --dearmor | sudo tee /usr/share/keyrings/regolith-archive-keyring.gpg > /dev/null
   ```

1. Fügen Sie den Repository-URL zu Ihrem lokalen `apt` hinzu:

   ```console
   echo deb "[arch=amd64 signed-by=/usr/share/keyrings/regolith-archive-keyring.gpg] \
   https://regolith-desktop.org/release-ubuntu-jammy-amd64 jammy main" | \
   sudo tee /etc/apt/sources.list.d/regolith.list
   ```

1. Aktualisieren Sie `apt` und installieren Sie Regolith

   ```console
   sudo apt update
   sudo apt install regolith-desktop regolith-compositor-picom-glx
   sudo apt upgrade
   ```

1. System-Neustart

Der Login-Manager muss neu gestartet werden, damit die neue Desktop-Sitzung erkannt wird. Der einfachste Weg, ihn neu zu starten, ist ein Neustart des Systems.

{{< hint info >}}
Ersetzen Sie `arm64` mit `amd64` an den beiden Stellen in der obigen Zeile, um auf ARM-basierten Systemen zu installieren.
{{< /hint >}}

{{< hint info >}}
The `regolith-compositor-picom-glx` compositor should work on most computers. If you experience driver or visual issues, [try another compositor](docs/howtos/customize-compositor).
{{< /hint >}}

{{< /tab >}}

{{< tab "Ubuntu 20.04" >}}

Regolith kann als Systempaket installiert werden. Dies macht das Aktualisieren und Entfernen einfach und konsistent. Die folgenden Schritte beschreiben, wie Sie Ihr System so konfigurieren, dass es Pakete aus dem Regolith-Paket-Repository
liest und das Desktop-Paket installiert.

1. Registrieren Sie den öffentlichen Schlüssel von Regolith in Ihrem lokalen `apt`:

   ```console
   wget -qO - https://regolith-desktop.org/regolith.key | sudo apt-key add -
   ```

1. Fügen Sie die Repository-URL zu Ihrem lokalen `apt` hinzu:

   ```console
   echo deb "[arch=amd64] https://regolith-desktop.org/release-ubuntu-focal-amd64 focal main" | \
   sudo tee /etc/apt/sources.list.d/regolith.list
   ```

{{< hint info >}}
Ersetzen Sie `arm64` mit `amd64` an den beiden Stellen in der obigen Zeile, um auf ARM-basierten Systemen zu installieren.
{{< /hint >}}

1. Aktualisieren Sie `apt` und installieren Sie Regolith

   ```console
   sudo apt update
   sudo apt install regolith-desktop regolith-compositor-picom-glx
   sudo apt upgrade
   ```

1. System-Neustart

Der Login-Manager muss neu gestartet werden, damit die neue Desktop-Sitzung erkannt wird. Der einfachste Weg, ihn neu zu
starten, ist ein Neustart des Systems.

{{< /tab >}}

{{< tab "Debian Bullseye" >}}

Regolith kann als Systempaket installiert werden. Dies macht das Aktualisieren und Entfernen einfach und konsistent. Die folgenden Schritte beschreiben, wie Sie Ihr System so konfigurieren, dass es Pakete aus dem Regolith-Paket-Repository
liest und das Desktop-Paket installiert.

1. Registrieren Sie den öffentlichen Schlüssel von Regolith in Ihrem lokalen `apt`:

   ```console
   wget -qO - https://regolith-desktop.org/regolith.key | \
   gpg --dearmor | sudo tee /usr/share/keyrings/regolith-archive-keyring.gpg > /dev/null
   ```

1. Fügen Sie den Repository-URL zu Ihrem lokalen `apt` hinzu:

   ```console
   echo deb "[arch=amd64 signed-by=/usr/share/keyrings/regolith-archive-keyring.gpg] \
   https://regolith-desktop.org/release-debian-bullseye-amd64 bullseye main" | \
   sudo tee /etc/apt/sources.list.d/regolith.list
   ```
{{< hint info >}}
Ersetzen Sie `arm64` mit `amd64` an den beiden Stellen in der obigen Zeile, um auf ARM-basierten Systemen zu installieren.
{{< /hint >}}

1. Aktualisieren Sie `apt` und installieren Sie Regolith

   ```console
   sudo apt update
   sudo apt install regolith-desktop regolith-compositor-picom-glx
   sudo apt upgrade
   ```

1. System-Neustart

Der Login-Manager muss neu gestartet werden, damit die neue Desktop-Sitzung erkannt wird. Der einfachste Weg, ihn neu zu starten, ist ein Neustart des Systems.

{{< /tab >}}
{{< tab "Regolith Linux 2.2" >}} 

Regolith Linux ist die Regolith-Desktop-Umgebung, die in einem angepassten Ubuntu 22.04-Installationsimage installiert ist. Es ermöglicht das Booten von einem USB-Laufwerk, um Regolith zu starten, ohne es installieren zu müssen. Es ermöglicht auch die Installation des Systems auf dem Laufwerk eines Computers. Regolith Linux bietet neben dem Regolith Desktop folgende Funktionen:

* Angepasster Startbildschirm
* Angepasster Anmeldebildschirm
* Verwendung von `lightdm` statt `gdm3`.
* Die folgenden Pakete werden nicht installiert: `gdm3`, `gnome-shell`, `ubuntu-session`, `evolution-data-server`
  , `snapd`. Diese Pakete können vom Benutzer nach Bedarf installiert werden.

{{< button href="https://github.com/regolith-linux/regolith-ubuntu-iso-builder/releases/download/ubuntu-kinetic-2.2.0-20221211_050200/regolith-ubuntu-kinetic-2.2.0.zip" >}}Download Regolith Linux 2.2{{< /button >}}

Weitere Informationen finden Sie in den [Regolith 2.2 release notes](docs/reference/Releases/regolith-2.2-release-notes).

{{< /tab >}}
{{< /tabs >}}

## Vorschau

***

{{< columns >}}

![](/regolith-ilia-keybindings.png)
Bei der ersten Anmeldung wird ein Overlay (jederzeit aktivierbar mit <span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">?</span></span>) die wichtigsten Tastenkombinationen, die in i3-wm verwendet werden.

<--->

![](/regolith-floating-terminal.png)
Für diejenigen, die im Terminal arbeiten, genügt die Tastenkombination <span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">enter</span></span> um loslegen zu können.

{{< /columns >}}

{{< columns >}}

![](/regolith-ilia-apps.png)
Der globaler App-Launcher ist jederzeit verfügbar, um Ihre Programme mit <span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">space</span></span> zu starten.</p>

<--->

![](/regolith-desktop-terminals.png)
Sie brauchen mehr Terminals? Erstellen Sie Layouts im Handumdrehen, indem Sie zwischen horizontalem und vertikalem Modus umschalten mit <span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">backspace</span></span> gefolgt von <span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">enter</span></span>. Navigieren Sie zu Fenstern mit <span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">h</span> <span class="badge badge-warning">j</span> <span class="badge badge-warning">k</span> <span class="badge badge-warning">l</span></span>.

{{< /columns >}}

{{< columns >}}

![](/regolith-floating-windows.png)
Wechseln Sie den Modus für schwebende Fenster mit <span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">F</span></span>.
Ändern der Fenstergröße geht mit <span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">r</span></span> und bewegen Sie sie mit der Maus, indem Sie <span class="badge badge-warning">super</span> gedrückt halten.

<--->

![](/regolith-gnome-flashback.png)
Gnome Flashback bietet eine konsistente und einfache Systemverwaltung. Passen Sie Ihre Benutzeroberfläche an, binden Sie Ihre USB-Laufwerke automatisch ein, verbinden Sie sich mit drahtlosen Netzwerken. Starten Sie die Systemsteuerung mit <span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">c</span></span>.

{{< /columns >}}

{{< columns >}}

![](/regolith-screenshot-look-selector.png)
Wechseln Sie einfach zu <a href="https://ethanschoonover.com/solarized">Solarized</a> oder anderen looks mit dem <code>regolith-look</code> Befehl. Da <b>looks</b>
den Paketmanager verwenden, speichern Sie nur die Themenressourcen, die Sie gerade verwenden.

<--->

![](/regolith-ilia-windows.png)
Haben Sie viel um die Ohren? Finden Sie schnell das gesuchte Fenster über <span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">ctrl</span> <span class="badge badge-warning">space</span></span> oder navigieren Sie über Arbeitsbereiche mit <span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">[0 - 19]</span></span>.

{{< /columns >}}

{{< columns >}}

![](/regolith-many-windows.png)
Verschwenden Sie keinen Platz für eine überflüssige Benutzeroberfläche und nutzen Sie jeden Pixel, ohne zum Mikro-Manager Ihrer Fensterlayouts zu werden.

<--->

![](/regolith-ilia-notifications.png)
Desktop-Benachrichtigungen kämpfen nicht um Ihre Aufmerksamkeit, sondern können über einen Dialog auf dem Bildschirm verwaltet werden, mit den Tasten <span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">n</span></span>.

{{< /columns >}}

# Community

{{< columns >}}

### Ankündigungen

* [Abonnieren Sie die Mailing-Liste für Veröffentlichungsankündigungen](https://www.freelists.org/list/regolith-linux)

<--->

### Hilfe und Austausch

* Besuchen Sie uns auf [Discussions](https://github.com/orgs/regolith-linux/discussions) für Hilfe und Gespräche (auf Englisch)
* Chat with community members on [the Regolith Desktop Matrix space](https://matrix.to/#/#regolith-desktop:matrix.org)
* Suchen Sie in [bestehenden Tickets oder erstellen Sie ein neues Ticket](https://github.com/regolith-linux/regolith-desktop/issues)
  für Bugs und Funktionswünsche (auf Englisch)
<--->

### Entwicklung

* In der [Regolith GitHub org](https://github.com/regolith-linux) findet die Entwicklung statt.

{{< /columns >}}
