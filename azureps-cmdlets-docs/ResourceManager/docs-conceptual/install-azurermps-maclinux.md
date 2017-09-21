---
title: "Installera och konfigurera Azure PowerShell på macOS och Linux | Microsoft Docs"
description: "Så här installerar och konfigurerar du Azure PowerShell på macOS och Linux för första gången."
services: azure
author: sdwheeler
ms.author: sewhee
manager: carmonm
ms.product: azure
ms.service: azure-powershell
ms.devlang: powershell
ms.topic: conceptual
ms.date: 09/06/2017
ms.openlocfilehash: 94b39c18acaca7a4b17b5207feed025442665acc
ms.sourcegitcommit: 202ec2df66c40a60f47ea06b30a6701ad444d229
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/08/2017
---
# <a name="install-and-configure-azure-powershell-on-macos-and-linux"></a><span data-ttu-id="981f5-103">Installera och konfigurera Azure PowerShell på macOS och Linux</span><span class="sxs-lookup"><span data-stu-id="981f5-103">Install and configure Azure PowerShell on macOS and Linux</span></span>

<span data-ttu-id="981f5-104">Nu är det möjligt att installera PowerShell 6 (beta) och Azure PowerShell på plattformar som inte är Windows-plattformar.</span><span class="sxs-lookup"><span data-stu-id="981f5-104">It is now possible to install PowerShell 6 (beta) and Azure PowerShell on non-Windows platforms.</span></span>
<span data-ttu-id="981f5-105">Processen för att installera Azure PowerShell på macOS och Linux är ungefär samma som för Windows, men du måste först installera PowerShell 6 (beta).</span><span class="sxs-lookup"><span data-stu-id="981f5-105">The process of installing Azure PowerShell on macOS and Linux is not that different from Windows, however, you must first install PowerShell 6 (beta).</span></span>

> [!NOTE]

