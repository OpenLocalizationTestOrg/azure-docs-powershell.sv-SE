---
title: "Komma igång med Azure PowerShell | Microsoft Docs"
description: 
services: azure
author: sdwheeler
ms.author: sewhee
manager: carmonm
ms.product: azure
ms.service: azure-powershell
ms.devlang: powershell
ms.topic: get-started-article
ms.date: 03/30/2017
ms.openlocfilehash: f1c13317f0b42b547166a8130dd8c29bed5759c9
ms.sourcegitcommit: db5c50de90764a9bdc7c1f1dbca3aed5bfeb05fa
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/22/2017
---
# <a name="getting-started-with-azure-powershell"></a><span data-ttu-id="b02cf-102">Komma igång med Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="b02cf-102">Getting started with Azure PowerShell</span></span>

<span data-ttu-id="b02cf-103">Azure PowerShell har utformats för att hantera och administrera Azure-resurser från kommandoraden och för att skapa automatiseringsskript som fungerar mot Azure Resource Manager.</span><span class="sxs-lookup"><span data-stu-id="b02cf-103">Azure PowerShell is designed for managing and administering Azure resources from the command line, and for building automation scripts that work against the Azure Resource Manager.</span></span> <span data-ttu-id="b02cf-104">Den här artikeln hjälper dig att komma igång med att använda det och lär dig grundbegreppen bakom.</span><span class="sxs-lookup"><span data-stu-id="b02cf-104">This article helps get you started using it, and teaches you the core concepts behind it.</span></span>

## <a name="install-azure-powershell"></a><span data-ttu-id="b02cf-105">Installera Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="b02cf-105">Install Azure PowerShell</span></span>

<span data-ttu-id="b02cf-106">Det första steget är att kontrollera att du har den senaste versionen av Azure PowerShell installerad.</span><span class="sxs-lookup"><span data-stu-id="b02cf-106">The first step is to make sure you have the latest version of the Azure PowerShell installed.</span></span> <span data-ttu-id="b02cf-107">Information om den senaste versionen finns i [viktig information](./release-notes-azureps.md).</span><span class="sxs-lookup"><span data-stu-id="b02cf-107">For information about the latest release, see the [release notes](./release-notes-azureps.md).</span></span>

1. <span data-ttu-id="b02cf-108">[Installera Azure PowerShell](install-azurerm-ps.md).</span><span class="sxs-lookup"><span data-stu-id="b02cf-108">[Install Azure PowerShell](install-azurerm-ps.md).</span></span>
2. <span data-ttu-id="b02cf-109">Kontrollera att installationen lyckades genom att köra `Get-Module AzureRM` från kommandoraden.</span><span class="sxs-lookup"><span data-stu-id="b02cf-109">To verify the installation was successful, run `Get-Module AzureRM` from your command line.</span></span>

## <a name="log-in-to-azure"></a><span data-ttu-id="b02cf-110">Logga in på Azure</span><span class="sxs-lookup"><span data-stu-id="b02cf-110">Log in to Azure</span></span>

<span data-ttu-id="b02cf-111">Logga in interaktivt:</span><span class="sxs-lookup"><span data-stu-id="b02cf-111">Sign on interactively:</span></span>

1. <span data-ttu-id="b02cf-112">Skriv `Login-AzureRmAccount`.</span><span class="sxs-lookup"><span data-stu-id="b02cf-112">Type `Login-AzureRmAccount`.</span></span> <span data-ttu-id="b02cf-113">En dialogruta som frågar efter dina Azure-autentiseringsuppgifter visas.</span><span class="sxs-lookup"><span data-stu-id="b02cf-113">You will get dialog box asking for your Azure credentials.</span></span> <span data-ttu-id="b02cf-114">Med alternativet ”-EnvironmentName” kan du logga in Azure Kina eller Azure Tyskland.</span><span class="sxs-lookup"><span data-stu-id="b02cf-114">Option '-EnvironmentName' can let you login in Azure China or Azure Germany.</span></span>

   <span data-ttu-id="b02cf-115">t.ex. Login-AzureRmAccount -EnvironmentName AzureChinaCloud</span><span class="sxs-lookup"><span data-stu-id="b02cf-115">e.g. Login-AzureRmAccount -EnvironmentName AzureChinaCloud</span></span>

