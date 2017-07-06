---
title: "Ändringslogg för Azure PowerShell | Microsoft Docs"
description: "Det här är en historik över de ändringar som gjorts i den senaste versionen av Azure PowerShell."
services: azure
author: sdwheeler
ms.author: sewhee
manager: carmonm
ms.service: azure-resource-manager
ms.product: azure
ms.devlang: powershell
ms.topic: conceptual
ms.workload: 
ms.date: 05/18/2017
ms.openlocfilehash: 5c8fa2a5a8f94cd24b66f42c237749a7b89af3b3
ms.sourcegitcommit: 226527be7cb647acfe2ea9ab151185053ab3c6db
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2017
---
# <a name="release-notes"></a>Viktig information

Det här är en lista över ändringar som har gjorts i Azure PowerShell i den här versionen.

## <a name="version-400"></a>Version 4.0.0

* Den här versionen innehåller större ändringar. Se [migreringsguiden](https://aka.ms/azps-migration-guide) för information om ändringar hur de påverkar befintliga skript.
* ApiManagement
  - Stöd har lagts till för att konfigurera externa grupper i New-AzureRmApiManagementGroup.
* Fakturering
  - Ny cmdlet Get-AzureRmBillingPeriod
    + cmdlet för att hämta azure-faktureringsperioder för prenumerationen.
  - Uppdaterad cmdlet Get-AzureRmBillingInvoice
  - ny egenskap BillingPeriodNames
  - utdata i listvyn
* Compute
  - Uppdaterade cmdletar Set-AzureRmVMAEMExtension och Test-AzureRmVMAEMExtension för att stödja Premium-hanterade diskar
  - Krypteringsinställningar för säkerhetskopiering av IaaS-VM:ar och återställning vid fel
  - Alternativet ChefServiceInterval byter namn till ChefDaemonInterval. Den gamla kommer dock fortsätta att fungera.
  - Duplicerade egenskaper för DataDiskNames och NetworkInterfaceIDs har tagits bort från PS VM-objekt.
  - Parametrarna DataDiskNames och NetworkInterfaceIDs har gjorts valfria i Remove-AzureRmVMDataDisk och Remove-AzureRmVMNetworkInterface.
  - Rörledningsproblemet vid Get cmdlets när Get cmdlets returnerar ett listobjekt.
  - Cmdletar som är i konflikt med RDFE-cmdletar har bytt namn. Se problemet https://github.com/Azure/azure-powershell/issues/2917 för ytterligare information
    + `New-AzureVMSqlServerAutoBackupConfig` har bytt namn till `New-AzureRmVMSqlServerAutoBackupConfig`
    + `New-AzureVMSqlServerAutoPatchingConfig` har bytt namn till `New-AzureRmVMSqlServerAutoPatchingConfig`
    + `New-AzureVMSqlServerKeyVaultCredentialConfig` har bytt namn till `New-AzureRmVMSqlServerKeyVaultCredentialConfig`
* Förbrukning
  - Ny cmdlet Get-AzureRmConsumptionUsageDetail
    + cmdlet för att användningsinformation för prenumerationen.
* ContainerRegistry
  - Lägg till PowerShell-cmdletar för Azure-behållarregistret
    + New-AzureRmContainerRegistry
    + Get-AzureRmContainerRegistry
    + Update-AzureRmContainerRegistry
    + Remove-AzureRmContainerRegistry
    + Get-AzureRmContainerRegistryCredential
    + Update-AzureRmContainerRegistryCredential
    + Test-AzureRmContainerRegistryNameAvailability
* DataLakeAnalytics
  - Stöd läggs till för hämta och lista katalogpaket
  - Stöd läggs till för att lista följande katalogobjekt från djupare överordnade:
    + Tabell
    + TVF
    + Visa
    + Statistik
* DataLakeStore
  - Spårningsloggning för `Import-AzureRMDataLakeStoreItem` och `Export-AzureRMDataLakeStoreItem` har inaktiverats som standard för att förbättra prestandan. Om du vill ha loggningsspårning, använder du parametrarna `-DiagnosticLogLevel` och `-DiagnosticLogPath`
  - En bugg som ibland gjorde att PowerShell kraschade vid uppladdning av många små filer till ADLS har fixats.
* EventHub
  - Felkorrigering:
    + Korrigering för cmdlet-felet i Set-AzureRmEventHubNamespace: ”Nivå” kan inte vara null när den ska vara ”SkuName”
    + Set-AzureRmEventHub – korrigering av objektreferensen inte inställd till en instans av ett objektfel vid uppdatering av EventHub
* Insikter
  - Add-AzureRm*AlertRule
    + Returnerar ett objekt: newResource, statusCode, requestId
  - Get-AzureRmAlertRule
    + Utdata räknas nu upp istället för att betraktas som ett enda objekt. Typen har inte ändrats, det är fortfarande en lista.
  - Remove-AzureRmAlertRule
    + StatusCode följer statuskoden som returneras av begäran, innan var det alltid Ok.
  - Add-AzureRmAutoscaleSetting
    + Returnerar nu ett enskilt objekt (inte en lista som tidigare) som innehåller statusCode, requestId och den nyligen skapade/uppdarerade resursen.
    + Statuskoden följer den status som begäran returnerar, innan var den alltid Ok.
  - New-AzureRmAutoscaleRule
    + Parametern ScaleActionType har utökats, den tar nu emot följande värden: ChangeCount, PercentChangeCount, ExactCount.
  - Remove-AzureRmAutoscaleSetting
    + StatusCode i utdata följer statusCode som returnerades av begäran. Innan var den alltid Ok.
  - Get-AzureRMLogProfile
    + Utdata räknas nu upp. Innan ansågs den som ett enda objekt. Utdatatypen fortsätter att vara en lista som tidigare.
  - Remove-AzureRmLogProfile
    + PassThru-parametern har implementerats.
  - Mått-API
    + SDK:n hämtar nu mått från MDM.
  - Get-AzureRmMetricDefinition
    + Utdata är fortfarande en lista, men listans struktur har ändrats.
  - Get-AzureRmMetric
    + Anropet har ändrats. Detta är den nya syntaxen: Get-AzureRmMetric ResourceId [MetricNames [TimeGrain] [AggregationType] [StartTime] [EndTime]] [DetailedOutput]
    + Utdata är en lista och strukturen för dess element har förändrats.
* KeyVault
  - Lägger till stöd för säkerhetskopiering/återställning av KeyVault-hemligheter
    + Hemligheter kan säkerhetskopieras och återställas, vilket matchar de funktioner som stöds för nycklar för tillfället

  - Säkerhetskopierings-cmdletar för nycklar och hemligheter accepterar nu ett motsvarande objekt som indataparameter
    + Anroparen kan kedja hämtning och säkerhetskopiering: Get-AzureKeyVaultKey -VaultName myVault -Name myKey | Backup-AzureKeyVaultKey

  - Säkerhetskopierings-cmdletar stöder nu en -Force växel för att skriva över en befintlig fil
    + Observera att försök att skriva över en befintlig fil inte längre kommer att misslyckas, utan istället tillfrågas användaren hur denne vill fortsätta.
* LogicApp
  - Nya parametrar för katastrofåterställnings-cmdletars utbyteskontrollnummer:
    + Valfri -AgreementType-parameter ("X12", eller "Edifact") för att specificera de relevanta kontrollnumren
* MachineLearning
  - Använd en ny version av Azure Machine Learning .Net-SDK:n och lägg till en ny cmdlet
    + Add-AzureRmMlWebServiceRegionalProperty
  - Mindre textkorrigeringar i hjälptexten.
* Nätverk
  - Lade till cmdleten Test-AzureRmNetworkWatcherConnectivity
    + Returnerar anslutningsinformation för en angiven käll-VM och ett mål
    + Om anslutningen mellan källa och mål inte går att upprätta, returnerar cmdleten information om problemet
* Profil
  - Lade till cmdleten Send-Feedback: låter en användare starta en uppsättning prompter som skickar feedback till Azure PowerShell-teamet.
  - Följande alias har tagits bort eftersom de är i konflikt med befintliga cmdlet-namn i Azure-modulen:
    + `Enable-AzureDataCollection` (stöds av `Enable-AzureRmDataCollection`)
    + `Disable-AzureDataCollection` (stöds av `Disable-AzureRmDataCollection`)
* Relä
  - Lägger till cmdletar för Azure-Relay, som låter användare skapa och hantera alla Azure Relay-resurser.
    + `New-AzureRmRelayNamespace`
    + `Get-AzureRmRelayNamespace`
    + `Set-AzureRmRelayNamespace`
    + `Remove-AzureRmRelayNamespace`
    + `New-AzureRmWcfRelay`
    + `Get-AzureRmWcfRelay`
    + `Set-AzureRmWcfRelay`
    + `Remove-AzureRmWcfRelay`
    + `New-AzureRmRelayHybridConnection`
    + `Get-AzureRmRelayHybridConnection`
    + `Set-AzureRmRelayHybridConnection`
    + `Remove-AzureRmRelayHybridConnection`
    + `Test-AzureRmRelayName`
    + `Get-AzureRmRelayOperation`
    + `New-AzureRmRelayKey`
    + `Get-AzureRmRelayKey`
    + `New-AzureRmRelayAuthorizationRule`
    + `Get-AzureRmRelayAuthorizationRule`
    + `Set-AzureRmRelayAuthorizationRule`
    + `Remove-AzureRmRelayAuthorizationRule`
* Resurser
  - Stöd för distributioner över resursgrupper för New-AzureRmResourceGroupDeployment
    + Användare kan nu använda kapslade distributioner för att distribuera till olika resursgrupper.
* ServiceBus

  - Felkorrigering: Egenskapsvärdena för ServiceBus-köobjektet var satt till null, objektet används som indataparameter i cmdleten Set-AzureRmServiceBusQueue för att uppdatera kön.
   - Egenskaper som påverkas är LockDuration, EntityAvailabilityStatus, DuplicateDetectionHistoryTimeWindow, MaxDeliveryCount och MessageCount
* ServiceFabric

  - Lade till cmdletar för Service Fabric
    + Add-AzureRmServiceFabricApplicationCertificate       Lägg till ett certifikat som kommer att användas som programcertifikat
    + Add-AzureRmServiceFabricClientCertificate       Lägg till ett namn eller tumavtryck till klusterinställningarna för klientautentiseringen
    + Add-AzureRmServiceFabricClusterCertificate       Lägg till ett sekundärt klustercertifikat till klustret för att rulla över det tidigare certifikatet
    + Add-AzureRmServiceFabricNodes Lägg till noder/VM:ar av en specifik nodtyp till ett kluster
    + Add-AzureRmServiceFabricNodeType Lägg till en nodtyp/VM:ar till ett befintligt kluster
    + Get-AzureRmServiceFabricCluster hämta information om klusterresursen
    + New-AzureRmServiceFabricCluster Skapa ett nytt ServiceFabric-kluster. Det här kommandot har många överlagringar för att täcka olika scenarier
    + Remove-AzureRmServiceFabricClientCertificate       Ta bort ett klientcertifikat från att användas för åtkomst till ett kluster
    + Remove-AzureRmServiceFabricClusterCertificate       Ta bort ett klustercertifikat från att användas för klustersäkerhet
    + Remove-AzureRmServiceFabricNodes       Ta bort noder från en specifik nodtyp från ett kluster
    + Remove-AzureRmServiceFabricNodeType       Ta bort en nodtyp från ett kluster
    + Remove-AzureRmServiceFabricSettings       Ta bort en eller flera ServiceFabric-inställningar från ett kluster
    + Set-AzureRmServiceFabricSettings       Lägg till eller uppdatera en eller flera ServiceFabric-inställningar för ett kluster
    + Set-AzureRmServiceFabricUpgradeType       Ändra ServiceFabric-uppgraderingstypen för ett kluster
    + Update-AzureRmServiceFabricDurability       Ändra hållbarhetsnivån för ett kluster
    + Update-AzureRmServiceFabricReliability       Ändra tillförlitlighetsnivån för ett kluster
* SQL
  - Lade till parametern -SampleName till New-AzureRmSqlDatabase
  - Uppdateringar till redundansgrupp-cmdletar
  - Tog bort Tagg-parametrarna
  - Tog bort parametrarna PartnerResourceGroupName och PartnerServerName från cmdleten Remove-AzureRmSqlDatabaseFailoverGroup
  - Lade till parametern GracePeriodWithDataLossHours till cmdletarna New- och Set- som så småningom kommer ersätta GracePeriodWithDataLossHour
  - Dokumentation har utökats och uppdaterats
  - Formateringen för returnerade objekt har ändrats och en del fel har korrigerats där fält inte alltid var ifyllda
  - Egenskaperna DatabaseNames och PartnerLocation har lagts till i redundansgruppobjektet
  - Felet som gjorde att Switch-cmdleten returnerade omedelbart istället för att vänta tills åtgärden var slutförd har korrigerats
  - Felet med heltalsspill har korrigerats för när ett högt respitperiodvärde används
  - Justera respitperioden till minst 1 timme om en lägre sådan anges
  - Ta bort "Usage_Anomaly" från godkända värden för "ExcludedDetectionType"-parametern för cmdleten Set-AzureRmSqlDatabaseThreatDetectionPolicy och cmdleten Set-AzureRmSqlServerThreatDetectionPolicy.
* Lagring
  - Uppgradera SRP SDK till 6.3.0
  - New/Set-AzureRmStorageAccount:Lägg till en ny parameter för att stödja EnableHttpsTrafficOnly
  - New/Set/Get-AzureRmStorageAccount: Returnerat lagringskonto innehåller ett nytt attribut EnableHttpsTrafficOnly
* Azure.Storage
  - Uppgradera till Azure Storage-klientbiblioteket 8.1.1 och Azure Storage DataMovement-biblioteket 0.5.1
  - Lägg till en ny cmdlet för att stödja den inkrementella kopieringsfunktionen i blobbar
