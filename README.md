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
* [Development Cooperation](#development-cooperation)
* [History](#History)
<!--te-->

## Description

Adds a tools menu to build plugin with multiple engine versions and compress the built plugin into a zip file that can be submitted to the marketplace.

## Requirement

Target version : UE4.27 ～ 5.3    
Target platform : Windows  

## Installation

Put the [Plugins/PluginBuilder](https://github.com/Naotsun19B/PluginBuilder) folder in your project's Plugins folder.  
Or install from the [marketplace](https://www.unrealengine.com/marketplace/en-US/product/pluginbuilder).  
If the feature is not available after installing the plugin, it is possible that the plugin has not been enabled, so please check if the plugin is enabled from Edit > Plugins.

## Features And Usages

You can access the functionality of this plugin from Package Plugin in the editor's Build menu (File menu in UE4).  

![BuildPlugin](https://user-images.githubusercontent.com/51815450/236683732-c4e03f0f-4534-4d1e-85bb-be34829dbf7d.png)
![EngineVersions](https://github.com/Naotsun19B/PluginBuilder-Document/assets/51815450/637b6282-d4ee-41a1-a142-511a4abfb8eb)
![TargetPlatforms](https://github.com/Naotsun19B/PluginBuilder-Document/assets/51815450/5f4f654d-b5a9-45cc-bf3e-42564fa0dcf4)
![BuildTargets](https://github.com/Naotsun19B/PluginBuilder-Document/assets/51815450/1052c6f7-54ae-4cbf-8370-18009459e7e0)

| **Item**             | **Item**                              | **Description**                                                                                                                                                                                                                                                                                |
|----------------------|---------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Build Plugin         |                                       | Builds and packages the plugin based on the set build configuration.                                                                                                                                                                                                                           |
| Build Configurations | Engine Versions                       | Specifies the engine versions to build the plugin.                                                                                                                                                                                                                                             |
|                      | Target Platforms                      | Specifies the target platforms to build the plugin.                                                                                                                                                                                                                                            |
|                      | Rocket                                | Whether to handle older versions that do not use the Rocket.txt file.                                                                                                                                                                                                                          |
|                      | Create Sub Folder                     | Whether to create a subfolder in the output built plugins folder.                                                                                                                                                                                                                              |
|                      | Strict Includes                       | Whether to judge the header inclusion of the plugin code strictly.                                                                                                                                                                                                                             |
|                      | Zip Up                                | Whether to create a zip file that contains only the files we need after the build.                                                                                                                                                                                                             |
|                      | Output All Zip Files To Single Folder | Whether to put the zip files into a single folder.<br/>If false will use a per engine folder for each zip file.                                                                                                                                                                                |
|                      | Keep Binaries Folder                  | Whether the zip folder should keep the binaries folder.<br/>Marketplace submissions expect the binaries folder to be deleted.                                                                                                                                                                  |
|                      | Keep .uplugin Properties              | Whether to keep the properties of uplugin that are deleted when outputting from UAT even after outputting.<br/>Examples of properties to delete by UAT: IsBetaVersion, IsExperimentalVersion, EnabledByDefault, etc.<br/>Marketplace submissions expect to use the uplugin file output by UAT. |
|                      | Compression Level                     | The compression strength when compressing the built plugin into a zip file.                                                                                                                                                                                                                    |
| Build Targets        |                                       | Select the plugin to build.                                                                                                                                                                                                                                                                    |
| Build Settings       |                                       | Opens the settings for Plugin Builder.                                                                                                                                                                                                                                                         |

![Packaging](https://user-images.githubusercontent.com/51815450/236683791-a3c05c65-f1de-4ef4-9a60-1652782e0d12.png)

During packaging, build progress is printed to the output log.  
On the editor notification, you can also cancel the package processing or open the output log.  

## Settings

![KeyboardShotcuts](https://github.com/Naotsun19B/PluginBuilder-Document/assets/51815450/df529a90-11ed-4059-8830-1cd33231c458)

The shortcut keys corresponding to the menus introduced in "Functions and Usage" can be changed from Keyboard Shortcuts in Editor Preferences.  

![Settings](https://github.com/Naotsun19B/PluginBuilder-Document/assets/51815450/87b934f8-b944-4b9f-a1aa-6f306ecbf3fa)

| **Category** | **Item**                                                    | **Description**                                                                                                                                                              |
|--------------|-------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Build Target | Search Only Enabled                                         | Whether to ensure that only valid plugins appear in the list of build targets.                                                                                               |
|              | Contains Project Plugins                                    | Whether to make plugin  in the project's plugins folder appear in the list of build targets.                                                                                 |
|              | Contains Engine Plugins                                     | Whether to make plugins in the engine's plugins folder appear in the list of build targets.                                                                                  |
| Output       | Select Output Directory Manually                            | Whether to select the output directory before starting the packaging process.                                                                                                |
|              | Output To Build Directory Of Each Project                   | Whether to use the Build directory for each project as the output directory.                                                                                                 |
|              | Output Directory Path                                       | A path to the directory where the packaged plugin will be output.                                                                                                            |
| Misc         | Use Friendly Name                                           | Whether to use friendly names in plugin output files, editor menus, etc.                                                                                                     |
|              | Show Only Logs From This Plugin When Package Process Starts | Whether to change the output log filter to show only log categories for this plugin when starting the package process.<br/>This feature is only available in UE5.1 or later. |
|              | Stop Packaging Process Immediately                          | Whether to stop the packaging process as soon as the cancel button is pressed during packaging.<br/> !!CAUTION!! You may get an error from UBT as it kills the process.      |

## License

[MIT License](https://en.wikipedia.org/wiki/MIT_License)

## Author

[Naotsun](https://twitter.com/Naotsun_UE)

## Development Cooperation

[@RyanDowlingSoka](https://twitter.com/RyanDowlingSoka)

## History

- (2023/09/07) v1.4  
  Added support for UE5.3

- (2023/06/26) v1.3  
  Added All to engine version preset button  
  Changed to remember the value for each project only for build targets  
  Changed to use UAT's Zip Utils for zip file compression  

- (2023/05/09) v1.2  
  Added option to use plugin Friendly Name for editor tool menu, output directory name, etc.  
  Added option to include Binaries in zip file  
  Added option to output all zip files to one directory  
  Added option to copy .uplugin file properties to exported plugins  
  Added an option to the editor preferences to show only this plugin's log in the output log when package processing is started (Only available in UE5.1 or later)  
  Added preset button to tool menu to select engine version  
  Added support for UE5.2  

- (2023/05/09) v1.1  
  Fixed a bug that the successful editor notification was displayed even if there were errors  

- (2023/05/07) v1.0   
  Publish plugin