2. <span data-ttu-id="b02cf-116">Ange e-postadressen och lösenordet som är kopplade till ditt konto.</span><span class="sxs-lookup"><span data-stu-id="b02cf-116">Type the email address and password associated with your account.</span></span> <span data-ttu-id="b02cf-117">Azure autentiserar och sparar autentiseringsuppgifterna och stänger sedan fönstret.</span><span class="sxs-lookup"><span data-stu-id="b02cf-117">Azure authenticates and saves the credential information, and then closes the window.</span></span>

<span data-ttu-id="b02cf-118">När du har loggat in på ett Azure-konto kan du använda Azure PowerShell-cmdletar för att komma åt och hantera resurserna i prenumerationen.</span><span class="sxs-lookup"><span data-stu-id="b02cf-118">Once you have signed in to an Azure account, you can use the Azure PowerShell cmdlets to access and manager the resources in your subscription.</span></span>

## <a name="create-a-resource-group"></a><span data-ttu-id="b02cf-119">Skapa en resursgrupp</span><span class="sxs-lookup"><span data-stu-id="b02cf-119">Create a resource group</span></span>

<span data-ttu-id="b02cf-120">Nu när allt har konfigurerats ska vi använda Azure PowerShell för att skapa resurser i Azure.</span><span class="sxs-lookup"><span data-stu-id="b02cf-120">Now that we've got everything set up, let's use Azure PowerShell to create resources within Azure.</span></span>

<span data-ttu-id="b02cf-121">Skapa först en resursgrupp.</span><span class="sxs-lookup"><span data-stu-id="b02cf-121">First, create a Resource Group.</span></span> <span data-ttu-id="b02cf-122">Resursgrupper i Azure ger ett sätt att hantera flera resurser som du vill gruppera logiskt.</span><span class="sxs-lookup"><span data-stu-id="b02cf-122">Resource Groups in Azure provide a way to manage multiple resources that you want to logically group together.</span></span> <span data-ttu-id="b02cf-123">Du kan till exempel skapa en resursgrupp för ett program eller projekt och lägga till en virtuell dator, en databas och en CDN-tjänst inom den.</span><span class="sxs-lookup"><span data-stu-id="b02cf-123">For example, you might create a Resource Group for an application or project and add a virtual machine, a database and a CDN service within it.</span></span>

<span data-ttu-id="b02cf-124">Vi ska skapa en resursgrupp med namnet "MyResourceGroup" i den västeuropeiska regionen för Azure.</span><span class="sxs-lookup"><span data-stu-id="b02cf-124">Let's create a resource group named "MyResourceGroup" in the westeurope region of Azure.</span></span> <span data-ttu-id="b02cf-125">Ange följande kommando:</span><span class="sxs-lookup"><span data-stu-id="b02cf-125">To do so type the following command:</span></span>

```powershell
New-AzureRmResourceGroup -Name 'myResourceGroup' -Location 'westeurope'
```

```
ResourceGroupName : myResourceGroup
Location          : westeurope
ProvisioningState : Succeeded
Tags              :
ResourceId        : /subscriptions/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX/resourceGroups/myResourceGroup
```

## <a name="create-a-windows-virtual-machine"></a><span data-ttu-id="b02cf-126">Skapa en virtuell Windows-dator</span><span class="sxs-lookup"><span data-stu-id="b02cf-126">Create a Windows Virtual Machine</span></span>

<span data-ttu-id="b02cf-127">Nu när vi har en resursgrupp kan vi skapa en virtuell Windows-dator i den.</span><span class="sxs-lookup"><span data-stu-id="b02cf-127">Now that we have our resource group, let's create a Windows VM within it.</span></span> <span data-ttu-id="b02cf-128">För att kunna skapa en ny virtuell dator måste vi först skapa de övriga resurser som krävs och tilldela dem till en konfiguration.</span><span class="sxs-lookup"><span data-stu-id="b02cf-128">To create a new VM we must first create the other required resources and assign them to a configuration.</span></span> <span data-ttu-id="b02cf-129">Vi kan sedan använda den konfigurationen för att skapa den virtuella datorn.</span><span class="sxs-lookup"><span data-stu-id="b02cf-129">Then we can use that configuration to create the VM.</span></span>

### <a name="create-the-required-network-resources"></a><span data-ttu-id="b02cf-130">Skapa nätverksresurser som krävs</span><span class="sxs-lookup"><span data-stu-id="b02cf-130">Create the required network resources</span></span>

