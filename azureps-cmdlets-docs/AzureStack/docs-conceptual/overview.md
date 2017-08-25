---
title: "Översikt över Azure Stack PowerShell | Microsoft Docs"
description: "Översikt över installation och konfiguration av Azure Stack PowerShell."
author: SnehaGunda
manager: Byronr
ms.product: azure-stack
ms.service: powershell
ms.devlang: powershell
ms.topic: reference
ms.author: sngun
ms.manager: byronr
ms.openlocfilehash: 2a03697e0f3e80d63c48f2dc5615f6c99b9ef716
ms.sourcegitcommit: 226527be7cb647acfe2ea9ab151185053ab3c6db
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2017
---
# <a name="azure-stack-powershell"></a><span data-ttu-id="0e3e6-103">Azure Stack PowerShell</span><span class="sxs-lookup"><span data-stu-id="0e3e6-103">Azure Stack PowerShell</span></span> 

<span data-ttu-id="0e3e6-104">Azure Stack kräver följande två PowerShell-moduler:</span><span class="sxs-lookup"><span data-stu-id="0e3e6-104">Azure Stack requires the following two PowerShell modules:</span></span>  

1. <span data-ttu-id="0e3e6-105">Den Azure Stack-kompatibla **AzureRM**-modulen som blir tillgänglig genom att installera API-versionsprofilen **2017-03-09-profile**.</span><span class="sxs-lookup"><span data-stu-id="0e3e6-105">The Azure Stack compatible **AzureRM** module which is available by installing the **2017-03-09-profile** API Version Profile.</span></span> <span data-ttu-id="0e3e6-106">De cmdletar som installeras med den här profilen kan användas av Azure Stack-molnadministratörer och klienter.</span><span class="sxs-lookup"><span data-stu-id="0e3e6-106">The cmdlets installed by using this profile can be used by the Azure Stack cloud administrators and the tenants.</span></span> <span data-ttu-id="0e3e6-107">Information om de PowerShell-cmdletar som är tillgängliga i den här profilen finns i PowerShell-referensinnehållet för modulen [AzureRM version1.2.9 ](https://docs.microsoft.com/en-us/powershell/azure/overview?view=azurermps-1.2.9).</span><span class="sxs-lookup"><span data-stu-id="0e3e6-107">To learn about the PowerShell cmdlets that are available in this profile, see the PowerShell reference content for the [1.2.9 version of AzureRM](https://docs.microsoft.com/en-us/powershell/azure/overview?view=azurermps-1.2.9) module.</span></span>  

2. <span data-ttu-id="0e3e6-108">Version **1.2.9** av **AzureStack**-modulen.</span><span class="sxs-lookup"><span data-stu-id="0e3e6-108">The **1.2.9** version of the **AzureStack** module.</span></span> <span data-ttu-id="0e3e6-109">De cmdletar som installeras med den här profilen kan endast användas av Azure Stack-molnadministratörer.</span><span class="sxs-lookup"><span data-stu-id="0e3e6-109">The cmdlets installed by using this module can be used by Azure Stack cloud administrators only.</span></span> <span data-ttu-id="0e3e6-110">Administratörer kan utföra åtgärder som att hantera erbjudanden, planer, tjänster, kvoter och annat med PowerShell-cmdletarna i modulen.</span><span class="sxs-lookup"><span data-stu-id="0e3e6-110">Administrator can perform operations such as manage offers, plans, services, quotas, etc. by using the PowerShell cmdlets provided by this module.</span></span> <span data-ttu-id="0e3e6-111">Mer information om PowerShell-cmdletarna i den här modulen finns i [AzureStackAdmin](https://docs.microsoft.com/en-us/powershell/module/azurerm.azurestackadmin/?view=azurestackps-1.2.9#azurerm.azurestackadmin)- och [AzureStackStorage](https://docs.microsoft.com/en-us/powershell/module/azurerm.azurestackstorage/?view=azurestackps-1.2.9#azurerm.azurestackstorage)-referensinnehållet.</span><span class="sxs-lookup"><span data-stu-id="0e3e6-111">To learn about the PowerShell cmdlets available in this module, see the [AzureStackAdmin](https://docs.microsoft.com/en-us/powershell/module/azurerm.azurestackadmin/?view=azurestackps-1.2.9#azurerm.azurestackadmin) and [AzureStackStorage](https://docs.microsoft.com/en-us/powershell/module/azurerm.azurestackstorage/?view=azurestackps-1.2.9#azurerm.azurestackstorage) Reference content.</span></span>

## <a name="next-steps"></a><span data-ttu-id="0e3e6-112">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="0e3e6-112">Next Steps</span></span>

* [<span data-ttu-id="0e3e6-113">Installera PowerShell för Azure Stack</span><span class="sxs-lookup"><span data-stu-id="0e3e6-113">Install PowerShell for Azure Stack</span></span>](https://docs.microsoft.com/en-us/azure/azure-stack/azure-stack-powershell-install?view=azurestackps-1.2.9&toc=%2fpowershell%2fmodule%2ftoc.json%3fview%3dazurestackps-1.2.9&view=azurestackps-1.2.9)
* [<span data-ttu-id="0e3e6-114">Konfigurera PowerShell för användning med Azure Stack</span><span class="sxs-lookup"><span data-stu-id="0e3e6-114">Configure PowerShell for use with Azure Stack</span></span>](https://docs.microsoft.com/en-us/azure/azure-stack/azure-stack-powershell-configure?view=azurestackps-1.2.9&toc=%2fpowershell%2fmodule%2ftoc.json%3fview%3dazurestackps-1.2.9&view=azurestackps-1.2.9)


