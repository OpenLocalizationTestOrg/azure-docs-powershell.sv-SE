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
ms.openlocfilehash: 5fe7591855577e083aad5923aed37b18d0b2a40c
ms.sourcegitcommit: b256bf48e15ee98865de0fae50e7b81878b03a54
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2017
---
# <a name="release-notes"></a><span data-ttu-id="c814f-103">Viktig information</span><span class="sxs-lookup"><span data-stu-id="c814f-103">Release notes</span></span>

<span data-ttu-id="c814f-104">Det här är en lista över ändringar som har gjorts i Azure PowerShell i den här versionen.</span><span class="sxs-lookup"><span data-stu-id="c814f-104">This is a list of changes made to Azure PowerShell in this release.</span></span>

## <a name="version-129"></a><span data-ttu-id="c814f-105">Version 1.2.9</span><span class="sxs-lookup"><span data-stu-id="c814f-105">Version 1.2.9</span></span>

<span data-ttu-id="c814f-106">Ändringar i den här versionen</span><span class="sxs-lookup"><span data-stu-id="c814f-106">Changes This Release</span></span>

* <span data-ttu-id="c814f-107">Modulen AzureRm.AzureStackAdmin</span><span class="sxs-lookup"><span data-stu-id="c814f-107">AzureRm.AzureStackAdmin Module</span></span>
    + <span data-ttu-id="c814f-108">Ändringar i cmdleten Add-AzureRmResourceProviderRegistration för stöd av delning av admin och klient för Azure Resource Manager.</span><span class="sxs-lookup"><span data-stu-id="c814f-108">Changes in the Add-AzureRmResourceProviderRegistration cmdlet for the support of Admin Azure resource manager and tenant azure resource manager split.</span></span> <span data-ttu-id="c814f-109">En ny parameter, -ResourceManagerType, har lagts till.</span><span class="sxs-lookup"><span data-stu-id="c814f-109">A new parameter -ResourceManagerType has been added.</span></span>
    + <span data-ttu-id="c814f-110">Parametrarna -AdminUri, -ApiVersion, -SubscriptionId och -Token har tagits bort från varje cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c814f-110">Removal of the parameters -AdminUri, -ApiVersion, -SubscriptionId and -Token from each cmdlets.</span></span> <span data-ttu-id="c814f-111">Vi har förvarnat om att dessa parametrar kommer att bli inaktuella och nu har de tagits bort.</span><span class="sxs-lookup"><span data-stu-id="c814f-111">We have been printing warnings that these parameters will be deprecated and now they got removed.</span></span>
* <span data-ttu-id="c814f-112">Modulen AzureStackStorage</span><span class="sxs-lookup"><span data-stu-id="c814f-112">AzureStackStorage module</span></span>
    + <span data-ttu-id="c814f-113">Nya cmdletar har lagts till för behållarmigreringsscenarier.</span><span class="sxs-lookup"><span data-stu-id="c814f-113">Added new cmdlets to support container migration scenarios.</span></span>
    + <span data-ttu-id="c814f-114">Cmdletar som refererar till interna komponenter och underliggande funktioner har tagits bort.</span><span class="sxs-lookup"><span data-stu-id="c814f-114">Removed cmdlets referring to internal components and underlying features.</span></span>
* <span data-ttu-id="c814f-115">AzureRM.BootStrapper</span><span class="sxs-lookup"><span data-stu-id="c814f-115">AzureRM.BootStrapper</span></span>
    + <span data-ttu-id="c814f-116">En ny modul har skapats för att hantera versioner av Azure PowerShell-cmdletar med hjälp av versionsprofiler</span><span class="sxs-lookup"><span data-stu-id="c814f-116">Created new module to manage versions of Azure PowerShell cmdlets through the use of version profiles</span></span>