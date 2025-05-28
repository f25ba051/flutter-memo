# Flutterについてのまとめ
# プロジェクトのフォルダ類
### 「.dart_tool」フォルダ
Dart言語が自動生成するファイル類を保管するところ。

### 「idea」フォルダ
IntelliJ IDEA開発ツールの設定情報。

### 「build」フォルダ
ビルドして生成されるファイル類。

### 「android」フォルダ
Androidアプリ生成に必要なファイル類(プラットフォームにAndroidを選択した場合)。 

### 「ios」フォルダ
iosアプリ生成に必要なファイル類(プラットフォームにIOSを選択した場合)。

### 「Linux」フォルダ
Linuxアプリ生成に必要なファイル類(プラットフォームにLinux を選択した場合)。

### 「macOS」フォルダ
macOSアプリ生成に必要なファイル類(プラットフォームに macOSを選択した場合)。

### 「windows」フォルダ
windowsアプリ生成に必要なファイル類(プラットフォームに Windowsを選択した場合)。

### 「web」フォルダ
Webアプリ生成に必要なファイル類(プラットフォームにWeb を選択した場合)。

### 「lib」フォルダ
ここにDartのスクリプトが保存される。

### 「test」フォルダ
ユニットテスト関連のファイル類。



# プロジェクトのファイル類

### .gitignore
Gitで利用するファイル。

### .metadata
Flutterツールが利用するファイル。

### .packages
利用しているパッケージ情報。

### anyrysis_options.yaml
Dartの分析に関するファイル。

### fluter_app.iml
モジュール定義ファイル。

### pubspec.lock
Pub (Dartのパッケージマネージャ)が利用するファイル。

### pubspec.yaml
Pubが利用するファイル。

### README.md
リードミーファイル。



# アプリ実行の仕組み
まず package flutter/materialdarn を読み込む  
Flutterマテリアルデザインによるアプリのウィジェットがまとめられているパッケージ


- void main()(
    - runApp( ウィジェット );  
- );

**main関数**...アプリ起動時に呼び出される処理。ここに記述していく  
**runApp関数**...アプリを起動する処理。

# Stateless Widgetクラスについて
**MyApp**...「Stateless Widget」というクラスのサブクラス  
**Stateless Widgetクラス**...ステート(状態を表す値)を持たないウィジェットのベースとなるクラス  

Stateless Widgetかステートを持つStateful Widgetのいずれかを継承してウィジェットのクラスを作成。


## StatelessWidgetの定義

- class **クラス名** extends StatelessWidget (  
    - @override  
    - widget build(BuildContext context) (  
        - return MaterialApp(...略...);

**build**...Stateless Widgetクラスのメソッド。ウィジェットが生成される際に呼び出される。  
**MaterialApp**...マテリアルデザインのアプリを管理するクラス。  
**BuildContext**...ウィジェットに関する機能がまとめられたもの

# Material Appクラスについて
- return MaterialApp(  
	- title: 'Flutter demo,  
	- home: Text(  
		- 'Hello, Flutter World!!!',  
		- style: TextStyle(fontSize:32.0),  
	- ),  
- );  

**title**...アプリケーションのタイトル  
**home**...アプリケーションに組み込まれるウィジェット

# ウィジェットまとめ
## Text ウィジェット
Text...テキストの表示を行うためのウィジェット
style...テキストスタイルを示す値（テキストサイズや太さ、フォントなど）

