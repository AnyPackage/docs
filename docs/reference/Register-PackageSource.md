---
external help file: AnyPackage.dll-Help.xml
Module Name: AnyPackage
online version: https://go.anypackage.dev/Register-PackageSource
parent: AnyPackage
schema: 2.0.0
---

# Register-PackageSource

## SYNOPSIS

Registers a package source.

## SYNTAX

```powershell
Register-PackageSource [-Name] <String> [-Location] <String> [-Provider] <String> [-Trusted] [-PassThru]
 [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Registers a package source.

## EXAMPLES

### Example 1

```powershell
Register-PackageSource -Name Test -Location C:\TestRepo -Provider PowerShellGet
```

This command registers a package source named `Test` for the `PowerShellGet` provider.

## PARAMETERS

### -Force

Overwrite the source if it already exists.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Location

Specifies the package source location.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

Specifies the name of the package source.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -PassThru

Returns a PackageSourceInfo object that represents the source that was registered.
By default, `Register-PackageSource` doesn't generate any output.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Provider

Specifies the package provider.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Trusted

Specifies the package source is trusted.
Stops prompts for an untrusted source when installing packages.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm

Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

You can use the pipeline to send a string for the source name.

## OUTPUTS

### AnyPackage.Provider.PackageSourceInfo

By default, this cmdlet doesn't return any objects. Use the `PassThru` parameter to a return objects that represent a package source.

## NOTES

## RELATED LINKS

[Get-PackageSource](Get-PackageSource.md)

[Set-PackageSource](Set-PackageSource.md)

[Unregister-PackageSource](Unregister-PackageSource.md)
