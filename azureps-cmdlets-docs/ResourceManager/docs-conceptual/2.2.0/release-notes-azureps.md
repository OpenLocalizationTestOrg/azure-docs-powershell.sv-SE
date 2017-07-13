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
ms.date: 05/18/2017
ms.openlocfilehash: 143d92384fd270711378f6741ba59e88c12833d1
ms.sourcegitcommit: 226527be7cb647acfe2ea9ab151185053ab3c6db
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2017
---
# <span data-ttu-id="14da0-103">Viktig information</span><span class="sxs-lookup"><span data-stu-id="14da0-103">Release notes</span></span>
<a id="release-notes" class="xliff"></a>

<span data-ttu-id="14da0-104">Det här är en lista över ändringar som har gjorts i Azure PowerShell i den här versionen.</span><span class="sxs-lookup"><span data-stu-id="14da0-104">This is a list of changes made to Azure PowerShell in this release.</span></span>

## <span data-ttu-id="14da0-105">Version 2.2.0</span><span class="sxs-lookup"><span data-stu-id="14da0-105">Version 2.2.0</span></span>
<a id="version-220" class="xliff"></a>
* <span data-ttu-id="14da0-106">Compute</span><span class="sxs-lookup"><span data-stu-id="14da0-106">Compute</span></span>
  - <span data-ttu-id="14da0-107">Stöd för frågor om krypteringsstatus från tillägget AzureDiskEncryptionForLinux har lagts till</span><span class="sxs-lookup"><span data-stu-id="14da0-107">Add support for querying encryption status from the AzureDiskEncryptionForLinux extension</span></span>
* <span data-ttu-id="14da0-108">DataFactory</span><span class="sxs-lookup"><span data-stu-id="14da0-108">DataFactory</span></span>
  - <span data-ttu-id="14da0-109">Ny cmdlet för att visa aktivitetsfönster har lagts till</span><span class="sxs-lookup"><span data-stu-id="14da0-109">Added new cmdlet for listing activity windows</span></span>
    + <span data-ttu-id="14da0-110">Get-AzureRmDataFactoryActivityWindow</span><span class="sxs-lookup"><span data-stu-id="14da0-110">Get-AzureRmDataFactoryActivityWindow</span></span>
* <span data-ttu-id="14da0-111">DataLake</span><span class="sxs-lookup"><span data-stu-id="14da0-111">DataLake</span></span>
  - <span data-ttu-id="14da0-112">Parametern `Host` har ändrats till `DatabaseHost` och alias har lagts till för `Host`</span><span class="sxs-lookup"><span data-stu-id="14da0-112">Changed parameter `Host` to `DatabaseHost` and added alias to `Host`</span></span>
    + <span data-ttu-id="14da0-113">New-AzureRmDataLakeAnalyticsCatalogSecret</span><span class="sxs-lookup"><span data-stu-id="14da0-113">New-AzureRmDataLakeAnalyticsCatalogSecret</span></span>
    + <span data-ttu-id="14da0-114">Set-AzureRmDataLakeAnalyticsCatalogSecret</span><span class="sxs-lookup"><span data-stu-id="14da0-114">Set-AzureRmDataLakeAnalyticsCatalogSecret</span></span>
  - <span data-ttu-id="14da0-115">Stöd för borttagning av ACL och standard-ACL har lagts till</span><span class="sxs-lookup"><span data-stu-id="14da0-115">Add support for ACL and Default ACL removal</span></span>
  - <span data-ttu-id="14da0-116">Stöd för att hämta och ange ej namngivna behörigheter för filer och mappar har lagts till</span><span class="sxs-lookup"><span data-stu-id="14da0-116">Add support for getting and setting unnamed permissions on files and folders</span></span>
