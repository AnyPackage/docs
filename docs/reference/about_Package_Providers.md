---
title: about_Package_Providers
parent: About
grand_parent: AnyPackage
nav_order: 3
---

# Package_Providers

## about_Package_Providers

## Short Description

Describes what a `AnyPackage` package provider is and how to use it.

## Long Description

A package provider is used to extend `AnyPackage` module.
This article contains information with interacting with package providers.

## Importing a Package Provider

Importing the `AnyPackage` module will not automatically load package providers.
The user is responsible for which providers are available.
To import a package provider run `Import-Module` with the module containing the provider.

> NOTE! Once a package provider is imported trying to load a different version requires PowerShell to be restarted.
This is due to how .NET does not reload types.

## Removing a Package Provider

To remove a package provider run `Remove-Module` containing the provider.
To confirm package provider has been removed run `Get-PackageProvider`.

## Provider Specific Parameters

Package providers can provide additional parameters in the context of provider and operation being performed.
For example, the `PowerShellGet` provider adds the `Tag` parameter to `Find-Package`.

Provider specific parameters are only available when the `-Provider` parameter is used. In the `PowerShellGet` example the command would be `Find-Package -Provider PowerShellGet -Tag DSC`.

The PowerShell engine has some limitations at this time on how discoverable dynamic parameters are.
To make this as easy as possible use the following recommendations:

* `Provider` parameter should be before any provider specific parameters.
* Use `PSReadLine` menu complete (CTRL+SPACE) or tab completion.

Here is an example of using `PSReadLine` menu complete and provider parameters.
The first command is using menu complete without any parameters.
Take note of how `Tag` is not present.
Type `Find-Package -` followed by CTRL+SPACE to bring up menu complete.

```powershell
Find-Package -
Name                 Provider             WarningAction        InformationVariable
Version              Verbose              InformationAction    OutVariable
Source               Debug                ErrorVariable        OutBuffer
Prerelease           ErrorAction          WarningVariable      PipelineVariable
```

Now we will add `-Provider PowerShellGet` to add the provider parameters.
Take note of how `Tag` is now available to use and the tooltip at the bottom gives the parameter type.

```powershell
Find-Package -Provider PowerShellGet -Tag
Name                 Tag                  ErrorAction          WarningVariable      PipelineVariable
Version              Type                 WarningAction        InformationVariable
Source               Verbose              InformationAction    OutVariable
Prerelease           Debug                ErrorVariable        OutBuffer

[string[]] Tag
```

## Provider Priority

A priority system is used to allow only a single provider to perform an action on a package name even if that package exists in multiple providers.
The commands that use the priority system are:

* Install-Package
* Save-Package
* Uninstall-Package

For example, lets say a user tries to install a package `Microsoft.PowerShell.Security`. This package exists in the `PowerShellGet` and `NuGet` provider.
If the user were run `Install-Package -Name Microsoft.PowerShell.Security` which provider would take priority? To answer that question lets describe how the priority systems works.

The priority scale is from `0-255` with a default value of `100`.
A lower number is higher priority.
If multiple providers have the same priority value then the provider's `FullName` will be used.
The provider `FullName` is the module and provider name in this format: `Module\Provider` for example, `PowerShellGet` provider would be `AnyPackage.Provider.PowerShellGet\PowerShellGet`.

To view a provider's priority use the `Get-PackageProvider` command.

```powershell
Get-PackageProvider

Name                 Priority Operations
----                 -------- ----------
NuGet                     100 Find, Get, Publish, Install, Save, Uninstall, Update, GetSource, SetSource
PowerShellGet             100 Find, Get, Publish, Install, Save, Uninstall, Update, GetSource, SetSource
```

To change a provider's priority first get the provider with `Get-PackageProvider` and save it to a variable.
Then set the `Priority` property with the new priority.

```powershell
$provider = Get-PackageProvider -Name PowerShellGet
$provider.Priority = 50
Get-PackageProvider -Name PowerShellGet

Name                 Priority Operations
----                 -------- ----------
PowerShellGet              50 Find, Get, Publish, Install, Save, Uninstall, Update, GetSource, SetSource
```

## See Also

* [about_Creating_Package_Providers](about_Creating_Package_Providers.md)
* [about_AnyPackage](about_AnyPackage.md)
