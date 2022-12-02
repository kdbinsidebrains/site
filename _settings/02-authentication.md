---
title: "Authentication"
permalink: /settings/authentication
excerpt: "Default authentication and custom authentication plugins"
toc: true
---

## Overview

There are three levels where you can change authentication settings for an instance applying in the following order:

- You can define authentication settings for an instance which will be used at the first place
- If an instance has no authentication settings, settings from its scope will be used
- If a scope has no settings, then default settings will be used

You can define default authentication settings in default settings at _Connections_ tab:

![authenticationMain](/assets/images/settings/authentication/authenticationMain.png)

## Custom Authentication

One of the plugin's ability is to ability to create custom authentication plugin that can be added in _Connections_ tab:

![authenticationPlugin](/assets/images/settings/authentication/authenticationPlugin.png)

There are 3 classes which you should implement for:

~~~ java
import org.kdb.inside.brains.core.credentials.CredentialEditor;
import org.kdb.inside.brains.core.credentials.CredentialProvider;
import org.kdb.inside.brains.core.credentials.CredentialsResolvingException;
~~~

and add one property into you Manifest file:

~~~ java
CredentialsProvider: <your class>
~~~

There is a small example created that does nothing but could be a good
start: [https://github.com/kdbinsidebrains/credentials]()