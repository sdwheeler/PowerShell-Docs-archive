---
external help file: Microsoft.PowerShell.PSReadline.dll-Help.xml
Locale: en-US
Module Name: PSReadline
ms.date: 12/07/2018
online version: https://learn.microsoft.com/previous-versions/powershell/module/psreadline/remove-psreadlinekeyhandler?view=powershell-5.0&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-PSReadlineKeyHandler
---

# Remove-PSReadlineKeyHandler

## SYNOPSIS
Removes a key binding.

## SYNTAX

```
Remove-PSReadlineKeyHandler [-Chord] <String[]> [-ViMode <ViMode>] [<CommonParameters>]
```

## DESCRIPTION

The `Remove-PSReadlineKeyHandler` cmdlet removes a specified key binding.

## EXAMPLES

### Example 1: Remove a binding

```powershell
Remove-PSReadlineKeyHandler -Chord Ctrl+Shift+B
```

This command removes the binding from the key combination, or chord, `Ctrl+Shift+B`.
The `Ctrl+Shift+B` chord is created in the `Set-PSReadlineKeyHandler` article.

## PARAMETERS

### -Chord

Specifies an array of keys or sequences of keys to be removed. A single binding is specified by
using a single string. If the binding is a sequence of keys, separate the keys by a comma, as in
the following example:

`Ctrl+X,Ctrl+L`

This parameter accepts an array of strings. Each string is a separate binding, not a sequence of
keys for a single binding.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: Key

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ViMode

Specify which vi mode the binding applies to. Possible values are: Insert, Command.

```yaml
Type: ViMode
Parameter Sets: (All)
Aliases:
Accepted values: Insert, Command

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

You cannot pipe objects to this cmdlet.

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-PSReadlineKeyHandler](Get-PSReadlineKeyHandler.md)

[Get-PSReadlineOption](Get-PSReadlineOption.md)

[Set-PSReadlineOption](Set-PSReadlineOption.md)

[Set-PSReadlineKeyHandler](Set-PSReadlineKeyHandler.md)

