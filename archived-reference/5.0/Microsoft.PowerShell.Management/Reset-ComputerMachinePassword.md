---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://learn.microsoft.com/previous-versions/powershell/module/microsoft.powershell.management/reset-computermachinepassword?view=powershell-5.0&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Reset-ComputerMachinePassword
---
# Reset-ComputerMachinePassword

## SYNOPSIS
Resets the machine account password for the computer.

## SYNTAX

```
Reset-ComputerMachinePassword [-Server <String>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

The **Reset-ComputerMachinePassword** cmdlet changes the computer account password that the computers use to authenticate to the domain controllers in the domain.
You can use it to reset the password of the local computer.

## EXAMPLES

### Example 1: Reset the password for the local computer

```
PS C:\> Reset-ComputerMachinePassword
```

This command resets the computer password for the local computer.
The command runs with the credentials of the current user.

### Example 2: Reset the password for the local computer by using a specified domain controller

```
PS C:\> Reset-ComputerMachinePassword -Server "DC01" -Credential Domain01\Admin01
```

This command resets the computer password of the local computer by using the DC01 domain controller.
It uses the *Credential* parameter to specify a user account that has permission to reset a computer password in the domain.

### Example 3: Reset the password on a remote computer

```
PS C:\> Invoke-Command -ComputerName "Server01" -ScriptBlock {Reset-ComputerMachinePassword}
```

This command uses the Invoke-Command cmdlet to run a **Reset-ComputerMachinePassword** command on the Server01 remote computer.

For more information about remote commands in Windows PowerShell, see about_Remote and **Invoke-Command**.

## PARAMETERS

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

### -Credential

Specifies a user account that has permission to perform this action.
The default is the current user.

Type a user name, such as User01 or Domain01\User01, or enter a **PSCredential** object, such as one generated by the Get-Credential cmdlet.
If you type a user name, this cmdlet prompts you for a password.

This parameter was introduced in Windows PowerShell 3.0.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Server

Specifies the name of a domain controller to use when this cmdlet sets the computer account password.

This parameter is optional.
If you omit this parameter, a domain controller is chosen to service the command.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

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
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

You cannot pipe input to this cmdlet.

## OUTPUTS

### None

This cmdlet does not generate any output.

## NOTES

## RELATED LINKS


