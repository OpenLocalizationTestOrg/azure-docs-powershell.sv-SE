---
title: Installera och konfigurera Azure PowerShell | Microsoft Docs
description: "Installera och konfigurera Azure PowerShell för första gången."
services: azure
author: sdwheeler
ms.author: sewhee
manager: carmonm
ms.product: azure
ms.service: azure-powershell
ms.devlang: powershell
ms.topic: conceptual
ms.date: 08/31/2017
ms.openlocfilehash: 0e560332c87fdcc8b7365f2271de24481003a4d6
ms.sourcegitcommit: b256bf48e15ee98865de0fae50e7b81878b03a54
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2017
---
# <a name="install-and-configure-azure-powershell"></a><span data-ttu-id="01218-103">Installera och konfigurera Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="01218-103">Install and configure Azure PowerShell</span></span>

<span data-ttu-id="01218-104">Den här artikeln beskriver stegen för att installera Azure PowerShell-moduler i en Windows-miljö.</span><span class="sxs-lookup"><span data-stu-id="01218-104">This article explains the steps to install the Azure PowerShell modules in a Windows environment.</span></span>
<span data-ttu-id="01218-105">Läs följande artikel om du vill använda Azure PowerShell på macOS eller Linux: [Installera och konfigurera Azure PowerShell på macOS och Linux](install-azurermps-maclinux.md).</span><span class="sxs-lookup"><span data-stu-id="01218-105">If you want to use Azure PowerShell on macOS or Linux, see the following article: [Install and configure Azure PowerShell on macOS and Linux](install-azurermps-maclinux.md).</span></span>

<span data-ttu-id="01218-106">Det rekommenderade sättet att installera Azure PowerShell är från PowerShell-galleriet.</span><span class="sxs-lookup"><span data-stu-id="01218-106">Installing Azure PowerShell from the PowerShell Gallery is the preferred method of installation.</span></span>

## <a name="step-1-install-powershellget"></a><span data-ttu-id="01218-107">Steg 1: Installera PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="01218-107">Step 1: Install PowerShellGet</span></span>

<span data-ttu-id="01218-108">Du måste ha modulen PowerShellGet för att kunna installera objekt från PowerShell-galleriet.</span><span class="sxs-lookup"><span data-stu-id="01218-108">Installing items from the PowerShell Gallery requires the PowerShellGet module.</span></span> <span data-ttu-id="01218-109">Kontrollera att du har rätt version av PowerShellGet och att datorn uppfyller övriga systemkrav.</span><span class="sxs-lookup"><span data-stu-id="01218-109">Make sure you have the appropriate version of PowerShellGet and other system requirements.</span></span> <span data-ttu-id="01218-110">Kör följande kommando för att se om du har PowerShellGet installerat på datorn.</span><span class="sxs-lookup"><span data-stu-id="01218-110">Run the following command to see if you have PowerShellGet installed on your system.</span></span>

```powershell
Get-Module PowerShellGet -list | Select-Object Name,Version,Path
```

<span data-ttu-id="01218-111">Nu bör du se utdata som ser ut ungefär så här:</span><span class="sxs-lookup"><span data-stu-id="01218-111">You should see something similar to the following output:</span></span>

```Output
Name          Version Path
----          ------- ----
PowerShellGet 1.0.0.1 C:\Program Files\WindowsPowerShell\Modules\PowerShellGet\1.0.0.1\PowerShellGet.psd1
```