* <span data-ttu-id="14da0-117">KeyVault</span><span class="sxs-lookup"><span data-stu-id="14da0-117">KeyVault</span></span>
  - <span data-ttu-id="14da0-118">Stöd för certifikat har lagts till</span><span class="sxs-lookup"><span data-stu-id="14da0-118">Add support for certificates</span></span>
    + <span data-ttu-id="14da0-119">Add-AzureKeyVaultCertificate</span><span class="sxs-lookup"><span data-stu-id="14da0-119">Add-AzureKeyVaultCertificate</span></span>
    + <span data-ttu-id="14da0-120">Add-AzureKeyVaultCertificateContact</span><span class="sxs-lookup"><span data-stu-id="14da0-120">Add-AzureKeyVaultCertificateContact</span></span>
    + <span data-ttu-id="14da0-121">Get-AzureKeyVaultCertificate</span><span class="sxs-lookup"><span data-stu-id="14da0-121">Get-AzureKeyVaultCertificate</span></span>
    + <span data-ttu-id="14da0-122">Get-AzureKeyVaultCertificateContact</span><span class="sxs-lookup"><span data-stu-id="14da0-122">Get-AzureKeyVaultCertificateContact</span></span>
    + <span data-ttu-id="14da0-123">Get-AzureKeyVaultCertificateIssuer</span><span class="sxs-lookup"><span data-stu-id="14da0-123">Get-AzureKeyVaultCertificateIssuer</span></span>
    + <span data-ttu-id="14da0-124">Get-AzureKeyVaultCertificateOperation</span><span class="sxs-lookup"><span data-stu-id="14da0-124">Get-AzureKeyVaultCertificateOperation</span></span>
    + <span data-ttu-id="14da0-125">Get-AzureKeyVaultCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="14da0-125">Get-AzureKeyVaultCertificatePolicy</span></span>
    + <span data-ttu-id="14da0-126">Import-AzureKeyVaultCertificate</span><span class="sxs-lookup"><span data-stu-id="14da0-126">Import-AzureKeyVaultCertificate</span></span>
    + <span data-ttu-id="14da0-127">New-AzureKeyVaultCertificateAdministratorDetails</span><span class="sxs-lookup"><span data-stu-id="14da0-127">New-AzureKeyVaultCertificateAdministratorDetails</span></span>
    + <span data-ttu-id="14da0-128">New-AzureKeyVaultCertificateOrganizationDetails</span><span class="sxs-lookup"><span data-stu-id="14da0-128">New-AzureKeyVaultCertificateOrganizationDetails</span></span>
    + <span data-ttu-id="14da0-129">New-AzureKeyVaultCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="14da0-129">New-AzureKeyVaultCertificatePolicy</span></span>
    + <span data-ttu-id="14da0-130">Remove-AzureKeyVaultCertificate</span><span class="sxs-lookup"><span data-stu-id="14da0-130">Remove-AzureKeyVaultCertificate</span></span>
    + <span data-ttu-id="14da0-131">Remove-AzureKeyVaultCertificateContact</span><span class="sxs-lookup"><span data-stu-id="14da0-131">Remove-AzureKeyVaultCertificateContact</span></span>
    + <span data-ttu-id="14da0-132">Remove-AzureKeyVaultCertificateIssuer</span><span class="sxs-lookup"><span data-stu-id="14da0-132">Remove-AzureKeyVaultCertificateIssuer</span></span>
    + <span data-ttu-id="14da0-133">Remove-AzureKeyVaultCertificateOperation</span><span class="sxs-lookup"><span data-stu-id="14da0-133">Remove-AzureKeyVaultCertificateOperation</span></span>
    + <span data-ttu-id="14da0-134">Set-AzureKeyVaultCertificateAttribute</span><span class="sxs-lookup"><span data-stu-id="14da0-134">Set-AzureKeyVaultCertificateAttribute</span></span>
    + <span data-ttu-id="14da0-135">Set-AzureKeyVaultCertificateIssuer</span><span class="sxs-lookup"><span data-stu-id="14da0-135">Set-AzureKeyVaultCertificateIssuer</span></span>
    + <span data-ttu-id="14da0-136">Set-AzureKeyVaultCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="14da0-136">Set-AzureKeyVaultCertificatePolicy</span></span>
    + <span data-ttu-id="14da0-137">Stop-AzureKeyVaultCertificateOperation</span><span class="sxs-lookup"><span data-stu-id="14da0-137">Stop-AzureKeyVaultCertificateOperation</span></span>
