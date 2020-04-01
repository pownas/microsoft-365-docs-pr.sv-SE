---
title: Simulerat virtuellt nätverk på flera platser i en Microsoft 365-testmiljö
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
description: 'Sammanfattning: Skapa ett virtuellt nätverk för flera platser i Microsoft Azure som en Microsoft 365-testmiljö.'
ms.openlocfilehash: 52ba80d8613f44b252389da87891359eadae752a
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42812266"
---
# <a name="simulated-cross-premises-virtual-network-in-a-microsoft-365-test-environment"></a><span data-ttu-id="15acc-103">Simulerat virtuellt nätverk på flera platser i en Microsoft 365-testmiljö</span><span class="sxs-lookup"><span data-stu-id="15acc-103">Simulated cross-premises virtual network in a Microsoft 365 test environment</span></span>

<span data-ttu-id="15acc-104">*Den här testlabbguiden kan användas i både Microsoft 365 Enterprise- och Office 365 Enterprise-testmiljöer.*</span><span class="sxs-lookup"><span data-stu-id="15acc-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="15acc-105">I den här artikeln beskrivs hur du använder Microsoft Azure för att skapa en simulerad, hybridbaserad molnmiljö med två virtuella Azure-nätverk.</span><span class="sxs-lookup"><span data-stu-id="15acc-105">This article steps you through creating a simulated hybrid cloud environment with Microsoft Azure using two Azure virtual networks.</span></span> <span data-ttu-id="15acc-106">Här är konfigurationsresultatet.</span><span class="sxs-lookup"><span data-stu-id="15acc-106">Here is the resulting configuration.</span></span> 
  
![Fas 3 av den simulerade testmiljön med ett virtuellt nätverk för flera platser, där den virtuella DC2-datorn finns i XPrem VNet](../media/simulated-cross-premises-microsoft-365-enterprise/df458c56-022b-4688-ab18-056c3fd776b4.png)
  
<span data-ttu-id="15acc-108">Den simulerar en hybridbaserad Azure Iaas-produktionsmiljö i molnet och består av:</span><span class="sxs-lookup"><span data-stu-id="15acc-108">This simulates an Azure IaaS hybrid cloud production environment and consists of:</span></span>
  
- <span data-ttu-id="15acc-109">Ett simulerat och förenklat lokalt nätverk som finns i ett virtuellt Azure-nätverk (det virtuella TestLab-nätverket).</span><span class="sxs-lookup"><span data-stu-id="15acc-109">A simulated and simplified on-premises network hosted in an Azure virtual network (the TestLab virtual network).</span></span>
    
- <span data-ttu-id="15acc-110">Ett simulerat, virtuellt nätverk för flera platser som lagras i Azure (XPrem).</span><span class="sxs-lookup"><span data-stu-id="15acc-110">A simulated cross-premises virtual network hosted in Azure (XPrem).</span></span>
    
- <span data-ttu-id="15acc-111">Ett virtuellt nätverk för peeringrelation mellan de två virtuella nätverken.</span><span class="sxs-lookup"><span data-stu-id="15acc-111">A VNet peering relationship between the two virtual networks.</span></span>
    
- <span data-ttu-id="15acc-112">En sekundär domänkontrollant i det virtuella XPrem-nätverket.</span><span class="sxs-lookup"><span data-stu-id="15acc-112">A secondary domain controller in the XPrem virtual network.</span></span>
    
<span data-ttu-id="15acc-113">På så sätt får du en grund och en gemensam utgångspunkt från vilken du kan göra följande:</span><span class="sxs-lookup"><span data-stu-id="15acc-113">This provides a basis and common starting point from which you can:</span></span> 
  
- <span data-ttu-id="15acc-114">Utveckla och testa programmen i en simulerad, hybridbaserad Azure IaaS-molnmiljö.</span><span class="sxs-lookup"><span data-stu-id="15acc-114">Develop and test applications in a simulated Azure IaaS hybrid cloud environment.</span></span>
    
- <span data-ttu-id="15acc-115">Skapa testkonfigurationer med datorer, där vissa ingår i det virtuella TestLab-nätverket och vissa i det virtuella XPrem-nätverket, för att simulera hybrid- och molnbaserade IT-arbetsbelastningar.</span><span class="sxs-lookup"><span data-stu-id="15acc-115">Create test configurations of computers, some within the TestLab virtual network and some within the XPrem virtual network, to simulate hybrid cloud-based IT workloads.</span></span>
    
