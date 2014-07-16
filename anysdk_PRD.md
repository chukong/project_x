# AnySDK Integration Product Requirements Document

## Revisions

v0.1 2014-07-16: Initial version

# INTRODUCTION

## Description

Services is one of the ways to monetize Project X. And AnySDK is one of the services that we provide.

Seamless integration between games and AnySDK is key, not only because we can monetize it, but also because our users need it. They also want to monetize their games.

The user probably won't care about AnySDK. What he wants is to use certain services (eg: I want to use Facebook, or monetize my game using Ads), but AnySDK should be the easiest way to integrate those services with cocos2d-x games.


## Use Cases

### 1. Add Ads into an already created Project X game

* User creates a Project X game.
* When User is about to finish the game he wants to add Ads into its game.
* User wants to see how the Ads look inside the game without registering a username in the Ads service.
* If he likes how the Ads look, he will create an account and setup the Ads params


### 2. Add Ads into an already created Cocos2d-x game

Similar to Use Case #1, but in this case the User wants to add Ads into a Cocos2d-x (not Project-X) game


### 3. See how the Ads perfom

* After the game is published the User would like to know how the Ads perform.


# SPECIFIC REQUIREMENTS
## Functional Requirements

Refer to the Use Cases to understand the rationale behind the requirements.

### AS-0001 - Add US Services into AnySDK: Vungle

* Add Vungle SDK into AnySDK for iOS and Android
* Make necessary changes to the AnySDK API if needed

### AS-0002 - Add US Services into AnySDK: Kochava

* Add Kochava SDK into AnySDK for iOS and Android
* Make necessary changes to the AnySDK API if needed

### AS-0003 - Add US Services into AnySDK: Chartboost

* Add Chartboost SDK into AnySDK for iOS and Android
* Make necessary changes to the AnySDK API if needed

### AS-0004 - Add US Services into AnySDK: Facebook

* Add Facebook SDK into AnySDK for iOS and Android
* Make necessary changes to the AnySDK API if needed

### AS-0005 - Add US Services into AnySDK: Google Play Basic

* Add Google Play SDK into AnySDK for iOS and Android
* Make necessary changes to the AnySDK API if needed
* It should include the following services:
  * Login
  * Leaderboard
  * Achievements
  * In App Purchases

### AS-0006 - Add US Services into AnySDK: Google Play Advanced

* Add Google Play SDK into AnySDK for iOS and Android
* Make necessary changes to the AnySDK API if needed
* It should include the following services:
  * Quests
  * Ads
  * Multiplayer: Turn-by-Turn 
  * Multiplayer: Realtime


### AS-0007 - Templates: Blank

* Project X must have a "Blank" Template
* It only has the needed code to compile and run the game.
* Nothing will appear on the screen since it is a blank game
* The template must be available for the following languages:
   * Lua
   * C++

### AS-0008 - Templates: Basic

* Project X must have a "Basic" Template
* _Basic_ template must include:
   * Main Menu Scene: two buttons, Game and About
   * Game Scene: must have an sprite and a back button
   * About Scene: must display a label and a back button
* _Basic_ template must have AnySDK code commented out
* The template must be available for the following languages:
   * Lua
   * C++


### AS-0009 - Templates: Facebook

* Project X must have a "Facebook" Template
* _Facebook_ template must show how to use Facebook
* The template must be available for the following languages:
   * C++

### AS-0010 - Templates: Google Play Services

* Project X must have a "Google Play Services" Template
* _Google Play Services_ template must show how to use Google Play Services
* The template must be available for the following languages:
   * C++


### AS-0011 - Templates: Vungle

* Project X must have a "Vungle" Template
* _Vungle_ template must show how to use Vungle Ads
* If possible, template shall run with a Test key, so the user doesn't need to provide a real key
* The template must be available for the following languages:
   * C++


### AS-0011 - Templates: Kochava

* Project X must have a "Kochava" Template
* _Kochava_ template must show how to use Kochava
* If possible, template shall run with a Test key, so the user doesn't need to provide a real key
* The template must be available for the following languages:
   * C++

### AS-0012 - Templates: Chartboost

* Project X must have a "Chartboost" Template
* _Chartboost_ template must show how to use Chartboost
* If possible, template shall run with a Test key, so the user doesn't need to provide a real key
* The template must be available for the following languages:
   * C++

### AS-0013 - Templates: Chinese Services ???

* Project X must have a template that shows how to use XXX (complete with Chinese services)


### AS-00014 - Project-X Installer SDK

* Project X shall install AnySDK libraries for all the supported platforms, where applicable.
* That includes all the Chinese and US services included in AnySDK

### AS-0015 - Project-X Installer Templates

* Project X shall install the templates, and setup (or just copy) a manifest file that includes:
   * Available templates
   * Name of the template
   * Description of the template
   * Category of the template: Like 'Default', 'Services'
   * Language used by the template: Lua, Cpp, JS
   * Path where the template is

### AS-0015 - Cocos Command Line Integration

* User shall be able to create any of the templates by using the Cocos Command Line Tool.
* Cocos Command Line Tool shall be able to parse the manifest file installed by the installer, and use any of the available tempaltes.

As an example, the user shall be able to do:

    $ cocos new MyGame --template Basic
    
or:

    $ cocos new MyGame --template Facebook 

### AS-0016 - Adding new templates

* Adding a new template into Project X shall be "easy"

By "easy", we mean something like:

* Adding the needed files to a certain folder
* Editing the Template Manifest file with the name, description, language, category and template path  


### AS-0017 - Launcher integration

* Launcher shall parse the Tempalte Manifest file and display the available options on the launcher
* Launcher shall display the available templates separated by the template's category

### AS-0018 - Project X project file: AnySDK settings

* Newly created games, as specified in the Launcher PRD, must create a Project X configuration file
* This file shall have a section for AnySDK. The AnySDK settings shall have
   * Information about all the available AnySDK services
   * Whether or not the services are enabled / disabled
   * Parameters for each service. Eg: Vungle Key for the Vungle services

### AS-0019 - Editing AnySDK settings: Cocos Studio

* User shall be able to edit the AnySDK settings of the Project X project file within Cocos Studio

A proposed workflow is:

* User double-clicks on the Game project file. This will open Cocos Studio
* From Cocos Studio, the User will click on File -> Project Settings
* A dialog with the Project Settings will appear
* User clicks on the AnySDK panel
* And from there the enables/disables/edits the different AnySDK services


### AS-0020 - Editing AnySDK settings: Text editor

By opening the Project X project file, the user shall be able to edit/enable/disable AnySDK services by using a regular text editor.

If the user breaks the file, it is Users responsibility.

### AS-0021 - AnySDK Repository

The AnySDK git repository shall be:

* public
* and in the Chukong organization

### AS-0022 - AnySDK API

* User shall be able to change the AnySDK services/settings from a config file.
* The current way of doing it is by calling an API. This way should still work, but the recommended way is to use a configuration file.

The benefits of using a configuration file are:

* User don't need to change code. The code will be the same.
* Easier to edit the AnySDK settings. Everything is located in one file


## Technical Requirements
TODO

## Integration
TODO

## Workflow, Timelines And Milestones

Milestone #1 (For the September 2014 Conference) we need all the above mentioned features.

## Evaluation Plan
TODO

## Performance Metrics
TODO

# ADDITIONAL MATERIALS
TODO

## Definitions

__AnySDK__: Is plugin-X

__Packager__: Is what in China is known as AnySDK


