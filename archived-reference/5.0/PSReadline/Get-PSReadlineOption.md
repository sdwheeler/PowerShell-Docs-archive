---
external help file: Microsoft.PowerShell.PSReadline.dll-Help.xml
Locale: en-US
Module Name: PSReadline
ms.date: 12/07/2018
online version: https://learn.microsoft.com/previous-versions/powershell/module/psreadline/get-psreadlineoption?view=powershell-5.0&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSReadlineOption
---

# Get-PSReadlineOption

## SYNOPSIS
Gets values for the options that can be configured.

## SYNTAX

```
Get-PSReadlineOption [<CommonParameters>]
```

## DESCRIPTION

The `Get-PSReadlineOption` cmdlet returns the current state of the settings that can be configured
by using the `Set-PSReadlineOption` cmdlet. You can use the returned object to change
**PSReadline** options. This provides a slightly simpler way to set syntax coloring options for
multiple kinds of tokens.

## EXAMPLES

### Example 1: Get options and their values

```powershell
Get-PSReadlineOption
```

```Output
EditMode                               : Windows
ContinuationPrompt                     : >>
ContinuationPromptForegroundColor      : DarkYellow
ContinuationPromptBackgroundColor      : DarkMagenta
ExtraPromptLineCount                   : 0
AddToHistoryHandler                    :
CommandValidationHandler               :
CommandsToValidateScriptBlockArguments : {ForEach-Object, %, Invoke-Command, icm...}
HistoryNoDuplicates                    : False
MaximumHistoryCount                    : 4096
MaximumKillRingCount                   : 10
HistorySearchCursorMovesToEnd          : False
ShowToolTips                           : False
DingTone                               : 1221
CompletionQueryItems                   : 100
WordDelimiters                         : ;:,.[]{}()/\|^&*-=+'"
DingDuration                           : 50
BellStyle                              : Audible
HistorySearchCaseSensitive             : False
ViModeIndicator                        : None
HistorySavePath                        : C:\Users\testuser\AppData\Roaming\Microsoft\Windows\PowerShell\PSReadline\Cons
                                         oleHost_history.txt
HistorySaveStyle                       : SaveIncrementally
DefaultTokenForegroundColor            : DarkYellow
CommentForegroundColor                 : DarkGreen
KeywordForegroundColor                 : Green
StringForegroundColor                  : DarkCyan
OperatorForegroundColor                : DarkGray
VariableForegroundColor                : Green
CommandForegroundColor                 : Yellow
ParameterForegroundColor               : DarkGray
TypeForegroundColor                    : Gray
NumberForegroundColor                  : White
MemberForegroundColor                  : White
DefaultTokenBackgroundColor            : DarkMagenta
CommentBackgroundColor                 : DarkMagenta
KeywordBackgroundColor                 : DarkMagenta
StringBackgroundColor                  : DarkMagenta
OperatorBackgroundColor                : DarkMagenta
VariableBackgroundColor                : DarkMagenta
CommandBackgroundColor                 : DarkMagenta
ParameterBackgroundColor               : DarkMagenta
TypeBackgroundColor                    : DarkMagenta
NumberBackgroundColor                  : DarkMagenta
MemberBackgroundColor                  : DarkMagenta
EmphasisForegroundColor                : Cyan
EmphasisBackgroundColor                : DarkMagenta
ErrorForegroundColor                   : Red
ErrorBackgroundColor                   : DarkMagenta
```

This command returns the list of available PSReadline options and their current values.

## PARAMETERS

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

You cannot pipe objects to this cmdlet.

## OUTPUTS

### Microsoft.PowerShell.PSConsoleReadLineOptions

## NOTES

## RELATED LINKS

[Remove-PSReadlineKeyHandler](Remove-PSReadlineKeyHandler.md)

[Get-PSReadlineKeyHandler](Get-PSReadlineKeyHandler.md)

[Set-PSReadlineOption](Set-PSReadlineOption.md)

[Set-PSReadlineKeyHandler](Set-PSReadlineKeyHandler.md)