<span data-ttu-id="b02cf-131">Vi måste först skapa en undernätskonfiguration som ska användas med processen för att skapa virtuella nätverk.</span><span class="sxs-lookup"><span data-stu-id="b02cf-131">First we need to create a subnet configuration to be used with the virtual network creation process.</span></span> <span data-ttu-id="b02cf-132">Vi skapar också en offentlig IP-adress så att vi kan ansluta till denna virtuella dator.</span><span class="sxs-lookup"><span data-stu-id="b02cf-132">We also create a public IP address so that we can connect to this VM.</span></span> <span data-ttu-id="b02cf-133">Vi skapar en nätverkssäkerhetsgrupp för att säkra åtkomst till den offentliga adressen.</span><span class="sxs-lookup"><span data-stu-id="b02cf-133">We create a network security group to secure access to the public address.</span></span> <span data-ttu-id="b02cf-134">Slutligen skapar vi ett virtuellt nätverkskort med alla föregående resurser.</span><span class="sxs-lookup"><span data-stu-id="b02cf-134">Finally we create the virtual NIC using all of the previous resources.</span></span>

```powershell
# Variables for common values
$resourceGroup = "myResourceGroup"
$location = "westeurope"
$vmName = "myWindowsVM"

# Create a subnet configuration
$subnetConfig = New-AzureRmVirtualNetworkSubnetConfig -Name mySubnet1 -AddressPrefix 192.168.1.0/24

# Create a virtual network
$vnet = New-AzureRmVirtualNetwork -ResourceGroupName $resourceGroup -Location $location `
  -Name MYvNET1 -AddressPrefix 192.168.0.0/16 -Subnet $subnetConfig

# Create a public IP address and specify a DNS name
$publicIp = New-AzureRmPublicIpAddress -ResourceGroupName $resourceGroup -Location $location `
  -Name "mypublicdns$(Get-Random)" -AllocationMethod Static -IdleTimeoutInMinutes 4
$publicIp | Select-Object Name,IpAddress

# Create an inbound network security group rule for port 3389
$nsgRuleRDP = New-AzureRmNetworkSecurityRuleConfig -Name myNetworkSecurityGroupRuleRDP  -Protocol Tcp `
  -Direction Inbound -Priority 1000 -SourceAddressPrefix * -SourcePortRange * -DestinationAddressPrefix * `
  -DestinationPortRange 3389 -Access Allow

# Create a network security group
$nsg = New-AzureRmNetworkSecurityGroup -ResourceGroupName $resourceGroup -Location $location `
  -Name myNetworkSecurityGroup1 -SecurityRules $nsgRuleRDP

# Create a virtual network card and associate with public IP address and NSG
$nic = New-AzureRmNetworkInterface -Name myNic1 -ResourceGroupName $resourceGroup -Location $location `
  -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $publicIp.Id -NetworkSecurityGroupId $nsg.Id
```

### <a name="create-the-virtual-machine"></a><span data-ttu-id="b02cf-135">Skapa den virtuella datorn</span><span class="sxs-lookup"><span data-stu-id="b02cf-135">Create the virtual machine</span></span>

<span data-ttu-id="b02cf-136">Vi måste först ha en uppsättning autentiseringsuppgifter för operativsystemet.</span><span class="sxs-lookup"><span data-stu-id="b02cf-136">First we need a set of credentials for the OS.</span></span>

```powershell
# Create user object
$cred = Get-Credential -Message "Enter a username and password for the virtual machine."
```

<span data-ttu-id="b02cf-137">Nu när vi har de nödvändiga resurserna kan vi skapa den virtuella datorn.</span><span class="sxs-lookup"><span data-stu-id="b02cf-137">Now that we have the required resources we can create the VM.</span></span> <span data-ttu-id="b02cf-138">För detta steg skapar vi ett VM-konfigurationsobjekt och sedan använder vi konfigurationen för att skapa den virtuella datorn.</span><span class="sxs-lookup"><span data-stu-id="b02cf-138">For this step, we create a VM configuration object, then we use the configuration to create the VM.</span></span>

```powershell
# Create a virtual machine configuration
$vmConfig = New-AzureRmVMConfig -VMName $vmName -VMSize Standard_D1 |
  Set-AzureRmVMOperatingSystem -Windows -ComputerName $vmName -Credential $cred |
  Set-AzureRmVMSourceImage -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version latest |
  Add-AzureRmVMNetworkInterface -Id $nic.Id

# Create a virtual machine
New-AzureRmVM -ResourceGroupName $resourceGroup -Location $location -VM $vmConfig
```

<span data-ttu-id="b02cf-139">Kommandot `New-AzureRmVM` ger resultat när den virtuella datorn har skapats färdigt och är redo att användas.</span><span class="sxs-lookup"><span data-stu-id="b02cf-139">The `New-AzureRmVM` command outputs results once the VM has been fully created and is ready to be used.</span></span>

