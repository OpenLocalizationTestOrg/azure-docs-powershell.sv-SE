---
title: <span data-ttu-id="4e3ed-101">Installera och konfigurera Azure PowerShell Service Management-modulen | Microsoft Docs</span><span class="sxs-lookup"><span data-stu-id="4e3ed-101">Install and configure the Azure PowerShell Service Management module | Microsoft Docs</span></span>
description: "<span data-ttu-id=\"4e3ed-102\">Installera och konfigurera Azure PowerShell för första gången.</span><span class=\"sxs-lookup\"><span data-stu-id=\"4e3ed-102\">How to install and configure Azure PowerShell for first time use.</span></span>"
services: azure
author: sdwheeler
manager: carmonm
ms.product: azure
ms.service: azure-powershell
ms.devlang: powershell
ms.topic: conceptual
ms.date: 03/06/2017
ms.openlocfilehash: c51c727c1cb022eca59f819c7f24d8e058c677da
ms.sourcegitcommit: 226527be7cb647acfe2ea9ab151185053ab3c6db
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2017
---
# <span data-ttu-id="4e3ed-103">Installera Azure PowerShell Service Management-modulen</span><span class="sxs-lookup"><span data-stu-id="4e3ed-103">Installing the Azure PowerShell Service Management module</span></span>
<a id="installing-the-azure-powershell-service-management-module" class="xliff"></a>

