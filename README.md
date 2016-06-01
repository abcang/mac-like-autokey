Mac Like AutoKey
===

AutoKeyを使ってMac風なショートカットを使えるようにしたもの

## AutoKey

```bash
$ sudo apt-get -y install autokey-gtk
```

AutoKeyから適当なディレクトリを作って、そこにMacLikeディレクトリをコピーしたら動くと思います。

## Ubuntuで使う場合
compizconfig 設定マネージャーを使ってSuperキーに割り当てられている機能をオフにしないとうまく動かないです。

```bash
$ sudo apt-get install -y compizconfig-settings-manager
```

* Superの解除
  * デスクトップ > Ubuntu Unity Plugin > Launcher > Key to show the Dash, Launcher and Help Overlay
* Super-Sの解除
  * デスクトップ > Expo > 割り当て > Expo Key
* Super-W、Shift-Super-Wの解除
  * ウィンドウ・マネジメント > スケール > 割り当て > ワイルドピッカー起動
  * ウィンドウ・マネジメント > スケール > 割り当て > すべてのウィンドウ対象のワイルドピッカー起動

## 注意点

### Ctrl系のコマンド
Terminalで使えるオリジナルのショートカットを上書きしないように、TerminalではAutoKeyが動作しないようにしています。
現状のAutoKeyは「指定したウィンドウ以外で動作させる」オプションが無いため、AutoKeyを使用するウィンドウを指定する形で対応しています。

AutoKeyのWindow Fillterでは正規表現が使えるので、複数のアプリで使いたい場合は以下のように設定してください。

```
^.*((slack.Slack)|(google-chrome.google-chrome)|(atom.Atom)).*$
```

これはslackとChromeとAtomで使えるような設定の例です。
正規表現でいずれかのウィンドウクラスが一致するように書いてあります。
ウィンドウクラスを調べたいときは、Detect Window Propertiesボタンを押して調べるといいでしょう。

[Githubのissue](https://github.com/autokey/autokey/issues/42)にも書かれているので、
そのうち「指定したウィンドウ以外で動作させる」オプションが作られるかもしれません。

### Ctrl-K
MacのCtrl-Kに相当するショートカットが存在しないので、「行末までを選択して切り取り」で代用しています。
本来の動きとは違う動きをするので注意が必要です。

### このリポジトリのファイルでは使えないショートカット
Super-ほげほげ系は自分で簡単に作れるので、他のファイルを参考に作ってみてください。
