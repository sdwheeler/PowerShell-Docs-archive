---
ms.date: 5/1/2019
schema:  2.0.0
locale:  en-us
keywords:  powershell,cmdlet
online version: https://go.microsoft.com/fwlink/?linkid=293900
external help file:  Microsoft.PowerShell.Commands.Management.dll-Help.xml
title:  Rename-Computer
---
# Rename-Computer

## SYNOPSIS
Renames a computer.

## SYNTAX

```
Rename-Computer [-ComputerName <String>] [-PassThru] [-DomainCredential <PSCredential>]
 [-LocalCredential <PSCredential>] [-NewName] <String> [-Force] [-Restart] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

The `Rename-Computer` cmdlet renames the local computer or a remote computer.
It renames one computer in each command.

This cmdlet was introduced in Windows PowerShell 3.0.

## EXAMPLES

### Example 1: Rename the local computer

This command renames the local computer to `Server044` and then restarts it to make the change
effective.

```powershell
Rename-Computer -NewName "Server044" -DomainCredential Domain01\Admin01 -Restart
```

### Example 2: Rename a remote computer

This command renames the `Srv01` computer to `Server001`. The computer is not restarted.

The **DomainCredential** parameter specifies the credentials of a user who has permission to rename
computers in the domain.

The **Force** parameter suppresses the confirmation prompt.

```powershell
Rename-Computer -ComputerName "Srv01" -NewName "Server001" -DomainCredential Domain01\Admin01 -Force
```

## PARAMETERS

### -ComputerName

Renames the specified remote computer.
The default is the local computer.

Type the NetBIOS name, an IP address, or a fully qualified domain name of a remote computer.
To specify the local computer, type the computer name, a dot (`.`), or `localhost`.

This parameter does not rely on PowerShell remoting.
You can use the **ComputerName** parameter of `Rename-Computer` even if your computer is not
configured to run remote commands.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Local Computer
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DomainCredential

Specifies a user account that has permission to connect to the domain.
Explicit credentials are required to rename a computer that is joined to a domain.

Type a user name, such as `User01` or `Domain01\User01`, or enter a **PSCredential** object, such
as one generated by the `Get-Credential` cmdlet.

If you type a user name, this cmdlet prompts you for a password.

To specify a user account that has permission to connect to the computer that is specified by the
**ComputerName** parameter, use the **LocalCredential** parameter.

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

### -Force

Forces the command to run without asking for user confirmation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -LocalCredential

Specifies a user account that has permission to connect to the computer specified by the
**ComputerName** parameter. The default is the current user.

Type a user name, such as `User01` or `Domain01\User01`, or enter a **PSCredential** object, such as
one generated by the `Get-Credential` cmdlet.

If you type a user name, this cmdlet prompts you for a password.

To specify a user account that has permission to connect to the domain, use the **DomainCredential**
parameter.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current User
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewName

Specifies a new name for the computer.
This parameter is required.

Standard names may contain letters (`a-z`), (`A-Z`), numbers (`0-9`), and hyphens (`-`), but no
spaces or periods (`.`). The name may not consist entirely of digits, and may not be longer than
63 characters

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

### -PassThru

Returns the results of the command.
Otherwise, this cmdlet does not generate any output.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Restart

Restarts the computer that was renamed.
A restart is often required to make the change effective.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
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

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## INPUTS

### None

This cmdlet does not have parameters that take input by value.
However, you can pipe the values of the **ComputerName** and **NewName** properties of objects to
this cmdlet.

## OUTPUTS

### Microsoft.PowerShell.Commands.ComputerChangeInfo

This cmdlet returns a **ComputerChangeInfo** object, if you specify the **PassThru** parameter.
Otherwise, it does not return any output.

## NOTES

## RELATED LINKS

[Add-Computer](Add-Computer.md)

[Remove-Computer](Remove-Computer.md)

[Reset-ComputerMachinePassword](Reset-ComputerMachinePassword.md)

[Restart-Computer](Restart-Computer.md)

[Stop-Computer](Stop-Computer.md)