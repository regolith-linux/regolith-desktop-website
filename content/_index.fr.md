---
title: Introduction
type: docs
bookToc: false
---

# L'environnement Regolith Desktop

![](/regolith-empty.png)

{{< columns >}}

### La productivité d'abord

Regolith utilise [i3](https://i3wm.org/): un gestionnaire de fenêtre en tuiles qui est populaire, rapide, configurable et très pratique pour tout piloter avec son clavier. Regolith intègre i3 avec d'autres composants comme `i3bar`, `rofication`, `gnome-flashback`, et [`ilia`](https://github.com/regolith-linux/ilia#readme) afin de fournir une interface de bureau complète.

<--->

### Système de gestion GNOME

En fournissant une session gnome avec [`gnome-flashback`](https://wiki.gnome.org/Projects/GnomeFlashback), Regolith s'affranchi d'une bonne partie de la complexité des environnements typiques basés sur `gnome-shell` en fournissant un système de gestion simple et consistant.

{{< /columns >}}

---

# Obtenir Regolith 2.2

{{< hint warning >}}
UPDATE: The Regolith repository key has changed.  Update it by re-running the first step for your distro/version from below. [More Details](https://github.com/orgs/regolith-linux/discussions/888)
{{< /hint >}}

{{< tabs "uniqueid" >}}
{{< tab "Ubuntu 22.10" >}}

Regolith peut être installé en tant que programme système. Cela permet de rendre la mise à jour et la suppression plus consistants.
Les étapes suivantes décrivent comment configurer votre système pour récupérer les paquets depuis le dépôt de paquets Regolith et installer le programme de bureau.

1. Enregistrer la clé publique de Regolith localement dans `apt`:

   ```console
   wget -qO - https://regolith-desktop.org/regolith.key | \
   gpg --dearmor | sudo tee /usr/share/keyrings/regolith-archive-keyring.gpg > /dev/null
   ```

1. Ajouter l'URL du dépôt dans vos sources `apt`:

   ```console
   echo deb "[arch=amd64 signed-by=/usr/share/keyrings/regolith-archive-keyring.gpg] \
   https://regolith-desktop.org/release-ubuntu-kinetic-amd64 kinetic main" | \
   sudo tee /etc/apt/sources.list.d/regolith.list
   ```

1. Mettre à jour les dépôts `apt` et installer Regolith

   ```console
   sudo apt update
   sudo apt install regolith-desktop regolith-compositor-picom-glx
   sudo apt upgrade
   ```

1. Redémarrer le système

Le gestionnaire de connexion doit être redémarré pour que la nouvelle session de bureau soit reconnue. La manière la plus simple de faire est de redémarrer votre système.

{{< hint info >}}
Le paquet `regolith-desktop` installe une configuration minimale qui devrait fonctionner sur la plupart des architectures.
Pour ajouter des paquets supplémentaires afin d'avoir un environnement plus riche et fonctionnel, vous pouvez lire [Paquets recommandés pour les nouveaux utilisateurs](/docs/using-regolith/configuration/#recommended-packages-for-new-users).
{{< /hint >}}

{{< hint info >}}
Remplacer `arm64` par `amd64` aux deux endroits dans les lignes ci-dessus pour une installation sur un système basé sur ARM.
{{< /hint >}}

{{< hint info >}}
The `regolith-compositor-picom-glx` compositor should work on most computers. If you experience driver or visual issues, [try another compositor](docs/howtos/customize-compositor).
{{< /hint >}}

{{< /tab >}}

{{< tab "Ubuntu 22.04" >}}

Regolith peut être installé en tant que programme système. Cela permet de rendre la mise à jour et la suppression plus consistants.
Les étapes suivantes (aussi disponible sous la forme d'un [script d'installation](<(/install-release-ubuntu-22.04-amd64.txt)>)) décrivent comment configurer votre système pour récupérer les paquets depuis le dépôt de paquets Regolith et installer le programme de bureau.

1. Enregistrer la clé publique de Regolith localement dans `apt`:

   ```console
   wget -qO - https://regolith-desktop.org/regolith.key | \
   gpg --dearmor | sudo tee /usr/share/keyrings/regolith-archive-keyring.gpg > /dev/null
   ```

1. Ajouter l'URL du dépôt dans vos sources `apt`:

   ```console
   echo deb "[arch=amd64 signed-by=/usr/share/keyrings/regolith-archive-keyring.gpg] \
   https://regolith-desktop.org/release-ubuntu-jammy-amd64 jammy main" | \
   sudo tee /etc/apt/sources.list.d/regolith.list
   ```

1. Mettre à jour les dépôts `apt` et installer Regolith

   ```console
   sudo apt update
   sudo apt install regolith-desktop regolith-compositor-picom-glx
   sudo apt upgrade
   ```

1. Redémarrer le système

Le gestionnaire de connexion doit être redémarré pour que la nouvelle session de bureau soit reconnue. La manière la plus simple de faire est de redémarrer votre système.

{{< hint info >}}
Le paquet `regolith-desktop` installe une configuration minimale qui devrait fonctionner sur la plupart des architectures.
Pour ajouter des paquets supplémentaires afin d'avoir un environnement plus riche et fonctionnel, vous pouvez lire [Paquets recommandés pour les nouveaux utilisateurs](/docs/using-regolith/configuration/#recommended-packages-for-new-users).
{{< /hint >}}

{{< hint info >}}
Remplacer `arm64` par `amd64` aux deux endroits dans les lignes ci-dessus pour une installation sur un système basé sur ARM.
{{< /hint >}}

{{< hint info >}}
The `regolith-compositor-picom-glx` compositor should work on most computers. If you experience driver or visual issues, [try another compositor](docs/howtos/customize-compositor).
{{< /hint >}}

{{< /tab >}}

{{< tab "Ubuntu 20.04" >}}

Regolith peut être installé en tant que programme système. Cela permet de rendre la mise à jour et la suppression plus consistants.
Les étapes suivantes (aussi disponible sous la forme d'un [script d'installation](<(/install-release-ubuntu-20.04-amd64.txt)>>)) décrivent comment configurer votre système pour récupérer les paquets depuis le dépôt de paquets Regolith et installer le programme de bureau.

1. Enregistrer la clé publique de Regolith localement dans `apt`:

   ```console
   wget -qO - https://regolith-desktop.org/regolith.key | sudo apt-key add -
   ```

1. Ajouter l'URL du dépôt dans vos sources `apt`:

   ```console
   echo deb "[arch=amd64] https://regolith-desktop.org/release-ubuntu-focal-amd64 focal main" | \
   sudo tee /etc/apt/sources.list.d/regolith.list
   ```

{{< hint info >}}
Remplacer `arm64` par `amd64` aux deux endroits dans les lignes ci-dessus pour une installation sur un système basé sur ARM.
{{< /hint >}}

1. Mettre à jour les dépôts `apt` et installer Regolith

   ```console
   sudo apt update
   sudo apt install regolith-desktop regolith-compositor-picom-glx
   sudo apt upgrade
   ```

{{< hint info >}}
Le paquet `regolith-desktop` installe une configuration minimale qui devrait fonctionner sur la plupart des architectures.
Pour ajouter des paquets supplémentaires afin d'avoir un environnement plus riche et fonctionnel, vous pouvez lire [Paquets recommandés pour les nouveaux utilisateurs](/docs/using-regolith/configuration/#recommended-packages-for-new-users).
{{< /hint >}}

1. Redémarrer le système

Le gestionnaire de connexion doit être redémarré pour que la nouvelle session de bureau soit reconnue. La manière la plus simple de faire est de redémarrer votre système.

{{< /tab >}}

{{< tab "Debian Bullseye" >}}

Regolith peut être installé en tant que programme système. Cela permet de rendre la mise à jour et la suppression plus consistants.
Les étapes suivantes (aussi disponible sous la forme d'un [script d'installation](<(/install-release-debian-11-amd64.txt)>>)) décrivent comment configurer votre système pour récupérer les paquets depuis le dépôt de paquets Regolith et installer le programme de bureau.

