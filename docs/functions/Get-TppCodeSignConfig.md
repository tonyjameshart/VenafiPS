# Get-TppCodeSignConfig

## SYNOPSIS
Get CodeSign Protect project settings

## SYNTAX

```
Get-TppCodeSignConfig [[-VenafiSession] <VenafiSession>] [<CommonParameters>]
```

## DESCRIPTION
Get CodeSign Protect project settings.
Must have token with scope codesign:manage.

## EXAMPLES

### EXAMPLE 1
```
Get-TppCodeSignConfig
```

Get settings

## PARAMETERS

### -VenafiSession
Session object created from New-VenafiSession method.
The value defaults to the script session object $VenafiSession.

```yaml
Type: VenafiSession
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: $Script:VenafiSession
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None
## OUTPUTS

### PSCustomObject with the following properties:
###     ApprovedKeyStorageLocations
###     AvailableKeyStorageLocations
###     DefaultCAContainer
###     DefaultCertificateContainer
###     DefaultCredentialContainer
###     KeyUseTimeout
###     ProjectDescriptionTooltip
###     RequestInProgressMessage
## NOTES

## RELATED LINKS

[http://venafitppps.readthedocs.io/en/latest/functions/Get-TppCodeSignConfig/](http://venafitppps.readthedocs.io/en/latest/functions/Get-TppCodeSignConfig/)

[https://github.com/gdbarron/VenafiTppPS/blob/main/VenafiTppPS/Code/Public/Get-TppCodeSignConfig.ps1](https://github.com/gdbarron/VenafiTppPS/blob/main/VenafiTppPS/Code/Public/Get-TppCodeSignConfig.ps1)

[https://docs.venafi.com/Docs/20.4SDK/TopNav/Content/SDK/CodeSignSDK/r-SDKc-GET-Codesign-GetGlobalConfiguration.php?tocpath=CodeSign%20Protect%20Admin%20REST%C2%A0API%7CGlobalConfiguration%7C_____1](https://docs.venafi.com/Docs/20.4SDK/TopNav/Content/SDK/CodeSignSDK/r-SDKc-GET-Codesign-GetGlobalConfiguration.php?tocpath=CodeSign%20Protect%20Admin%20REST%C2%A0API%7CGlobalConfiguration%7C_____1)
