# Flutter 開発環境セットアップ

## 実行環境
Windows 端末:  
Windows 10 Home 64bit バージョン 1909（OS ビルド 18363.1082）  
Git 2.28.0.windows.1  

Androidデバイス:   
Android 9  

以降のコマンドは Windows Terminal で開いた Git Bash で行う。

## flutter と dart のインストール
Flutter をインストールする。Flutter 用の Dart は Flutter に同梱されている。 
```console
scoop install flutter
```

## Android Studio のインストール
Android Studio をインストールする。
```console
scoop install android-studio
```

これにより、Android SDK、Android SDK コマンドラインツール、および Android SDK ビルドツールがインストールされる。これらは、Android 向けに開発するときに Flutter に必要となる。

## 開発者向けオプションと USB デバッグの有効化
手持ちの Android デバイスでビルド番号を表示させる。
```
[設定] > [システム] > [電話情報] > [ビルド番号]
```

この [ビルド番号] を7回タップする。7回タップすることで「開発者向けオプション」を有効にすることができる。


次に「開発者向けオプション」画面を開く。
```
[設定] > [システム] > [詳細設定] > [開発者向けオプション]
```

「開発者向けオプション」画面内に「USB デバッグ」の切り替えがあるので、ON にする。

Android 端末に USB 接続すると Android 端末側に「USB デバッグを許可しますか？」のメッセージが表示されるので、「OK」をタップする。

flutter devices コマンドで Android 端末を認識できていることを確認する。
```console
flutter devices
```

接続できることは確認できたので一旦、USB 接続は外しておく。

## VSCode のインストール
VSCode のポータブル版をインストールする。

## Flutter エクステンションのインストール
Ctr + Shift + X で拡張機能ペインを開き、検索窓に「flutter」と入力する。

Flutter 拡張が表示されるので、これをインストールする。

Flutter 拡張をインストールすると、同時に Dart 拡張もインストールされる。

## Flutter プロジェクトを作成する
VSCode を開く。Ctr + Shift + X でコマンドパレットを開き、「flutter」と入力する。

「Flutter: New Project」コマンドが表示されるので、このコマンドを選択する。

初回は Flutter SDK の場所を聞かれるので、以下のフォルダを指定する。
```
C:\Users\＜ユーザ名＞\scoop\apps\flutter\current\bin
```

次にプロジェクト名を入力する（hello_world など）。

そして、プロkジェクトを作成する場所を指定する（Desktop など）。

これで Flutter プロジェクトが作成される。

## エミュレータの作成
事前に Android Studio の AMD（Android Device Manager）でエミュレータを作成しておく。

エミュレータを作成しておいたら、Android Studio は閉じておいても OK。

## VSCode でエミュレータを開く
VSCode で Flutter プロジェクトを開くと、右下のバーに「No Device」と表示される。

この「No Device」をクリックする。

すると、コマンドパレットに利用できるエミュレータが表示されるので、利用したいエミュレータを選択する。

## Flutter プロジェクトの起動

### Run / Debug ボタンで起動する方法
VSCode では、Flutter プロジェクトの起点となる main メソッドの上に「Run」「Debug」ボタンが表示される。

このボタンをクリックすることで、エミュレータでプロジェクトが起動する。

### Flutter コマンドで起動する方法
以下のコマンドで Flutter プロジェクトを起動することもできる。
```console
flutter run
```

## Android 端末でデバッグする
Android 端末を USB 接続する。

すると、接続した Android 端末が自動的に認識される。

VSCode 画面の右下に接続された Android 端末名が表示されたら、Flutter プロジェクトを起動する。