```
RequestId IsSuccessStatusCode StatusCode ReasonPhrase
--------- ------------------- ---------- ------------
                         True         OK OK
```

<span data-ttu-id="b02cf-140">Logga nu in på den virtuella Windows Server-dator som har skapats med hjälp av Fjärrskrivbord och den virtuella datorns offentliga IP-adress.</span><span class="sxs-lookup"><span data-stu-id="b02cf-140">Now log on to your newly created Windows Server VM using Remote Desktop and the public IP address of the VM.</span></span> <span data-ttu-id="b02cf-141">Följande kommando visar den offentliga IP-adress som skapades i föregående skript.</span><span class="sxs-lookup"><span data-stu-id="b02cf-141">The following command displays the public IP address created in the previous script.</span></span>

```powershell
$publicIp | Select-Object Name,IpAddress
```

```
Name                  IpAddress
----                  ---------
mypublicdns1400512543 xx.xx.xx.xx
```

<span data-ttu-id="b02cf-142">Om du använder ett Windows-baserat system kan du göra detta från kommandoraden med mstsc-kommandot:</span><span class="sxs-lookup"><span data-stu-id="b02cf-142">If you are on a Windows-based system, you can do this from the command line using the mstsc command:</span></span>

```
mstsc /v:xx.xxx.xx.xxx
```

<span data-ttu-id="b02cf-143">Ange samma kombination av användarnamn/lösenord för att logga in som du använde när du skapade den virtuella datorn.</span><span class="sxs-lookup"><span data-stu-id="b02cf-143">Supply the same username/password combination you used when creating the VM to log in.</span></span>


## <a name="create-a-linux-virtual-machine"></a><span data-ttu-id="b02cf-144">Skapa en virtuell Linux-dator</span><span class="sxs-lookup"><span data-stu-id="b02cf-144">Create a Linux Virtual Machine</span></span>

<span data-ttu-id="b02cf-145">För att kunna skapa en ny virtuell Linux-dator måste vi först skapa de övriga resurser som krävs och tilldela dem till en konfiguration.</span><span class="sxs-lookup"><span data-stu-id="b02cf-145">To create a new Linux VM we must first create the other required resources and assign them to a configuration.</span></span> <span data-ttu-id="b02cf-146">Vi kan sedan använda den konfigurationen för att skapa den virtuella datorn.</span><span class="sxs-lookup"><span data-stu-id="b02cf-146">Then we can use that configuration to create the VM.</span></span> <span data-ttu-id="b02cf-147">Detta förutsätter att du redan har skapat resursgruppen på det sätt som visats tidigare.</span><span class="sxs-lookup"><span data-stu-id="b02cf-147">This assumes that you have already created the resource group as previously shown.</span></span> <span data-ttu-id="b02cf-148">Du behöver även ha en offentlig SSH-nyckel med namnet `id_rsa.pub` i .ssh-katalogen för din användarprofil.</span><span class="sxs-lookup"><span data-stu-id="b02cf-148">Also, you will need to have an SSH public key named `id_rsa.pub` in the .ssh directory of your user profile.</span></span>

### <a name="create-the-required-network-resources"></a><span data-ttu-id="b02cf-149">Skapa nätverksresurser som krävs</span><span class="sxs-lookup"><span data-stu-id="b02cf-149">Create the required network resources</span></span>

<span data-ttu-id="b02cf-150">Vi måste först skapa en undernätskonfiguration som ska användas med processen för att skapa virtuella nätverk.</span><span class="sxs-lookup"><span data-stu-id="b02cf-150">First we need to create a subnet configuration to be used with the virtual network creation process.</span></span> <span data-ttu-id="b02cf-151">Vi skapar också en offentlig IP-adress så att vi kan ansluta till denna virtuella dator.</span><span class="sxs-lookup"><span data-stu-id="b02cf-151">We also create a public IP address so that we can connect to this VM.</span></span> <span data-ttu-id="b02cf-152">Vi skapar en nätverkssäkerhetsgrupp för att säkra åtkomst till den offentliga adressen.</span><span class="sxs-lookup"><span data-stu-id="b02cf-152">We create a network security group to secure access to the public address.</span></span> <span data-ttu-id="b02cf-153">Slutligen skapar vi ett virtuellt nätverkskort med alla föregående resurser.</span><span class="sxs-lookup"><span data-stu-id="b02cf-153">Finally we create the virtual NIC using all of the previous resources.</span></span>

