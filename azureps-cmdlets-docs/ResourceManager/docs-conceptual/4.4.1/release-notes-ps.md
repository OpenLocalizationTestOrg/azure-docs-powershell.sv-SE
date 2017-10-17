Azure PowerShell 4.3.1-installationsprogram: [länk](https://github.com/Azure/azure-powershell/releases/download/v4.3.1-August2017/azure-powershell.4.3.1.msi)

Gallerimodul för ARM-cmdletar: [länk](https://www.powershellgallery.com/packages/AzureRM/4.3.1)

Gallerimodul för tidigare cmdletar för Service Management (RDFE): [länk](https://www.powershellgallery.com/packages/Azure/4.3.1)

## <a name="changes-in-431"></a>Ändringar i 4.3.1

- Åtgärdat fel med vissa osignerade sammansättningar, vilket har resulterat i `could not load file or assembly` fel vid import av moduler

## <a name="changes-in-430"></a>Ändringar i 4.3.0

* AnalysisServices
    * Programfel i Set-AzureRmAnalysisServciesServer har åtgärdats
        - Om ingen admin angetts så tas admin bort.
    * BackupBlobContainerUri in New-AzureRmAnalysisServicesServer och Set-AzureRmAnalysisServicesServer har lagts till
        - Inställning/inaktivering av säkerhetskopia av blobbehållare för säkerhetskopiering/återställning av Azure Analysis Services Server har aktiverats
    * SKU-sökning i New-AzureRmAnalysisServicesServer och Set-AzureRmAnalysisServicesServer har uppdaterats
        - Hårdkodad SKU i dynamisk sökning har ändrats.
    * Add-AzureAnalysisServicesAccount som stöd för inloggning med tjänstens huvudnamn
* Automation
    * Ändringar har gjorts av AutomationDSC*-cmdletar för att hämta över 100 poster
    * Har löst problemet med att utförliga strömmar slutar fungera efter anrop av Automation-cmdletar (till exempel Get-AzureRmAutomationVariable, Get-AzureRmAutomationJob).
    * Stöd för versionshantering av NodeConfiguration-version har lagts till i StartAzureAutomationDscCompilationJob och ImportAzureAutomationDscNodeConfiguration.
    * Korrigering av programfel för befintliga problem – Problemet med alias #3775 och runOn-alias och stöd för HybridWorkers har åtgärdats.
* Compute
    * Set-AzureRmVMAEMExtension: Lägg till stöd för nya Premium-diskstorlekar
    * Set-AzureRmVMAEMExtension: Lägg till stöd för M-serien
    * Lägg till ForceUpdateTag-parametern i Add-AzureRmVmssExtension
    * Lägg till Primary-parametern i New-AzureRmVmssIpConfig
    * Lägg till EnableAcceleratedNetworking-parametern i Add-AzureRmVmssNetworkInterfaceConfig
    * Lägg till InstanceId i Set-AzureRmVmss
    * Exponera MaintenanceRedeployStatus för Get-AzureRmVM -Status-utdata
    * Exponera begränsning och kapacitet för tabellformatet i Get-AzureRmComputeResourceSku
* DataLakeStore
    * Korrigering av problemet: https://github.com/Azure/azure-powershell/issues/4323
* EventHub
    * ResourceGroup-egenskapen har lagts till i NamespaceAttributes
        - ”ResourceGroup” hämtar namnet på den resursgrupp där namnområdet finns
    * cmdletar har uppdaterats med ny parameter och parameteralias
        - cmdletarna nedan har uppdaterats med Parametersets för namnområde och EventHub för drift av AuthorizationRule
        - New-AzureRmEventHubAuthorizationRule
            + En ny AuthorizationRule läggs till i befintlig NameSpace eller EventHub.
        - Get-AzureRmEventHubAuthorizationRule
            + Hämtar AuthorizationRule/lista över AuthorizationRules för befintlig NameSpace eller EventHub.
        - Set-AzureRmEventHubAuthorizationRule
            + Uppdaterat egenskaper för befintlig AuthorizationRule för EventHub NameSpace.
        - Remove-AzureRmEventHubAuthorizationRule
            + Tar bort befintlig AuthorizationRule i befintlig NameSpace eller EventHub.
        - New-AzureRmEventHubKey
            + Skapar ny primär/sekundär nyckel för AuthorizationRule för befintlig NameSpace eller EventHub.
        - Get-AzureRmEventHubKey
            + Hämtar ny primär/sekundär nyckel för AuthorizationRule för befintlig NameSpace eller EventHub.
* Nätverk
    * New-AzureRmExpressRouteCircuitPeeringConfig: Stöd för IPv6 har lagts till. Ny valfri parameter har lagts till
        - PeerAddressType
    * Set-AzureRmExpressRouteCircuitPeeringConfig: Stöd för IPv6 har lagts till. Ny valfri parameter har lagts till
        - PeerAddressType
    * Remove-AzureRmExpressRouteCircuitPeeringConfig: Stöd för IPv6 har lagts till. Ny valfri parameter har lagts till
        - PeerAddressType
    * Parametern -ProbeEnabled har markerats som inaktuell
        - Add-AzureRmApplicationGatewayBackendHttpSettings
        - New-AzureRmApplicationGatewayBackendHttpSettings
        - Set-AzureRmApplicationGatewayBackendHttpSettings
* Profil
    * Datainsamling har aktiverats som standard. Användningsdata samlas in av Microsoft för att förbättra användarupplevelsen. Data är anonyma och omfattar inte värden för kommandoradsargument.
        - Använd cmdleten Disable-AzureRmDataCollection för att inaktivera funktionen
        - Använd cmdleten Enable-AzureRmDataCollection för att aktivera funktionen
* Resurser
    * Lägg till stöd för verifiering av omfång för följande rolldefinitions- och rolltilldelningskommandon innan förfrågan skickas till ARM
        - Get-AzureRMRoleAssignment
        - New-AzureRMRoleAssignment
        - Remove-AzureRMRoleAssignment
        - Get-AzureRMRoleDefinition
        - New-AzureRMRoleDefinition
        - Remove-AzureRMRoleDefinition
        - Set-AzureRMRoleDefinition
* ServiceBus
    * Följande nya kommandon för AuthorizationRules för NameSpace, Queue och Topic har lagts till. i enlighet med parameterinställningen har auktoriseringsreglerna utförts.
     - New-AzureRmServiceBusAuthorizationRule
       - Lägger till en ny AuthorizationRule i befintlig ServiceBus NameSpace/Queue/Topic.
     - Get-AzureRmServiceBusAuthorizationRule
       - Hämtar AuthorizationRule/lista över AuthorizationRules för befintlig Service Bus NameSpace/Queue/Topic.
     - Set-AzureRmServiceBusAuthorizationRule
       - Uppdaterar egenskaperna för befintlig AuthorizationRule för Servicebus NameSpace/Queue/Topic.
     - New-AzureRmServiceBusKey
       - Skapar en ny primär/sekundär nyckel för AuthorizationRule för befintlig ServiceBus NameSpace/Queue/Topic.
     - Get-AzureRmServiceBusKey
       - Hämtar primär/sekundär nyckel för AuthorizationRule för befintlig ServiceBus NameSpace/Queue/Topic.
     - Remove-AzureRmServiceBusNamespaceAuthorizationRule
       - Tar bort egenskaperna för befintlig AuthorizationRule för ServiceBus NameSpace/Queue/Topic.
    * Egenskap för resursgrupp har lagts till i NamespceAttributes
* SQL
    * Uppdaterar Set-AzureRmSqlServerTransparentDataEncryptionProtector så att en varning visas och bekräftelse krävs om krypteringsskyddstypen är AzureKeyVault
    * Lägger till nya uppdaterade cmdletar för granskningsinställningar
        - Lägger till cmdleten Get-AzureRmSqlDatabaseAuditing som hämtar granskningsinställningarna för en Azure SQL-databas.
        - Lägger till Get-AzureRmSqlServerAuditing-cmdlet som hämtar granskningsinställningarna för en Azure SQL-server.
        - Lägger till cmdleten Set-AzureRmSqlDatabaseAuditing som ändrar granskningsinställningarna för en Azure SQL-databas.
        - Lägger till cmdleten Set-AzureRmSqlServerAuditing som ändrar granskningsinställningarna för en Azure SQL-server.
    * Avvecklar befintliga cmdletar för granskningsprincipen
        - Avvecklar Get-AzureRmSqlDatabaseAuditingPolicy
        - Avvecklar Get-AzureRmSqlServerAuditingPolicy
        - Avvecklar Set-AzureRmSqlDatabaseAuditingPolicy
        - Avvecklar Set-AzureRmSqlServerAuditingPolicy
        - Avvecklar Use-AzureRmSqlServerAuditingPolicy
        - Avvecklar Remove-AzureRmSqlDatabaseAuditing
        - Avvecklar Remove-AzureRmSqlServerAuditing
    * Parsning av schemafil för Update-AzureRmSqlSyncGroup är nu skiftlägeskänslig.
* Lagring
    * Lägg till NetworkRule-stöd för cmdletar för lagringskontot i resursläget
        - New-AzureRmStorageAccount
        - Set-AzureRmStorageAccount
        - Get-AzureRmStorageAccountNetworkRuleSet
        - Update-AzureRmStorageAccountNetworkRuleSet
        - Add-AzureRmStorageAccountNetworkRule
        - Remove-AzureRmStorageAccountNetworkRule

Visa [ändringar sedan den senaste versionen](https://github.com/Azure/azure-powershell/compare/v4.2.1-July2017...v4.3.1-August2017)