<span data-ttu-id="15acc-116">Konfigurationen av testmiljön består av tre huvudfaser:</span><span class="sxs-lookup"><span data-stu-id="15acc-116">There are three major phases to setting up this test environment:</span></span>
  
1. <span data-ttu-id="15acc-117">Konfigurera det virtuella TestLab-nätverket.</span><span class="sxs-lookup"><span data-stu-id="15acc-117">Configure the TestLab virtual network.</span></span>
    
2. <span data-ttu-id="15acc-118">Skapa det virtuella nätverket på flera platser.</span><span class="sxs-lookup"><span data-stu-id="15acc-118">Create the cross-premises virtual network.</span></span>
    
3. <span data-ttu-id="15acc-119">Konfigurera DC2.</span><span class="sxs-lookup"><span data-stu-id="15acc-119">Configure DC2.</span></span>
    
> [!NOTE]
> <span data-ttu-id="15acc-120">Konfigurationen kräver en betald Azure-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="15acc-120">This configuration requires a paid Azure subscription.</span></span> 

<span data-ttu-id="15acc-121">Du kan använda den resulterande miljön för att testa funktionerna och funktionaliteten i [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise) med ytterligare [testlabbguider](m365-enterprise-test-lab-guides.md) eller på egen hand.</span><span class="sxs-lookup"><span data-stu-id="15acc-121">You can use the resulting environment to test the features and functionality of [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise) with additional [Test Lab Guides](m365-enterprise-test-lab-guides.md) or on your own.</span></span>

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="15acc-123">Klicka [här](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) om du vill se en översikt över alla artiklar i samlingen med Microsoft 365 Enterprise-testlabbguider.</span><span class="sxs-lookup"><span data-stu-id="15acc-123">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-configure-the-testlab-virtual-network"></a><span data-ttu-id="15acc-124">Fas 1: Konfigurera det virtuella TestLab-nätverket.</span><span class="sxs-lookup"><span data-stu-id="15acc-124">Phase 1: Configure the TestLab virtual network</span></span>

<span data-ttu-id="15acc-125">Använd anvisningarna i **Fas 1** av [baskonfigurationen för det simulerade företaget](simulated-ent-base-configuration-microsoft-365-enterprise.md) för att konfigurera DC1-, APP1-och KLIENT1-datorerna i det virtuella Azure-nätverket med namnet TestLab.</span><span class="sxs-lookup"><span data-stu-id="15acc-125">Use the instructions in **Phase 1** of the [simulated enterprise base configuration](simulated-ent-base-configuration-microsoft-365-enterprise.md) to configure the DC1, APP1, and CLIENT1 computers in the Azure virtual network named TestLab.</span></span>
  
<span data-ttu-id="15acc-126">Det här är den aktuella konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="15acc-126">This is your current configuration.</span></span> 
  
![Baskonfiguration för simulerat företag i Azure](../media/simulated-cross-premises-microsoft-365-enterprise/25a010a6-c870-4690-b8f3-84421f8bc5c7.png)
  
## <a name="phase-2-create-the-xprem-virtual-network"></a><span data-ttu-id="15acc-128">Steg 2: Skapa det virtuella XPrem-nätverket</span><span class="sxs-lookup"><span data-stu-id="15acc-128">Phase 2: Create the XPrem virtual network</span></span>

<span data-ttu-id="15acc-129">I den här fasen skapar och konfigurerar du det nya virtuella XPrem-nätverket och ansluter det sedan till det virtuella TestLab-nätverket med VNet-peering.</span><span class="sxs-lookup"><span data-stu-id="15acc-129">In this phase, you create and configure the new XPrem virtual network and then connect it to the TestLab virtual network with VNet peering.</span></span>
  
<span data-ttu-id="15acc-130">Starta först en Azure PowerShell-kommandotolk på din lokala dator.</span><span class="sxs-lookup"><span data-stu-id="15acc-130">First, start an Azure PowerShell prompt on your local computer.</span></span>
  
> [!NOTE]
> <span data-ttu-id="15acc-131">Följande kommandouppsättningar använder den senaste versionen av Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="15acc-131">The following command sets use the latest version of Azure PowerShell.</span></span> <span data-ttu-id="15acc-132">Se [Kom igång med Azure PowerShell-cmdletar](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/).</span><span class="sxs-lookup"><span data-stu-id="15acc-132">See [Get started with Azure PowerShell cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/).</span></span> 
  