```powershell
# Variables for common values
$resourceGroup = "myResourceGroup"
$location = "westeurope"
$vmName = "myLinuxVM"

# Definer user name and blank password
$securePassword = ConvertTo-SecureString ' ' -AsPlainText -Force
$cred = New-Object System.Management.Automation.PSCredential ("azureuser", $securePassword)

# Create a subnet configuration
$subnetConfig = New-AzureRmVirtualNetworkSubnetConfig -Name mySubnet2 -AddressPrefix 192.168.2.0/24

# Create a virtual network
$vnet = New-AzureRmVirtualNetwork -ResourceGroupName $resourceGroup -Location $location `
  -Name MYvNET2 -AddressPrefix 192.168.0.0/16 -Subnet $subnetConfig

# Create a public IP address and specify a DNS name
$publicIp = New-AzureRmPublicIpAddress -ResourceGroupName $resourceGroup -Location $location `
  -Name "mypublicdns$(Get-Random)" -AllocationMethod Static -IdleTimeoutInMinutes 4
$publicIp | Select-Object Name,IpAddress

# Create an inbound network security group rule for port 22
$nsgRuleSSH = New-AzureRmNetworkSecurityRuleConfig -Name myNetworkSecurityGroupRuleSSH  -Protocol Tcp `
  -Direction Inbound -Priority 1000 -SourceAddressPrefix * -SourcePortRange * -DestinationAddressPrefix * `
  -DestinationPortRange 22 -Access Allow

# Create a network security group
$nsg = New-AzureRmNetworkSecurityGroup -ResourceGroupName $resourceGroup -Location $location `
  -Name myNetworkSecurityGroup2 -SecurityRules $nsgRuleSSH

# Create a virtual network card and associate with public IP address and NSG
$nic = New-AzureRmNetworkInterface -Name myNic2 -ResourceGroupName $resourceGroup -Location $location `
  -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $publicIp.Id -NetworkSecurityGroupId $nsg.Id
```

### <a name="create-the-virtual-machine"></a><span data-ttu-id="b02cf-154">Skapa den virtuella datorn</span><span class="sxs-lookup"><span data-stu-id="b02cf-154">Create the virtual machine</span></span>

<span data-ttu-id="b02cf-155">Nu när vi har de nödvändiga resurserna kan vi skapa den virtuella datorn.</span><span class="sxs-lookup"><span data-stu-id="b02cf-155">Now that we have the required resources we can create the VM.</span></span> <span data-ttu-id="b02cf-156">För detta steg skapar vi ett VM-konfigurationsobjekt och sedan använder vi konfigurationen för att skapa den virtuella datorn.</span><span class="sxs-lookup"><span data-stu-id="b02cf-156">For this step, we create a VM configuration object, then we use the configuration to create the VM.</span></span>

```powershell
# Create a virtual machine configuration
$vmConfig = New-AzureRmVMConfig -VMName $vmName -VMSize Standard_D1 |
  Set-AzureRmVMOperatingSystem -Linux -ComputerName $vmName -Credential $cred -DisablePasswordAuthentication |
  Set-AzureRmVMSourceImage -PublisherName Canonical -Offer UbuntuServer -Skus 14.04.2-LTS -Version latest |
  Add-AzureRmVMNetworkInterface -Id $nic.Id

# Configure SSH Keys
$sshPublicKey = Get-Content "$env:USERPROFILE\.ssh\id_rsa.pub"
Add-AzureRmVMSshPublicKey -VM $vmConfig -KeyData $sshPublicKey -Path "/home/azureuser/.ssh/authorized_keys"

# Create a virtual machine
New-AzureRmVM -ResourceGroupName $resourceGroup -Location $location -VM $vmConfig
```

<span data-ttu-id="b02cf-157">Nu när den virtuella datorn har skapats kan du logga in på den nya virtuella Linux-datorn med hjälp av SSH med den offentliga IP-adressen för den virtuella dator du skapade:</span><span class="sxs-lookup"><span data-stu-id="b02cf-157">Now that the VM has been created, you can log on to your new Linux VM using SSH with the public IP address of the VM you created:</span></span>

```bash
ssh xx.xxx.xxx.xxx
```

