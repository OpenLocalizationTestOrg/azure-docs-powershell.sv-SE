---
title: <span data-ttu-id="c3ab1-101">Logga in med Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="c3ab1-101">Log in with Azure PowerShell</span></span>
description: <span data-ttu-id="c3ab1-102">Logga in med Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="c3ab1-102">Log in with Azure PowerShell</span></span>
services: azure
author: sdwheeler
ms.author: sewhee
manager: carmonm
ms.product: azure
ms.service: azure-powershell
ms.devlang: powershell
ms.topic: conceptual
ms.date: 05/15/2017
ms.openlocfilehash: f6d249ca5bb09c4fe8445ba5b339ffa6012815ed
ms.sourcegitcommit: 226527be7cb647acfe2ea9ab151185053ab3c6db
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2017
---
# <span data-ttu-id="c3ab1-103">Logga in med Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="c3ab1-103">Log in with Azure PowerShell</span></span>
<a id="log-in-with-azure-powershell" class="xliff"></a>

<span data-ttu-id="c3ab1-104">Azure PowerShell har stöd för flera inloggningsmetoder.</span><span class="sxs-lookup"><span data-stu-id="c3ab1-104">Azure PowerShell supports multiple login methods.</span></span> <span data-ttu-id="c3ab1-105">Det är enklast att komma igång genom att logga in interaktivt via kommandoraden.</span><span class="sxs-lookup"><span data-stu-id="c3ab1-105">The simplest way to get started is to log in interactively at the command line.</span></span>

## <span data-ttu-id="c3ab1-106">Interaktiv inloggning</span><span class="sxs-lookup"><span data-stu-id="c3ab1-106">Interactive log in</span></span>
<a id="interactive-log-in" class="xliff"></a>

1. <span data-ttu-id="c3ab1-107">Skriv `Login-AzureRmAccount`.</span><span class="sxs-lookup"><span data-stu-id="c3ab1-107">Type `Login-AzureRmAccount`.</span></span> <span data-ttu-id="c3ab1-108">En dialogruta som frågar efter dina Azure-autentiseringsuppgifter visas.</span><span class="sxs-lookup"><span data-stu-id="c3ab1-108">You will get dialog box asking for your Azure credentials.</span></span>

2. <span data-ttu-id="c3ab1-109">Ange e-postadressen och lösenordet som är kopplade till ditt konto.</span><span class="sxs-lookup"><span data-stu-id="c3ab1-109">Type the email address and password associated with your account.</span></span> <span data-ttu-id="c3ab1-110">Azure autentiserar och sparar autentiseringsuppgifterna och stänger sedan fönstret.</span><span class="sxs-lookup"><span data-stu-id="c3ab1-110">Azure authenticates and saves the credential information, and then closes the window.</span></span>

## <span data-ttu-id="c3ab1-111">Logga in med ett huvudnamn för tjänsten</span><span class="sxs-lookup"><span data-stu-id="c3ab1-111">Log in with a service principal</span></span>
<a id="log-in-with-a-service-principal" class="xliff"></a>

<span data-ttu-id="c3ab1-112">Tjänstens huvudnamn ger dig ett sätt att skapa icke-interaktiva konton som du sedan kan använda för att manipulera resurser.</span><span class="sxs-lookup"><span data-stu-id="c3ab1-112">Service principals provide a way for you to create non-interactive accounts that you can use to manipulate resources.</span></span> <span data-ttu-id="c3ab1-113">Huvudnamn för tjänsten liknar användarkonton som du kan tillämpa regler på med Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c3ab1-113">Service principals are like user accounts to which you can apply rules using Azure Active Directory.</span></span> <span data-ttu-id="c3ab1-114">Du kan säkerställa att dina automatiseringsskript är ännu säkrare genom att tilldela dem den lägsta behörigheten som krävs för ett huvudnamn för tjänsten.</span><span class="sxs-lookup"><span data-stu-id="c3ab1-114">By granting the minimum permissions needed to a service principal, you can ensure your automation scripts are even more secure.</span></span>

1. <span data-ttu-id="c3ab1-115">Om du inte redan har ett huvudnamn för tjänsten kan du [skapa ett](create-azure-service-principal-azureps.md).</span><span class="sxs-lookup"><span data-stu-id="c3ab1-115">If you don't already have a service principal, [create one](create-azure-service-principal-azureps.md).</span></span>

2. <span data-ttu-id="c3ab1-116">Logga in med huvudnamnet för tjänsten.</span><span class="sxs-lookup"><span data-stu-id="c3ab1-116">Log in with the service principal.</span></span>

    ```powershell
    Login-AzureRmAccount -ServicePrincipal -ApplicationId  "http://my-app" -Credential $pscredential -TenantId $tenantid
    ```

    <span data-ttu-id="c3ab1-117">För att få ditt TenantId loggar du in interaktivt och hämtar sedan ditt TenantId från prenumerationen.</span><span class="sxs-lookup"><span data-stu-id="c3ab1-117">To get your TenantId, log in interactively and then get the TenantId from your subscription.</span></span>

    ```powershell
    Get-AzureRmSubscription
    ```

    ```
    Environment           : AzureCloud
    Account               : username@contoso.com
    TenantId              : XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX
    SubscriptionId        : XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX
    SubscriptionName      : My Production Subscription
    CurrentStorageAccount :
    ```

