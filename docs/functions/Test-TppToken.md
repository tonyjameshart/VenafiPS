# Test-TppToken

## SYNOPSIS
Test if a Tpp token is valid

## SYNTAX

### AccessToken (Default)
```
Test-TppToken -AuthServer <String> -AccessToken <PSCredential> [-GrantDetail] [<CommonParameters>]
```

### VaultAccessToken
```
Test-TppToken [-AuthServer <String>] -VaultAccessTokenName <String> [-GrantDetail] [<CommonParameters>]
```

### TppToken
```
Test-TppToken -TppToken <PSObject> [-GrantDetail] [<CommonParameters>]
```

### Session
```
Test-TppToken [-GrantDetail] [-VenafiSession <VenafiSession>] [<CommonParameters>]
```

## DESCRIPTION
Use the TPP API call 'Authorize/Verify' to test if the current token is valid.

## EXAMPLES

### EXAMPLE 1
```
Test-TppToken
Verify that accesstoken stored in $VenafiSession object is valid.
```

### EXAMPLE 2
```
$TppToken | Test-TppToken
Verify that token object from pipeline is valid. Can be used to validate directly object from New-TppToken.
```

### EXAMPLE 3
```
Test-TppToken -AuthServer venafi.mycompany.com -AccessToken $cred
Verify that PsCredential object containing accesstoken is valid.
```

### EXAMPLE 4
```
Test-TppToken -VaultAccessTokenName access-token
Verify access token stored in VenafiPS vault, metadata stored with secret
```

### EXAMPLE 5
```
Test-TppToken -VaultAccessTokenName access-token -AuthServer venafi.mycompany.com
Verify access token stored in VenafiPS vault providing server to authenticate against
```

### EXAMPLE 6
```
Test-TppToken -GrantDetail
Verify that accesstoken stored in $VenafiSession object is valid and return PsCustomObject as output with details.
```

## PARAMETERS

### -AuthServer
Auth server or url, venafi.company.com or https://venafi.company.com.
This will be used to access vedauth for token-based authentication.
If just the server name is provided, https:// will be appended.

```yaml
Type: String
Parameter Sets: AccessToken
Aliases: Server

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: VaultAccessToken
Aliases: Server

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AccessToken
Access token retrieved outside this module. 
Provide a credential object with the access token as the password.

```yaml
Type: PSCredential
Parameter Sets: AccessToken
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TppToken
Token object obtained from New-TppToken

```yaml
Type: PSObject
Parameter Sets: TppToken
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VaultAccessTokenName
Name of the SecretManagement vault entry for the access token; the name of the vault must be VenafiPS.
Note: '-Server' parameter is required if the vault does not contain saved metadata.
See New-VenafiSession -VaultMetaData

```yaml
Type: String
Parameter Sets: VaultAccessToken
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GrantDetail
Provides detailed info about the token object from the TPP server response as an output. 
Supported on TPP 20.4 and later.

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

### -VenafiSession
Session object created from New-VenafiSession method. 
The value defaults to the script session object $VenafiSession.

```yaml
Type: VenafiSession
Parameter Sets: Session
Aliases:

Required: False
Position: Named
Default value: $script:VenafiSession
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### AccessToken, TppToken
## OUTPUTS

### Boolean (default)
### PSCustomObject (GrantDetail)
###     ClientId
###     AccessIssued
###     GrantIssued
###     Scope
###     Identity
###     RefreshExpires
## NOTES

## RELATED LINKS

[http://VenafiPS.readthedocs.io/en/latest/functions/Test-TppToken/](http://VenafiPS.readthedocs.io/en/latest/functions/Test-TppToken/)

[https://github.com/Venafi/VenafiPS/blob/main/VenafiPS/Public/Test-TppToken.ps1](https://github.com/Venafi/VenafiPS/blob/main/VenafiPS/Public/Test-TppToken.ps1)

[https://docs.venafi.com/Docs/current/TopNav/Content/SDK/AuthSDK/r-SDKa-GET-Authorize-Verify.php](https://docs.venafi.com/Docs/current/TopNav/Content/SDK/AuthSDK/r-SDKa-GET-Authorize-Verify.php)