> <span data-ttu-id="981f5-106">För tillfället är både PowerShell 6 (beta) och Azure PowerShell för .NET Core fortfarande i beta.</span><span class="sxs-lookup"><span data-stu-id="981f5-106">At this time, both PowerShell 6 (beta) and Azure PowerShell for .NET Core are still in beta.</span></span>
> <span data-ttu-id="981f5-107">De här produkterna har begränsad support.</span><span class="sxs-lookup"><span data-stu-id="981f5-107">Support for these products is limited.</span></span> <span data-ttu-id="981f5-108">Skicka gärna in ärenden till GitHub om du har problem eller upptäcker buggar.</span><span class="sxs-lookup"><span data-stu-id="981f5-108">If you have problems or discover bugs, please file Issues in GitHub.</span></span>
>
> * [<span data-ttu-id="981f5-109">Problem med PowerShell 6 (beta)</span><span class="sxs-lookup"><span data-stu-id="981f5-109">Issues for PowerShell 6 (beta)</span></span>](https://github.com/PowerShell/PowerShell/issues)
> * [<span data-ttu-id="981f5-110">Problem med Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="981f5-110">Issues for Azure PowerShell</span></span>](https://github.com/azure/azure-docs-powershell/issues)

## <a name="step-1-install-powershell-6-beta"></a><span data-ttu-id="981f5-111">Steg 1: Installera PowerShell 6 (beta)</span><span class="sxs-lookup"><span data-stu-id="981f5-111">Step 1: Install PowerShell 6 (beta)</span></span>

<span data-ttu-id="981f5-112">Processen för att installera PowerShell 6 (beta) varierar beroende på måloperativsystemet.</span><span class="sxs-lookup"><span data-stu-id="981f5-112">The process of installing PowerShell 6 (beta) on varies depending on the target operating system.</span></span>
<span data-ttu-id="981f5-113">Det är möjligt att installera PowerShell 6 (beta) på Windows, men den här artikeln fokuserar på macOS och Linux.</span><span class="sxs-lookup"><span data-stu-id="981f5-113">While it is possible to install PowerShell 6 (beta) on Windows, this article focuses on macOS and Linux.</span></span> <span data-ttu-id="981f5-114">Om du vill använda Azure PowerShell på Windows kan du läsa artikeln om att [installera](./install-azurerm-ps.md) på Windows.</span><span class="sxs-lookup"><span data-stu-id="981f5-114">If you want to use Azure PowerShell on Windows, see the [install](./install-azurerm-ps.md) article for Windows.</span></span>

<span data-ttu-id="981f5-115">För att installera **PowerShell 6** (beta) på Linux eller macOS måste du:</span><span class="sxs-lookup"><span data-stu-id="981f5-115">To install **PowerShell 6** (beta) on Linux or macOS, you need to:</span></span>

1. <span data-ttu-id="981f5-116">Hämta PowerShell för den specifika operativsystemsversionen från [GitHub](https://github.com/powershell/powershell#get-powershell)</span><span class="sxs-lookup"><span data-stu-id="981f5-116">Get PowerShell for the specific OS and version, from [GitHub](https://github.com/powershell/powershell#get-powershell)</span></span>
2. <span data-ttu-id="981f5-117">Följa installationsinstruktionerna</span><span class="sxs-lookup"><span data-stu-id="981f5-117">Follow the installation instructions</span></span>
   - [<span data-ttu-id="981f5-118">Linux</span><span class="sxs-lookup"><span data-stu-id="981f5-118">Linux</span></span>](https://github.com/PowerShell/PowerShell/blob/master/docs/installation/linux.md)
   - [<span data-ttu-id="981f5-119">macOS</span><span class="sxs-lookup"><span data-stu-id="981f5-119">macOS</span></span>](https://github.com/PowerShell/PowerShell/blob/master/docs/installation/linux.md#macos-1012)

## <a name="step-2-install-azure-powershell-for-net-core"></a><span data-ttu-id="981f5-120">Steg 2: Installera Azure PowerShell för .NET Core</span><span class="sxs-lookup"><span data-stu-id="981f5-120">Step 2: Install Azure PowerShell for .NET Core</span></span>

<span data-ttu-id="981f5-121">I PowerShell 6 (beta) är modulen PowerShellGet redan installerad.</span><span class="sxs-lookup"><span data-stu-id="981f5-121">PowerShell 6 (beta) comes with the PowerShellGet module already installed.</span></span> <span data-ttu-id="981f5-122">Det gör det enkelt att installera alla moduler som har publicerats i PowerShell-galleriet.</span><span class="sxs-lookup"><span data-stu-id="981f5-122">This makes it easy to install any module that is published to the PowerShell Gallery.</span></span> <span data-ttu-id="981f5-123">Öppna en ny PowerShell-session och kör följande kommando för att installera Azure PowerShell:</span><span class="sxs-lookup"><span data-stu-id="981f5-123">To install Azure PowerShell, open a new PowerShell session and run the following command:</span></span>

```powershell
Install-Module AzureRM.NetCore
```

## <a name="step-3-load-the-azurermnetcore-module"></a><span data-ttu-id="981f5-124">Steg 3: Läs in modulen AzureRM.Netcore</span><span class="sxs-lookup"><span data-stu-id="981f5-124">Step 3: Load the AzureRM.Netcore module</span></span>

<span data-ttu-id="981f5-125">När modulen har installerats måste du läsa in modulen i din PowerShell-session.</span><span class="sxs-lookup"><span data-stu-id="981f5-125">Once the module is installed, you need to load the module into your PowerShell session.</span></span> <span data-ttu-id="981f5-126">Moduler läses in med `Import-Module`-cmdleten enligt följande:</span><span class="sxs-lookup"><span data-stu-id="981f5-126">Modules are loaded using the `Import-Module` cmdlet, as follows:</span></span>

```powershell
Import-Module AzureRM.Netcore
```

<span data-ttu-id="981f5-127">När importen är färdig kan du testa din nya installation och modulen genom att försöka logga in på Azure med hjälp av följande kommando:</span><span class="sxs-lookup"><span data-stu-id="981f5-127">After the import completes, you can test your newly installed and module by attempting to sign into Azure using the following command:</span></span>

```powershell
Login-AzureRMAccount
```

<span data-ttu-id="981f5-128">När du har angivit kommandot ovan visas en dialogruta som ber dig att gå till `https://aka.ms/devicelogin` och ange koden som tillhandahålls.</span><span class="sxs-lookup"><span data-stu-id="981f5-128">The above command should prompt you to go to `https://aka.ms/devicelogin` and enter the provided code.</span></span>

## <a name="available-cmdlets"></a><span data-ttu-id="981f5-129">Tillgängliga cmdlet:ar</span><span class="sxs-lookup"><span data-stu-id="981f5-129">Available cmdlets</span></span>

<span data-ttu-id="981f5-130">Azure PowerShell-moduler för .NET Standard är fortfarande under utveckling.</span><span class="sxs-lookup"><span data-stu-id="981f5-130">The Azure PowerShell modules for .NET Standard are still in development.</span></span> <span data-ttu-id="981f5-131">De här modulerna tillhandahåller inte den fullständiga uppsättningen cmdlet:ar som är tillgängliga för Windows-versionen av modulerna.</span><span class="sxs-lookup"><span data-stu-id="981f5-131">These modules do not provide the full set of cmdlets that are available for the Windows version of the modules.</span></span> <span data-ttu-id="981f5-132">Följande funktioner är implementerade i AzureRM.Netcore-moduler:</span><span class="sxs-lookup"><span data-stu-id="981f5-132">The following functions are implemented in AzureRM.Netcore modules:</span></span>

* <span data-ttu-id="981f5-133">Kontohantering</span><span class="sxs-lookup"><span data-stu-id="981f5-133">Account management</span></span>
  - <span data-ttu-id="981f5-134">Logga in med ett Microsoft-konto, organisationskonto eller tjänstens huvudnamn via Microsoft Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="981f5-134">Login with Microsoft account, Organizational account, or Service Principal through Microsoft Azure Active Directory</span></span>
  - <span data-ttu-id="981f5-135">Spara autentiseringsuppgifterna till disken med Save-AzureRmContext och läs in sparade autentiseringsuppgifter med Import-AzureRmContext</span><span class="sxs-lookup"><span data-stu-id="981f5-135">Save Credentials to disk with Save-AzureRmContext and load saved credentials using Import-AzureRmContext</span></span>
* <span data-ttu-id="981f5-136">Miljö</span><span class="sxs-lookup"><span data-stu-id="981f5-136">Environment</span></span>
  - <span data-ttu-id="981f5-137">Hämta andra Microsoft Azure-miljöer</span><span class="sxs-lookup"><span data-stu-id="981f5-137">Get the different out-of-box Microsoft Azure environments</span></span>
  - <span data-ttu-id="981f5-138">Lägg till/Ange/Ta bort anpassade miljöer (t.ex. Azure Stack eller Windows Azure Pack-miljöer)</span><span class="sxs-lookup"><span data-stu-id="981f5-138">Add/Set/Remove customized environments (like your Azure Stack or Windows Azure Pack environments)</span></span>
* <span data-ttu-id="981f5-139">Cmdlet:ar på hanteringsnivå för Azure-tjänster med Resource Manager- och Service Management-gränssnitt.</span><span class="sxs-lookup"><span data-stu-id="981f5-139">Management plane cmdlets for Azure services using Resource Manager and Service Management interfaces.</span></span>
  - <span data-ttu-id="981f5-140">Virtuell dator</span><span class="sxs-lookup"><span data-stu-id="981f5-140">Virtual Machine</span></span>
  - <span data-ttu-id="981f5-141">App Service (Websites)</span><span class="sxs-lookup"><span data-stu-id="981f5-141">App Service (Websites)</span></span>
  - <span data-ttu-id="981f5-142">SQL Database</span><span class="sxs-lookup"><span data-stu-id="981f5-142">SQL Database</span></span>
  - <span data-ttu-id="981f5-143">Lagring</span><span class="sxs-lookup"><span data-stu-id="981f5-143">Storage</span></span>
  - <span data-ttu-id="981f5-144">Nätverk</span><span class="sxs-lookup"><span data-stu-id="981f5-144">Network</span></span>

## <a name="next-steps"></a><span data-ttu-id="981f5-145">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="981f5-145">Next Steps</span></span>

<span data-ttu-id="981f5-146">Mer information om användning av Azure PowerShell finns i artikeln [Kom igång med Azure PowerShell](get-started-azureps.md).</span><span class="sxs-lookup"><span data-stu-id="981f5-146">For more information about using Azure PowerShell, see the [Get started with Azure PowerShell](get-started-azureps.md) article.</span></span>
