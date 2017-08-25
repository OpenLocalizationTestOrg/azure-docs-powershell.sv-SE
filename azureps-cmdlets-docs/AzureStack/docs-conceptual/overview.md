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
# <a name="azure-stack-powershell"></a>Azure Stack PowerShell 

Azure Stack kräver följande två PowerShell-moduler:  

1. Den Azure Stack-kompatibla **AzureRM**-modulen som blir tillgänglig genom att installera API-versionsprofilen **2017-03-09-profile**. De cmdletar som installeras med den här profilen kan användas av Azure Stack-molnadministratörer och klienter. Information om de PowerShell-cmdletar som är tillgängliga i den här profilen finns i PowerShell-referensinnehållet för modulen [AzureRM version1.2.9 ](https://docs.microsoft.com/en-us/powershell/azure/overview?view=azurermps-1.2.9).  

2. Version **1.2.9** av **AzureStack**-modulen. De cmdletar som installeras med den här profilen kan endast användas av Azure Stack-molnadministratörer. Administratörer kan utföra åtgärder som att hantera erbjudanden, planer, tjänster, kvoter och annat med PowerShell-cmdletarna i modulen. Mer information om PowerShell-cmdletarna i den här modulen finns i [AzureStackAdmin](https://docs.microsoft.com/en-us/powershell/module/azurerm.azurestackadmin/?view=azurestackps-1.2.9#azurerm.azurestackadmin)- och [AzureStackStorage](https://docs.microsoft.com/en-us/powershell/module/azurerm.azurestackstorage/?view=azurestackps-1.2.9#azurerm.azurestackstorage)-referensinnehållet.

## <a name="next-steps"></a>Nästa steg

* [Installera PowerShell för Azure Stack](https://docs.microsoft.com/en-us/azure/azure-stack/azure-stack-powershell-install?view=azurestackps-1.2.9&toc=%2fpowershell%2fmodule%2ftoc.json%3fview%3dazurestackps-1.2.9&view=azurestackps-1.2.9)
* [Konfigurera PowerShell för användning med Azure Stack](https://docs.microsoft.com/en-us/azure/azure-stack/azure-stack-powershell-configure?view=azurestackps-1.2.9&toc=%2fpowershell%2fmodule%2ftoc.json%3fview%3dazurestackps-1.2.9&view=azurestackps-1.2.9)