* <span data-ttu-id="14da0-138">Nätverk</span><span class="sxs-lookup"><span data-stu-id="14da0-138">Network</span></span>

  - <span data-ttu-id="14da0-139">Ny switchparameter har lagts till för nätverksgränssnittet för att aktivera/inaktivera accelererat nätverk +New-AzureRmNetworkInterface -EnableAcceleratedNetworking</span><span class="sxs-lookup"><span data-stu-id="14da0-139">New switch parameter added for network interface to enable/disable accelerated networking +New-AzureRmNetworkInterface -EnableAcceleratedNetworking</span></span>
  - <span data-ttu-id="14da0-140">PowerShell-cmdletar för att aktivera gateway-funktionen aktiv-aktiv</span><span class="sxs-lookup"><span data-stu-id="14da0-140">Enable Active-Active gateway feature PowerShell cmdlets</span></span>
    + <span data-ttu-id="14da0-141">Add-AzureRmVirtualNetworkGatewayIpConfig</span><span class="sxs-lookup"><span data-stu-id="14da0-141">Add-AzureRmVirtualNetworkGatewayIpConfig</span></span>
    + <span data-ttu-id="14da0-142">Remove-AzureRmVirtualNetworkGatewayIpConfig</span><span class="sxs-lookup"><span data-stu-id="14da0-142">Remove-AzureRmVirtualNetworkGatewayIpConfig</span></span>
  - <span data-ttu-id="14da0-143">Ny cmdlet har lagts till</span><span class="sxs-lookup"><span data-stu-id="14da0-143">Added new cmdlet</span></span>
    + <span data-ttu-id="14da0-144">Test-AzureRmPrivateIpAddressAvailability</span><span class="sxs-lookup"><span data-stu-id="14da0-144">Test-AzureRmPrivateIpAddressAvailability</span></span>
* <span data-ttu-id="14da0-145">Resurser</span><span class="sxs-lookup"><span data-stu-id="14da0-145">Resources</span></span>
  - <span data-ttu-id="14da0-146">Stöd för zoner i provider- och resurs-cmdletar</span><span class="sxs-lookup"><span data-stu-id="14da0-146">Support zones in provider and resource cmdlets</span></span>
    + <span data-ttu-id="14da0-147">Get-AzureRmProvider</span><span class="sxs-lookup"><span data-stu-id="14da0-147">Get-AzureRmProvider</span></span>
    + <span data-ttu-id="14da0-148">New-AzureRmResource</span><span class="sxs-lookup"><span data-stu-id="14da0-148">New-AzureRmResource</span></span>
    + <span data-ttu-id="14da0-149">Set-AzureRmResource</span><span class="sxs-lookup"><span data-stu-id="14da0-149">Set-AzureRmResource</span></span>