<span data-ttu-id="4e3ed-104">Vi rekommenderar att du installerar Azure PowerShell från [PowerShell-galleriet](https://www.powershellgallery.com/).</span><span class="sxs-lookup"><span data-stu-id="4e3ed-104">Installing Azure PowerShell from the [PowerShell Gallery](https://www.powershellgallery.com/) is the preferred method of installation.</span></span>

## <span data-ttu-id="4e3ed-105">Steg 1: Installera PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="4e3ed-105">Step 1: Install PowerShellGet</span></span>
<a id="step-1-install-powershellget" class="xliff"></a>

<span data-ttu-id="4e3ed-106">Du måste ha modulen PowerShellGet för att kunna installera objekt från PowerShell-galleriet.</span><span class="sxs-lookup"><span data-stu-id="4e3ed-106">Installing items from the PowerShell Gallery requires the PowerShellGet module.</span></span> <span data-ttu-id="4e3ed-107">Kontrollera att du har rätt version av PowerShellGet och att datorn uppfyller övriga systemkrav.</span><span class="sxs-lookup"><span data-stu-id="4e3ed-107">Make sure you have the appropriate version of PowerShellGet and other system requirements.</span></span> <span data-ttu-id="4e3ed-108">Kör följande kommando för att se om du har PowerShellGet installerat på datorn.</span><span class="sxs-lookup"><span data-stu-id="4e3ed-108">Run the following command to see if you have PowerShellGet installed on your system.</span></span>

```powershell
Get-Module PowerShellGet -list | Select-Object Name,Version,Path
```

<span data-ttu-id="4e3ed-109">Nu bör du se utdata som ser ut ungefär så här:</span><span class="sxs-lookup"><span data-stu-id="4e3ed-109">You should see something similar to the following output:</span></span>

```
Name          Version Path
----          ------- ----
PowerShellGet 1.0.0.1 C:\Program Files\WindowsPowerShell\Modules\PowerShellGet\1.0.0.1\PowerShellGet.psd1
```

<span data-ttu-id="4e3ed-110">Om du inte har installerat PowerShellGet kan du läsa avsnittet [Hämta PowerShellGet](install-azurerm-ps.md#how-to-get-powershellget).</span><span class="sxs-lookup"><span data-stu-id="4e3ed-110">If you do not have PowerShellGet installed, see the [How to get PowerShellGet](install-azurerm-ps.md#how-to-get-powershellget).</span></span>

## <span data-ttu-id="4e3ed-111">Steg 2: Installera Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="4e3ed-111">Step 2: Install Azure PowerShell</span></span>
<a id="step-2-install-azure-powershell" class="xliff"></a>

<span data-ttu-id="4e3ed-112">Kör följande kommando från Windows PowerShell-konsolen som körs som administratör:</span><span class="sxs-lookup"><span data-stu-id="4e3ed-112">Run the following command from the Windows PowerShell console running as Administrator:</span></span>

```powershell
Install-Module Azure
```

<span data-ttu-id="4e3ed-113">Azure-modulen är en sammanslagen modul för Azure Resource Manager-cmdletar.</span><span class="sxs-lookup"><span data-stu-id="4e3ed-113">The Azure module is a rollup module for the Azure Resource Manager cmdlets.</span></span> <span data-ttu-id="4e3ed-114">När du installerar AzureRM-modulen kommer alla övriga Azure-moduler som inte har installerats att hämtas och installeras från PowerShell-galleriet.</span><span class="sxs-lookup"><span data-stu-id="4e3ed-114">When you install the AzureRM module, any other Azure modules that have not previously been installed will be downloaded and installed from the PowerShell Gallery.</span></span>

<span data-ttu-id="4e3ed-115">Azure Service Management-modulen delar beroenden med Azure PowerShell Resource Manager-modulerna.</span><span class="sxs-lookup"><span data-stu-id="4e3ed-115">The Azure Service Management module shares dependencies with the Azure PowerShell Resource Manager modules.</span></span> <span data-ttu-id="4e3ed-116">Om du har installerat Azure PowerShell Resource Manager-modulerna måste du lägga till parametern `-AllowClobber` i installationskommandot.</span><span class="sxs-lookup"><span data-stu-id="4e3ed-116">If you have installed the Azure PowerShell Resource Manager modules, you will need to add the `-AllowClobber` parameter to the install command.</span></span> <span data-ttu-id="4e3ed-117">Det tillåter att befintliga delade beroenden uppdateras.</span><span class="sxs-lookup"><span data-stu-id="4e3ed-117">This allows this existing shared dependencies to be updated.</span></span> <span data-ttu-id="4e3ed-118">Utan den här parametern misslyckas installationen av modulen.</span><span class="sxs-lookup"><span data-stu-id="4e3ed-118">Without this parameter, installation of the module fails.</span></span>

```powershell
Install-Module Azure -AllowClobber
```

<span data-ttu-id="4e3ed-119">När du har installerat den här modulen kan du importera modulen genom att köra följande kommando:</span><span class="sxs-lookup"><span data-stu-id="4e3ed-119">After you install this module, you can import the module by running the following command:</span></span>

```powershell
Import-Module Azure
```

## <span data-ttu-id="4e3ed-120">Använda cmdletar</span><span class="sxs-lookup"><span data-stu-id="4e3ed-120">To use the cmdlets</span></span>
<a id="to-use-the-cmdlets" class="xliff"></a>

<span data-ttu-id="4e3ed-121">Logga först in på ditt Azure-konto om du vill börja arbeta med cmdletar för Azure Service Management.</span><span class="sxs-lookup"><span data-stu-id="4e3ed-121">To start working with the Azure Service Management cmdlets, first log on to your Azure account.</span></span> <span data-ttu-id="4e3ed-122">Kör följande kommando för att logga in på ditt konto:</span><span class="sxs-lookup"><span data-stu-id="4e3ed-122">To log on to your account, run the following command:</span></span>

```powershell
Add-AzureAccount
```

<span data-ttu-id="4e3ed-123">När du har loggat in på Azure skapar Azure PowerShell en kontext för den angivna sessionen.</span><span class="sxs-lookup"><span data-stu-id="4e3ed-123">After logging into Azure, Azure PowerShell creates a context for the given session.</span></span> <span data-ttu-id="4e3ed-124">Den kontexten innehåller miljö, konto, klient och prenumeration för Azure PowerShell som ska användas för alla cmdletar i den sessionen.</span><span class="sxs-lookup"><span data-stu-id="4e3ed-124">That context contains the Azure PowerShell environment, account, tenant, and subscription that will be used for all cmdlets within that session.</span></span> <span data-ttu-id="4e3ed-125">Du är nu redo att använda modulerna nedan.</span><span class="sxs-lookup"><span data-stu-id="4e3ed-125">Now you are ready to use the modules below.</span></span>

## <span data-ttu-id="4e3ed-126">Azure Service Management-cmdletar</span><span class="sxs-lookup"><span data-stu-id="4e3ed-126">Azure Service Management cmdlets</span></span>
<a id="azure-service-management-cmdlets" class="xliff"></a>

<span data-ttu-id="4e3ed-127">Azure PowerShell-modulerna uppdateras kontinuerligt.</span><span class="sxs-lookup"><span data-stu-id="4e3ed-127">Azure PowerShell modules are updated frequently.</span></span> <span data-ttu-id="4e3ed-128">Om du märker att onlinehjälpen för cmdletar omfattar cmdletar eller parametrar som inte finns i din modul bör du hämta och installera den senaste versionen av modulen.</span><span class="sxs-lookup"><span data-stu-id="4e3ed-128">If you notice that the online cmdlet help includes cmdlets or parameters that are not in your module, download and install the latest version of the module.</span></span> <span data-ttu-id="4e3ed-129">Du kan hitta modulens version genom att skriva in: `(Get-Module Azure).Version`.</span><span class="sxs-lookup"><span data-stu-id="4e3ed-129">To find the version of your module, type: `(Get-Module Azure).Version`.</span></span>

<span data-ttu-id="4e3ed-130">Om du vill ha exempelskript som kan hjälpa dig att automatisera vissa av de vanliga uppgifterna i Azure kan du se [Windows Azure Script Center](http://www.windowsazure.com/documentation/scripts/).</span><span class="sxs-lookup"><span data-stu-id="4e3ed-130">For sample scripts that can help you automate some of the common tasks in Azure, see the [Windows Azure Script Center](http://www.windowsazure.com/documentation/scripts/).</span></span>

<span data-ttu-id="4e3ed-131">Allmän information om installation, inlärning, användning och anpassning av Windows PowerShell finns i [Skript med Windows PowerShell](http://go.microsoft.com/fwlink/p/?linkid=320210).</span><span class="sxs-lookup"><span data-stu-id="4e3ed-131">For general information about installing, learning, using, and customizing Windows PowerShell, see [Scripting with Windows PowerShell](http://go.microsoft.com/fwlink/p/?linkid=320210).</span></span>
