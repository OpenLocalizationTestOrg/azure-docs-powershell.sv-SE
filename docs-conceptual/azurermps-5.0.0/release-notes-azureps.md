---
title: "Ändringslogg för Azure PowerShell | Microsoft Docs"
description: "Det här är en historik över de ändringar som gjorts i den senaste versionen av Azure PowerShell."
services: azure
author: sdwheeler
ms.author: sewhee
manager: carmonm
ms.service: azure-powershell
ms.product: azure
ms.devlang: powershell
ms.topic: conceptual
ms.workload: 
ms.date: 11/14/2017
ms.openlocfilehash: ab35cbc4ec1a0bd4e7ee40e1864bd7941f5bca87
ms.sourcegitcommit: 79dd3700b5cb4cb90b268778b482082052160093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/14/2017
---
# <a name="release-notes"></a>Viktig information

Det här är en lista över ändringar som har gjorts i Azure PowerShell i den här versionen.

## <a name="20171110-version-501"></a>2017-11-10 Version 5.0.1
* Problem med sammansättningsinläsning som orsakade att vissa cmdletar misslyckades med att köras i följande moduler har åtgärdats:
    - AzureRM.ApiManagement
    - AzureRM.Backup
    - AzureRM.Batch
    - AzureRM.Compute
    - AzureRM.DataFactories
    - AzureRM.HDInsight
    - AzureRM.KeyVault
    - AzureRM.RecoveryServices
    - AzureRM.RecoveryServices
    - AzureRM.RecoveryServices
    - AzureRM.RedisCache
    - AzureRM.SiteRecovery
    - AzureRM.Sql
    - AzureRM.Storage
    - AzureRM.StreamAnalytics

