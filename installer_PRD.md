# Project X's Installer Product Requirements Document

## Revisions

v0.1 2014-07-10: Initial version

# INTRODUCTION

## Description

_Installer_ is responsible for installing and setting up Project X.

Installing means: Placing the Project X files in the _correct_ place.
Setting Up means: Making the necessary changes in the system so that Project X can be used.

## Requirements

### IN-0001: Download From Homepage

User shall be able to download the installer from Project X's homepage.
There must be an installer for Mac computers and another for Windows computers.

### IN-0002: Download for correct OS

The homepage should detect the Browser's Operating System, and highlight the correct installer for the Browser Operating System.

As an example, if the user is trying to download Project X with Firefox for Mac, the download page should highlight the download version for Mac.
Users should be able to download the Windows or Mac version regardless of the Browser operating system.

### IN-0003: Installer Packaging

* The Mac version could be either a .pkg or a .dmg file, but avoid putting a .pkg inside a .dmg since it is redundant.
* The Windows version could be a .zip file or any other popular package size for windows


### IN-0004: Verified Packager

The installer must be signed (verified) in order to prevent the following dialog:

![](https://raw.githubusercontent.com/chukong/project_x/master/images/installer-verified.png?token=232330__eyJzY29wZSI6IlJhd0Jsb2I6Y2h1a29uZy9wcm9qZWN0X3gvbWFzdGVyL2ltYWdlcy9pbnN0YWxsZXItdmVyaWZpZWQucG5nIiwiZXhwaXJlcyI6MTQwNTcxMTA2NH0%3D--cf1d12a34673f811454132c259566691a626cb64)


### IN-0005: Placing the files Application

The install shall place all the needed files (Launcher, Cocos Studio, Cocos Code IDE, Cocos Command Line Tools, Game Templates, needed libraries for different platforms, etc.) in:

* `/Applications/Project X` folder for Mac  (`Project X` is just a temporal name. It shall be replaced by the final name once we have it)
* TODO for Windows


### IN-0006: Configuring the NDK

The installer must be able to setup the Android NDK.

If Android NDK is already installed:

* It should ask the user where it is located, and verify that the location provided by the user is correct
* And use the location provided by the user for Project X

If Android NDK is not installed:

* It shall download the latest stable version of the NDK and install it under `/Applications/Project X/ndk/` (for Windows, it should be placed in... TBD)
* And use it

Setting up the NDK is an optional step. The user shall be able to Skip this step. If he does so, he shall be able to setup the NDK later. TBD


### IN-0007: Configuring Xcode

__Mac Only__: If the Xcode is not already installed if shall tell the user to install it, and open the Xcode's page in the Apple Store.


### IN-0008: Configuring the Cocos Command Line Tool

The Cocos Command Line tool shall be added into the path.

The user shall be able to run the Cocos Command Line Tool from a console once the installation is finished


### IN-0009: Launcher

After the installation is finished, it shall launch the Launcher. The user shall be able to create a game (by using the Launcher) right after the installation.



### IN-0010: App Store

__Mac Only__: Product X shall be available on the Apple Store


## Timelines And Milestones

For the first release of Product X (September 2014), Requirements IN-0001 to IN-0010 must be done. The only requirement that can be added later is IN-0010.


## Additional comments

### .pkg or .dmg

__Mac Only__:

As mentioned in `IN-0003` the Installer shall use either .pkg or .dmg, but not both.

Benefits of DMG:

* User can install (drag & drop) the product where ever he wants. He just drag & drop to any folder
* Compatible with Apple Store


Benefits of PKG:

* Setup can be part of the installation


We have 2 requirements:

* Setup Project X during the installation
* Compatible with Apple Store

It is impossible to fulfill both requirements at the same time, but we can do something similar to Xcode.
Xcode is on the Apple Store, but it also needs to extra steps to work correctly, like downloading extra Simulators, or the documentation. Xcode does the extra steps the very first time that Xcode is executed. And we could do something like that for Project X.