<span data-ttu-id="15acc-133">Logga in på ditt Azure-konto med det här kommandot.</span><span class="sxs-lookup"><span data-stu-id="15acc-133">Sign in to your Azure account with this command.</span></span>
  
```powershell
Connect-AzAccount
```

<span data-ttu-id="15acc-134">Hämta ditt prenumerationsnamn med det här kommandot.</span><span class="sxs-lookup"><span data-stu-id="15acc-134">Get your subscription name using this command.</span></span>
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

<span data-ttu-id="15acc-135">Ange din Azure-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="15acc-135">Set your Azure subscription.</span></span> <span data-ttu-id="15acc-136">Ersätt allt inom citattecknen, inklusive tecknen \< och >, med de rätta namnen.</span><span class="sxs-lookup"><span data-stu-id="15acc-136">Replace everything within the quotes, including the \< and > characters, with the correct names.</span></span>
  
```powershell
$subscrName="<subscription name>"
Select-AzSubscription -SubscriptionName $subscrName
```

<span data-ttu-id="15acc-137">Skapa sedan det virtuella XPrem-nätverket och skydda det med en nätverkssäkerhetsgrupp med dessa kommandon.</span><span class="sxs-lookup"><span data-stu-id="15acc-137">Next, create the XPrem virtual network and protect it with a network security group with these commands.</span></span>
  
```powershell
$rgName="<name of the resource group that you used for your TestLab virtual network>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$Testnet=New-AzVirtualNetworkSubnetConfig -Name "Testnet" -AddressPrefix 192.168.0.0/24
New-AzVirtualNetwork -Name "XPrem" -ResourceGroupName $rgName -Location $locName -AddressPrefix 192.168.0.0/16 -Subnet $Testnet -DNSServer 10.0.0.4
$rule1=New-AzNetworkSecurityRuleConfig -Name "RDPTraffic" -Description "Allow RDP to all VMs on the subnet" -Access Allow -Protocol Tcp -Direction Inbound -Priority 100 -SourceAddressPrefix Internet -SourcePortRange * -DestinationAddressPrefix * -DestinationPortRange 3389
New-AzNetworkSecurityGroup -Name "Testnet" -ResourceGroupName $rgName -Location $locName -SecurityRules $rule1
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name XPrem
$nsg=Get-AzNetworkSecurityGroup -Name "Testnet" -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name "Testnet" -AddressPrefix 192.168.0.0/24 -NetworkSecurityGroup $nsg
$vnet | Set-AzVirtualNetwork
```

<span data-ttu-id="15acc-138">Nästa steg är att skapa ett virtuellt nätverk för peeringrelation mellan de virtuella TestLab- och XPrem-nätverken med dessa kommandon.</span><span class="sxs-lookup"><span data-stu-id="15acc-138">Next, you create the VNet peering relationship between the TestLab and XPrem VNets with these commands.</span></span>
  
```powershell
$rgName="<name of the resource group that you used for your TestLab virtual network>"
$vnet1=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name TestLab
$vnet2=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name XPrem
Add-AzVirtualNetworkPeering -Name TestLab2XPrem -VirtualNetwork $vnet1 -RemoteVirtualNetworkId $vnet2.Id
Add-AzVirtualNetworkPeering -Name XPrem2TestLab -VirtualNetwork $vnet2 -RemoteVirtualNetworkId $vnet1.Id
```

<span data-ttu-id="15acc-139">Det här är den aktuella konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="15acc-139">This is your current configuration.</span></span> 
  
![Fas 2 av den simulerade testmiljön med ett virtuellt nätverk för flera platser, med det virtuella XPrem-nätverket och det virtuella nätverket för peeringrelation](../media/simulated-cross-premises-microsoft-365-enterprise/cac5e999-69c7-4f4c-bfce-a7f4006115ef.png)
  
## <a name="phase-3-configure-dc2"></a><span data-ttu-id="15acc-141">Fas 3: Konfigurera DC2</span><span class="sxs-lookup"><span data-stu-id="15acc-141">Phase 3: Configure DC2</span></span>

<span data-ttu-id="15acc-142">I den här fasen skapar du den virtuella DC2-datorn i det virtuella XPrem-nätverket och konfigurerar den sedan som en replikeringsdomänkontrollant.</span><span class="sxs-lookup"><span data-stu-id="15acc-142">In this phase, you create the DC2 virtual machine in the XPrem virtual network and then configure it as a replica domain controller.</span></span>
  