1. Enregistrer la clé publique de Regolith localement dans `apt`:

   ```console
   wget -qO - https://regolith-desktop.org/regolith.key | \
   gpg --dearmor | sudo tee /usr/share/keyrings/regolith-archive-keyring.gpg > /dev/null
   ```

1. Ajouter l'URL du dépôt dans vos sources `apt`:

   ```console
   echo deb "[arch=amd64 signed-by=/usr/share/keyrings/regolith-archive-keyring.gpg] \
   https://regolith-desktop.org/release-debian-bullseye-amd64 bullseye main" | \
   sudo tee /etc/apt/sources.list.d/regolith.list
   ```

{{< hint info >}}
Remplacer `arm64` par `amd64` aux deux endroits dans les lignes ci-dessus pour une installation sur un système basé sur ARM.
{{< /hint >}}

1. Mettre à jour les dépôts `apt` et installer Regolith

   ```console
   sudo apt update
   sudo apt install regolith-desktop regolith-compositor-picom-glx
   sudo apt upgrade
   ```

{{< hint info >}}
Le paquet `regolith-desktop` installe une configuration minimale qui devrait fonctionner sur la plupart des architectures.
Pour ajouter des paquets supplémentaires afin d'avoir un environnement plus riche et fonctionnel, vous pouvez lire [Paquets recommandés pour les nouveaux utilisateurs](/docs/using-regolith/configuration/#recommended-packages-for-new-users).
{{< /hint >}}

1. Redémarrer le système

Le gestionnaire de connexion doit être redémarré pour que la nouvelle session de bureau soit reconnue. La manière la plus simple de faire est de redémarrer votre système.

{{< /tab >}}
{{< tab "Regolith Linux 2.2 ISO" >}}

