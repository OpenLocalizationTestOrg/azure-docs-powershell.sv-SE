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
ms.sourcegitcommit: c42c7176276ec4e1cc3360a93e6b15d32083bf9f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/14/2017
---
# <a name="install-and-configure-azure-powershell-on-macos-and-linux"></a>Installera och konfigurera Azure PowerShell på macOS och Linux

Nu är det möjligt att installera PowerShell 6 (beta) och Azure PowerShell på plattformar som inte är Windows-plattformar.
Processen för att installera Azure PowerShell på macOS och Linux är ungefär samma som för Windows, men du måste först installera PowerShell 6 (beta).

> [!NOTE]

> För tillfället är både PowerShell 6 (beta) och Azure PowerShell för .NET Core fortfarande i beta.
> De här produkterna har begränsad support. Skicka gärna in ärenden till GitHub om du har problem eller upptäcker buggar.
>
> * [Problem med PowerShell 6 (beta)](https://github.com/PowerShell/PowerShell/issues)
> * [Problem med Azure PowerShell](https://github.com/azure/azure-docs-powershell/issues)

## <a name="step-1-install-powershell-6-beta"></a>Steg 1: Installera PowerShell 6 (beta)

Processen för att installera PowerShell 6 (beta) varierar beroende på måloperativsystemet.
Det är möjligt att installera PowerShell 6 (beta) på Windows, men den här artikeln fokuserar på macOS och Linux. Om du vill använda Azure PowerShell på Windows kan du läsa artikeln om att [installera](./install-azurerm-ps.md) på Windows.

För att installera **PowerShell 6** (beta) på Linux eller macOS måste du:

1. Hämta PowerShell för den specifika operativsystemsversionen från [GitHub](https://github.com/powershell/powershell#get-powershell)
2. Följa installationsinstruktionerna
   - [Linux](https://github.com/PowerShell/PowerShell/blob/master/docs/installation/linux.md)
   - [macOS](https://github.com/PowerShell/PowerShell/blob/master/docs/installation/linux.md#macos-1012)

## <a name="step-2-install-azure-powershell-for-net-core"></a>Steg 2: Installera Azure PowerShell för .NET Core

I PowerShell 6 (beta) är modulen PowerShellGet redan installerad. Det gör det enkelt att installera alla moduler som har publicerats i PowerShell-galleriet. Öppna en ny PowerShell-session och kör följande kommando för att installera Azure PowerShell:

```powershell
Install-Module AzureRM.NetCore
```

## <a name="step-3-load-the-azurermnetcore-module"></a>Steg 3: Läs in modulen AzureRM.Netcore

När modulen har installerats måste du läsa in modulen i din PowerShell-session. Moduler läses in med `Import-Module`-cmdleten enligt följande:

```powershell
Import-Module AzureRM.Netcore
```

När importen är färdig kan du testa din nya installation och modulen genom att försöka logga in på Azure med hjälp av följande kommando:

```powershell
Login-AzureRMAccount
```

När du har angivit kommandot ovan visas en dialogruta som ber dig att gå till `https://aka.ms/devicelogin` och ange koden som tillhandahålls.

## <a name="available-cmdlets"></a>Tillgängliga cmdlet:ar

Azure PowerShell-moduler för .NET Standard är fortfarande under utveckling. De här modulerna tillhandahåller inte den fullständiga uppsättningen cmdlet:ar som är tillgängliga för Windows-versionen av modulerna. Följande funktioner är implementerade i AzureRM.Netcore-moduler:

* Kontohantering
  - Logga in med ett Microsoft-konto, organisationskonto eller tjänstens huvudnamn via Microsoft Azure Active Directory
  - Spara autentiseringsuppgifterna till disken med Save-AzureRmContext och läs in sparade autentiseringsuppgifter med Import-AzureRmContext
* Miljö
  - Hämta andra Microsoft Azure-miljöer
  - Lägg till/Ange/Ta bort anpassade miljöer (t.ex. Azure Stack eller Windows Azure Pack-miljöer)
* Cmdlet:ar på hanteringsnivå för Azure-tjänster med Resource Manager- och Service Management-gränssnitt.
  - Virtuell dator
  - App Service (Websites)
  - SQL Database
  - Lagring
  - Nätverk

## <a name="next-steps"></a>Nästa steg

Mer information om användning av Azure PowerShell finns i artikeln [Kom igång med Azure PowerShell](get-started-azureps.md).
