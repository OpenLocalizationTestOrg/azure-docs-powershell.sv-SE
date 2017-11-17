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
ms.sourcegitcommit: b256bf48e15ee98865de0fae50e7b81878b03a54
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2017
---
# <a name="release-notes"></a><span data-ttu-id="4e198-103">Viktig information</span><span class="sxs-lookup"><span data-stu-id="4e198-103">Release notes</span></span>

<span data-ttu-id="4e198-104">Det här är en lista över ändringar som har gjorts i Azure PowerShell i den här versionen.</span><span class="sxs-lookup"><span data-stu-id="4e198-104">This is a list of changes made to Azure PowerShell in this release.</span></span>

## <a name="version-220"></a><span data-ttu-id="4e198-105">Version 2.2.0</span><span class="sxs-lookup"><span data-stu-id="4e198-105">Version 2.2.0</span></span>
* <span data-ttu-id="4e198-106">Compute</span><span class="sxs-lookup"><span data-stu-id="4e198-106">Compute</span></span>
  - <span data-ttu-id="4e198-107">Stöd för frågor om krypteringsstatus från tillägget AzureDiskEncryptionForLinux har lagts till</span><span class="sxs-lookup"><span data-stu-id="4e198-107">Add support for querying encryption status from the AzureDiskEncryptionForLinux extension</span></span>
* <span data-ttu-id="4e198-108">DataFactory</span><span class="sxs-lookup"><span data-stu-id="4e198-108">DataFactory</span></span>
  - <span data-ttu-id="4e198-109">Ny cmdlet för att visa aktivitetsfönster har lagts till</span><span class="sxs-lookup"><span data-stu-id="4e198-109">Added new cmdlet for listing activity windows</span></span>
    + <span data-ttu-id="4e198-110">Get-AzureRmDataFactoryActivityWindow</span><span class="sxs-lookup"><span data-stu-id="4e198-110">Get-AzureRmDataFactoryActivityWindow</span></span>
* <span data-ttu-id="4e198-111">DataLake</span><span class="sxs-lookup"><span data-stu-id="4e198-111">DataLake</span></span>
  - <span data-ttu-id="4e198-112">Parametern `Host` har ändrats till `DatabaseHost` och alias har lagts till för `Host`</span><span class="sxs-lookup"><span data-stu-id="4e198-112">Changed parameter `Host` to `DatabaseHost` and added alias to `Host`</span></span>
    + <span data-ttu-id="4e198-113">New-AzureRmDataLakeAnalyticsCatalogSecret</span><span class="sxs-lookup"><span data-stu-id="4e198-113">New-AzureRmDataLakeAnalyticsCatalogSecret</span></span>
    + <span data-ttu-id="4e198-114">Set-AzureRmDataLakeAnalyticsCatalogSecret</span><span class="sxs-lookup"><span data-stu-id="4e198-114">Set-AzureRmDataLakeAnalyticsCatalogSecret</span></span>
  - <span data-ttu-id="4e198-115">Stöd för borttagning av ACL och standard-ACL har lagts till</span><span class="sxs-lookup"><span data-stu-id="4e198-115">Add support for ACL and Default ACL removal</span></span>
  - <span data-ttu-id="4e198-116">Stöd för att hämta och ange ej namngivna behörigheter för filer och mappar har lagts till</span><span class="sxs-lookup"><span data-stu-id="4e198-116">Add support for getting and setting unnamed permissions on files and folders</span></span>