## <span data-ttu-id="c3ab1-118">Logga in på ett annat moln</span><span class="sxs-lookup"><span data-stu-id="c3ab1-118">Log in to another Cloud</span></span>
<a id="log-in-to-another-cloud" class="xliff"></a>

<span data-ttu-id="c3ab1-119">Azure-molntjänster erbjuder olika miljöer som följer olika myndigheters regler för datahantering.</span><span class="sxs-lookup"><span data-stu-id="c3ab1-119">Azure cloud services provide different environments that adhere to the data-handling regulations of various governments.</span></span> <span data-ttu-id="c3ab1-120">Om ditt Azure-konto finns i ett myndighetsmoln, behöver du specificera miljön när du loggar in.</span><span class="sxs-lookup"><span data-stu-id="c3ab1-120">If your Azure account is in one the government clouds, you need to specify the environment when you sign in.</span></span> <span data-ttu-id="c3ab1-121">Om ditt konto till exempel befinner sig i Kina-molnet, loggar du in med följande kommando:</span><span class="sxs-lookup"><span data-stu-id="c3ab1-121">For example, if you account is in the China cloud you sign on using the following command:</span></span>

```powershell
Login-AzureRmAccount -EnvironmentName AzureChinaCloud
```

<span data-ttu-id="c3ab1-122">Använd följande kommando för att få en lista över tillgängliga miljöer:</span><span class="sxs-lookup"><span data-stu-id="c3ab1-122">Use the following command to get a list of available environments:</span></span>

```powershell
Get-AzureRmEnvironment | Select-Object Name
```

```
Name
----
AzureCloud
AzureChinaCloud
AzureUSGovernment
AzureGermanCloud
```

## <span data-ttu-id="c3ab1-123">Lär dig mer om att hantera rollbaserad åtkomstkontroll i Azure</span><span class="sxs-lookup"><span data-stu-id="c3ab1-123">Learn more about managing Azure role-based access</span></span>
<a id="learn-more-about-managing-azure-role-based-access" class="xliff"></a>

<span data-ttu-id="c3ab1-124">Mer information om hantering av autentisering och prenumerationer i Azure finns i [Hantera konton, prenumerationer och administrativa roller](/azure/active-directory/role-based-access-control-configure).</span><span class="sxs-lookup"><span data-stu-id="c3ab1-124">For more information about authentication and subscription management in Azure, see [Manage Accounts, Subscriptions, and Administrative Roles](/azure/active-directory/role-based-access-control-configure).</span></span>

<span data-ttu-id="c3ab1-125">Azure PowerShell-cmdletar för rollhantering</span><span class="sxs-lookup"><span data-stu-id="c3ab1-125">Azure PowerShell cmdlets for role management</span></span>

* [<span data-ttu-id="c3ab1-126">Get-AzureRmRoleAssignment</span><span class="sxs-lookup"><span data-stu-id="c3ab1-126">Get-AzureRmRoleAssignment</span></span>](/powershell/module/AzureRM.Resources/Get-AzureRmRoleAssignment)
* [<span data-ttu-id="c3ab1-127">Get-AzureRmRoleDefinition</span><span class="sxs-lookup"><span data-stu-id="c3ab1-127">Get-AzureRmRoleDefinition</span></span>](/powershell/module/AzureRM.Resources/Get-AzureRmRoleDefinition)
* [<span data-ttu-id="c3ab1-128">New-AzureRmRoleAssignment</span><span class="sxs-lookup"><span data-stu-id="c3ab1-128">New-AzureRmRoleAssignment</span></span>](/powershell/module/AzureRM.Resources/New-AzureRmRoleAssignment)
* [<span data-ttu-id="c3ab1-129">New-AzureRmRoleDefinition</span><span class="sxs-lookup"><span data-stu-id="c3ab1-129">New-AzureRmRoleDefinition</span></span>](/powershell/module/AzureRM.Resources/New-AzureRmRoleDefinition)
* [<span data-ttu-id="c3ab1-130">Remove-AzureRmRoleAssignment</span><span class="sxs-lookup"><span data-stu-id="c3ab1-130">Remove-AzureRmRoleAssignment</span></span>](/powershell/module/AzureRM.Resources/Remove-AzureRmRoleAssignment)
* [<span data-ttu-id="c3ab1-131">Remove-AzureRmRoleDefinition</span><span class="sxs-lookup"><span data-stu-id="c3ab1-131">Remove-AzureRmRoleDefinition</span></span>](/powershell/module/AzureRM.Resources/Remove-AzureRmRoleDefinition)
* [<span data-ttu-id="c3ab1-132">Set-AzureRmRoleDefinition</span><span class="sxs-lookup"><span data-stu-id="c3ab1-132">Set-AzureRmRoleDefinition</span></span>](/powershell/moduel/AzureRM.Resources/Set-AzureRmRoleDefinition)
