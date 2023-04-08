---
external help file: AnyPackage.dll-Help.xml
Module Name: AnyPackage
online version: https://go.anypackage.dev/Publish-Package
parent: AnyPackage
schema: 2.0.0
---

# Publish-Package

## SYNOPSIS

Publishes a package.

## SYNTAX

```none
Publish-Package [-Path] <String> [-Provider] <String> [-Source <String>] [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Publishes a package.

## EXAMPLES

### Example 1

```powershell
PS C:\> Publish-Package -Path C:\module -Provider PowerShellGet -Source PSGallery
```

This command publishes the module to `PSGallery` using the `PowerShellGet` provider.

## PARAMETERS

### -PassThru

Specifies if the package information should output.

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

### -Path

Specifies the path to the package.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Provider

Specifies the package provider.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Source

Specifies the package source.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Repository

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

You can a path to this cmdlet.

## OUTPUTS

### AnyPackage.Provider.PackageInfo

By default, this cmdlet doesn't return any objects. Use the `PassThru` parameter to a return objects that represent a package.

## NOTES

## RELATED LINKS

[Get-Package](Get-Package.md)

[Find-Package](Find-Package.md)

[Install-Package](Install-Package.md)

[Save-Package](Save-Package.md)

[Update-Package](Update-Package.md)

[Uninstall-Package](Uninstall-Package.md)
