---
title: "Andra sätt att installera Azure PowerShell | Microsoft Docs"
description: "Så här installerar du Azure PowerShell med hjälp av MSI-paketet eller installationsprogrammet för webbplattformen."
services: azure
author: sdwheeler
ms.author: sewhee
manager: carmonm
ms.product: azure
ms.service: azure-powershell
ms.devlang: powershell
ms.topic: conceptual
ms.date: 05/15/2017
ms.openlocfilehash: 9cee582f74b7f3260c6ae167a8ac358d360ad8ab
ms.sourcegitcommit: 45587b5091293288e16cfae8ac412e0d42f8f450
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/15/2017
---
# <a name="other-installation-methods"></a><span data-ttu-id="5e5bb-103">Andra installationsmetoder</span><span class="sxs-lookup"><span data-stu-id="5e5bb-103">Other installation methods</span></span>

<span data-ttu-id="5e5bb-104">Azure PowerShell har flera olika installationsmetoder.</span><span class="sxs-lookup"><span data-stu-id="5e5bb-104">Azure PowerShell has multiple installation methods.</span></span> <span data-ttu-id="5e5bb-105">Vi rekommenderar att du använder PowerShellGet med PowerShell-galleriet.</span><span class="sxs-lookup"><span data-stu-id="5e5bb-105">Using PowerShellGet with the PowerShell Gallery is the preferred method.</span></span> <span data-ttu-id="5e5bb-106">Azure PowerShell kan installeras med installationsprogram för webbplattformen (WebPI) eller med hjälp av MSI-filen som är tillgänglig från [GitHub](https://github.com/Azure/azure-powershell/releases/latest).</span><span class="sxs-lookup"><span data-stu-id="5e5bb-106">Azure PowerShell can be installed using the Web Platform Installer (WebPI) or by using the MSI file available from [GitHub](https://github.com/Azure/azure-powershell/releases/latest).</span></span>

## <a name="docker"></a><span data-ttu-id="5e5bb-107">Docker</span><span class="sxs-lookup"><span data-stu-id="5e5bb-107">Docker</span></span>

<span data-ttu-id="5e5bb-108">Vi underhåller en Docker-avbildning som är förkonfigurerad med Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5e5bb-108">We maintain a Docker image preconfigured with Azure PowerShell.</span></span>

<span data-ttu-id="5e5bb-109">Kör behållaren med `docker run`.</span><span class="sxs-lookup"><span data-stu-id="5e5bb-109">Run the container with `docker run`.</span></span>

```powershell
docker run azuresdk/azure-powershell
```

<span data-ttu-id="5e5bb-110">Dessutom underhåller vi en delmängd cmdletar som PowerShell Core-behållare.</span><span class="sxs-lookup"><span data-stu-id="5e5bb-110">In addition, we maintain a subset of cmdlets as a PowerShell Core container.</span></span>

<span data-ttu-id="5e5bb-111">Använd `latest`-avbildningen för Mac/Linux.</span><span class="sxs-lookup"><span data-stu-id="5e5bb-111">For Mac/Linux, use the `latest` image.</span></span>

```bash
docker run azuresdk/azure-powershell-core:latest
```

<span data-ttu-id="5e5bb-112">Använd `nanoserver`-avbildningen för Windows.</span><span class="sxs-lookup"><span data-stu-id="5e5bb-112">For Windows, use the `nanoserver` image.</span></span>

```powershell
docker run azuresdk/azure-powershell-core:nanoserver
```

<span data-ttu-id="5e5bb-113">Azure PowerShell är installerat på avbildningen via `Install-Module` från [PowerShell-galleriet](https://www.powershellgallery.com/).</span><span class="sxs-lookup"><span data-stu-id="5e5bb-113">Azure PowerShell is installed on the image via `Install-Module` from the [PowerShell Gallery](https://www.powershellgallery.com/).</span></span>

## <a name="install-using-the-web-platform-installer"></a><span data-ttu-id="5e5bb-114">Installera med hjälp av installationsprogrammet för webbplattformen</span><span class="sxs-lookup"><span data-stu-id="5e5bb-114">Install using the Web Platform Installer</span></span>

<span data-ttu-id="5e5bb-115">Att installera den senaste versionen av Azure PowerShell från WebPI går till på samma sätt som det gjorde för tidigare versioner.</span><span class="sxs-lookup"><span data-stu-id="5e5bb-115">Installing the latest Azure PowerShell from WebPI is the same as it was for previous versions.</span></span>
<span data-ttu-id="5e5bb-116">Hämta [Azure PowerShell WebPI-paketet](http://aka.ms/webpi-azps) och starta installationen.</span><span class="sxs-lookup"><span data-stu-id="5e5bb-116">Download the [Azure PowerShell WebPI package](http://aka.ms/webpi-azps) and start the install.</span></span>

> [!NOTE]
> <span data-ttu-id="5e5bb-117">Om du tidigare har installerat Azure-moduler från PowerShell-galleriet så kommer installationsprogrammet automatiskt att ta bort dem.</span><span class="sxs-lookup"><span data-stu-id="5e5bb-117">If you have previously installed Azure modules from the PowerShell Gallery, the installer automatically removes them.</span></span> <span data-ttu-id="5e5bb-118">Detta förenklar din miljö genom att se till att endast en version av Azure PowerShell är installerad.</span><span class="sxs-lookup"><span data-stu-id="5e5bb-118">This simplifies your environment by ensuring that only one version of Azure PowerShell is installed.</span></span> <span data-ttu-id="5e5bb-119">Det finns dock scenarier där du kan behöva flera versioner installerade på samma gång.</span><span class="sxs-lookup"><span data-stu-id="5e5bb-119">However, there are scenarios where you may need multiple versions installed at the same time.</span></span>
>
> <span data-ttu-id="5e5bb-120">PowerShell-galleriets moduler installerar moduler i `$env:ProgramFiles\WindowsPowerShell\Modules`.</span><span class="sxs-lookup"><span data-stu-id="5e5bb-120">PowerShell Gallery modules install modules in `$env:ProgramFiles\WindowsPowerShell\Modules`.</span></span> <span data-ttu-id="5e5bb-121">WebPI-installationsprogrammet däremot installerar Azure moduler i `$env:ProgramFiles(x86)\Microsoft SDKs\Azure\PowerShell\`.</span><span class="sxs-lookup"><span data-stu-id="5e5bb-121">In contrast, the WebPI installer installs the Azure modules in `$env:ProgramFiles(x86)\Microsoft SDKs\Azure\PowerShell\`.</span></span>
>
> <span data-ttu-id="5e5bb-122">Om ett fel inträffar under installationen kan du ta bort Azure*-mapparna manuellt i din `$env:ProgramFiles\WindowsPowerShell\Modules`-mapp och försöka installera igen.</span><span class="sxs-lookup"><span data-stu-id="5e5bb-122">If an error occurs during install, you can manually remove the Azure* folders in your `$env:ProgramFiles\WindowsPowerShell\Modules` folder, and try the installation again.</span></span>

<span data-ttu-id="5e5bb-123">När installationen är färdig bör din `$env:PSModulePath`-inställning inkludera de kataloger som innehåller Azure PowerShell-cmdletarna.</span><span class="sxs-lookup"><span data-stu-id="5e5bb-123">Once the installation completes, your `$env:PSModulePath` setting should include the directories containing the Azure PowerShell cmdlets.</span></span> <span data-ttu-id="5e5bb-124">Följande kommando kan användas för att kontrollera att Azure PowerShell är korrekt installerad.</span><span class="sxs-lookup"><span data-stu-id="5e5bb-124">The following command can be used to verify that the Azure PowerShell is installed properly.</span></span>

```powershell
# To make sure the Azure PowerShell module is available after you install
Get-Module -ListAvailable Azure* | Select-Object Name, Version, Path
```

> [!NOTE]
> <span data-ttu-id="5e5bb-125">Det finns ett känt problem som kan uppstå när du installerar från WebPI.</span><span class="sxs-lookup"><span data-stu-id="5e5bb-125">There is a known issue that can occur when installing from WebPI.</span></span> <span data-ttu-id="5e5bb-126">Om datorn kräver en omstart på grund av systemuppdateringar eller andra installationer kan det göra att uppdateringarna för `$env:PSModulePath` inte inkluderar sökvägen där Azure PowerShell är installerat.</span><span class="sxs-lookup"><span data-stu-id="5e5bb-126">If your computer requires a restart due to system updates or other installations, it may cause updates to `$env:PSModulePath` to fail to include the path where Azure PowerShell is installed.</span></span>

<span data-ttu-id="5e5bb-127">När du försöker läsa in eller köra cmdletar efter installationen kan du få följande felmeddelande:</span><span class="sxs-lookup"><span data-stu-id="5e5bb-127">When attempting to load or execute cmdlets after installation, you can receive the following error message:</span></span>

```
PS C:\> Login-AzureRmAccount
Login-AzureRmAccount : The term 'Login-AzureRmAccount' is not recognized as the name of a cmdlet,
function, script file, or operable program. Check the spelling of the name, or if a path was
included, verify that the path is correct and try again.
At line:1 char:1
+ Login-AzureRmAccount
+ ~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : ObjectNotFound: (Login-AzureRmAccount:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException
```

<span data-ttu-id="5e5bb-128">Det här felet kan korrigeras genom att starta om datorn eller importera modulen med den fullständigt kvalificerade sökvägen.</span><span class="sxs-lookup"><span data-stu-id="5e5bb-128">This error can be corrected by restarting the machine or importing the module using the fully qualified path.</span></span> <span data-ttu-id="5e5bb-129">Exempel:</span><span class="sxs-lookup"><span data-stu-id="5e5bb-129">For example:</span></span>

```powershell
Import-Module "$env:ProgramFiles(x86)\Microsoft SDKs\Azure\PowerShell\AzureRM.psd1"
```

## <a name="install-using-the-msi-package"></a><span data-ttu-id="5e5bb-130">Installera med hjälp av MSI-paketet</span><span class="sxs-lookup"><span data-stu-id="5e5bb-130">Install using the MSI Package</span></span>

<span data-ttu-id="5e5bb-131">Azure PowerShell kan installeras med hjälp av MSI-filen som är tillgänglig från [GitHub](https://github.com/Azure/azure-powershell/releases/latest).</span><span class="sxs-lookup"><span data-stu-id="5e5bb-131">Azure PowerShell can be installed using the MSI file available from [GitHub](https://github.com/Azure/azure-powershell/releases/latest).</span></span> <span data-ttu-id="5e5bb-132">Om du har installerat tidigare versioner av Azure-moduler så kommer installationsprogrammet automatiskt att ta bort dem.</span><span class="sxs-lookup"><span data-stu-id="5e5bb-132">If you have installed previous versions of Azure modules, the installer automatically removes them.</span></span> <span data-ttu-id="5e5bb-133">MSI-paketet installerar moduler i `$env:ProgramFiles\WindowsPowerShell\Modules` men skapar inte versionsspecifika mappar.</span><span class="sxs-lookup"><span data-stu-id="5e5bb-133">The MSI package installs modules in `$env:ProgramFiles\WindowsPowerShell\Modules` but does not create version-specific folders.</span></span>