## <a name="2017118---version-500"></a>2017-11-08 – version 5.0.0
* Obs! Detta är en viktig ändring. I migreringsguiden (https://aka.ms/azps-migration-guide) finns en fullständig lista över viktiga ändringar som har introducerats.
* Alla cmdletar i AzureRM stöder nu onlinehjälp
    - Kör Get-Help med parametern -Online för att öppna onlinehjälpen i din standardwebbläsare
* AnalysisServices
    * Kommandot Synchronize-AzureAsInstance har åtgärdats så att det fungerar med ny AsAzure REST API för synkronisering
* ApiManagement
    * I migreringsguiden finns information om viktiga ändringar av ApiManagement i den här versionen
    * Cmdleten Get-AzureRmApiManagementUser har uppdaterats för att åtgärda problem https://github.com/Azure/azure-powershell/issues/4510
    * Cmdleten New-AzureRmApiManagementApi har uppdaterats för att skapa API med en tom sökväg https://github.com/Azure/azure-powershell/issues/4069
* ApplicationInsights
    * Lägg till kommandon för att hämta/skapa/ta bort Application Insights-resurs
        - Get-AzureRmApplicationInsights
        - New-AzureRmApplicationInsights
        - Remove-AzureRmApplicationInsights
    * Lägg till kommandon för att hämta/uppdatera prissättning/dagligt tak för Application Insights-resurs
        - Get-AzureRmApplicationInsights -IncludeDailyCap
        - Set-AzureRmApplicationInsightsPricingPlan
        - Set-AzureRmApplicationInsightsDailyCap
    * Lägg till kommandon för att hämta/skapa/uppdatera/ta bort löpande export av Application Insights-resurs
        - Get-AzureRmApplicationInsightsContinuousExport
        - Set-AzureRmApplicationInsightsContinuousExport
        - New-AzureRmApplicationInsightsContinuousExport
        - Remove-AzureRmApplicationInsightsContinuousExport
    * Lägg till kommandon för att hämta/skapa/ta bort API-nycklar för Application Insights-resurs
        - Get-AzureRmApplicationInsightsApiKey
        - New-AzureRmApplicationInsightsApiKey
        - Remove-AzureRmApplicationInsightsApiKey
* AzureBatch
    * Nya parametrar har lagts till för `New-AzureRmBatchAccount`.
        - `PoolAllocationMode`: Allokeringsläget som ska användas för att skapa pooler i Batch-kontot. Om du vill skapa ett Batch-konto som allokerar poolnoder i användarens prenumeration ställer du in detta på `UserSubscription`.
        - `KeyVaultId`: Resurs-ID:t till det Azure-nyckelvalv som är associerat till Batch-kontot.
        - `KeyVaultUrl`: Webbadressen till det Azure-nyckelvalv som är associerat till Batch-kontot.
    * Uppdaterade parametrar till `New-AzureBatchTask`.
        - Switchen `RunElevated` har tagits bort. Parametern `UserIdentity` har lagts till för att ersätta `RunElevated`, och motsvarande beteende kan uppnås om en `PSUserIdentity` byggs enligt nedan:
            - $autoUser = New-Object Microsoft.Azure.Commands.Batch.Models.PSAutoUserSpecification -ArgumentList @("Task", "Admin")
            - $userIdentity = New-Object Microsoft.Azure.Commands.Batch.Models.PSUserIdentity $autoUser
        - Parametern `AuthenticationTokenSettings` har lagts till. Med den här parametern kan du begära att Batch-tjänsten tillhandahåller ett autentiseringstoken till uppgiften när den körs för att undvika behovet av att skicka Batch-kontonycklar till uppgiften för att utfärda begäran för Batch-tjänsten.
        - Parametern `ContainerSettings` har lagts till.
            - Med den här parametern kan du begära att Batch-tjänsten kör uppgiften i en behållare.
        - Parametern `OutputFiles` har lagts till.
            - Med den här parametern kan du konfigurera uppgiften för att ladda upp filer till Azure Storage när den har avslutats.
    * Parametrar för `New-AzureBatchPool` har uppdaterats.
        - Parametern `UserAccounts` har lagts till.
            - Den här parametern definierar användarkonton som skapats på varje nod i poolen.
        - `TargetLowPriorityComputeNodes` har lagts till, och `TargetDedicated` har bytt namn till `TargetDedicatedComputeNodes`.
            - Ett `TargetDedicated` alias skapades för parametern `TargetDedicatedComputeNodes`.
        - Parametern `NetworkConfiguration` har lagts till.
            - Med den här parametern kan du konfigurera nätverksinställningarna för pooler.
    * Parametrar för `New-AzureBatchCertificate` har uppdaterats.
        - Parametern `Password` är nu en `SecureString`.
    * Parametrar för `New-AzureBatchComputeNodeUser` har uppdaterats.
        - Parametern `Password` är nu en `SecureString`.
    * Parametrar för `Set-AzureBatchComputeNodeUser` har uppdaterats.
        - Parametern `Password` är nu en `SecureString`.
    * Bytte namn på parametern `Name` till `Path` på `Get-AzureBatchNodeFile`, `Get-AzureBatchNodeFileContent` och `Remove-AzureBatchNodeFile`.
        - Ett `Name` alias skapades för parametern `Path`.
    * Ändringar av objekt
        - I Batch-ändringsloggen finns en fullständig lista
    * Stöd har lagts till för Azure Active Directory-baserad autentisering.
        - För att använda Azure Active Directory-autentisering hämtar du ett `BatchAccountContext` objekt som använder cmdleten `Get-AzureRmBatchAccount`, och tillhandahåller det `BatchAccountContext` till parametern `-BatchContext` i en cmdlet i Batch-tjänsten. Azure Active Directory-autentisering är obligatoriskt för konton med `PoolAllocationMode = UserSubscription`.
        - För befintliga konton eller för nya konton som skapats med `PoolAllocationMode = BatchService` kan du fortsätta att använda autentisering för delade nycklar genom att hämta ett `BatchAccountContext`-objekt med cmdleten `Get-AzureRmBatchAccoutKeys`.
* Compute
    * Kommandon för Azure Disk Encryption-tillägg
        - Ny parameter för ”Set-AzureRmVmDiskEncryptionExtension”: ”-EncryptFormatAll” som gör det möjligt att kryptera och formatera datadiskar
        - Nya parametrar för ”Set-AzureRmVmDiskEncryptionExtension”: ”-ExtensionPublisherName” och ”-ExtensionType” som gör det möjligt att växla till andra versioner av tillägget
        - Nya parametrar för ”Disable-AzureRmVmDiskEncryption”: ”-ExtensionPublisherName”: ”-ExtensionPublisherName” och ”-ExtensionType” som gör det möjligt att växla till andra versioner av tillägget
        - Nya parametrar för ”Get-AzureRmVmDiskEncryptionStatus”: ”-ExtensionPublisherName” and ”-ExtensionType” som gör det möjligt att växla till andra versioner av tillägget
* DataLakeAnalytics
    * I migreringsguiden finns information om viktiga ändringar av DataLakeAnalytics i den här versionen
    * En av två OutputTypes i Get-AzureRmDataLakeAnalyticsAccount har ändrats
        - List\<DataLakeAnalyticsAccount> till List\<PSDataLakeAnalyticsAccountBasic>
        - Egenskaperna för PSDataLakeAnalyticsAccountBasic är en strikt delmängd av egenskaperna i DataLakeAnalyticsAccount
        - Ytterligare egenskaper som finns i DataLakeAnalyticsAccount returneras inte av tjänsten.  Den här ändringen är därför till för att återspegla detta korrekt. Dessa ytterligare egenskaper är fortfarande i PSDataLakeAnalyticsAccountBasic, men de är märkta som föråldrade.
    * En av två OutputTypes i Get-AzureRmDataLakeAnalyticsJob har ändrats
        - List\<JobInformation> till List\<PSJobInformationBasic>
        - Egenskaperna i PSJobInformationBasic är en strikt delmängd av egenskaperna i JobInformation
        - Ytterligare egenskaper som finns i JobInformation returneras inte av tjänsten.  Den här ändringen är därför till för att återspegla detta korrekt. Dessa ytterligare egenskaper är fortfarande i PSJobInformationBasic, men de är märkta som föråldrade.
* DataLakeStore
    * I migreringsguiden finns information om viktiga ändringar av DataLakeStore i den här versionen
    * En av två OutputTypes i Get-AzureRmDataLakeStoreAccount har ändrats
        - List\<PSDataLakeStoreAccount> till List\<PSDataLakeStoreAccountBasic>
        - Egenskaperna för PSDataLakeStoreAccountBasic är en strikt delmängd av egenskaperna i PSDataLakeStoreAccount
        - Ytterligare egenskaper som finns i PSDataLakeStoreAccount returneras inte av tjänsten.  Den här ändringen är därför till för att återspegla detta korrekt. Dessa ytterligare egenskaper är fortfarande i PSDataLakeStoreAccountBasic, men de är märkta som föråldrade.
* DNS
    * Stöd för CAA-posttyper i Azure DNS
       - Stöder alla åtgärder på CAA-posttyp
* EventHub
    * I migreringsguiden finns information om viktiga ändringar av EventHub i den här versionen
* Insikter
    * I migreringsguiden finns information om viktiga ändringar av Insights i den här versionen
* Nätverk
    * I migreringsguiden finns information om viktiga ändringar av Network i den här versionen
    * Cmdlet för att lista tillgängliga internetleverantörer har lagts till för en angiven Azure-region
        - Get-AzureRmNetworkWatcherReachabilityProvidersList
    * Cmdlet har lagts till för att hämta den relativa latenspoängen för internetleverantörer från en angiven plats till Azure-regioner
        - Get-AzureRmNetworkWatcherReachabilityReport
* Profil
    - Set-AzureRmDefault
        - Använd denna cmdlet om du vill ange en standardresursgrupp.  Det gör parametern -ResourceGroup valfri för vissa cmdletar och använder standardvärdet när ingen resursgrupp är angiven
        - ```Set-AzureRmDefault -ResourceGroupName "ExampleResourceGroup"```
        - Om det finns en angiven resursgrupp i prenumerationen ställs den in på standardvärdet.  Annars skapas resursgruppen och ställs in på standardvärdet.
    - Get-AzureRmDefault
        - Använd denna cmdlet för att hämta den aktuella standardresursgruppen (och andra kommande standardinställningar).
        - ```Get-AzureRmDefault -ResourceGroup```
    - Clear-AzureRmDefault
        - Använd den här cmdleten för att ta bort den aktuella standardresursgruppen
        - ```Clear-AzureRmDefault -ResourceGroup```
    - Add-AzureRmEnvironment och Set-AzureRmEnvironment
        - Lägg till parametern BatchAudience. Den gör att du kan ange Azure Batch Active Directory-målgruppen som ska användas när du hämtar autentiseringstoken för Batch-tjänsten.
* RecoveryServices.Backup
    * Cmdletar för att utföra ögonblicklig filåterställning har lagts till.
        - Get-AzureRmRecoveryServicesBackupRPMountScript
        - Disable-AzureRmRecoveryServicesBackupRPMountScript
    * Versionen av RecoveryServices.Backup SDK har uppdaterats till den senaste
    * Test för Azure VM-arbetsbelastningen har uppdaterats, så att alla nödvändiga konfigurationer för testkörningar görs av testen själva.
    * Korrigeringar https://github.com/Azure/azure-powershell/issues/3164
* RecoveryServices.SiteRecovery
    * Ändringar för ASR VMware till Azure Site Recovery (cmdletar stöder för närvarande åtgärder för Enterprise till Enterprise, Enterprise till Azure, HyperV till Azure)
        - New-AzureRmRecoveryServicesAsrPolicy
        - New-AzureRmRecoveryServicesAsrProtectedItem
        - Update-AzureRmRecoveryServicesAsrPolicy
        - Update-AzureRmRecoveryServicesAsrProtectionDirection
    * Stöd för AAD-baserat valv har lagts till
    * Cmdletar för att hantera VCenter-resurser har lagts till
        - Get-AzureRmRecoveryServicesAsrVCenter
        - New-AzureRmRecoveryServicesAsrVCenter
        - Remove-AzureRmRecoveryServicesAsrVCenter
        - Update-AzureRmRecoveryServicesAsrVCenter
    * Andra cmdletar har lagts till
        - Get-AzureRmRecoveryServicesAsrAlertSetting
        - Get-AzureRmRecoveryServicesAsrEvent
        - New-AzureRmRecoveryServicesAsrProtectableItem
        - Set-AzureRmRecoveryServicesAsrAlertSetting
        - Start-AzureRmRecoveryServicesAsrResynchronizeReplicationJob
        - Start-AzureRmRecoveryServicesAsrSwitchProcessServerJob
        - Start-AzureRmRecoveryServicesAsrTestFailoverCleanupJob
        - Update-AzureRmRecoveryServicesAsrMobilityService
* ServiceBus
    - I migreringsguiden finns information om viktiga ändringar av ServiceBus i den här versionen
* SQL
    * Stöd har lagts till för att ange och avbryta asynkron updateslo-åtgärd för databasen
        - uppdatera befintlig cmdlet Get-AzureRmSqlDatabaseActivity för att returnera DB updateslo-driftsstatus.
        - lägg till ny cmdlet Stop-AzureRmSqlDatabaseActivity för att avbryta den asynkrona updateslo-åtgärden för databasen.
    * Stöd har lagts till för zonredundans för databaser och elastiska pooler
        - Switchparametern ZoneRedundant har lagts till i New-AzureRmSqlDatabase
        - Switchparametern ZoneRedundant har lagts till i Set-AzureRmSqlDatabase
        - Switchparametern ZoneRedundant har lagts till i New-AzureRmSqlElasticPool
        - Switchparametern ZoneRedundant har lagts till i Set-AzureRmSqlElasticPool
    * Stöd för Server DNS-alias har lagts till
        - Lägger till cmdleten Get-AzureRmSqlServerDnsAlias som hämtar server-dns-alias via server- och aliasnamn eller en lista över server-dns-alias för en azure Sql Server.
        - Lägger till cmdleten New-AzureRmSqlServerDnsAlias som skapar ett nytt server-dns-alias för en viss Azure Sql server
        - Lägger till cmdleten Set-AzurermSqlServerDnsAlias som möjliggör uppdatering till en Azure Sql Server mot vilken server-dns-aliaset pekar
        - Lägger till cmdleten Remove-AzureRmSqlServerDnsAlias som tar bort ett server-dns-alias för en Azure Sql Server
* Azure.Storage
    * Uppgradera till Azure Storage-klientbiblioteket 8.5.0 och Azure Storage DataMovement-biblioteket 0.6.3
    * Lägg till stöd för funktion för ögonblicksbild av filresurs
        - Lägg till ”SnapshotTime”-parametern i Get-AzureStorageShare
        - Lägg till ”IncludeAllSnapshot”-parametern till Remove-AzureStorageShare