* <span data-ttu-id="4e198-117">KeyVault</span><span class="sxs-lookup"><span data-stu-id="4e198-117">KeyVault</span></span>
  - <span data-ttu-id="4e198-118">Stöd för certifikat har lagts till</span><span class="sxs-lookup"><span data-stu-id="4e198-118">Add support for certificates</span></span>
    + <span data-ttu-id="4e198-119">Add-AzureKeyVaultCertificate</span><span class="sxs-lookup"><span data-stu-id="4e198-119">Add-AzureKeyVaultCertificate</span></span>
    + <span data-ttu-id="4e198-120">Add-AzureKeyVaultCertificateContact</span><span class="sxs-lookup"><span data-stu-id="4e198-120">Add-AzureKeyVaultCertificateContact</span></span>
    + <span data-ttu-id="4e198-121">Get-AzureKeyVaultCertificate</span><span class="sxs-lookup"><span data-stu-id="4e198-121">Get-AzureKeyVaultCertificate</span></span>
    + <span data-ttu-id="4e198-122">Get-AzureKeyVaultCertificateContact</span><span class="sxs-lookup"><span data-stu-id="4e198-122">Get-AzureKeyVaultCertificateContact</span></span>
    + <span data-ttu-id="4e198-123">Get-AzureKeyVaultCertificateIssuer</span><span class="sxs-lookup"><span data-stu-id="4e198-123">Get-AzureKeyVaultCertificateIssuer</span></span>
    + <span data-ttu-id="4e198-124">Get-AzureKeyVaultCertificateOperation</span><span class="sxs-lookup"><span data-stu-id="4e198-124">Get-AzureKeyVaultCertificateOperation</span></span>
    + <span data-ttu-id="4e198-125">Get-AzureKeyVaultCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="4e198-125">Get-AzureKeyVaultCertificatePolicy</span></span>
    + <span data-ttu-id="4e198-126">Import-AzureKeyVaultCertificate</span><span class="sxs-lookup"><span data-stu-id="4e198-126">Import-AzureKeyVaultCertificate</span></span>
    + <span data-ttu-id="4e198-127">New-AzureKeyVaultCertificateAdministratorDetails</span><span class="sxs-lookup"><span data-stu-id="4e198-127">New-AzureKeyVaultCertificateAdministratorDetails</span></span>
    + <span data-ttu-id="4e198-128">New-AzureKeyVaultCertificateOrganizationDetails</span><span class="sxs-lookup"><span data-stu-id="4e198-128">New-AzureKeyVaultCertificateOrganizationDetails</span></span>
    + <span data-ttu-id="4e198-129">New-AzureKeyVaultCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="4e198-129">New-AzureKeyVaultCertificatePolicy</span></span>
    + <span data-ttu-id="4e198-130">Remove-AzureKeyVaultCertificate</span><span class="sxs-lookup"><span data-stu-id="4e198-130">Remove-AzureKeyVaultCertificate</span></span>
    + <span data-ttu-id="4e198-131">Remove-AzureKeyVaultCertificateContact</span><span class="sxs-lookup"><span data-stu-id="4e198-131">Remove-AzureKeyVaultCertificateContact</span></span>
    + <span data-ttu-id="4e198-132">Remove-AzureKeyVaultCertificateIssuer</span><span class="sxs-lookup"><span data-stu-id="4e198-132">Remove-AzureKeyVaultCertificateIssuer</span></span>
    + <span data-ttu-id="4e198-133">Remove-AzureKeyVaultCertificateOperation</span><span class="sxs-lookup"><span data-stu-id="4e198-133">Remove-AzureKeyVaultCertificateOperation</span></span>
    + <span data-ttu-id="4e198-134">Set-AzureKeyVaultCertificateAttribute</span><span class="sxs-lookup"><span data-stu-id="4e198-134">Set-AzureKeyVaultCertificateAttribute</span></span>
    + <span data-ttu-id="4e198-135">Set-AzureKeyVaultCertificateIssuer</span><span class="sxs-lookup"><span data-stu-id="4e198-135">Set-AzureKeyVaultCertificateIssuer</span></span>
    + <span data-ttu-id="4e198-136">Set-AzureKeyVaultCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="4e198-136">Set-AzureKeyVaultCertificatePolicy</span></span>
    + <span data-ttu-id="4e198-137">Stop-AzureKeyVaultCertificateOperation</span><span class="sxs-lookup"><span data-stu-id="4e198-137">Stop-AzureKeyVaultCertificateOperation</span></span>
