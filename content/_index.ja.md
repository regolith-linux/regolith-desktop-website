---
title: 概要
type: docs
bookToc: false
---

# Regolithデスクトップ環境

![](/regolith-empty.png)

{{< columns >}}

### 生産性第一

Regolithは、人気があり、高速で、構成しやすく、キーボードを中心とした生産的なワークフローに最適な、[i3](https://i3wm.org/)と[Sway](https://swaywm.org/)で実行されます。Regolithは、i3とSwayを、 `i3bar`、`rofication`、`i3status-rs`、[`ilia`](https://github.com/regolith-linux/ilia#readme)といった他のデスクトップコンポーネントと統合し、完全なデスクトップエクスペリエンスを提供します。

<--->

### GNOMEのシステム管理

軽量なウィンドウマネージャーを`gnome-session`と統合することで、Regolithは典型的な`gnome-shell`ベースの環境の複雑な点の多くを回避し、シンプルで一貫したシステム環境を提供します。

{{< /columns >}}

***

## Regolithのインストール

[Regolith Desktop 3.0のインストール手順（英語）](/docs/using-regolith/install)

## ビジュアルツアー
***

{{< columns >}}

[![](/regolith-ilia-keybindings.png)](/regolith-ilia-keybindings.png)
初回ログイン時に、i3-wmで使用する最も重要なキーバインドをオーバーレイで表示します（<span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">?</span></span>でいつでも切り替えられます）。

<--->

[![](/regolith-floating-terminal.png)](/regolith-floating-terminal.png)
ターミナル上で作業する人は、<span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">enter</span></span>を押すことで作業に取り掛かることができます。

{{< /columns >}}

{{< columns >}}

[![](/regolith-ilia-apps.png)](/regolith-ilia-apps.png)
プログラムを実行する単一のグローバルアプリランチャーが、<span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">space</span></span>を押すことで、どこからでも、即座に利用することができます。</p>

<--->

[![](/regolith-desktop-terminals.png)](/regolith-desktop-terminals.png)
もっとターミナルが必要ですか？<span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">backspace</span></span>と<span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">enter</span></span>で水平・垂直モードを切り替えて、その場でレイアウトを作成できます。<span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">h</span> <span class="badge badge-warning">j</span> <span class="badge badge-warning">k</span> <span class="badge badge-warning">l</span></span>でウィンドウの位置を移動できます。

{{< /columns >}}

{{< columns >}}

[![](/regolith-floating-windows.png)](/regolith-floating-windows.png)
<span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">F</span></span>でフローティングモードに切り替えることができます。<span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">r</span></span>でウィンドウをリサイズし、<span class="badge badge-warning">super</span>を押しながらマウスで移動させます。

<--->

[![](/regolith-gnome-flashback.png)](/regolith-gnome-flashback.png)
Gnome Flashbackは一貫したシンプルなシステム環境を提供します。 UIの調整、USBドライブの自動マウント、ワイヤレスネットワークへの接続を行います。<span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">c</span></span>からコントロールパネルを起動することができます。

{{< /columns >}}

{{< columns >}}

[![](/regolith-screenshot-look-selector.png)](/regolith-screenshot-look-selector.png)
<code>regolith-look</code>コマンドで、<a href="https://ethanschoonover.com/solarized">Solarized</a> や他の外観に簡単に切り替えられます。<b>looks</b>ではパッケージマネージャを利用するため、使用するテーマリソースのみを保存します。 

<--->

[![](/regolith-ilia-windows.png)](/regolith-ilia-windows.png)
もっとやりたいことがありますか？<span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">ctrl</span> <span class="badge badge-warning">space</span></span>や<span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">[0 - 19]</span></span>を押すことで、瞬時に必要なウィンドウを見つけることができます。

{{< /columns >}}

{{< columns >}}

[![](/regolith-many-windows.png)](/regolith-many-windows.png)
無駄なUIを省き、ウィンドウレイアウトを細かく管理することなく、ピクセル単位で活用することができます。

<--->

[![](/regolith-ilia-notifications.png)](/regolith-ilia-notifications.png)
デスクトップ通知は注意を引こうと競合することなく、<span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">n</span></span>を押して画面上のダイアログで管理することが可能です。

{{< /columns >}}

# お問い合わせ

{{< columns >}}

### お知らせ

* [メーリングリストでリリースのお知らせを受け取る](https://www.freelists.org/list/regolith-linux)

<--->

### 議論やヘルプ

* [GitHub Discussions](https://github.com/orgs/regolith-linux/discussions)に参加してヘルプや議論をする
* [既存のIssueや新規Issue](https://github.com/regolith-linux/regolith-desktop/issues)でバグの報告や機能リクエストをする
<--->

### 開発

* [Regolith GitHub org](https://github.com/regolith-linux)で開発が行われています。

{{< /columns >}}
