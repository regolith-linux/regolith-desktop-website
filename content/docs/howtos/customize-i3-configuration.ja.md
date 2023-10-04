---
title: "i3設定のカスタマイズ"
linkTitle: "i3の設定をカスタマイズする方法"
weight: 1
description: >
  i3の外観や動作を変更する方法。
---

# How to work with Regolith's defaults

既定の設定は`/usr/share/regolith/i3/config.d`に保存されています。これらはアルファベット順に読み込まれます。次に、`~/.config/regolith3/i3/config.d`のユーザー設定をアルファベット順に読み込みます。Regolithの既定の設定は`Xresources`値の設定や、ユーザー設定の追加や、`apt`による既定の設定の追加・削除でカスタマイズできるように構築されています。これにより、Regolithではi3のカスタマイズ方法に、設定をクリーンにするため、個別に、もしくは組み合わせて使用できる複数のアプローチがあります：

- `Xresources`によるキーバインド・文字列・プログラム名・色といった、上書き値の使用
- `apt`によるRegolithの既定ファイルを追加や削除
- 独自の設定ファイルの追加
- Regolithの設定の大規模の置き換え

## `Xresources`変数を設定する方法

次の設定例（`/usr/share/regolith/i3/config.d/80_compositor`）より、`$wm.program.compositor`を設定することで、既存のi3設定ファイルを編集したり上書きすることなく、使用したいコンポジターを読み込むようにカスタマイズすることができます。

{{< hint warning >}}
Regolithバージョン3.0ではXresourceキーが"i3-wm"から"wm"に置き換えられます。このページの内容はRegolith 3.0以降のものに更新されています。それ以前のバージョンを使用する場合は、キーの名前を"wm"から"i3-wm"として使用してください。例として、Regolith 1.xと2.xでは`wm.foo.bar`は`i3-wm.foo.bar`に変更されます。
{{< /hint >}}

```
set_from_resource $wm.program.compositor wm.program.compositor /usr/share/regolith-compositor/init
exec_always --no-startup-id $wm.program.compositor
```

これを行うには、`~/.config/regolith3/Xresources`に以下の行を追加するのみです：

```
# 自作のコンポジターを使用する
wm.program.compositor: /usr/local/bin/my-compositor
```

同様に、`/usr/share/regolith/i3/config.d`のファイルを基にした`Xresources`で他のオプションの上書きをすることもできます：

```
## 間隔の設定
wm.gaps.inner.size: 1

## 分割線の設定
wm.window.border.size: 3
wm.client.focused.color.child_border: #AAD3E9

## ワークスペースの名前
wm.workspace.01.name: 1:FOO
```

詳しくは、[`Xresources`に関するより詳細なディスカッション]({{< ref "docs/howtos/override-xres.md" >}})を参照してください。

## 既定の部分をアンインストールする方法

提供された既定の部分設定を全体的に置き換えたり削除したい場合、提供された部分を`apt`でパッケージとして削除することができます。

削除したい部分を提供するパッケージの名前を特定するには：

```console
dpkg -S /usr/share/doc/regolith-i3-workspace-config
```

出力結果にパッケージの名前が含まれている場合：

```
regolith-i3-workspace-config: /usr/share/doc/regolith-i3-workspace-config
```

このパッケージで提供されるファイルの完全なリストを確認し、何を削除しようとしているのかわかっている場合：

```console
dpkg -L regolith-i3-workspace-config
```

部分を削除するには：

```console
sudo apt remove regolith-i3-workspace-config
```

## 既定の部分をカスタマイズする方法

{{< hint warning >}}
警告：Regolithの既定部分のみをカスタマイズする場合、`~/.config/regolith3/i3/config`ファイルが存在**しない**ことを確認してください。これはRegolithの既定を上書きするため、このHowToの内容と互換性がありません。
{{< /hint >}}

初めに、, ensure that a directory exists for user config partials.

```console
mkdir -p ~/.config/regolith3/i3/config.d
```

次に、既定の設定を独自の設定ディレクトリにコピーします：

```console
cp /usr/share/regolith/i3/config.d/40_workspace-config ~/.config/regolith3/i3/config.d/
```

希望に沿った変更を加えます：

```console
vim ~/.config/regolith3/i3/config.d/40_workspace-config
```

既定に含まれているパッケージをクリーンアップするには：

```console
sudo apt remove regolith-i3-workspace-config
```

最後に、**i3を再起動するか、ログアウトしてから戻ります**。

## Regolithの既定を完全に置き換える方法

Regolithの既定を保持したくない場合、（例えば、あなたが完全な個人設定を使いたい経験豊富な`i3`ユーザーであるとき）の場合、すべてのRegolithの部分設定をアンインストールしたり、独自のRoot設定を`~/.config/regolith3/i3/config`に作成することができます。