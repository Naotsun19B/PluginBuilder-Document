# PluginBuilder

![Plugin](https://user-images.githubusercontent.com/51815450/236666641-574dcfbd-9588-4192-87f1-33e13d713e55.png)

<!--ts-->
* [Description](#Description)
* [Requirement](#Requirement)
* [Installation](#Installation)
* [Features And Usages](#features-and-usages)
* [Settings](#Settings)
* [License](#License)
* [Author](#Author)
* [History](#History)
<!--te-->

## Description

Adds a tools menu to build plugin with multiple engine versions and compress the built plugin into a zip file that can be submitted to the marketplace.

## Requirement

Target version : UE4.27 ～ 5.1    
Target platform : Windows  

## Installation

Put the [Plugins/PluginBuilder](https://github.com/Naotsun19B/PluginBuilder) folder in your project's Plugins folder.  
Or install from the [marketplace](https://www.unrealengine.com/marketplace/en-US/product/pluginbuilder).  
If the feature is not available after installing the plugin, it is possible that the plugin has not been enabled, so please check if the plugin is enabled from Edit > Plugins.

## Features And Usages

You can access the functionality of this plugin from Package Plugin in the editor's Build menu (File menu in UE4).  

![BuildPlugin](https://user-images.githubusercontent.com/51815450/236683732-c4e03f0f-4534-4d1e-85bb-be34829dbf7d.png)
![EngineVersions](https://user-images.githubusercontent.com/51815450/236683752-09411600-6b4b-4f25-9460-1e014159b135.png)
![TargetPlatforms](https://user-images.githubusercontent.com/51815450/236683763-444c5780-bef0-440a-a7b0-601282d767b0.png)
![BuildTargets](https://user-images.githubusercontent.com/51815450/236683773-a41db51c-8ddd-41c3-93cf-34366a5e386a.png)

| **Item**             | **Item**          | **Description**                                                                    |
|----------------------|-------------------|------------------------------------------------------------------------------------|
| Build Plugin         |                   | Builds and packages the plugin based on the set build configuration.               |
| Build Configurations | Engine Versions   | Specifies the engine versions to build the plugin.                                 |
|                      | Target Platforms  | Specifies the target platforms to build the plugin.                                |
|                      | Rocket            | Whether to handle older versions that do not use the Rocket.txt file.              |
|                      | Create Sub Folder | Whether to create a subfolder in the output built plugins folder.                  |
|                      | Strict Includes   | Whether to judge the header inclusion of the plugin code strictly.                 |
|                      | Zip Up            | Whether to create a zip file that contains only the files we need after the build. |
| Build Targets        |                   | Select the plugin to build.                                                        |
| Build Settings       |                   | Opens the settings for Plugin Builder.                                             |

![Packaging](https://user-images.githubusercontent.com/51815450/236683791-a3c05c65-f1de-4ef4-9a60-1652782e0d12.png)

During packaging, build progress is printed to the output log.  
On the editor notification, you can also cancel the package processing or open the output log.  

## Settings

![KeyboardShotcuts](https://user-images.githubusercontent.com/51815450/236667003-60527edd-ded5-404c-b729-7f26aea66337.png)

The shortcut keys corresponding to the menus introduced in "Functions and Usage" can be changed from Keyboard Shortcuts in Editor Preferences.  

![Settings](https://user-images.githubusercontent.com/51815450/236667052-eab7626d-6cf7-4c0b-9d57-9051c1111c73.png)

| **Category** | **Item**                           | **Description**                                                                                                                                                          |
|--------------|------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Build Target | Search Only Enabled                | Whether to ensure that only valid plugins appear in the list of build targets.                                                                                           |
|              | Contains Project Plugins           | Whether to make plugin  in the project's plugins folder appear in the list of build targets.                                                                             |
|              | Contains Engine Plugins            | Whether to make plugins in the engine's plugins folder appear in the list of build targets.                                                                              |
| Output       | Select Output Directory Manually   | Whether to select the output directory before starting the packaging process.                                                                                            |
|              | Output Directory Path              | A path to the directory where the packaged plugin will be output.                                                                                                        |
| Process      | Stop Packaging Process Immediately | Whether to stop the packaging process as soon as the cancel button is pressed during packaging.<br/> !!CAUTION!! You may get an error from UBT as it kills the process.  |

## License

[MIT License](https://en.wikipedia.org/wiki/MIT_License)

## Author

[Naotsun](https://twitter.com/Naotsun_UE)

## History

- (2023/05/09) v1.1  
  Fixed a bug that the successful editor notification was displayed even if there were errors  

- (2023/05/07) v1.0   
  Publish plugin
