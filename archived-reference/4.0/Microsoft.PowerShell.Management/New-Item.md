---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 04/23/2019
online version: https://learn.microsoft.com/previous-versions/powershell/module/microsoft.powershell.management/new-item?view=powershell-4.0&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Item
---
# New-Item

## SYNOPSIS
Creates a new item.

## SYNTAX

### pathSet (Default)

```
New-Item [-Path] <String[]> [-ItemType <String>] [-Value <Object>] [-Force] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [-UseTransaction] [<CommonParameters>]
```

### nameSet

```
New-Item [[-Path] <String[]>] -Name <String> [-ItemType <String>] [-Value <Object>] [-Force]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-UseTransaction] [<CommonParameters>]
```

## DESCRIPTION

The `New-Item` cmdlet creates a new item and sets its value. The types of items that can be created
depend on the location of the item. For example, in the file system, `New-Item` creates files and
folders. In the registry, `New-Item` creates registry keys and entries.

`New-Item` can also set the value of the items that it creates. For example, when it creates a new
file, `New-Item` can add initial content to the file.

## EXAMPLES

### Example 1: Create a file in the current directory

This command creates a text file that is named "testfile1.txt" in the current directory. The dot
('.') in the value of the **Path** parameter indicates the current directory. The quoted text that
follows the **Value** parameter is added to the file as content.

```powershell
New-Item -Path . -Name "testfile1.txt" -ItemType "file" -Value "This is a text string."
```

### Example 2: Create a directory

This command creates a directory named "Logfiles" in the `C:` drive. The **ItemType** parameter
specifies that the new item is a directory, not a file or other file system object.

```powershell
New-Item -Path "c:\" -Name "logfiles" -ItemType "directory"
```

### Example 3: Create a profile

This command creates a PowerShell profile in the path that is specified by the `$profile` variable.

You can use profiles to customize PowerShell. `$profile` is an automatic (built-in) variable that
stores the path and file name of the "CurrentUser/CurrentHost" profile. By default, the profile does
not exist, even though PowerShell stores a path and file name for it.

In this command, the `$profile` variable represents the path of the file. **ItemType** parameter
specifies that the command creates a file. The **Force** parameter lets you create a file in the
profile path, even when the directories in the path do not exist.

After you create a profile, you can enter aliases, functions, and scripts in the profile to
customize your shell.

For more information, see [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)
and [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).

```powershell
New-Item -Path $profile -ItemType "file" -Force
```

> [!NOTE]
> When you create a file using this method, the resulting file is encoded as UTF-8 without a
> byte-order-mark (BOM).

### Example 4: Create a directory in a different directory

This example creates a new Scripts directory in the "C:\PS-Test" directory.

The name of the new directory item, "Scripts", is included in the value of **Path** parameter,
instead of being specified in the value of **Name**. As indicated by the syntax, either command form
is valid.

```powershell
New-Item -ItemType "directory" -Path "c:\ps-test\scripts"
```

### Example 5: Create multiple files

This example creates files in two different directories. Because **Path** takes multiple strings,
you can use it to create multiple items.

```powershell
New-Item -ItemType "file" -Path "c:\ps-test\test.txt", "c:\ps-test\Logs\test.log"
```

## PARAMETERS

### -Credential

> [!NOTE]
> This parameter is not supported by any providers installed with PowerShell. To impersonate another
> user or elevate your credentials when running this cmdlet, use `Invoke-Command`.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force

Forces this cmdlet to create an item that writes over an existing read-only item. Implementation
varies from provider to provider. For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).
Even using the **Force** parameter, the cmdlet cannot override security restrictions.

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

### -ItemType

Specifies the provider-specified type of the new item. The available values of this parameter depend
on the current provider you are using.

If your location is in a `FileSystem` drive, the following values are allowed:

- File
- Directory
- Junction
- HardLink

When you create a file using this method, the resulting file is encoded as UTF-8 without a
byte-order-mark (BOM).

In a `Certificate` drive, these are the values you can specify:

- Certificate Provider
- Certificate
- Store
- StoreLocation

For more information see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

```yaml
Type: String
Parameter Sets: (All)
Aliases: Type

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

Specifies the name of the new item.

You can specify the name of the new item in the **Name** or **Path** parameter value, and you can
specify the path of the new item in **Name** or **Path** value.

```yaml
Type: String
Parameter Sets: nameSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path

Specifies the path of the location of the new item.
Wildcard characters are permitted.

You can specify the name of the new item in **Name**, or include it in **Path**.

```yaml
Type: String[]
Parameter Sets: pathSet, nameSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -UseTransaction

Includes the command in the active transaction. This parameter is valid only when a transaction is
in progress. For more information, see [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: usetx

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Value

Specifies the value of the new item. You can also pipe a value to `New-Item`.

```yaml
Type: Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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
Default value: False
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
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`,
`-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`,
`-Verbose`, `-WarningAction`, and `-WarningVariable`. For more information, see
[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## INPUTS

### System.Object

You can pipe a value for the new item to this cmdlet.

## OUTPUTS

### System.Object

This cmdlet returns the item that it creates.

## NOTES

`New-Item` is designed to work with the data exposed by any provider. To list the providers
available in your session, type `Get-PsProvider`. For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

## RELATED LINKS

[Clear-Item](Clear-Item.md)

[Copy-Item](Copy-Item.md)

[Get-Item](Get-Item.md)

[Invoke-Item](Invoke-Item.md)

[Move-Item](Move-Item.md)

[Remove-Item](Remove-Item.md)

[Rename-Item](Rename-Item.md)

[Set-Item](Set-Item.md)

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)