* <span data-ttu-id="4e198-138">Nätverk</span><span class="sxs-lookup"><span data-stu-id="4e198-138">Network</span></span>

  - <span data-ttu-id="4e198-139">Ny switchparameter har lagts till för nätverksgränssnittet för att aktivera/inaktivera accelererat nätverk +New-AzureRmNetworkInterface -EnableAcceleratedNetworking</span><span class="sxs-lookup"><span data-stu-id="4e198-139">New switch parameter added for network interface to enable/disable accelerated networking +New-AzureRmNetworkInterface -EnableAcceleratedNetworking</span></span>
  - <span data-ttu-id="4e198-140">PowerShell-cmdletar för att aktivera gateway-funktionen aktiv-aktiv</span><span class="sxs-lookup"><span data-stu-id="4e198-140">Enable Active-Active gateway feature PowerShell cmdlets</span></span>
    + <span data-ttu-id="4e198-141">Add-AzureRmVirtualNetworkGatewayIpConfig</span><span class="sxs-lookup"><span data-stu-id="4e198-141">Add-AzureRmVirtualNetworkGatewayIpConfig</span></span>
    + <span data-ttu-id="4e198-142">Remove-AzureRmVirtualNetworkGatewayIpConfig</span><span class="sxs-lookup"><span data-stu-id="4e198-142">Remove-AzureRmVirtualNetworkGatewayIpConfig</span></span>
  - <span data-ttu-id="4e198-143">Ny cmdlet har lagts till</span><span class="sxs-lookup"><span data-stu-id="4e198-143">Added new cmdlet</span></span>
    + <span data-ttu-id="4e198-144">Test-AzureRmPrivateIpAddressAvailability</span><span class="sxs-lookup"><span data-stu-id="4e198-144">Test-AzureRmPrivateIpAddressAvailability</span></span>
* <span data-ttu-id="4e198-145">Resurser</span><span class="sxs-lookup"><span data-stu-id="4e198-145">Resources</span></span>
  - <span data-ttu-id="4e198-146">Stöd för zoner i provider- och resurs-cmdletar</span><span class="sxs-lookup"><span data-stu-id="4e198-146">Support zones in provider and resource cmdlets</span></span>
    + <span data-ttu-id="4e198-147">Get-AzureRmProvider</span><span class="sxs-lookup"><span data-stu-id="4e198-147">Get-AzureRmProvider</span></span>
    + <span data-ttu-id="4e198-148">New-AzureRmResource</span><span class="sxs-lookup"><span data-stu-id="4e198-148">New-AzureRmResource</span></span>
    + <span data-ttu-id="4e198-149">Set-AzureRmResource</span><span class="sxs-lookup"><span data-stu-id="4e198-149">Set-AzureRmResource</span></span>
