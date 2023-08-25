---
title: "Console"
permalink: /features/console
excerpt: "Functionality of Kdb Console tool window"
toc: true
---

## Overview

The _Kdb Console_ tool window is located in the left bottom corner and hidden by default. You have to click on
it to activate the console.

By default, the console is empty, and you have to connect to an instance in
the [Instances Tree](/features/instances#connections) or with [active connection](/features/instances#active-connection)
.

Another way to create new connection and start new console - just create new connection directly from the console by _+_
sign in the title of the console windows:

![consoleBlank](/assets/images/features/console/consoleBlank.png)

## Console Tab

Each connected instance has many tabs in the console of two types:

- **Console** tab is command line view where you can send commands to the instance and see its results. If [Watches Panel](/features/watches) is enabled it's displayed in the right part of the console.

![watches.png](/assets/images/features/console/consoleWatches.png)

- **Table Result** and all other tabs - on demand tabs which shown when you have a table/dict/list as result or expand
  any exist table result.

![consoleTabs](/assets/images/features/console/consoleTabs.png)

Please check [Tables](/features/tables) secton to get more details.

## Toolboxes

There are many toolboxes in a _Console View_:

- **Console View Toolbox** related to the instance itself on the left side where you can:
    - Connect/Disconnect the instance
    - Quickly change the instance settings, like name or connection parameters
    - Stop active query, if possible
    - [Watches](/features/watches) expressions
    - Upload any file to the instance
    - Open local binary file with KDB data encoded into IPC format
    - Change the Console view layout with two options
    - and finally, just close the connection and remove the _Console View_
- **Console Toolbox** where you can manage output of the commands, like:
    - should be text in the console wrapped to new line if it's too long
    - should be new output auto-visible
    - is history of all commands should be visible
    - and finally ability to clean all history for the console
- Each **Table Result** has own toolbox with huge functionality. Please check [Table View](/features/tables) section to
  get more details about _Table Result_ view.

## View Layout

By default, _Console_ table and each _Table Result_ are placed in separate tabs, and you have to switch between them to
check a table result and output of the console from the toolbox:

![consoleLayout](/assets/images/features/console/consoleLayout.png)

where:

- **Tabs view** - is default view when each result is located in separate tab
- **Split Down** - the console tab will be placed at the top but all Table Result tabs at the bottom:<br>
  ![consoleLayoutDown](/assets/images/features/console/consoleLayoutDown.png)
- **Split Right** - the console tab will be placed on the top but all Table Result tabs on the right:<br>
  ![consoleLayoutRight](/assets/images/features/console/consoleLayoutRight.png)

Depends on your working place one or another layout may be more suitable for you.

You can change default layout for all _Console Views_ in [Configuration Options](/settings/options).
{: .notice--info}

## Rename/Pin Tab

By default, each instance has only one _Table Result_ tab that is updating each time when new table/dict/vector is
received, but you can pin any _Table Result_ by renaming the tab.

Just double-click on a _Table Result_ header or right-click on it to see context menu:

![consoleRenameTab](/assets/images/features/console/consoleRenameTab.png)

The tab will be renamed and new _Table Result_ will be opened for new data:

![consolePinnedTab](/assets/images/features/console/consolePinnedTab.png)

You should remember that each _Table Result_ takes memory depends on how much data you have. If you don't have memory -
probably it's time to close some tabs.
{: .notice--info}

## Floating Results

Although _Console_ tab is always pinned to the _Console View_, you can drop out and drag in any _Table Result_ tabs to
create separated window:

![consoleFloatingResult](/assets/images/features/console/consoleFloatingResult.png)

Each floated _Table Result_ has own context and expanding table cells will be opened as new tab of the window rather
than in the _Console View_

## Uploading File

You can upload any local file to the instance with _Upload File_ functionality:

![consoleUploadFile](/assets/images/features/console/consoleUploadFile.png)

There are two options how a file can be uploaded and that is driven by the option in uploading dialog:

- _binary file_ - uploaded as array of bytes
- _text file_ - uploaded as array of strings where each string is in the array is a line in the text file.

The plugin tries to guess a file type but please make sure that the type is correct before uploading the file.
