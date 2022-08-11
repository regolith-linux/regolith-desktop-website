---
title: "Modifier les Xresources"
description: >
  Apprenez à organiser des copies utilisateur des fichiers de configuration Regolith
---

{{< hint danger >}}
NOTE: Cette page a été copiée depuis le site de [Regolith 1.x](https://regolith-linux.org) et n'a pas été mise à jour pour Regolith 2. Elle peut contenir des informations qui ne sont plus d'actualité.
{{< /hint >}}

Regolith repose sur le système [Xresources](https://en.wikipedia.org/wiki/X_resources) pour fournir une interface de configuration solide.
Pour change les valeurs `Xresources`, Regolith peut être modifié pour mettre à jour l'interface utilisateur, spécifier des comportements, ou définir des formats spécifiques pour certains blocs de la barre.

{{< hint info >}}
Dans Regolith, les valeurs `Xresources` peuvent être changées avec deux méthodes: en fournissant vos propres fichiers `Xresources` et en ré-écrivant les valeurs `Xresources` existantes. La seconde approche est fortement recommandée car elle permet d'avoir des mises à jour de Regolith moins sensibles aux configurations changeantes.
Si vous copiez l'arbre `Xresources` entièrement, vous aurez besoin d'intégrer à la main chaque changement de configuration dans les futures versions.
{{< /hint >}}

## Initialisation

Quand une session Regolith démarre, les Xresources sont charger dans l'ordre suivant:

| Fichier                          | Optionel | Notes                                           |
| -------------------------------- | -------- | ----------------------------------------------- |
| `~/.Xresources`                  | Y        | Pour les paramètres non- Regolith               |
| `/usr/share/regolith-look/**/`   | N        | Les `Xresources` de Regolith liées à des thèmes |
| `~/.config/regolith2/Xresources` | Y        | Ré-écritures de configurations par défaut       |

Il est recommandé d'utiliser `~/.config/regolith2/Xresources` pour les modifications car cela évite d'avoir des paramètres redondants et facilite la maintenance dans le temps.

## Déterminer quelles valeurs doivent être changées

L'outil `xrdb` peut être utilisé pour lister les valeurs `Xresouces`.
Il y a [un certain nombre de valeurs existantes]({{< ref "/docs/Reference/xresources.md" >}}) dans la version R1.4.1:

```console
$ xrdb -query
[...]
gnome.icon.theme:	Moka
gnome.terminal.font:	JetBrains Mono 12
gnome.terminal.scrollbar:	never
gnome.wallpaper:	/usr/share/backgrounds/ESP_016895_1525_desktop.jpg
gnome.wm.theme:	Ayu-Mirage-Dark
[...]
```

## Exemples

Notez que les commandes ci-dessous ajoutent du texte à un fichier. Dans lancer la commande plusieurs fois va générer des lignes dupliquées.

### Exemple - Modifier l'UTI pour utiliser High DPI Screens

En utilisant le fichier `~/.config/regolith2/Xresources`, vous aurez uniquement à spécifier les valeurs que vous souhaitez changer.
L'outil `xrdb` peut être utilisé pour détemriner les valeurs actuels des variables.

1. Créer ou ajouter la valeur suivante au fichier `~/.config/regolith2/Xresources`:

```console
Xft.dpi: 192
```

2. Recharger la configuraiton `Xresources`:

```console
$ regolith-look refresh
```

3. Ouvrir un nouveau terminal pour voir les changements

`192` est juste un exemple que vous pouvez adapter à vos besoins.

### Exemple - Changer la position de la barre i3

```console
$ xrdb -query | grep position
i3-wm.bar.position:	bottom
$ echo "i3-wm.bar.position:	top" >> ~/.config/regolith2/Xresources
$ regolith-look refresh
```

### Exemple - Changer le thème GTK

```console
$ xrdb -query | grep gtk
gnome.gtk.theme:	Ayu-Mirage-Dark
$ echo "gnome.gtk.theme:	Adwaita" >> ~/.config/regolith2/Xresources
$ regolith-look refresh
```

### Exemple - Désactiver la barre d'état

```console
$ echo "i3-wm.bar.trayoutput:	none" >> ~/.config/regolith2/Xresources
$ regolith-look refresh
```

### Exemple - Utiliser Alt plutôt que la touche Win comme touche Super

```console
$ echo "i3-wm.mod: Mod1" >> ~/.config/regolith2/Xresources
$ echo "i3-wm.alt: Mod4" >> ~/.config/regolith2/Xresources
```

Ensuite, recharger i3 pour que le changement prenne effet.

### Exemple - Lancer `nm-applet` quand i3 démarre

Certains utilisateurs préfèrent utiliser l'application `nm-applet` pour configurer et gérer le réseau sans-fil (depuis Regolith 1.5, `nm-applet` est exécuté par défaut en arrière-plan). Le fichier de configuration i3 peut être modifié pour lancer certains programmes au lancement. Mais, plutôt que de copier tout le fichier, il est possible de fixer jusqu'à trois programmes via Xresources sans avoir à changer le fichier de configuration i3. Pour cela, assurez-vous que la barre d'état système est activé (voir ci-dessus).

```console
$ echo "i3-wm.program.1: /usr/bin/nm-applet" >> ~/.config/regolith2/Xresources
```

Ce changement nécessite que vous vous déconnectiez puir reconnectiez pour prendre effet.

# Informations supplémentaires

Voir [la page de référence sur les configurations]({{< ref "/docs/Reference/configurations.md" >}}) pour plus de détails concernant la configuration de Regolith.
