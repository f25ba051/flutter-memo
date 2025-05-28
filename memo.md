# Flutterについてのまとめ
# プロジェクトのフォルダ類
>### 「.dart_tool」フォルダ
>Dart言語が自動生成するファイル類を保管するところ。

>### 「idea」フォルダ
> IntelliJ IDEA開発ツールの設定情報。

>### 「build」フォルダ
> ビルドして生成されるファイル類。

>### 「android」フォルダ
>Androidアプリ生成に必要なファイル類(プラットフォームにAndroidを選択した場合)。 

>### 「ios」フォルダ
>iosアプリ生成に必要なファイル類(プラットフォームにIOSを選択した場合)。

>### 「Linux」フォルダ
>Linuxアプリ生成に必要なファイル類(プラットフォームにLinux を選択した場合)。

>### 「macOS」フォルダ
>macOSアプリ生成に必要なファイル類(プラットフォームに macOSを選択した場合)。

>### 「windows」フォルダ
>windowsアプリ生成に必要なファイル類(プラットフォームに Windowsを選択した場合)。

>### 「web」フォルダ
>Webアプリ生成に必要なファイル類(プラットフォームにWeb を選択した場合)。

>### 「lib」フォルダ
>ここにDartのスクリプトが保存される。

>### 「test」フォルダ
>ユニットテスト関連のファイル類。



# プロジェクトのファイル類

>### .gitignore
>Gitで利用するファイル。

>### .metadata
>Flutterツールが利用するファイル。

>### .packages
>利用しているパッケージ情報。

>### anyrysis_options.yaml
>Dartの分析に関するファイル。

>### fluter_app.iml
>モジュール定義ファイル。

>### pubspec.lock
>Pub (Dartのパッケージマネージャ)が利用するファイル。

>### pubspec.yaml
>Pubが利用するファイル。

>### README.md
>リードミーファイル。



# アプリ実行の仕組み
まず package flutter/materialdarn を読み込む  
Flutterマテリアルデザインによるアプリのウィジェットがまとめられているパッケージ


>- void main()(
>    - runApp( ウィジェット );  
>- );

**main関数**...アプリ起動時に呼び出される処理。ここに記述していく  
**runApp関数**...アプリを起動する処理。

# Stateless Widgetクラスについて
**MyApp**...「Stateless Widget」というクラスのサブクラス  
**Stateless Widgetクラス**...ステート(状態を表す値)を持たないウィジェットのベースとなるクラス  

Stateless Widgetかステートを持つStateful Widgetのいずれかを継承してウィジェットのクラスを作成。


## StatelessWidgetの定義

>- class **クラス名** extends StatelessWidget (  
>    - @override  
>    - widget build(BuildContext context) (  
>        - return MaterialApp(...略...);  
>	- ),
> - )

**build**...Stateless Widgetクラスのメソッド。ウィジェットが生成される際に呼び出される。  
**MaterialApp**...マテリアルデザインのアプリを管理するクラス。  
**BuildContext**...ウィジェットに関する機能がまとめられたもの

# Material Appクラスについて
>- return MaterialApp(  
>	- title: 'Flutter demo,  
>	- home: Text(  
>		- 'Hello, Flutter World!!!',  
>		- style: TextStyle(fontSize:32.0),  
>	- ),  
>- );  

**title**...アプリケーションのタイトル  
**home**...アプリケーションに組み込まれるウィジェット

# ウィジェットまとめ
## Text ウィジェット
テキストの表示を行うためのウィジェット
>- Text(
>	- 表示したい文字列,
>	- style = TextStyle(
>		- fontSize: サイズ,
>		- color: 色,
>		- fontWeight: 太さ,
>		- fontFamily: フォント,
>	- )
>- )
**style**...テキストスタイルを示す値（テキストサイズや太さ、フォントなど）

### TextStyleのプロパティ一覧
|プロパティ名|入力|例|
|:---:|:---:|:---:|
|fontSize|数値|30
|color|Colors.カラー名 <br> Color(ARGB)|Colors.red <br> Color(0xFF000000)|
|fontWeight|FontWeight.w100~900（百の位のみ）<br> FontWeight.bold|FontWeight.w400
|fontFamily|フォント名|"Roboto"|

## Padding ウィジェット
ウィジェットの周りに余白を作るためのウィジェット
>- Padding(
>	- padding: 余白,
>	- child: ウィジェット
>- )

### Paddingウィジェットのプロパティ一覧
|プロパティ名|入力|例|
|:---:|:---:|:---:|
|padding|EdgeInsets.only（左右上下個別に設定） <br> EdgeInsets.all（左右上下すべて一気に設定）|EdgeInsets.only(top: 10, bottom: 5, left: 20, right: 15) <br> EdgeInsets.all(20)
|child|Text、Iconウィジェットなど|Text(...略...)|