```
Welcome to Ubuntu 14.04.4 LTS (GNU/Linux 3.19.0-65-generic x86_64)

 * Documentation:  https://help.ubuntu.com/

  System information as of Sun Feb 19 00:32:28 UTC 2017

  System load: 0.31              Memory usage: 3%   Processes:       89
  Usage of /:  39.6% of 1.94GB   Swap usage:   0%   Users logged in: 0

  Graph this data and manage this system at:
    https://landscape.canonical.com/

  Get cloud support with Ubuntu Advantage Cloud Guest:
    http://www.ubuntu.com/business/services/cloud

0 packages can be updated.
0 updates are security updates.



The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.

my-login@MyLinuxVM:~$
```

## <a name="creating-other-resources-in-azure"></a><span data-ttu-id="b02cf-158">Skapa andra resurser i Azure</span><span class="sxs-lookup"><span data-stu-id="b02cf-158">Creating other resources in Azure</span></span>

<span data-ttu-id="b02cf-159">Vi har nu gått igenom hur du skapar en resursgrupp, en virtuell Linux-dator och en virtuell Windows Server-dator.</span><span class="sxs-lookup"><span data-stu-id="b02cf-159">We've now walked through how to create a Resource Group, a Linux VM, and a Windows Server VM.</span></span> <span data-ttu-id="b02cf-160">Du kan även skapa många andra typer av Azure-resurser.</span><span class="sxs-lookup"><span data-stu-id="b02cf-160">You can create many other types of Azure resources as well.</span></span>

<span data-ttu-id="b02cf-161">Om du till exempel vill skapa en belastningsutjämnare för Azure-nätverk som vi sedan kan koppla till de virtuella datorer vi precis har skapat kan vi använda följande kommando för att skapa:</span><span class="sxs-lookup"><span data-stu-id="b02cf-161">For example, to create an Azure Network Load Balancer that we could then associate with our newly created VMs, we can use the following create command:</span></span>

```powershell
New-AzureRmLoadBalancer -Name MyLoadBalancer -ResourceGroupName myResourceGroup -Location westeurope
```

<span data-ttu-id="b02cf-162">Vi kan också skapa ett nytt privat virtuellt nätverk (som ofta kallas ett "VNet" i Azure) för infrastrukturen med följande kommando:</span><span class="sxs-lookup"><span data-stu-id="b02cf-162">We could also create a new private Virtual Network (commonly referred to as a "VNet" within Azure) for our infrastructure using the following command:</span></span>

```powershell
$subnetConfig = New-AzureRmVirtualNetworkSubnetConfig -Name mySubnet2 -AddressPrefix 10.0.0.0/16
$vnet = New-AzureRmVirtualNetwork -ResourceGroupName myResourceGroup -Location westeurope `
  -Name MYvNET3 -AddressPrefix 10.0.0.0/16 -Subnet $subnetConfig
```

<span data-ttu-id="b02cf-163">Det som gör Azure och Azure PowerShell så kraftfulla är att vi kan använda dem inte bara för att få molnbaserad infrastruktur, utan också för att skapa hanterade plattformstjänster.</span><span class="sxs-lookup"><span data-stu-id="b02cf-163">What makes Azure and the Azure PowerShell powerful is that we can use it not just to get cloud-based infrastructure but also to create managed platform services.</span></span> <span data-ttu-id="b02cf-164">De hanterade plattformstjänsterna kan också kombineras med infrastruktur för att skapa ännu mer kraftfulla lösningar.</span><span class="sxs-lookup"><span data-stu-id="b02cf-164">The managed platform services can also be combined with infrastructure to build even more powerful solutions.</span></span>

<span data-ttu-id="b02cf-165">Du kan till exempel använda Azure PowerShell för att skapa en Azure AppService.</span><span class="sxs-lookup"><span data-stu-id="b02cf-165">For example, you can use the Azure PowerShell to create an Azure AppService.</span></span> <span data-ttu-id="b02cf-166">Azure AppService är en hanterad plattformstjänst som ger ett utmärkt sätt att agera värd för webbappar utan att behöva bekymra sig över infrastruktur.</span><span class="sxs-lookup"><span data-stu-id="b02cf-166">Azure AppService is a managed platform service that provides a great way to host web apps without having to worry about infrastructure.</span></span> <span data-ttu-id="b02cf-167">När du har skapat Azure AppService kan du skapa två nya Azure-webbappar i AppService med hjälp av följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="b02cf-167">After creating the Azure AppService, you can create two new Azure Web Apps within the AppService using the following commands:</span></span>

```powershell
# Create an Azure AppService that we can host any number of web apps within
New-AzureRmAppServicePlan -Name MyAppServicePlan -Tier Basic -NumberofWorkers 2 -WorkerSize Small -ResourceGroupName myResourceGroup -Location westeurope