* <span data-ttu-id="14da0-150">SQL</span><span class="sxs-lookup"><span data-stu-id="14da0-150">Sql</span></span>
  - <span data-ttu-id="14da0-151">Nya cmdletar har lagts till för principhantering av Azure SQL-hotidentifiering på servernivå</span><span class="sxs-lookup"><span data-stu-id="14da0-151">Added new cmdlets for Azure SQL threat detection policy management at server level</span></span>
    + <span data-ttu-id="14da0-152">Get-AzureRmSqlServerThreatDetectionPolicy</span><span class="sxs-lookup"><span data-stu-id="14da0-152">Get-AzureRmSqlServerThreatDetectionPolicy</span></span>
    + <span data-ttu-id="14da0-153">Remove-AzureRmSqlServerThreatDetectionPolicy</span><span class="sxs-lookup"><span data-stu-id="14da0-153">Remove-AzureRmSqlServerThreatDetectionPolicy</span></span>
    + <span data-ttu-id="14da0-154">Set-AzureRmSqlServerThreatDetectionPolicy</span><span class="sxs-lookup"><span data-stu-id="14da0-154">Set-AzureRmSqlServerThreatDetectionPolicy</span></span>
  - <span data-ttu-id="14da0-155">Nya cmdletar har lagts till för aktivera/inaktivera GeoBackupPolicy för Sql Azure DataWarehouses</span><span class="sxs-lookup"><span data-stu-id="14da0-155">Added new cmdlets to support enabling/disabling GeoBackupPolicy for Sql Azure DataWarehouses</span></span>
    + <span data-ttu-id="14da0-156">Get-AzureRmSqlDatabaseGeoBackupPolicy</span><span class="sxs-lookup"><span data-stu-id="14da0-156">Get-AzureRmSqlDatabaseGeoBackupPolicy</span></span>
    + <span data-ttu-id="14da0-157">Set-AzureRmSqlDatabaseGeoBackupPolicy</span><span class="sxs-lookup"><span data-stu-id="14da0-157">Set-AzureRmSqlDatabaseGeoBackupPolicy</span></span>
  - <span data-ttu-id="14da0-158">Nya cmdletar har lagts till för Azure SQL Advisors och för API:er för rekommenderade åtgärder</span><span class="sxs-lookup"><span data-stu-id="14da0-158">Added new cmdlets for Azure Sql Advisors and Recommended Actions APIs</span></span>
    + <span data-ttu-id="14da0-159">Get-AzureRmSqlDatabaseAdvisor</span><span class="sxs-lookup"><span data-stu-id="14da0-159">Get-AzureRmSqlDatabaseAdvisor</span></span>
    + <span data-ttu-id="14da0-160">Get-AzureRmSqlElasticPoolAdvisor</span><span class="sxs-lookup"><span data-stu-id="14da0-160">Get-AzureRmSqlElasticPoolAdvisor</span></span>
    + <span data-ttu-id="14da0-161">Get-AzureRmSqlServerAdvisor</span><span class="sxs-lookup"><span data-stu-id="14da0-161">Get-AzureRmSqlServerAdvisor</span></span>
    + <span data-ttu-id="14da0-162">Get-AzureRmSqlDatabaseRecommendedActions</span><span class="sxs-lookup"><span data-stu-id="14da0-162">Get-AzureRmSqlDatabaseRecommendedActions</span></span>
    + <span data-ttu-id="14da0-163">Get-AzureRmSqlElasticPoolRecommendedActions</span><span class="sxs-lookup"><span data-stu-id="14da0-163">Get-AzureRmSqlElasticPoolRecommendedActions</span></span>
    + <span data-ttu-id="14da0-164">Get-AzureRmSqlServerRecommendedActions</span><span class="sxs-lookup"><span data-stu-id="14da0-164">Get-AzureRmSqlServerRecommendedActions</span></span>
    + <span data-ttu-id="14da0-165">Set-AzureRmSqlDatabaseAdvisorAutoExecuteStatus</span><span class="sxs-lookup"><span data-stu-id="14da0-165">Set-AzureRmSqlDatabaseAdvisorAutoExecuteStatus</span></span>
    + <span data-ttu-id="14da0-166">Set-AzureRmSqlElasticPoolAdvisorAutoExecuteStatus</span><span class="sxs-lookup"><span data-stu-id="14da0-166">Set-AzureRmSqlElasticPoolAdvisorAutoExecuteStatus</span></span>
    + <span data-ttu-id="14da0-167">Set-AzureRmSqlServerAdvisorAutoExecuteStatus</span><span class="sxs-lookup"><span data-stu-id="14da0-167">Set-AzureRmSqlServerAdvisorAutoExecuteStatus</span></span>
    + <span data-ttu-id="14da0-168">Set-AzureRmSqlDatabaseRecommendedActionState</span><span class="sxs-lookup"><span data-stu-id="14da0-168">Set-AzureRmSqlDatabaseRecommendedActionState</span></span>
    + <span data-ttu-id="14da0-169">Set-AzureRmSqlElasticPoolRecommendedActionState</span><span class="sxs-lookup"><span data-stu-id="14da0-169">Set-AzureRmSqlElasticPoolRecommendedActionState</span></span>
    + <span data-ttu-id="14da0-170">Set-AzureRmSqlServerRecommendedActionState</span><span class="sxs-lookup"><span data-stu-id="14da0-170">Set-AzureRmSqlServerRecommendedActionState</span></span>
