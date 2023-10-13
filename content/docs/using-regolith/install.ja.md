---
title: "インストール"
linkTitle: "Install"
weight: 1
description: >
  Regolithのインストール
---

# Regolith 3.0を入手

以前のバージョンのRegolithからアップグレードする場合、[リリースノート](/docs/reference/Releases/regolith-3.0-release-notes) 、特に[移行ガイド](/docs/reference/Releases/regolith-3.0-release-notes/#migration-guide)に興味があるかもしれません。

## インストール時に選択するパッケージ

Regolith 3.0では、複数のセッション(X11: `regolith-session-flashback`, Wayland: `regolith-session-sway`)から選択することができるようになりました。このため、Regolith 3.0をインストールするときは、使用するセッションを一方か両方を指定します。さらに、Regolith 3.0からはインストール時にRegolithの外観を指定できるようになったことで、後で設定する必要があるセットアップが節約されます。DebianベースのシステムのX11で推奨される基本的なインストールは以下の通りです。

```console
sudo apt install regolith-desktop regolith-session-flashback regolith-look-lascaille
#                ^-- ﾍﾞｰｽ ﾊﾟｯｹｰｼﾞ ^-- ｾｯｼｮﾝ                  ^ -- 外観 
```

* セッションについて、次の内の一方か両方を選ぶことができます：`regolith-session-flashback` (X11), `regolith-session-sway` (Wayland)
* 外観について、次の外観パッケージから*1つ*を選ぶことができます。
```
regolith-look-ayu-dark
regolith-look-ayu-mirage
regolith-look-ayu
regolith-look-blackhole
regolith-look-default-loader
regolith-look-default
regolith-look-dracula
regolith-look-gruvbox
regolith-look-i3-default
regolith-look-lascaille
regolith-look-nevil
regolith-look-nord
regolith-look-solarized-dark
```

上記の推奨事項の例と代替案として、ここでは、Swayセッションに外観"Nord"を適用してインストールする`apt`コマンドが存在します。

```console
sudo apt install regolith-desktop regolith-session-sway regolith-look-nord
```

## サポートするOS

以下は、Regolithデスクトップのインストールを取り扱っている特定のLinuxベースのOSごとに分割されています。

### Ubuntu

{{< tabs "ubuntu-tabs" >}}
{{< tab "Ubuntu 23.04" >}}

Regolithはシステムパッケージとしてインストールすることができます。これは簡単に更新や削除ができ、一貫することができます。
下記のステップでは、Regolithのパッケージリポジトリからパッケージを読み込み可能にして、デスクトップパッケージをインストールできるようにシステムを設定する方法について記しています。

1. ローカルの`apt`にRegolithの公開鍵を登録する。

   ```console
   wget -qO - https://regolith-desktop.org/regolith.key | \
   gpg --dearmor | sudo tee /usr/share/keyrings/regolith-archive-keyring.gpg > /dev/null
   ```

1. ローカルの`apt`にリポジトリのURLを追加する。

   ```console
   echo deb "[arch=amd64 signed-by=/usr/share/keyrings/regolith-archive-keyring.gpg] \
   https://regolith-desktop.org/release-3_0-ubuntu-lunar-amd64 lunar main" | \
   sudo tee /etc/apt/sources.list.d/regolith.list
   ```

1. `apt`を更新してRegolithをインストールする。

   ```console
   sudo apt update
   sudo apt install regolith-desktop regolith-session-flashback regolith-look-lascaille
   ```
1. システムを再起動する。

ログインマネージャーは新しいデスクトップセッションを識別するため、再起動が必要になります。システムを再起動するのはログインマネージャーを再起動するための簡単な方法です。

{{< hint info >}}
ARMベースのシステムにインストールするときは、上記の内容から2箇所の`amd64`を`arm64`に置き換えてください。
{{< /hint >}}

{{< /tab >}}
{{< tab "Ubuntu 22.04" >}}

Regolithはシステムパッケージとしてインストールすることができます。これは簡単に更新や削除ができ、一貫することができます。
下記のステップでは、Regolithのパッケージリポジトリからパッケージを読み込み可能にして、デスクトップパッケージをインストールできるようにシステムを設定する方法について記しています([こちらでダウンロード可能なスクリプト](/install-release-ubuntu-22.04-amd64.txt)が利用できます)。

1. ローカルの`apt`にRegolithの公開鍵を登録する。

   ```console
   wget -qO - https://regolith-desktop.org/regolith.key | \
   gpg --dearmor | sudo tee /usr/share/keyrings/regolith-archive-keyring.gpg > /dev/null
   ```

1. ローカルの`apt`にリポジトリのURLを追加する。

   ```console
   echo deb "[arch=amd64 signed-by=/usr/share/keyrings/regolith-archive-keyring.gpg] \
   https://regolith-desktop.org/release-3_0-ubuntu-jammy-amd64 jammy main" | \
   sudo tee /etc/apt/sources.list.d/regolith.list
   ```

1. `apt`を更新してRegolithをインストールする。

   ```console
   sudo apt update
   sudo apt install regolith-desktop regolith-session-flashback regolith-look-lascaille
   ```
1. システムを再起動する。

ログインマネージャーは新しいデスクトップセッションを識別するため、再起動が必要になります。システムを再起動するのはログインマネージャーを再起動するための簡単な方法です。

{{< hint info >}}
ARMベースのシステムにインストールするときは、上記の内容から2箇所の`amd64`を`arm64`に置き換えてください。
{{< /hint >}}

{{< /tab >}}

{{< tab "Ubuntu 20.04" >}}

Regolithはシステムパッケージとしてインストールすることができます。これは簡単に更新や削除ができ、一貫することができます。
下記のステップでは、Regolithのパッケージリポジトリからパッケージを読み込み可能にして、デスクトップパッケージをインストールできるようにシステムを設定する方法について記しています([こちらでダウンロード可能なスクリプト](/install-release-ubuntu-20.04-amd64.txt)が利用できます)。

1. ローカルの`apt`にRegolithの公開鍵を登録する。

   ```console
   wget -qO - https://regolith-desktop.org/regolith.key | sudo apt-key add -
   ```

1. ローカルの`apt`にリポジトリのURLを追加する。

   ```console
   echo deb "[arch=amd64] https://regolith-desktop.org/release-3_0-ubuntu-focal-amd64 focal main" | \
   sudo tee /etc/apt/sources.list.d/regolith.list
   ```

1. `apt`を更新してRegolithをインストールする。

   ```console
   sudo apt update
   sudo apt install regolith-desktop regolith-session-flashback regolith-look-lascaille
   ```

1. システムを再起動する。

ログインマネージャーは新しいデスクトップセッションを識別するため、再起動が必要になります。システムを再起動するのはログインマネージャーを再起動するための簡単な方法です。

{{< hint info >}}
ARMベースのシステムにインストールするときは、上記の内容から2箇所の`amd64`を`arm64`に置き換えてください。
{{< /hint >}}

{{< /tab >}}

{{< tab "Regolith Linux 2.2 ISO" >}} 

Regolith LinuxはRegolithデスクトップ環境がインストールされた、Ubuntu 22.10のインストールイメージです。USBドライブから起動して、インストールすることなくRegolithを実行することを可能にします。また、コンピューターのドライブにシステムをインストールすることもできます。Regolith Linuxでは、以下の特徴がRegolithデスクトップに追加されています。

* 起動画面とロック画面Regolith用にブランディングされています
* 不要な依存関係を避けて`gdm3`の代わりに`lightdm`ディスプレイマネージャーを使用しています
* 次のパッケージがインストールされていません。これらのパッケージは、ユーザーが必要であればインストールすることができます：`gdm3`, `gnome-shell`, `ubuntu-session`, `evolution-data-server`, `snapd`

{{< button href="https://github.com/regolith-linux/regolith-ubuntu-iso-builder/releases/download/ubuntu-kinetic-2.2.0-20221211_050200/regolith-ubuntu-kinetic-2.2.0.zip" >}}Regolith Linux 2.2をダウンロード{{< /button >}}

詳しい情報は[Regolith 2.2のリリースノート](docs/reference/Releases/regolith-2.2-release-notes)を参照してください。

ISOはLinuxでは[dd](https://www.man7.org/linux/man-pages/man1/dd.1.html)、[ディスク](https://wiki.gnome.org/Apps/Disks)や[KDE ISO Image Writer](https://community.kde.org/ISOImageWriter)などを用いてUSBドライブに書き込むことができます。macOSでは、[Etcher](https://www.balena.io/etcher/)を使用します。Windowsでは[Rufus](https://rufus.ie/)を用いて、DDモードで書き込むことができます。

{{< /tab >}}
{{< /tabs >}}

### Debian

{{< tabs "debian-tabs" >}}

{{< tab "Debian Bookworm" >}}

Regolithはシステムパッケージとしてインストールすることができます。これは簡単に更新や削除ができ、一貫することができます。
下記のステップでは、Regolithのパッケージリポジトリからパッケージを読み込み可能にして、デスクトップパッケージをインストールできるようにシステムを設定する方法について記しています([こちらでダウンロード可能なスクリプト](/install-release-debian-12-amd64.txt)が利用できます)。

1. ローカルの`apt`にRegolithの公開鍵を登録する。

   ```console
   wget -qO - https://regolith-desktop.org/regolith.key | \
   gpg --dearmor | sudo tee /usr/share/keyrings/regolith-archive-keyring.gpg > /dev/null
   ```

1. ローカルの`apt`にリポジトリのURLを追加する。

   ```console
   echo deb "[arch=amd64 signed-by=/usr/share/keyrings/regolith-archive-keyring.gpg] \
   https://regolith-desktop.org/release-3_0-debian-bookworm-amd64 bookworm main" | \
   sudo tee /etc/apt/sources.list.d/regolith.list
   ```

1. `apt`を更新してRegolithをインストールする。

   ```console
   sudo apt update
   sudo apt install regolith-desktop regolith-session-flashback regolith-look-lascaille
   ```
1. システムを再起動する。

ログインマネージャーは新しいデスクトップセッションを識別するため、再起動が必要になります。システムを再起動するのはログインマネージャーを再起動するための簡単な方法です。

{{< hint info >}}
ARMベースのシステムにインストールするときは、上記の内容から2箇所の`amd64`を`arm64`に置き換えてください。
{{< /hint >}}

{{< hint info >}}
`regolith-desktop`パッケージは、多くのハードウェアで動作する必要最小限の設定でインストールします。追加で高級なパッケージやもっと便利な環境を追加するには、[新規ユーザーに推奨されるパッケージ]({{< ref "docs/using-regolith/configuration.md#recommended-packages-for-new-users" >}})を参照してください。
{{< /hint >}}

{{< hint info >}}
`regolith-compositor-picom-glx`コンポジターは多くのコンピューターで動作します。もしドライバや視覚的な問題に遭遇した場合は、[他のコンポジターをお試しください]({{< ref "docs/howtos/customize-compositor" >}})。
{{< /hint >}}

{{< /tab >}}


{{< tab "Debian Bullseye" >}}

Regolithはシステムパッケージとしてインストールすることができます。これは簡単に更新や削除ができ、一貫することができます。
下記のステップでは、Regolithのパッケージリポジトリからパッケージを読み込み可能にして、デスクトップパッケージをインストールできるようにシステムを設定する方法について記しています([こちらでダウンロード可能なスクリプト](/install-release-debian-11-amd64.txt)が利用できます)。

1. ローカルの`apt`にRegolithの公開鍵を登録する。

   ```console
   wget -qO - https://regolith-desktop.org/regolith.key | \
   gpg --dearmor | sudo tee /usr/share/keyrings/regolith-archive-keyring.gpg > /dev/null
   ```

1. ローカルの`apt`にリポジトリのURLを追加する。

   ```console
   echo deb "[arch=amd64 signed-by=/usr/share/keyrings/regolith-archive-keyring.gpg] \
   https://regolith-desktop.org/release-3_0-debian-bullseye-amd64 bullseye main" | \
   sudo tee /etc/apt/sources.list.d/regolith.list
   ```

1. `apt`を更新してRegolithをインストールする。

   ```console
   sudo apt update
   sudo apt install regolith-desktop regolith-compositor-picom-glx
   ```
1. システムを再起動する。

ログインマネージャーは新しいデスクトップセッションを識別するため、再起動が必要になります。システムを再起動するのはログインマネージャーを再起動するための簡単な方法です。

{{< hint info >}}
ARMベースのシステムにインストールするときは、上記の内容から2箇所の`amd64`を`arm64`に置き換えてください。
{{< /hint >}}

{{< hint info >}}
`regolith-desktop`パッケージは、多くのハードウェアで動作する必要最小限の設定でインストールします。追加で高級なパッケージやもっと便利な環境を追加するには、[新規ユーザーに推奨されるパッケージ]({{< ref "docs/using-regolith/configuration.md#recommended-packages-for-new-users" >}})を参照してください。
{{< /hint >}}

{{< hint info >}}
`regolith-compositor-picom-glx`コンポジターは多くのコンピューターで動作します。もしドライバや視覚的な問題に遭遇した場合は、[他のコンポジターをお試しください]({{< ref "docs/howtos/customize-compositor" >}})。
{{< /hint >}}

{{< /tab >}}

{{< /tabs >}}

## リリースの変更ポリシー

 Regolith 3.0以降では、すべてのリリースにおいて、パッケージリポジトリのURLに一意の名前が使用されます。これは、ユーザーが、新しいリリースにアップグレードするタイミングを完全に制御できることを意味します。パッケージマネージャーに常に最新版をインストールしてほしいユーザーには、`release-current` という特別な段階が提供されています。
