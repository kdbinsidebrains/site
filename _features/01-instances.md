---
title: "Instances"
permalink: /features/instances
excerpt: "KDB Scopes and Instances manager"
toc: true
---

## Active Connection

There are many ways how you can connect to a KDB instance, and the fastest one is to use active 'Kdb Connection'
combobox in
the toolbar:

![toolbarConnectionBox](/assets/images/features/instances/toolbarConnectionBox.png)

The ComboBox contains a list of active connections which you can switch between as well as a list of disconnected
instances
since the last IDEA restart:

![toolbarConnectionList](/assets/images/features/instances/toolbarConnectionList.png)

Another feature of the 'Kdb Connection' toolbox is searching or filtering instances by typing its name or URI:

![toolbarConnectionFiltering](/assets/images/features/instances/toolbarConnectionFiltering.png)

And the last one ability is to just create a new connection for non-exist instance by typing its full URI:

![toolbarConnection](/assets/images/features/instances/toolbarConnection.png)

and you can create a free configured instance with default settings, or you can select a Scope which new instance will
belong to. In the last case, the Scope parameters, like credentials and encoding, will be used.

## Scopes

### New Scope

'_Kdb Instances_' or '_Scope Manager_' is a tool windows located at the top right:

![scopesEmpty](/assets/images/features/instances/scopesEmpty.png)

All scopes and instances created in a scope as stored in IDEA configuration files and can belong to a project or shared
across many projects.

You can create new scope by '_Create New Scope_' button in the middle of the tool windows you use or right-click on the
tool windows tab to open a menu for scopes management as well as for importing a scope or exporting the current one.

![scopesMenu](/assets/images/features/instances/scopesMenu.png)

You also can use the appropriate button in the tool windows toolbar to load _Scopes Management_ dialog.
{: .notice--info}

If someone in your team already uses the plugin, you can ask her or him to export required scopes and import it on your
side.
{: .notice--info}

### Scope Dialog

The _Scope Dialog_ is the main and only one place where you can manager your scopes:

![scopesDialog](/assets/images/features/instances/scopesDialog.png)

There are two types of scopes:

- _Local_ - a local scope configuration and all defined instances are stored only in the project configuration file. If
  you'd like to use the same scope in another project, you have export and import the scope or make it shared
- _Shared_ - a shared across all project (where the plugin is enabled
  by [adding new module or framework](/project/module)) scope. Configuration files and defined instances are stored in
  the IDEA configuration files instead of a project and changing the scope content affects all projects.

You can change a scope type just by clicking on checkbox next to the scope name.
{: .notice--info}

Each scope contains can redefine [default authentication parameters](/settings/authentication) as well
as [connection options](/settings/authentication).

Each scope defined in the _Scope Dialog_ is shown as a separate tab in the tool window:
![scopesTabs](/assets/images/features/instances/scopesTabs.png)

### Scope Import/Export

Any scope can be exported into XML file:
![scopesExport](/assets/images/features/instances/scopesExport.png)

One thing to remember: when you export your scope, you should explicitly approve if you'd like to export all credentials
as well, or they must be ignored:
![scopesExportWarn](/assets/images/features/instances/scopesExportWarn.png)

## Instances

### Instances Tree

You can organize instances inside a scope in a tree-link structure for simpler organization. Just use the toolbar or
right-click to get the menu:  
![instancesMenu](/assets/images/features/instances/instancesMenu.png)

You can use drag-and-drop to manage the InstancesTree. You can hold _Ctrl_ button at dragging time to create a copy.
{: .notice--info}

### Highlighting Severity

If some of your instances are more important, and you'd like to protect yourself from mistakes, you can mark such
instances or a subtree with all instances by a color:

![severityMenu](/assets/images/features/instances/severityMenu.png)

After a color selection:

- all instances in the _Instances View_ will be marked with the color

- the same color will be used in _Connection ComboBox_:<br>
  ![severityCombobox](/assets/images/features/instances/severityCombobox.png)

- and the same color will be used to mark _Console_ tab in [Kdb Console](/features/console):<br>
  ![severityConsole](/assets/images/features/instances/severityConsole.png)

You can disable console background coloring in [the plugin options](/settings/options) if you don't like it and
leave only the _Console_ tab color:<br><br>
![severityDisableBackground](/assets/images/features/instances/severityDisableBackground.png)
{: .notice--info}

### Searching and Replacing

If your InstancesTree is quite big, you can straggle with finding required instance. There are two options that you
can use to search and one to replace instance parameters in the InstancesTree:

- **Quick Search** the search is activated by _Ctrl+F_ or from the context menu or starting typing when
  the InstancesTree component has focus:

![instancesQuickSeach](/assets/images/features/instances/instancesQuickSeach.png)

In this mode, a space is used as a tokens' separator and an instance that contains all the tokens will be selected and
highlighted.
You can use arrows up and down to move over found instances.

- **Search by Parameters** is activated by _Ctrl+Shift+F_ or from the context menu and is stricter than quick
  search functionality as search by the instance name or address and using a matching case, whole world or RegEx
  ![instancesSeachByParameters](/assets/images/features/instances/instancesSeachByParameters.png)

- **Replace by Parameters** is activated by _Ctrl+Shift+R_ or from the context menu and additionally
  to _Search by Parameters_ allows replacing found parameters

![instancesReplaceByParameters](/assets/images/features/instances/instancesReplaceByParameters.png)

Additional filter allows to search/replace in only in the name or in the address, if required.

![instancesReplaceByParametersFilter](/assets/images/features/instances/instancesReplaceByParametersFilter.png)

### Instances Import/Export

Apart from Importing/Exporting whole scope, you also can Import/Export an instance or a subtree from the context menu:

![instancesIE](/assets/images/features/instances/instancesIE.png)

Export is done in the same format as a scope exporting, and any scope can be imported as a subtree of another scope, if
required.

You also can import data from another application. Please check _Import->Import from ..._ submenu of the context menu
to get list all supported formats.

## Connections

Double-click on any instance in the tree open connection to the instance. If an instance is already connected, it will
be
activated.

Connected instances market with bold text and last status and update time shown in the tree.

Failed instances (connection was lost or can't be created) highlighted with red color.

## File format

A scope Import/Export file format is XML-based and is very simple. The file can be generated from any application and
imported into the _InstancesTree_:

An example of the file:

~~~ xml
<scopes>
  <scope name="Local Instances" type="LOCAL">
    <package name="prod" color="#ffecec">
      <instance name="`:localhost:9090" host="localhost" port="9090" />
    </package>
    <package name="uat">
      <instance name="`:localhost:9090" host="localhost" port="9090" />
      <instance name="`:localhost:9091" host="localhost" port="9091" />
    </package>
  </scope>
</scopes>
~~~