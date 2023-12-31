# 概要
　このリポジトリはCodespaceでflutterの開発をする際のテンプレート用で作成したものです。

# .devcontainer
 .devcontainerディレクトリ内に、devcontainer.jsonという名前のファイルを作成します。このファイルは、Codespaceの構成を定義するためのものです。

```
{
  "name": "Flutter Development",
  "image": "",
  "extensions": ["dart-code.dart-code", "dart-code.flutter"],
  "settings": {
    "dart.sdkPath": "/usr/lib/dart"
  },
  "forwardPorts": [8080, 8888]
}
```

# 使い方

## 1.Codespaceの起動:
 　Codespacesにアクセスし、対象のリポジトリを開きます。
　リポジトリ内にある.devcontainer/devcontainer.jsonファイルを使用して、Codespaceを起動します。
This project is a starting point for a Flutter application.

## 2.VS Codeのセットアップ:
　Codespaceが起動したら、ウェブ上のVS Codeエディタを使用して開発作業を行います。
　初回起動時には、VS Codeの拡張機能が自動的にインストールされます。もしインストールされない場合は、FlutterとDartの拡張機能を手動でインストールしてください。
A few resources to get you started if this is your first Flutter project:

## 3.Flutterプロジェクトの作成:
　ターミナルを開き、Flutterプロジェクトを作成するためのコマンドを実行します。例えば、以下のコマンドで新しいプロジェクトを作成します。

```
flutter create my_app
```

## 4.プロジェクトの実行:

　作成したFlutterプロジェクトのディレクトリに移動し、ターミナルで以下のコマンドを実行します。

```
flutter run
```

　これにより、デバッグモードでアプリが実行されます。

## 5.コードの編集とデバッグ:

　VS Codeのエディタを使用して、Flutterプロジェクトのコードを編集します。編集箇所は主にlib/main.dartです。
　変更したコードを保存すると、自動的にHot Reloadがトリガーされ、アプリがリロードされます。
　デバッグのためにブレークポイントを設定し、デバッガを使用することもできます。

## 6.プロジェクトのビルドとデプロイ:

FlutterプロジェクトをビルドしてAPK(Android)やIPA(iOS)ファイルを生成するには、ターミナルで以下のコマンドを実行します。

```
flutter build apk  // Androidの場合
flutter build ios  // iOSの場合
```

ビルドが成功すると、対応するプラットフォーム向けのファイルが生成されます。

## 7.ビルドのやり直すために

　Flutterではビルドし直す前にビルドした状態を綺麗にした方が良いようです。

 ```
 flutter clean
 ```

 # 8.webでデバッグするために
　codespaceからダウンロードしてAndrodi/iPhoneにアプリをインストールして確認するのは面倒くさいため、ウェブを利用してデバッグをしたい。ということで、ウェブを使うための方法。

```
flutter run --release -d web-server --web-hostname=0.0.0.0 --web-port=8080
flutter run --release -d web-server --web-hostname=0.0.0.0 --web-port=8888
```

　なお、このweb-portはdevcontainer.jsonに記述しているforwardPortsから取ってきている。portsを変更すれば、web-portも変更することが必要であるため注意されたい。