# Create Two Web Apps within the AppService (note: name param must be a unique DNS entry)
New-AzureRmWebApp -Name MyWebApp43432 -AppServicePlan MyAppServicePlan -ResourceGroupName myResourceGroup -Location westeurope
New-AzureRmWebApp -Name MyWebApp43433 -AppServicePlan MyAppServicePlan -ResourceGroupName myResourceGroup -Location westeurope
```

## <a name="listing-deployed-resources"></a><span data-ttu-id="b02cf-168">Skapa en lista över distribuerade resurser</span><span class="sxs-lookup"><span data-stu-id="b02cf-168">Listing deployed resources</span></span>

<span data-ttu-id="b02cf-169">Du kan använda cmdleten `Get-AzureRmResource` för att få fram en lista över de resurser som körs i Azure.</span><span class="sxs-lookup"><span data-stu-id="b02cf-169">You can use the `Get-AzureRmResource` cmdlet to list the resources running in Azure.</span></span> <span data-ttu-id="b02cf-170">I följande exempel visas resurserna som vi nyss skapade i den nya resursgruppen.</span><span class="sxs-lookup"><span data-stu-id="b02cf-170">The following example shows the resources we just created in the new resource group.</span></span>

```powershell
Get-AzureRmResource |
  Where-Object ResourceGroupName -eq myResourceGroup |
    Select-Object Name,Location,ResourceType