* <span data-ttu-id="4e198-150">SQL</span><span class="sxs-lookup"><span data-stu-id="4e198-150">Sql</span></span>
  - <span data-ttu-id="4e198-151">Nya cmdletar har lagts till för principhantering av Azure SQL-hotidentifiering på servernivå</span><span class="sxs-lookup"><span data-stu-id="4e198-151">Added new cmdlets for Azure SQL threat detection policy management at server level</span></span>
    + <span data-ttu-id="4e198-152">Get-AzureRmSqlServerThreatDetectionPolicy</span><span class="sxs-lookup"><span data-stu-id="4e198-152">Get-AzureRmSqlServerThreatDetectionPolicy</span></span>
    + <span data-ttu-id="4e198-153">Remove-AzureRmSqlServerThreatDetectionPolicy</span><span class="sxs-lookup"><span data-stu-id="4e198-153">Remove-AzureRmSqlServerThreatDetectionPolicy</span></span>
    + <span data-ttu-id="4e198-154">Set-AzureRmSqlServerThreatDetectionPolicy</span><span class="sxs-lookup"><span data-stu-id="4e198-154">Set-AzureRmSqlServerThreatDetectionPolicy</span></span>
  - <span data-ttu-id="4e198-155">Nya cmdletar har lagts till för aktivera/inaktivera GeoBackupPolicy för Sql Azure DataWarehouses</span><span class="sxs-lookup"><span data-stu-id="4e198-155">Added new cmdlets to support enabling/disabling GeoBackupPolicy for Sql Azure DataWarehouses</span></span>
    + <span data-ttu-id="4e198-156">Get-AzureRmSqlDatabaseGeoBackupPolicy</span><span class="sxs-lookup"><span data-stu-id="4e198-156">Get-AzureRmSqlDatabaseGeoBackupPolicy</span></span>
    + <span data-ttu-id="4e198-157">Set-AzureRmSqlDatabaseGeoBackupPolicy</span><span class="sxs-lookup"><span data-stu-id="4e198-157">Set-AzureRmSqlDatabaseGeoBackupPolicy</span></span>
  - <span data-ttu-id="4e198-158">Nya cmdletar har lagts till för Azure SQL Advisors och för API:er för rekommenderade åtgärder</span><span class="sxs-lookup"><span data-stu-id="4e198-158">Added new cmdlets for Azure Sql Advisors and Recommended Actions APIs</span></span>
    + <span data-ttu-id="4e198-159">Get-AzureRmSqlDatabaseAdvisor</span><span class="sxs-lookup"><span data-stu-id="4e198-159">Get-AzureRmSqlDatabaseAdvisor</span></span>
    + <span data-ttu-id="4e198-160">Get-AzureRmSqlElasticPoolAdvisor</span><span class="sxs-lookup"><span data-stu-id="4e198-160">Get-AzureRmSqlElasticPoolAdvisor</span></span>
    + <span data-ttu-id="4e198-161">Get-AzureRmSqlServerAdvisor</span><span class="sxs-lookup"><span data-stu-id="4e198-161">Get-AzureRmSqlServerAdvisor</span></span>
    + <span data-ttu-id="4e198-162">Get-AzureRmSqlDatabaseRecommendedActions</span><span class="sxs-lookup"><span data-stu-id="4e198-162">Get-AzureRmSqlDatabaseRecommendedActions</span></span>
    + <span data-ttu-id="4e198-163">Get-AzureRmSqlElasticPoolRecommendedActions</span><span class="sxs-lookup"><span data-stu-id="4e198-163">Get-AzureRmSqlElasticPoolRecommendedActions</span></span>
    + <span data-ttu-id="4e198-164">Get-AzureRmSqlServerRecommendedActions</span><span class="sxs-lookup"><span data-stu-id="4e198-164">Get-AzureRmSqlServerRecommendedActions</span></span>
    + <span data-ttu-id="4e198-165">Set-AzureRmSqlDatabaseAdvisorAutoExecuteStatus</span><span class="sxs-lookup"><span data-stu-id="4e198-165">Set-AzureRmSqlDatabaseAdvisorAutoExecuteStatus</span></span>
    + <span data-ttu-id="4e198-166">Set-AzureRmSqlElasticPoolAdvisorAutoExecuteStatus</span><span class="sxs-lookup"><span data-stu-id="4e198-166">Set-AzureRmSqlElasticPoolAdvisorAutoExecuteStatus</span></span>
    + <span data-ttu-id="4e198-167">Set-AzureRmSqlServerAdvisorAutoExecuteStatus</span><span class="sxs-lookup"><span data-stu-id="4e198-167">Set-AzureRmSqlServerAdvisorAutoExecuteStatus</span></span>
    + <span data-ttu-id="4e198-168">Set-AzureRmSqlDatabaseRecommendedActionState</span><span class="sxs-lookup"><span data-stu-id="4e198-168">Set-AzureRmSqlDatabaseRecommendedActionState</span></span>
    + <span data-ttu-id="4e198-169">Set-AzureRmSqlElasticPoolRecommendedActionState</span><span class="sxs-lookup"><span data-stu-id="4e198-169">Set-AzureRmSqlElasticPoolRecommendedActionState</span></span>
    + <span data-ttu-id="4e198-170">Set-AzureRmSqlServerRecommendedActionState</span><span class="sxs-lookup"><span data-stu-id="4e198-170">Set-AzureRmSqlServerRecommendedActionState</span></span>