<span data-ttu-id="15acc-143">Börja med att skapa en virtuell dator för DC2.</span><span class="sxs-lookup"><span data-stu-id="15acc-143">First, create a virtual machine for DC2.</span></span> <span data-ttu-id="15acc-144">Kör dessa kommandon i Azure PowerShell-kommandotolken på din lokala dator.</span><span class="sxs-lookup"><span data-stu-id="15acc-144">Run these commands at the Azure PowerShell command prompt on your local computer.</span></span>
  
```powershell
$rgName="<your resource group name>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name XPrem -ResourceGroupName $rgName
$pip=New-AzPublicIpAddress -Name DC2-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name DC2-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id -PrivateIpAddress 192.168.0.4
$vm=New-AzVMConfig -VMName DC2 -VMSize Standard_A2_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for DC2."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName DC2 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "DC2-OS" -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType "Standard_LRS"
$diskConfig=New-AzDiskConfig -AccountType "Standard_LRS" -Location $locName -CreateOption Empty -DiskSizeGB 20
$dataDisk1=New-AzDisk -DiskName "DC2-DataDisk1" -Disk $diskConfig -ResourceGroupName $rgName
$vm=Add-AzVMDataDisk -VM $vm -Name "DC2-DataDisk1" -CreateOption Attach -ManagedDiskId $dataDisk1.Id -Lun 1
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

<span data-ttu-id="15acc-145">Anslut sedan till den nya, virtuella DC2-datorn från [Azure-portalen](https://portal.azure.com) med hjälp av den lokala administratörens kontonamn och lösenord.</span><span class="sxs-lookup"><span data-stu-id="15acc-145">Next, connect to the new DC2 virtual machine from the [Azure portal](https://portal.azure.com) using its local administrator account name and password.</span></span>
  
<span data-ttu-id="15acc-146">Därefter konfigurerar du en Windows-brandväggsregel för att tillåta trafik för grundläggande anslutningstester.</span><span class="sxs-lookup"><span data-stu-id="15acc-146">Next, configure a Windows Firewall rule to allow traffic for basic connectivity testing.</span></span> <span data-ttu-id="15acc-147">Kör de här kommandona i en Windows PowerShell-kommandotolk på DC2 på administratörsnivå.</span><span class="sxs-lookup"><span data-stu-id="15acc-147">From an administrator-level Windows PowerShell command prompt on DC2, run these commands.</span></span> 
  
```powershell
Set-NetFirewallRule -DisplayName "File and Printer Sharing (Echo Request - ICMPv4-In)" -enabled True
ping dc1.corp.contoso.com
```

<span data-ttu-id="15acc-148">Ping-kommandot ska resultera i fyra lyckade svar från IP-adressen 10.0.0.4.</span><span class="sxs-lookup"><span data-stu-id="15acc-148">The ping command should result in four successful replies from IP address 10.0.0.4.</span></span> <span data-ttu-id="15acc-149">Det här är ett test av trafiken i det virtuella nätverket för peeringrelation.</span><span class="sxs-lookup"><span data-stu-id="15acc-149">This is a test of traffic across the VNet peering relationship.</span></span> 
  
<span data-ttu-id="15acc-150">Lägg sedan till den extra datadisken som en ny volym med enhetsbokstaven F: med det här kommandot i Windows PowerShell-kommandotolken på DC2.</span><span class="sxs-lookup"><span data-stu-id="15acc-150">Next, add the extra data disk as a new volume with the drive letter F: with this command from the Windows PowerShell command prompt on DC2.</span></span>
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

<span data-ttu-id="15acc-151">Därefter konfigurerar du DC2 som en replikeringsdomänkontrollant för domänen corp.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="15acc-151">Next, configure DC2 as a replica domain controller for the corp.contoso.com domain.</span></span> <span data-ttu-id="15acc-152">Kör de här kommandona i Windows PowerShell-kommandotolken på DC2.</span><span class="sxs-lookup"><span data-stu-id="15acc-152">Run these commands from the Windows PowerShell command prompt on DC2.</span></span>
  
```powershell
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSDomainController -Credential (Get-Credential CORP\User1) -DomainName "corp.contoso.com" -InstallDns:$true -DatabasePath "F:\NTDS" -LogPath "F:\Logs" -SysvolPath "F:\SYSVOL"
```

<span data-ttu-id="15acc-153">Observera att du uppmanas att ange både lösenordet CORP\\User1 och ett lösenord för återställningsläge för katalogtjänster, och att starta om DC2.</span><span class="sxs-lookup"><span data-stu-id="15acc-153">Note that you are prompted to supply both the CORP\\User1 password and a Directory Services Restore Mode (DSRM) password, and to restart DC2.</span></span> 
  
<span data-ttu-id="15acc-154">När det virtuella XPrem-nätverket nu har en egen DNS-server (DC2) måste du konfigurera det virtuella XPrem-nätverket så att det använder DNS-servern.</span><span class="sxs-lookup"><span data-stu-id="15acc-154">Now that the XPrem virtual network has its own DNS server (DC2), you must configure the XPrem virtual network to use this DNS server.</span></span> <span data-ttu-id="15acc-155">Kör dessa kommandon i Azure PowerShell-kommandotolken på din lokala dator.</span><span class="sxs-lookup"><span data-stu-id="15acc-155">Run these commands from the Azure PowerShell command prompt on your local computer.</span></span>
  
```powershell
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -name "XPrem"
$vnet.DhcpOptions.DnsServers="192.168.0.4" 
Set-AzVirtualNetwork -VirtualNetwork $vnet
Restart-AzVM -ResourceGroupName $rgName -Name "DC2"
```

<span data-ttu-id="15acc-156">Från Azure-portalen på din lokala dator ansluter du till DC1 med autentiseringsuppgifterna CORP\\User1.</span><span class="sxs-lookup"><span data-stu-id="15acc-156">From the Azure portal on your local computer, connect to DC1 with the CORP\\User1 credentials.</span></span> <span data-ttu-id="15acc-157">Om du vill konfigurera CORP-domänen så att datorerna och användarna använder den lokala domänkontrollanten för autentisering kör du dessa kommandon från en Windows PowerShell-kommandotolk på administratörsnivå på DC1.</span><span class="sxs-lookup"><span data-stu-id="15acc-157">To configure the CORP domain so that computers and users use their local domain controller for authentication, run these commands from an administrator-level Windows PowerShell command prompt on DC1.</span></span>
  
```powershell
New-ADReplicationSite -Name "TestLab" 
New-ADReplicationSite -Name "XPrem"
New-ADReplicationSubnet -Name "10.0.0.0/8" -Site "TestLab"
New-ADReplicationSubnet -Name "192.168.0.0/16" -Site "XPrem"
```

<span data-ttu-id="15acc-158">Det här är den aktuella konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="15acc-158">This is your current configuration.</span></span> 
  
![Fas 3 av den simulerade testmiljön med ett virtuellt nätverk för flera platser, där den virtuella DC2-datorn finns i XPrem VNet](../media/simulated-cross-premises-microsoft-365-enterprise/df458c56-022b-4688-ab18-056c3fd776b4.png)
  
<span data-ttu-id="15acc-160">Din simulerade Azure-hybridmolnmiljö är nu redo att testas.</span><span class="sxs-lookup"><span data-stu-id="15acc-160">Your simulated Azure hybrid cloud environment is now ready for testing.</span></span>
  
<span data-ttu-id="15acc-161">Nu är du redo att experimentera med fler funktioner i [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span><span class="sxs-lookup"><span data-stu-id="15acc-161">You are now ready to experiment with additional features of [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="15acc-162">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="15acc-162">Next steps</span></span>

<span data-ttu-id="15acc-163">Utforska dessa ytterligare uppsättningar testlabbguider:</span><span class="sxs-lookup"><span data-stu-id="15acc-163">Explore these additional sets of Test Lab Guides:</span></span>
  
- [<span data-ttu-id="15acc-164">Identitet</span><span class="sxs-lookup"><span data-stu-id="15acc-164">Identity</span></span>](m365-enterprise-test-lab-guides.md#identity)
- [<span data-ttu-id="15acc-165">Hantering av mobila enheter</span><span class="sxs-lookup"><span data-stu-id="15acc-165">Mobile device management</span></span>](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [<span data-ttu-id="15acc-166">Informationsskydd</span><span class="sxs-lookup"><span data-stu-id="15acc-166">Information protection</span></span>](m365-enterprise-test-lab-guides.md#information-protection)

## <a name="see-also"></a><span data-ttu-id="15acc-167">Snabbreferens</span><span class="sxs-lookup"><span data-stu-id="15acc-167">See also</span></span>

[<span data-ttu-id="15acc-168">Testlabbguider för Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="15acc-168">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="15acc-169">Distribuera Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="15acc-169">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="15acc-170">Microsoft 365 Enterprise-dokumentation</span><span class="sxs-lookup"><span data-stu-id="15acc-170">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)