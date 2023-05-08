# PluginBuilder

![Plugin](https://user-images.githubusercontent.com/51815450/236666641-574dcfbd-9588-4192-87f1-33e13d713e55.png)

<!--ts-->
* [概要](#概要)
* [動作環境](#動作環境)
* [インストール](#インストール)
* [機能と使い方](#機能と使い方)
* [オプション](#オプション)
* [ライセンス](#ライセンス)
* [作者](#作者)
* [履歴](#履歴)
<!--te-->

## 概要

プラグインを複数のバージョンでビルドしたり、ビルドされたプラグインをマーケットプレイスに提出できる形式の zip ファイルに圧縮する機能を追加します。  

## 動作環境

対象バージョン : UE4.27 ～ 5.1    
対象プラットフォーム : Windows  

## インストール

プロジェクトの Plugins フォルダに [Plugins/PluginBuilder](https://github.com/Naotsun19B/PluginBuilder) フォルダを入れてください。  
または、[マーケットプレイス](https://www.unrealengine.com/marketplace/ja/product/pluginbuilder)からインストールしてください。  
プラグインのインストール後に機能が使用できない場合は、プラグインが有効化されていない可能性がありますので、編集 > プラグイン からプラグインの有効のチェックが入っているかをご確認ください。

## 機能と使い方

エディタの Build メニュー(UE4 では File メニュー)の Package Plugin からこのプラグインの機能を利用できます。  

![BuildPlugin](https://user-images.githubusercontent.com/51815450/236683732-c4e03f0f-4534-4d1e-85bb-be34829dbf7d.png)
![EngineVersions](https://user-images.githubusercontent.com/51815450/236683752-09411600-6b4b-4f25-9460-1e014159b135.png)
![TargetPlatforms](https://user-images.githubusercontent.com/51815450/236683763-444c5780-bef0-440a-a7b0-601282d767b0.png)
![BuildTargets](https://user-images.githubusercontent.com/51815450/236683773-a41db51c-8ddd-41c3-93cf-34366a5e386a.png)

| **項目**               | **項目**            | **説明**                                |
|----------------------|-------------------|---------------------------------------|
| Build Plugin         |                   | 設定されたビルド構成に基づいてプラグインをビルドおよびパッケージ化します。 |
| Build Configurations | Engine Versions   | プラグインをビルドするエンジンのバージョンを指定します。          |
|                      | Target Platforms  | プラグインをビルドするプラットフォームを指定します。            |
|                      | Rocket            | Rocket.txt を使用しない古いバージョンを処理するかどうか。    |
|                      | Create Sub Folder | 出力されるプラグインのフォルダーにサブフォルダを作成するかどうか。     |
|                      | Strict Includes   | プラグインコードのヘッダーインクルードを厳密に判断するかどうか。      |
|                      | Zip Up            | ビルド後に必要なファイルのみを含む zip ファイルを作成するかどうか。  |
| Build Targets        |                   | ビルドするプラグインを選択します。                     |
| Build Settings       |                   | PluginBuilderの設定を開きます。                |

![Packaging](https://user-images.githubusercontent.com/51815450/236683791-a3c05c65-f1de-4ef4-9a60-1652782e0d12.png)

パッケージ化中はビルドの進捗がアウトプットログに出力されます。  
また、エディタ通知上からパッケージ処理のキャンセル及びアウトプットログを開くことができます。  

## オプション

![KeyboardShotcuts](https://user-images.githubusercontent.com/51815450/236667003-60527edd-ded5-404c-b729-7f26aea66337.png)

「機能と使い方」でご紹介したメニューに対応するショートカットキーはエディタ環境設定のキーボードショートカットから変更できます。  

![Settings](https://user-images.githubusercontent.com/51815450/236667052-eab7626d-6cf7-4c0b-9d57-9051c1111c73.png)

| **カテゴリ**     | **項目**                             | **説明**                                                                                         |
|--------------|------------------------------------|------------------------------------------------------------------------------------------------|
| Build Target | Search Only Enabled                | 有効なプラグインのみがビルドターゲットのリストに表示されるようにするかどうか。                                                        |
|              | Contains Project Plugins           | プロジェクトの plugins フォルダ内のプラグインをビルドターゲットのリストに表示するかどうか。                                             |
|              | Contains Engine Plugins            | エンジンの plugins フォルダ内のプラグインをビルドターゲットのリストに表示するかどうか。                                               |
| Output       | Select Output Directory Manually   | パッケージ化プロセスを開始する前に出力先のディレクトリを選択するかどうか。                                                          |
|              | Output Directory Path              | パッケージ化されたプラグインが出力されるディレクトリのパス。 　                                                               |
| Process      | Stop Packaging Process Immediately | パッケージ化中にキャンセルボタンが押されるとすぐにパッケージ化プロセスを停止するかどうか。<br/> !!注意!! プロセスを強制終了するため、UBT からエラーが発生する場合があります。 |


## ライセンス

[MITライセンス](https://ja.wikipedia.org/wiki/MIT_License)

## 作者

[Naotsun](https://twitter.com/Naotsun_UE)

## 履歴

- (2023/05/07) v1.0   
  プラグインを公開