<span data-ttu-id="01218-112">Om du inte har installerat PowerShellGet kan du läsa avsnittet [Hämta PowerShellGet](#how-to-get-powershellget) i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="01218-112">If you do not have PowerShellGet installed, see the [How to get PowerShellGet](#how-to-get-powershellget) section of this article.</span></span>

> [!NOTE]
> <span data-ttu-id="01218-113">För att kunna använda PowerShellGet, krävs en körningsprincip som låter dig köra skript.</span><span class="sxs-lookup"><span data-stu-id="01218-113">Using PowerShellGet requires an Execution Policy that allows you to run scripts.</span></span> <span data-ttu-id="01218-114">Mer information om PowerShell-körningsprincipen finns i [Om körningsprinciper](/powershell/module/microsoft.powershell.core/about/about_execution_policies).</span><span class="sxs-lookup"><span data-stu-id="01218-114">For more information about PowerShell's Execution Policy, see [About Execution Policies](/powershell/module/microsoft.powershell.core/about/about_execution_policies).</span></span>

## <a name="step-2-install-azure-powershell"></a><span data-ttu-id="01218-115">Steg 2: Installera Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="01218-115">Step 2: Install Azure PowerShell</span></span>

<span data-ttu-id="01218-116">För installation av Azure PowerShell från PowerShell-galleriet krävs utökade behörigheter.</span><span class="sxs-lookup"><span data-stu-id="01218-116">Installing Azure PowerShell from the PowerShell Gallery requires elevated privileges.</span></span> <span data-ttu-id="01218-117">Kör följande kommando från en utökad PowerShell-session:</span><span class="sxs-lookup"><span data-stu-id="01218-117">Run the following command from an elevated PowerShell session:</span></span>

```powershell
# Install the Azure Resource Manager modules from the PowerShell Gallery
Install-Module AzureRM -AllowClobber
```

<span data-ttu-id="01218-118">Som standard konfigureras inte PowerShell-galleriet som en betrodd lagringsplats för PowerShellGet.</span><span class="sxs-lookup"><span data-stu-id="01218-118">By default, the PowerShell gallery is not configured as a Trusted repository for PowerShellGet.</span></span> <span data-ttu-id="01218-119">Första gången du använder PSGallery visas följande meddelande:</span><span class="sxs-lookup"><span data-stu-id="01218-119">The first time you use the PSGallery you see the following prompt:</span></span>

```Output
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the Set-PSRepository cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"): Y
```

<span data-ttu-id="01218-120">Svara Ja, eller Ja till alla om du vill fortsätta med installationen.</span><span class="sxs-lookup"><span data-stu-id="01218-120">Answer 'Yes' or 'Yes to All' to continue with the installation.</span></span>

> [!NOTE]
> <span data-ttu-id="01218-121">Om du har en version av NuGet som är äldre än 2.8.5.201, uppmanas du att ladda ner och installera den senaste versionen av NuGet.</span><span class="sxs-lookup"><span data-stu-id="01218-121">If you have a version older than 2.8.5.201 of NuGet, you are prompted to download and install the latest version of NuGet.</span></span>

<span data-ttu-id="01218-122">Modulen AzureRM är en sammanslagen modul för Azure Resource Manager-cmdletar.</span><span class="sxs-lookup"><span data-stu-id="01218-122">The AzureRM module is a rollup module for the Azure Resource Manager cmdlets.</span></span> <span data-ttu-id="01218-123">När du installerar AzureRM-modulen, kommer alla övriga Azure PowerShell-moduler som inte har installerats att laddas ner och installeras från PowerShell-galleriet.</span><span class="sxs-lookup"><span data-stu-id="01218-123">When you install the AzureRM module, any Azure PowerShell module not previously installed is downloaded and from the PowerShell Gallery.</span></span>

<span data-ttu-id="01218-124">Om du har en tidigare version av Azure PowerShell installerad så kan du få ett felmeddelande.</span><span class="sxs-lookup"><span data-stu-id="01218-124">If you have a previous version of Azure PowerShell installed you may receive an error.</span></span> <span data-ttu-id="01218-125">För att lösa problemet kan du se avsnittet [uppdatera till en ny version av Azure PowerShell](#update-azps) i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="01218-125">To resolve this issue, see the [Updating to a new version of Azure PowerShell](#update-azps) section of this article.</span></span>

## <a name="step-3-load-the-azurerm-module"></a><span data-ttu-id="01218-126">Steg 3: Läs in AzureRM-modulen</span><span class="sxs-lookup"><span data-stu-id="01218-126">Step 3: Load the AzureRM module</span></span>
<span data-ttu-id="01218-127">När modulen har installerats måste du läsa in modulen i din PowerShell-session.</span><span class="sxs-lookup"><span data-stu-id="01218-127">Once the module is installed, you need to load the module into your PowerShell session.</span></span> <span data-ttu-id="01218-128">Du bör göra det här i en normal (icke-förhöjd) PowerShell-session.</span><span class="sxs-lookup"><span data-stu-id="01218-128">You should do this in a normal (non-elevated) PowerShell session.</span></span> <span data-ttu-id="01218-129">Moduler läses in med `Import-Module`-cmdleten enligt följande:</span><span class="sxs-lookup"><span data-stu-id="01218-129">Modules are loaded using the `Import-Module` cmdlet, as follows:</span></span>

```powershell
Import-Module AzureRM
```

## <a name="next-steps"></a><span data-ttu-id="01218-130">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="01218-130">Next Steps</span></span>

<span data-ttu-id="01218-131">Mer information om hur du använder Azure PowerShell finns i följande artiklar:</span><span class="sxs-lookup"><span data-stu-id="01218-131">For more information about using Azure PowerShell, see the following articles:</span></span>

* [<span data-ttu-id="01218-132">Kom igång med Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="01218-132">Get started with Azure PowerShell</span></span>](get-started-azureps.md)

## <a name="reporting-issues-and-feedback"></a><span data-ttu-id="01218-133">Rapportera problem och feedback</span><span class="sxs-lookup"><span data-stu-id="01218-133">Reporting issues and feedback</span></span>

<span data-ttu-id="01218-134">Om du stöter på några buggar med verktyget kan du rapportera problemet i [problem](https://github.com/Azure/azure-powershell/issues)-delen av vårt GitHub-repo.</span><span class="sxs-lookup"><span data-stu-id="01218-134">If you encounter any bugs with the tool, file an issue in the [Issues](https://github.com/Azure/azure-powershell/issues) section of our GitHub repo.</span></span> <span data-ttu-id="01218-135">Om du vill ge feedback från kommandoraden, använder du cmdleten `Send-Feedback`.</span><span class="sxs-lookup"><span data-stu-id="01218-135">To provide feedback from the command line, use the `Send-Feedback` cmdlet.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="01218-136">Vanliga frågor och svar</span><span class="sxs-lookup"><span data-stu-id="01218-136">Frequently asked questions</span></span>

### <a name="how-to-get-powershellget"></a><span data-ttu-id="01218-137">Hämta PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="01218-137">How to get PowerShellGet</span></span>

|<span data-ttu-id="01218-138">OS-version</span><span class="sxs-lookup"><span data-stu-id="01218-138">OS Version</span></span>|<span data-ttu-id="01218-139">Installationsinstruktioner</span><span class="sxs-lookup"><span data-stu-id="01218-139">Install instructions</span></span>|
|---|---|
|<span data-ttu-id="01218-140">Jag har Windows 10 eller Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="01218-140">I have Windows 10 or Windows Server 2016</span></span>|<span data-ttu-id="01218-141">Inbyggt i Windows Management Framework (WMF) 5.0 som ingår i operativsystemet</span><span class="sxs-lookup"><span data-stu-id="01218-141">Built into Windows Management Framework (WMF) 5.0 included in the OS</span></span>|
|<span data-ttu-id="01218-142">Jag vill uppgradera till PowerShell 5</span><span class="sxs-lookup"><span data-stu-id="01218-142">I want to upgrade to PowerShell 5</span></span>|[<span data-ttu-id="01218-143">Installera den senaste versionen av WMF</span><span class="sxs-lookup"><span data-stu-id="01218-143">Install the latest version of WMF</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=54616)|
|<span data-ttu-id="01218-144">Jag använder en Windows-version med PowerShell 3 eller PowerShell 4</span><span class="sxs-lookup"><span data-stu-id="01218-144">I am running on a version of Windows with PowerShell 3 or PowerShell 4</span></span>|[<span data-ttu-id="01218-145">Hämta PackageManagement-moduler</span><span class="sxs-lookup"><span data-stu-id="01218-145">Get the PackageManagement modules</span></span>](http://go.microsoft.com/fwlink/?LinkID=746217)|

<a id="helpmechoose"></a>
### <a name="checking-the-version-of-azure-powershell"></a><span data-ttu-id="01218-146">Kontrollera Azure PowerShell-versionen</span><span class="sxs-lookup"><span data-stu-id="01218-146">Checking the version of Azure PowerShell</span></span>

<span data-ttu-id="01218-147">Det finns stöd för flera versioner av Azure PowerShell, men vi rekommenderar att du uppgraderar till den senaste versionen så snart som möjligt.</span><span class="sxs-lookup"><span data-stu-id="01218-147">Although we encourage you to upgrade to the latest version as early as possible, several versions of Azure PowerShell are supported.</span></span> <span data-ttu-id="01218-148">Om du vill kontrollera vilken version av Azure PowerShell som du har installerat kör du `Get-Module AzureRM` från kommandoraden.</span><span class="sxs-lookup"><span data-stu-id="01218-148">To determine the version of Azure PowerShell you have installed, run `Get-Module AzureRM` from your command line.</span></span>

```powershell
Get-Module AzureRM -list | Select-Object Name,Version,Path
```

### <a name="support-for-classic-deployment-methods"></a><span data-ttu-id="01218-149">Stöd för klassiska distributionsmetoder</span><span class="sxs-lookup"><span data-stu-id="01218-149">Support for classic deployment methods</span></span>

<span data-ttu-id="01218-150">Om du har distributioner som använder den klassiska distributionsmodellen så kan du installera Service Management-versionen av Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="01218-150">If you have deployments that use the classic deployment model you can install the Service Management version of Azure PowerShell.</span></span> <span data-ttu-id="01218-151">Läs mer i informationen om hur du [installerar Azure PowerShell Service Management-modulen](/powershell/azure/servicemanagement/install-azure-ps).</span><span class="sxs-lookup"><span data-stu-id="01218-151">For more information, see [Install the Azure PowerShell Service Management module](/powershell/azure/servicemanagement/install-azure-ps).</span></span> <span data-ttu-id="01218-152">Azure- och AzureRM-moduler delar gemensamma beroenden.</span><span class="sxs-lookup"><span data-stu-id="01218-152">The Azure and AzureRM modules share common dependencies.</span></span> <span data-ttu-id="01218-153">Om du använder både Azure- och AzureRM-moduler, bör du installera samma version av varje paket.</span><span class="sxs-lookup"><span data-stu-id="01218-153">If you use both the Azure and AzureRM modules, you should install the same version of each package.</span></span>

### <a id="update-azps"></a><span data-ttu-id="01218-154">Uppdatera till en ny version av Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="01218-154">Updating to a new version of Azure PowerShell</span></span>

<span data-ttu-id="01218-155">Om du har en tidigare version av Azure PowerShell installerad som innehåller tjänsthanteringsmodulen, kan följande felmeddelande komma upp:</span><span class="sxs-lookup"><span data-stu-id="01218-155">If you have a previous version of Azure PowerShell installed that includes the Service Management module, you may receive the following error:</span></span>

```Output
PackageManagement\Install-Package : A command with name 'Get-AzureStorageContainerAcl' is already
available on this system. This module 'Azure.Storage' may override the existing commands. If you
still want to install this module 'Azure.Storage', use -AllowClobber parameter.

At C:\Program Files\WindowsPowerShell\Modules\PowerShellGet\1.0.0.1\PSModule.psm1:1772 char:21
+ ...          $null = PackageManagement\Install-Package @PSBoundParameters
+                      ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (Microsoft.Power....InstallPackage:InstallPackage) [Install-Package], Exception
    + FullyQualifiedErrorId : CommandAlreadyAvailable,Validate-ModuleCommandAlreadyAvailable,Microsoft.PowerShell.PackageManagement.Cmdlets.InstallPackage
```

<span data-ttu-id="01218-156">Precis som felmeddelandet säger så behöver du använda parametern -AllowClobber för att installera modulen.</span><span class="sxs-lookup"><span data-stu-id="01218-156">As the error message states, you need to use the -AllowClobber parameter to install the module.</span></span> <span data-ttu-id="01218-157">Ange följande kommando:</span><span class="sxs-lookup"><span data-stu-id="01218-157">Use the following command:</span></span>

```powershell
# Install the Azure Resource Manager modules from the PowerShell Gallery
Install-Module AzureRM -AllowClobber
```

<span data-ttu-id="01218-158">Mer information finns i hjälpavsnittet för [Install-Module](https://msdn.microsoft.com/powershell/reference/5.1/PowerShellGet/install-module).</span><span class="sxs-lookup"><span data-stu-id="01218-158">For more information, see the help topic for [Install-Module](https://msdn.microsoft.com/powershell/reference/5.1/PowerShellGet/install-module).</span></span>

### <a name="installing-module-versions-side-by-side"></a><span data-ttu-id="01218-159">Installera modulversioner sida vid sida</span><span class="sxs-lookup"><span data-stu-id="01218-159">Installing module versions side by side</span></span>

<span data-ttu-id="01218-160">PowerShellGet är den enda installationsmetoden som stöder installation av flera versioner.</span><span class="sxs-lookup"><span data-stu-id="01218-160">The PowerShellGet method of installation is the only method that supports the installation of multiple versions.</span></span> <span data-ttu-id="01218-161">Du kan till exempel ha skript som är skrivna med en tidigare version av Azure PowerShell som du inte har tid eller resurser att uppdatera.</span><span class="sxs-lookup"><span data-stu-id="01218-161">For example, you may have scripts written using a previous version of Azure PowerShell that you don't have the time or resources to updated.</span></span> <span data-ttu-id="01218-162">Följande kommandon visar hur du installerar flera versioner av Azure PowerShell:</span><span class="sxs-lookup"><span data-stu-id="01218-162">The following commands illustrate how to install multiple versions of Azure PowerShell:</span></span>

```powershell
Install-Module -Name AzureRM -RequiredVersion 3.7.0
Install-Module -Name AzureRM -RequiredVersion 1.2.9
```

<span data-ttu-id="01218-163">Endast en version av modulen kan läsas in i en PowerShell-session.</span><span class="sxs-lookup"><span data-stu-id="01218-163">Only one version of the module can be loaded in a PowerShell session.</span></span> <span data-ttu-id="01218-164">Du måste öppna ett nytt PowerShell-fönster och använda `Import-Module` för att importera en specifik version av AzureRM-cmdletarna:</span><span class="sxs-lookup"><span data-stu-id="01218-164">You must open a new PowerShell window and use `Import-Module` to import a specific version of the AzureRM cmdlets:</span></span>

```powershell
Import-Module AzureRM -RequiredVersion 1.2.9
```

> [!NOTE]
> <span data-ttu-id="01218-165">Version 2.1.0 och 1.2.6 är de första modulversionerna som är avsedda att installeras och användas sida vid sida.</span><span class="sxs-lookup"><span data-stu-id="01218-165">Version 2.1.0 and version 1.2.6 are the first module versions designed to be installed and used side by side.</span></span> <span data-ttu-id="01218-166">När du laddar en tidigare version av Azure PowerShell, laddas inkompatibla versioner av modulen **AzureRM.Profile**.</span><span class="sxs-lookup"><span data-stu-id="01218-166">When loading an earlier version of the Azure PowerShell, incompatible versions of the **AzureRM.Profile** module are loaded.</span></span> <span data-ttu-id="01218-167">Det gör att cmdletarna ber dig logga in när du kör en av dem.</span><span class="sxs-lookup"><span data-stu-id="01218-167">This results in the cmdlets prompting you to log in whenever you execute a cmdlet.</span></span>

### <a name="other-installation-methods"></a><span data-ttu-id="01218-168">Andra installationsmetoder</span><span class="sxs-lookup"><span data-stu-id="01218-168">Other installation methods</span></span>

<span data-ttu-id="01218-169">Information om hur du installerar med hjälp av installationsprogrammet för webbplattform eller MSI-paketet finns [Andra installationsmetoder](other-install.md)</span><span class="sxs-lookup"><span data-stu-id="01218-169">For information about installing using the Web Platform Installer or the MSI Package, see [Other installation methods](other-install.md)</span></span>