Regolith Linux est un environnement de bureau Regolith installé dans une image customisée d'Ubuntu 22.04. Cela permet de démarrer depuis une clé USB afin d'exécuter Regolith sans avoir à l'installer.
Cela permet également d'installer sur le disque d'un ordinateur. Regolith Linux ajoute les fonctionnalités suivantes par rapport à Regolith Desktop:

- Le design Regolith lors du démarrage et des écrans de connexion
- Utilise `lightdm` comme gestionnaire d'affichage plutôt que `gdm3` pour éviter les dépendances inutiles
- Les paquets suivants ne sont pas installés: `gdm3`, `gnome-shell`, `ubuntu-session`, `evolution-data-server`, `snapd`. Ils peuvent néanmoins être installés par l'utilisateur.

{{< button href="https://github.com/regolith-linux/regolith-ubuntu-iso-builder/releases/download/ubuntu-kinetic-2.2.0-20221211_050200/regolith-ubuntu-kinetic-2.2.0.zip" >}}Download Regolith Linux 2.2{{< /button >}}

Rendez-vous sur [Regolith 2.2 release notes](docs/reference/Releases/regolith-2.2-release-notes) pour plus d'informations.

{{< /tab >}}
{{< /tabs >}}

## Aperçu des fonctionnalités

---

{{< columns >}}

![](/regolith-ilia-keybindings.png)
Lors de la première connexion, un dialogue (activé à n'importe quand avec <span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">?</span></span>) présente les raccourcis clavier les plus important utilisés avec i3-wm.

<--->

![](/regolith-floating-terminal.png)
Pour celles et ceux qui travaillent dans le terminal, pressez <span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">enter</span></span> suffit à vous satisfaire.

{{< /columns >}}

{{< columns >}}

![](/regolith-ilia-apps.png)
Un lanceur d'application global est immédiatement accessible depuis partout pour lancer vos programmes avec <span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">space</span></span>.</p>

<--->

![](/regolith-desktop-terminals.png)
Besoin de plus de terminaux ? Créez un agencement à la volée en basculant entre mode horizontal et verical avec <span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">backspace</span></span> suivi de <span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">enter</span></span>.
Naviguez vers les fenêtres selon leur position avec <span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">h</span> <span class="badge badge-warning">j</span> <span class="badge badge-warning">k</span> <span class="badge badge-warning">l</span></span>.

{{< /columns >}}

{{< columns >}}

![](/regolith-floating-windows.png)
Activez le mode fenêtre flottante avec <span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">F</span></span>.
Redimmensionnez les fenêtres avec <span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">r</span></span> et déplacez-les avec la souris en pressant <span class="badge badge-warning">super</span>.

<--->

![](/regolith-gnome-flashback.png)
Gnome Flashback fourni un système de gestion simple et consistant. Personnalisez votre UI, montez automatiquement vos disques USB, connectez vous à des réseaux sans fils.
Vous pouvez lancer le panneau de contrôle avec <span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">c</span></span>.

{{< /columns >}}

{{< columns >}}

![](/regolith-screenshot-look-selector.png)
Changer facilement de thème pour <a href="https://ethanschoonover.com/solarized">Solarized</a> ou d'autres thèmes avec la commande <code>regolith-look</code>.
Comme les **thèmes** utilisent le gestionnaire de paquet, vous stockez seulement les ressources des thèmes que vous utilisez.

<--->

![](/regolith-ilia-windows.png)
Trop de choses sur le feu ? Trouvez rapidement la fenêtre que vous cherchez avec <span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">ctrl</span> <span class="badge badge-warning">space</span></span> ou naviguer entre les espaces de travail avec <span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">[0 - 19]</span></span>.

{{< /columns >}}

{{< columns >}}

![](/regolith-many-windows.png)
Ne perdez pas de place avec des interfaces frivoles et profitez de chaque pixel sans avoir à faire du micro-management de votre agencement de fenêtres.

<--->

![](/regolith-ilia-notifications.png)
Les notifications de bureau ne se battent pas pour votre attention mais peuvent être gérées depuis un dialogue en pressant <span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">n</span></span>.

{{< /columns >}}

# Interaction

{{< columns >}}

### Annonces

- [Souscrivez à notre mailing list pour recevoir les annonces des prochaines versions](https://www.freelists.org/list/regolith-linux)

<--->

### Discussions et Aide

- Rejoignez-nous sur [GitHub Discussions](https://github.com/orgs/regolith-linux/discussions) pour discuter et obtenir de l'aide
- Chat with community members on [the Regolith Desktop Matrix space](https://matrix.to/#/#regolith-desktop:matrix.org)
- Cherchez dans les [issues existantes ou créez-en une nouvelle](<(https://github.com/regolith-linux/regolith-desktop/issues)>) si vous trouvez un bug ou avez une demande de fonctionnalité
  <--->

### Développement

- [Le dépôt GitHub Regolith](https://github.com/regolith-linux) est l'endroit où les choses se passent.

{{< /columns >}}