```

```
Name                                                  Location   ResourceType
----                                                  --------   ------------
myLinuxVM_OsDisk_1_36ca038791f642ba91270879088c249a   westeurope Microsoft.Compute/disks
myWindowsVM_OsDisk_1_f627e6e2bb454c72897d72e9632adf9a westeurope Microsoft.Compute/disks
myLinuxVM                                             westeurope Microsoft.Compute/virtualMachines
myWindowsVM                                           westeurope Microsoft.Compute/virtualMachines
myWindowsVM/BGInfo                                    westeurope Microsoft.Compute/virtualMachines/extensions
myNic1                                                westeurope Microsoft.Network/networkInterfaces
myNic2                                                westeurope Microsoft.Network/networkInterfaces
myNetworkSecurityGroup1                               westeurope Microsoft.Network/networkSecurityGroups
myNetworkSecurityGroup2                               westeurope Microsoft.Network/networkSecurityGroups
mypublicdns245369171                                  westeurope Microsoft.Network/publicIPAddresses
mypublicdns779537141                                  westeurope Microsoft.Network/publicIPAddresses
MYvNET1                                               westeurope Microsoft.Network/virtualNetworks
MYvNET2                                               westeurope Microsoft.Network/virtualNetworks
micromyresomywi032907510                              westeurope Microsoft.Storage/storageAccounts
```

## <a name="deleting-resources"></a><span data-ttu-id="b02cf-171">Ta bort resurser</span><span class="sxs-lookup"><span data-stu-id="b02cf-171">Deleting resources</span></span>

<span data-ttu-id="b02cf-172">Om du vill rensa i Azure-kontot kan du ta bort de resurser vi skapade i detta exempel.</span><span class="sxs-lookup"><span data-stu-id="b02cf-172">To clean up your Azure account, you want to remove the resources we created in this example.</span></span> <span data-ttu-id="b02cf-173">Du kan använda cmdletarna `Remove-AzureRm*` för att ta bort de resurser du inte längre behöver.</span><span class="sxs-lookup"><span data-stu-id="b02cf-173">You can use the `Remove-AzureRm*` cmdlets to delete the resources you no longer need.</span></span> <span data-ttu-id="b02cf-174">Använd följande kommando om du vill ta bort den virtuella Windows-dator vi skapade:</span><span class="sxs-lookup"><span data-stu-id="b02cf-174">To remove the Windows VM we created, using the following command:</span></span>

```powershell
Remove-AzureRmVM -Name myWindowsVM -ResourceGroupName myResourceGroup
```

<span data-ttu-id="b02cf-175">Du uppmanas att bekräfta att du vill ta bort resursen.</span><span class="sxs-lookup"><span data-stu-id="b02cf-175">You will be prompted to confirm that you want to remove the resource.</span></span>

```
Confirm
Are you sure you want to remove resource group 'myResourceGroup'
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): Y
```

<span data-ttu-id="b02cf-176">Du kan också ta bort många resurser i taget.</span><span class="sxs-lookup"><span data-stu-id="b02cf-176">You can also use the delete many resources at one time.</span></span> <span data-ttu-id="b02cf-177">Följande kommando tar till exempel bort hela resursgruppen "MyResourceGroup" som vi har använt för alla exempel i denna handledning.</span><span class="sxs-lookup"><span data-stu-id="b02cf-177">For example, the following command deletes all the resource group "MyResourceGroup" that we've used for all the samples in this Get Started tutorial.</span></span> <span data-ttu-id="b02cf-178">Detta tar bort resursgruppen och alla resurser i den.</span><span class="sxs-lookup"><span data-stu-id="b02cf-178">This removes the resource group and all of the resources in it.</span></span>

```powershell
Remove-AzureRmResourceGroup -Name myResourceGroup
```

```
Confirm
Are you sure you want to remove resource group 'myResourceGroup'
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): Y
```

<span data-ttu-id="b02cf-179">Det kan ta flera minuter att slutföra.</span><span class="sxs-lookup"><span data-stu-id="b02cf-179">This can take several minutes to complete.</span></span>

## <a name="get-samples"></a><span data-ttu-id="b02cf-180">Hämta exempel</span><span class="sxs-lookup"><span data-stu-id="b02cf-180">Get samples</span></span>

<span data-ttu-id="b02cf-181">Om du vill lära dig mer om att använda Azure PowerShell kan du ta en titt på våra vanligaste skript för [virtuella Linux-datorer](/azure/virtual-machines/virtual-machines-linux-powershell-samples?toc=%2fpowershell%2fazure%%2ftoc.json), [virtuella Windows-datorer](/azure/virtual-machines/virtual-machines-windows-powershell-samples?toc=%2fpowershell%2fazure%%2ftoc.json), [webbappar](/azure/app-service-web/app-service-powershell-samples?toc=%2fpowershell%2fazure%%2ftoc.json) och [SQL-databaser](/azure/sql-database/sql-database-powershell-samples?toc=%2fpowershell%2fazure%%2ftoc.json).</span><span class="sxs-lookup"><span data-stu-id="b02cf-181">To learn more about ways to use the Azure PowerShell, check out our most common scripts for [Linux VMs](/azure/virtual-machines/virtual-machines-linux-powershell-samples?toc=%2fpowershell%2fazure%%2ftoc.json), [Windows VMs](/azure/virtual-machines/virtual-machines-windows-powershell-samples?toc=%2fpowershell%2fazure%%2ftoc.json), [Web Apps](/azure/app-service-web/app-service-powershell-samples?toc=%2fpowershell%2fazure%%2ftoc.json), and [SQL Databases](/azure/sql-database/sql-database-powershell-samples?toc=%2fpowershell%2fazure%%2ftoc.json).</span></span>

## <a name="next-steps"></a><span data-ttu-id="b02cf-182">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="b02cf-182">Next steps</span></span>

* [<span data-ttu-id="b02cf-183">Logga in med Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="b02cf-183">Login with Azure PowerShell</span></span>](authenticate-azureps.md)
* [<span data-ttu-id="b02cf-184">Hantera Azure-prenumerationer med Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="b02cf-184">Manage Azure subscriptions with Azure PowerShell</span></span>](manage-subscriptions-azureps.md)
* [<span data-ttu-id="b02cf-185">Skapa tjänstens huvudnamn i Azure med Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="b02cf-185">Create service principals in Azure using Azure PowerShell</span></span>](create-azure-service-principal-azureps.md)
* <span data-ttu-id="b02cf-186">Läs den viktiga informationen om att migrera från en äldre version: [https://github.com/Azure/azure-powershell/tree/dev/documentation/release-notes](https://github.com/Azure/azure-powershell/tree/dev/documentation/release-notes).</span><span class="sxs-lookup"><span data-stu-id="b02cf-186">Read the Release notes about migrating from an older release: [https://github.com/Azure/azure-powershell/tree/dev/documentation/release-notes](https://github.com/Azure/azure-powershell/tree/dev/documentation/release-notes).</span></span>
* <span data-ttu-id="b02cf-187">Få hjälp från communityn:</span><span class="sxs-lookup"><span data-stu-id="b02cf-187">Get help from the community:</span></span>
  + [<span data-ttu-id="b02cf-188">Azure-forumet på MSDN</span><span class="sxs-lookup"><span data-stu-id="b02cf-188">Azure forum on MSDN</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=320212)
  + [<span data-ttu-id="b02cf-189">stackoverflow</span><span class="sxs-lookup"><span data-stu-id="b02cf-189">stackoverflow</span></span>](http://go.microsoft.com/fwlink/?LinkId=320213)
