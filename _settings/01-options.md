---
title: "Configuration Options"
permalink: /settings/options
excerpt: "Plugin configuration options"
toc: true
---

## Overview

The plugin has a set of [configuration settings](https://www.jetbrains.com/help/idea/settings-preferences-dialog.html)
available in _Language & Frameworks_ section for KDB+ Q language:

![optionsMain](/assets/images/settings/options/optionsMain.png)

All they are splat by categories for better orientation.

## Console Options

_Console options_ relating to all settings for [Kdb Console](/features/console).

## Execution Options

_Execution Options_ sometimes are more tricky, so it's better to provide some explanation here.

### Log Queries

if enabled, when you execute a query in a [console](/features/console), your query is logged into **.kdbinb** folder of
your project with an additional option (enabled by default) to split files by months folders.

![optionsLogQuery](/assets/images/settings/options/optionsLogQuery.png)

If slip is enabled, a log file will be stored in a directory the current year and month, like 2022.12:

~~~
.kdbinb
    /2022.11
        queries2022-11-01.log
        .
        queries2022-11-30.log
    /2022.12    
        queries2022-12-01.log
        .
        queries2022-12-31.log
~~~

If the option is disabled, all log files will be stored in root **.kdbinb** folder.

Each log file is splat by dates and each query has a header in format:

~~~
 <timestamp>, <instance uri>, <instance name>, <roundtrip, nanos>, <result type or error message>
 <Full query>
 <line separator>
~~~

and a simple log looks like:

~~~ q 
/ 2022-12-02D16:37:09.822185100, `:localhost:5011, Local Instances/uat/RDB, 13662400, long
10+20
~~~

### Normalize Query

When you load a script to KDB instance with _\l xxx_ or _system "l xxx"_ command, you can have no problems, but when you
try to execute the same code from the editor, sometimes it fails.

It happens for two reasons:

1. KDB interpreter doesn't process load instructions (_\l xxxx_) and if the options are enabled, all load instructions are
   converted to system load calls (_system "l xxx"_)

2. The issue is related to closing curly bracket indent placed on new line. Let's suppose you have the following code:

~~~
.my.func1:{
}

.my.func2:{
}
~~~

this code will be loaded with no errors from a file but doesn't work when you'll try to execute it. We are not sure, is
it the issue in KDB lib or expected behaviour, but closing curly bracket must have one space before and semicolon after:

~~~
.my.func1:{
 };

.my.func2:{
 };
~~~

if the option is enabled, the plug updates the code in the appropriate way as well to fix the issue.

As the option updates original code, it's possible that something code go wrong. Please be careful with it.
{: .notice--warning}

### Binding Strategy

When you have many open source files and many connections, probably that you work with all of these simultaneously and a
legitimate question arises: how to manage a file with a connection?

The plugin provides three options here:

- **Manual binding** - default options and editors are independent of active connection. That means when you change
  active connection or active editor tab, you have to make sure you are working with correct instance. In this mode you
  can also use manual binding button on the main toolbar:<br>
  ![optionsBindConnection](/assets/images/settings/options/optionsBindConnection.png)<br>
  and when you open an editor with bound connection, the connection will be activated. If you open another tab without
  binding - active connection won't be changed
- **Bind a tab to the connection** - Each activated editor is binding to active connection and the connection will be
  selected each time when the editor is activated.
- **Bind a connection to the tab** - When active connection is changed, new connection is binding to current editor and
  will be auto-selected each time when the tab is activated. No binding is happened if active connection is not changed.

### Oversized response

The plugin checks the size of a response received from the server. There is nothing wrong with big responses, but as IDEA
is Java-based application, the application has memory limits, you can easily get OutOfMemory, so the plugin shows a
warning message if the response is more than a specified threshold:

![optionsOversizedResponse](/assets/images/settings/options/optionsOversizedResponse.png)

Please check [tricks](/tricks#memory) page to find out how to increase memory for IntelliJ IDEA
{: .notice--info}