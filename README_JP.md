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
* [開発協力](#開発協力)
* [履歴](#履歴)
<!--te-->

## 概要

プラグインを複数のバージョンでビルドしたり、ビルドされたプラグインをマーケットプレイスに提出できる形式の zip ファイルに圧縮する機能を追加します。  

## 動作環境

対象バージョン : UE4.27 ～ 5.6    
対象プラットフォーム : Windows  

## インストール

プロジェクトの Plugins フォルダに [Plugins/PluginBuilder](https://github.com/Naotsun19B/PluginBuilder) フォルダを入れてください。  
または、[マーケットプレイス](https://www.unrealengine.com/marketplace/ja/product/pluginbuilder)からインストールしてください。  
プラグインのインストール後に機能が使用できない場合は、プラグインが有効化されていない可能性がありますので、編集 > プラグイン からプラグインの有効のチェックが入っているかをご確認ください。

## 機能と使い方

エディタの Build メニュー(UE4 では File メニュー)の Package Plugin からこのプラグインの機能を利用できます。  

![BuildPlugin](https://user-images.githubusercontent.com/51815450/236683732-c4e03f0f-4534-4d1e-85bb-be34829dbf7d.png)
![EngineVersions](https://github.com/Naotsun19B/PluginBuilder-Document/assets/51815450/637b6282-d4ee-41a1-a142-511a4abfb8eb)
![TargetPlatforms](https://github.com/Naotsun19B/PluginBuilder-Document/assets/51815450/5f4f654d-b5a9-45cc-bf3e-42564fa0dcf4)
![BuildTargets](https://github.com/Naotsun19B/PluginBuilder-Document/assets/51815450/1052c6f7-54ae-4cbf-8370-18009459e7e0)

| **項目**               | **項目**                                | **説明**                                                                                                                                                                     |
|----------------------|---------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Build Plugin         |                                       | 設定されたビルド構成に基づいてプラグインをビルドおよびパッケージ化します。                                                                                                                                      |
| Build Configurations | Engine Versions                       | プラグインをビルドするエンジンのバージョンを指定します。                                                                                                                                               |
|                      | No Host Platform                      | ホスト上でエディタープラットフォームのコンパイルを禁止するかどうか。                                                                                                                                         |
|                      | Host Platforms                        | プラグインを構築するホストプラットフォームを指定します。                                                                                                                                               |
|                      | Target Platforms                      | プラグインをビルドするプラットフォームを指定します。                                                                                                                                                 |
|                      | Rocket                                | Rocket.txt を使用しない古いバージョンを処理するかどうか。                                                                                                                                         |
|                      | Create Sub Folder                     | 出力されるプラグインのフォルダにサブフォルダを作成するかどうか。                                                                                                                                           |
|                      | Strict Includes                       | プラグインコードのヘッダーインクルードを厳密に判断するかどうか。                                                                                                                                           |
|                      | Unversioned                           | ビルドするエンジンのバージョンを.upluginに埋め込むかどうか。                                                                                                                                         |
|                      | Zip Up                                | ビルド後に必要なファイルのみを含む zip ファイルを作成するかどうか。                                                                                                                                       |
|                      | Output All Zip Files To Single Folder | zip ファイルを1つのフォルダに入れるかどうか。<br/>false の場合、zip ファイルごとにエンジンごとのフォルダが使用されます。                                                                                                     |
|                      | Keep Binaries Folder                  | zip フォルダにバイナリフォルダを保存するかどうか。<br/>マーケットプレイスへ提出する場合はバイナリフォルダを含めないようにしてください。                                                                                                   |
|                      | Keep .uplugin Properties              | UATから出力する際に削除された.upluginのプロパティを出力後も保持するかどうか。<br/>UATで削除するプロパティの例: IsBetaVersion, IsExperimentalVersion, EnabledByDefault, など。<br/>マーケットプレイスへの提出する場合はUATから出力されたものを使用してください。 |
|                      | Compression Level                     | ビルドしたプラグインをzipファイルに圧縮する際の圧縮率。                                                                                                                                              |
| Build Targets        |                                       | ビルドするプラグインを選択します。                                                                                                                                                          |
| Build Settings       |                                       | PluginBuilderの設定を開きます。                                                                                                                                                     |

![Packaging](https://user-images.githubusercontent.com/51815450/236683791-a3c05c65-f1de-4ef4-9a60-1652782e0d12.png)

パッケージ化中はビルドの進捗がアウトプットログに出力されます。  
また、エディタ通知上からパッケージ処理のキャンセル及びアウトプットログを開くことができます。  

## オプション

![KeyboardShotcuts](https://github.com/Naotsun19B/PluginBuilder-Document/assets/51815450/df529a90-11ed-4059-8830-1cd33231c458)

「機能と使い方」でご紹介したメニューに対応するショートカットキーはエディタ環境設定のキーボードショートカットから変更できます。  

![Settings](https://github.com/Naotsun19B/PluginBuilder-Document/assets/51815450/87b934f8-b944-4b9f-a1aa-6f306ecbf3fa)

| **カテゴリ**     | **項目**                                                      | **説明**                                                                                         |
|--------------|-------------------------------------------------------------|------------------------------------------------------------------------------------------------|
| Build Target | Search Only Enabled                                         | 有効なプラグインのみがビルドターゲットのリストに表示されるようにするかどうか。                                                        |
|              | Contains Project Plugins                                    | プロジェクトの plugins フォルダ内のプラグインをビルドターゲットのリストに表示するかどうか。                                             |
|              | Contains Engine Plugins                                     | エンジンの plugins フォルダ内のプラグインをビルドターゲットのリストに表示するかどうか。                                               |
| Output       | Select Output Directory Manually                            | パッケージ化プロセスを開始する前に出力先のディレクトリを選択するかどうか。                                                          |
|              | Output To Build Directory Of Each Project                   | 各プロジェクトの Build ディレクトリを出力ディレクトリとして使用するかどうか。                                                     |
|              | Output Directory Path                                       | パッケージ化されたプラグインが出力されるディレクトリのパス。 　                                                               |
| Misc         | Use Friendly Name                                           | プラグインの出力ファイル、エディタのメニューなどでプラグインの Friendly Name を使用するかどうか。                                       |
|              | Show Only Logs From This Plugin When Package Process Starts | パッケージプロセスの開始時に、このプラグインのログカテゴリのみを表示するように出力ログフィルタを変更するかどうか。<br/>この機能は UE5.1 以降でのみ利用可能です。         |
|              | Stop Packaging Process Immediately                          | パッケージ化中にキャンセルボタンが押されるとすぐにパッケージ化プロセスを停止するかどうか。<br/> !!注意!! プロセスを強制終了するため、UBT からエラーが発生する場合があります。 |


## ライセンス

[MITライセンス](https://ja.wikipedia.org/wiki/MIT_License)

## 作者

[Naotsun](https://twitter.com/Naotsun_UE)

## 開発協力

[@RyanDowlingSoka](https://twitter.com/RyanDowlingSoka)

## 履歴

- (2025/06/04) v1.7  
  UE5.6に対応しました  
  エディタ環境設定やビルド構成などの設定が正常に保存されない不具合の修正を行いました  
  ビルド構成に関する設定はプロジェクトごとに保存されるように変更しました  
  エンジンバージョンの全ての選択を解除するプリセットのClearを追加しました   

- (2024/12/24) v1.6  
  UE5.5に対応しました  
  TargetPlatformの引数のフォーマットの誤りを修正しました  

- (2024/04/24) v1.5  
  UE5.4に対応しました  
  UE5.3では「Strict Includes」を使用するとエンジンコードでビルドエラーが発生するため、UE5.3でだけ自動で使用しないようにする対応をしました  
  設定項目に「No Host Platform」、「Host Platforms」、「Unversioned」の3つを追加しました  

- (2023/09/07) v1.4  
  UE5.3に対応しました

- (2023/06/26) v1.3  
  エンジンバージョンのプリセットボタンにAllを追加しました  
  ビルド対象のみプロジェクトごとの値を記憶するように変更しました  
  zipファイルへの圧縮処理をUATのZipUtilsを使用して行うように変更しました  

- (2023/05/09) v1.2  
  エディタのツールメニューや出力ディレクトリ名などにプラグインの Friendly Name を使うオプションを追加しました  
  zip ファイルに Binaries を含めるオプションを追加しました  
  全ての zip ファイルを1つのディレクトリに出力するオプションを追加しました  
  .uplugin ファイルのプロパティをエクスポートされたプラグインにコピーするオプションを追加しました  
  パッケージ処理の開始時に出力ログにこのプラグインのログのみを表示するオプションを追加しました (UE5.1 以降でのみ利用可能)  
  エンジンのバージョンのプリセットボタンをツールメニューに追加しました  
  UE5.2に対応しました  

- (2023/05/09) v1.1  
  パッケージ処理でエラーがあっても成功した際のエディタ通知が表示される不具合を修正  

- (2023/05/07) v1.0   
  プラグインを公開
