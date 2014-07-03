# Launcher Product Requirements Document

## Revisions

v0.1 2014-06-30: Initial version

# INTRODUCTION

## Description

_Launcher_ is one of the components that belong to _Cocos_. As described in the Cocos PRD, the Launcher is the first thing that is being launched when Cocos is executed.

## Use Cases

### 1. Login

In order to use _Cocos_, the User needs to register a developer account.

The user will launch Cocos, and the Login dialog will appear.

![Launcher Login Dialog](./Launcher%20-%20Login.png)

If the User has an account:
- The User must enter its user name and password.
- The username/password are going to be validated with the server
- If they are correct, the _Launcher Main Dialog_ dialog must appear
- If they are not correct, an error message must appear an the User should be able to enter its username/password again.

If the User doesn't remember its username and/or password, then there must be a way to recover them.

If the User doesn't have a developer account , the User will click on Create Account and the 'Create Account' dialog will appear:

![Launcher Registration Dialog](./Launcher%20-%20Registration.png)

The User must provide:

- Its real name (Name and Last Name)
- a desired user account name
- Its email

After creating the account, the user will be logged in, and _Launcher Main Dialog_ dialog must appear.

### 2. Create a new Game

In order to create a New Game, the User needs to launch _Cocos_.
If the User is not logged in, the Login dialog will appear. See Use Case #1.
If the User is already logged in, the _Launcher Main Dialog_ will appear.

![Launcher Main Dialog](./Launcher%20-%20Main%20Window.png)

Then the User must click on _New Game_ and the Launcher New Game Dialog must appear. The User must provide:

- Game Name
- Game company (needed for the ID)
- Game Genre:
    - Empty
    - Base
- Game Language:
    - Lua
    - C++
- Services to Use
    - Nothing
    - AnySDK
    - ???
- Directory where the project is going to be created
    - Possibility to create Git repository

![Launcher Registration Dialog](./Launcher%20-%20New%20Game.png)
![Launcher Registration Dialog](./Launcher%20-%20New%20Game%20-%20Directory.png)


### 3. Open an existing game

User can open an existing game by:

- Clicking on the _Recent Games_ list that is displayed on the _Launcher Main Dialog_
- Clicking _Open another game_ from the _Launcher Main Dialog_
- Double-clicking on the _Cocos_ project file (created by New Game)

### 4. Open News Feed
TODO

### 5. Logout
TODO

### 6. Edit User account
TODO

### 7. Use the Asset Store
TODO


# SPECIFIC REQUIREMENTS
## Functional Requirements

Refer to the Use Cases to understand the rationale behind the requirements.

### LN-0001 - Login
In case the User is not already logged in, the _Launcher_ must provide a way for the User to log in.

### LN-0002 - Create User
In case the User doesn't have a developers account, _Launcher_ must provide a way for the User to create a new account.
Creating the Account must be extremely easy and fast. 
See Intel's NDK as a reference.

### LN-0003 - Recover password / username
In case the User doesn't remember its username or password, _Launcher_ must provide a way for the User to recover them.

### LN-0004 - Create new game
_Launcher's Main Dialog_ must provide a way for the User to create a new game.
Basic game properties must be provided like:

- Game Name. Default value: "My Game"
- Company Domain. Default value: "my.company.com"
- Game Genre. Default value: "Base"
- Game Language. Default value: "C++"
- Integration with Services. Default value. AnySDK selected by default
- Destination folder. Default value: Previously used folder.
- Whether or not to create a Git repository locally. Default value. Disabled.

_Launcher_ shall invoke _Cocos Command Line Tool_ passing that information as arguments in order to create the new game.

### LN-0005 - Command Line Tool - Create New Game

`$ cocos new` shall keep working as it is today with the following additions:

It shall create a Cocos Project file with the following information:

- Game Name
- Company Domain
- Integrated services
- Source files being used
- Asset files being used

### LN-0006 - Cocos Project File Format

- The Cocos Project file shall be in text format. It could be in JSON, or XML or any other text format. JSON is preferred.
- It shall be possible the edit the Project File with any text editor, and within Cocos Studio by doing: Cocos Studio -> Project -> Edit Properties
- The Cocos Project file format could be the same as the Cocos Studio project file format.
- Cocos Studio shall be able to parse the Cocos Project file format
- The file extension shall be descriptive, something like 'cocosproj'. Example: "mygame.cocosproj"

For clarification purposes think of:

- The Cocos Project file is analogous the the Xcode project file
- Cocos Studio is analogous to Xcode: It is just a visual interface to the project file
- Cocos Command Line Tools is analogous to `xcrun`, the Xcode Command Line Tool. You can compile Xcode project and `xcrun`

### LN-0007 - Open existing project

_Launcher's Main Dialog_ shall display the 5 most recent used Cocos Projects.
Clicking in any of those projects shall open Cocos Studio with that project opened.

### LN-0008 - Double-Click on Cocos Project file

Double-Clicking on a Cocos Project File shall open Cocos Studio with that project opened.
If Cocos Studio is already opened, a new instance of Cocos Studio shall be created (similar to Xcode).

### LN-0009 - Open other projects

_Launcher's Main Dialog_ shall provide a way to open other Cocos Project that are not listed in the "Recently Used projects".
Clicking on the "Open another project" button shall let the user choose other projects by browsing the file system.

### LN-0010 - News feed

_Launcher's Main Dialog_ shall display Cocos News Feed (TBD)


### LN-0011 - Cocos Resources Links

_Launcher's Main Dialog_ shall have links to the following sites:

- Cocos Forum
- Cocos Documentation

(TBD)

### LN-0012 - Cocos Resources Links

_Launcher's Main Dialog_ shall have links to the following sites:

- Cocos Forum
- Cocos Documentation

(TBD)

### LN-0013 - Logout

_Launcher's Main Dialog_ shall provide a way for the User to logout

### LN-0014 - User Profile

_Launcher's Main Dialog_ shall provide a way for the User to access the User settings.
The User settings could displayed in the same _Launcher_ or it could open a web browser with the User settings.

### LN-0015 - One Developer Account

The Developer account used by the user must be the same account used by the forum, and future Cocos services.
With only one account our users shall be able to access all our services.


(TBD)



## Technical Requirements
TODO

## Integration
TODO

## Workflow, Timelines And Milestones

Milestone #1 (For the September 2014 Conference) we need all the above mentioned features with the exception of the Asset Store.
The News Feed is optional.

## Evaluation Plan
TODO

## Performance Metrics
TODO

# ADDITIONAL MATERIALS
TODO

