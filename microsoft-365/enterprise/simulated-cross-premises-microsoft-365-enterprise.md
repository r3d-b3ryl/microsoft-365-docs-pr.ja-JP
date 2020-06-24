---
title: Microsoft 365 テスト環境でのシミュレートされたクロスプレミスの仮想ネットワーク
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
ms.custom: seo-marvel-apr2020
description: '概要: Microsoft 365 テスト環境として、シミュレートされたクロスプレミスの仮想ネットワークを Microsoft Azure に作成します。'
ms.openlocfilehash: 6a9eb7377ff7ce3aa5b251d345e57ae2a25ba926
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817073"
---
# <a name="simulated-cross-premises-virtual-network-in-a-microsoft-365-test-environment"></a><span data-ttu-id="2b9c9-103">Microsoft 365 テスト環境でのシミュレートされたクロスプレミスの仮想ネットワーク</span><span class="sxs-lookup"><span data-stu-id="2b9c9-103">Simulated cross-premises virtual network in a Microsoft 365 test environment</span></span>

<span data-ttu-id="2b9c9-104">*このテストラボ ガイドは、Microsoft 365 Enterprise および Office 365 Enterprise テスト環境に使用できます。*</span><span class="sxs-lookup"><span data-stu-id="2b9c9-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="2b9c9-105">This article steps you through creating a simulated hybrid cloud environment with Microsoft Azure using two Azure virtual networks.</span><span class="sxs-lookup"><span data-stu-id="2b9c9-105">This article steps you through creating a simulated hybrid cloud environment with Microsoft Azure using two Azure virtual networks.</span></span> <span data-ttu-id="2b9c9-106">Here is the resulting configuration.</span><span class="sxs-lookup"><span data-stu-id="2b9c9-106">Here is the resulting configuration.</span></span> 
  
![XPrem VNet の DC2 仮想マシンを使用した、シミュレートされたクロスプレミス仮想ネットワーク テスト環境のフェーズ 3](../media/simulated-cross-premises-microsoft-365-enterprise/df458c56-022b-4688-ab18-056c3fd776b4.png)
  
<span data-ttu-id="2b9c9-108">これは Azure IaaS ハイブリッド クラウド運用環境をシミュレートするもので、次のもので構成されます。</span><span class="sxs-lookup"><span data-stu-id="2b9c9-108">This simulates an Azure IaaS hybrid cloud production environment and consists of:</span></span>
  
- <span data-ttu-id="2b9c9-109">Azure 仮想ネットワークでホストされる、シミュレートおよび単純化されたオンプレミス ネットワーク (TestLab 仮想ネットワーク)。</span><span class="sxs-lookup"><span data-stu-id="2b9c9-109">A simulated and simplified on-premises network hosted in an Azure virtual network (the TestLab virtual network).</span></span>
    
- <span data-ttu-id="2b9c9-110">Azure でホストされる、シミュレートされたクロスプレミスの仮想ネットワーク (XPrem)。</span><span class="sxs-lookup"><span data-stu-id="2b9c9-110">A simulated cross-premises virtual network hosted in Azure (XPrem).</span></span>
    
- <span data-ttu-id="2b9c9-111">2 つの仮想ネットワーク間の VNet ピアリング関係。</span><span class="sxs-lookup"><span data-stu-id="2b9c9-111">A VNet peering relationship between the two virtual networks.</span></span>
    
- <span data-ttu-id="2b9c9-112">XPrem 仮想ネットワークのセカンダリ ドメイン コントローラー。</span><span class="sxs-lookup"><span data-stu-id="2b9c9-112">A secondary domain controller in the XPrem virtual network.</span></span>
    
<span data-ttu-id="2b9c9-113">これは次のことを行うための基礎および共通の開始点となります。</span><span class="sxs-lookup"><span data-stu-id="2b9c9-113">This provides a basis and common starting point from which you can:</span></span> 
  
- <span data-ttu-id="2b9c9-114">シミュレートされた Azure IaaS ハイブリッド クラウド環境におけるアプリケーションの開発およびテスト。</span><span class="sxs-lookup"><span data-stu-id="2b9c9-114">Develop and test applications in a simulated Azure IaaS hybrid cloud environment.</span></span>
    
- <span data-ttu-id="2b9c9-115">ハイブリッド クラウドベース IT ワークロードをシミュレートするための、コンピューターのテスト構成の作成 (TestLab 仮想ネットワーク内、および XPrem 仮想ネットワーク内)。</span><span class="sxs-lookup"><span data-stu-id="2b9c9-115">Create test configurations of computers, some within the TestLab virtual network and some within the XPrem virtual network, to simulate hybrid cloud-based IT workloads.</span></span>
    
<span data-ttu-id="2b9c9-116">このテスト環境のセットアップには、3 つの主要なフェーズが存在します。</span><span class="sxs-lookup"><span data-stu-id="2b9c9-116">There are three major phases to setting up this test environment:</span></span>
  
1. <span data-ttu-id="2b9c9-117">TestLab 仮想ネットワークを構成します。</span><span class="sxs-lookup"><span data-stu-id="2b9c9-117">Configure the TestLab virtual network.</span></span>
    
2. <span data-ttu-id="2b9c9-118">クロスプレミスの仮想ネットワークを作成します。</span><span class="sxs-lookup"><span data-stu-id="2b9c9-118">Create the cross-premises virtual network.</span></span>
    
3. <span data-ttu-id="2b9c9-119">DC2 を構成します。</span><span class="sxs-lookup"><span data-stu-id="2b9c9-119">Configure DC2.</span></span>
    
> [!NOTE]
> <span data-ttu-id="2b9c9-120">この構成では、有料版の Azure サブスクリプションが必要です。</span><span class="sxs-lookup"><span data-stu-id="2b9c9-120">This configuration requires a paid Azure subscription.</span></span> 

<span data-ttu-id="2b9c9-121">完成した環境は、その他の [テスト ラボ ガイド](m365-enterprise-test-lab-guides.md)や各自の実験で、[Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise) の機能をテストするために使用できます。</span><span class="sxs-lookup"><span data-stu-id="2b9c9-121">You can use the resulting environment to test the features and functionality of [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise) with additional [Test Lab Guides](m365-enterprise-test-lab-guides.md) or on your own.</span></span>

![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="2b9c9-123">Microsoft 365 Enterprise テスト ラボガイド内のすべての記事への視覚的なマップについては、[Microsoft 365 Enterprise テスト ラボガイド スタック](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)に移動して探します。</span><span class="sxs-lookup"><span data-stu-id="2b9c9-123">Go to [Microsoft 365 Enterprise Test Lab Guide Stack](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-configure-the-testlab-virtual-network"></a><span data-ttu-id="2b9c9-124">フェーズ 1: TestLab 仮想ネットワークを構成する</span><span class="sxs-lookup"><span data-stu-id="2b9c9-124">Phase 1: Configure the TestLab virtual network</span></span>

<span data-ttu-id="2b9c9-125">[シミュレートされたエンタープライズ基本構成](simulated-ent-base-configuration-microsoft-365-enterprise.md)の**フェーズ 1** の手順により、TestLab という名前の Azure 仮想ネットワークに DC1、APP1、CLIENT1 コンピューターを構成します。</span><span class="sxs-lookup"><span data-stu-id="2b9c9-125">Use the instructions in **Phase 1** of the [simulated enterprise base configuration](simulated-ent-base-configuration-microsoft-365-enterprise.md) to configure the DC1, APP1, and CLIENT1 computers in the Azure virtual network named TestLab.</span></span>
  
<span data-ttu-id="2b9c9-126">こちらが現在の構成です。</span><span class="sxs-lookup"><span data-stu-id="2b9c9-126">This is your current configuration.</span></span> 
  
![Azure のシミュレートされたエンタープライズ基本構成](../media/simulated-cross-premises-microsoft-365-enterprise/25a010a6-c870-4690-b8f3-84421f8bc5c7.png)
  
## <a name="phase-2-create-the-xprem-virtual-network"></a><span data-ttu-id="2b9c9-128">フェーズ 2: XPrem 仮想ネットワークを作成する</span><span class="sxs-lookup"><span data-stu-id="2b9c9-128">Phase 2: Create the XPrem virtual network</span></span>

<span data-ttu-id="2b9c9-129">このフェーズでは、新しい XPrem 仮想ネットワークを作成および構成し、それを VNet ピアリングで TestLab 仮想ネットワークに接続します。</span><span class="sxs-lookup"><span data-stu-id="2b9c9-129">In this phase, you create and configure the new XPrem virtual network and then connect it to the TestLab virtual network with VNet peering.</span></span>
  
<span data-ttu-id="2b9c9-130">最初に、ローカル コンピューターで Azure PowerShell プロンプトを起動します。</span><span class="sxs-lookup"><span data-stu-id="2b9c9-130">First, start an Azure PowerShell prompt on your local computer.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2b9c9-131">The following command sets use the latest version of Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2b9c9-131">The following command sets use the latest version of Azure PowerShell.</span></span> <span data-ttu-id="2b9c9-132">See [Get started with Azure PowerShell cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/).</span><span class="sxs-lookup"><span data-stu-id="2b9c9-132">See [Get started with Azure PowerShell cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/).</span></span> 
  
<span data-ttu-id="2b9c9-133">このコマンドを使用して Azure アカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="2b9c9-133">Sign in to your Azure account with this command.</span></span>
  
```powershell
Connect-AzAccount
```

<span data-ttu-id="2b9c9-134">このコマンドを使用して、サブスクリプションの名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="2b9c9-134">Get your subscription name using this command.</span></span>
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

<span data-ttu-id="2b9c9-135">Set your Azure subscription.</span><span class="sxs-lookup"><span data-stu-id="2b9c9-135">Set your Azure subscription.</span></span> <span data-ttu-id="2b9c9-136">Replace everything within the quotes, including the \< and > characters, with the correct names.</span><span class="sxs-lookup"><span data-stu-id="2b9c9-136">Replace everything within the quotes, including the \< and > characters, with the correct names.</span></span>
  
```powershell
$subscrName="<subscription name>"
Select-AzSubscription -SubscriptionName $subscrName
```

<span data-ttu-id="2b9c9-137">次に、これらのコマンドを使用して、XPrem 仮想ネットワークを作成し、ネットワーク セキュリティ グループで保護します。</span><span class="sxs-lookup"><span data-stu-id="2b9c9-137">Next, create the XPrem virtual network and protect it with a network security group with these commands.</span></span>
  
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

<span data-ttu-id="2b9c9-138">次に、これらのコマンドを使用して、TestLab と XPrem VNet 間の VNet ピアリング関係を作成します。</span><span class="sxs-lookup"><span data-stu-id="2b9c9-138">Next, you create the VNet peering relationship between the TestLab and XPrem VNets with these commands.</span></span>
  
```powershell
$rgName="<name of the resource group that you used for your TestLab virtual network>"
$vnet1=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name TestLab
$vnet2=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name XPrem
Add-AzVirtualNetworkPeering -Name TestLab2XPrem -VirtualNetwork $vnet1 -RemoteVirtualNetworkId $vnet2.Id
Add-AzVirtualNetworkPeering -Name XPrem2TestLab -VirtualNetwork $vnet2 -RemoteVirtualNetworkId $vnet1.Id
```

<span data-ttu-id="2b9c9-139">こちらが現在の構成です。</span><span class="sxs-lookup"><span data-stu-id="2b9c9-139">This is your current configuration.</span></span> 
  
![XPrem VNet および VNet ピアリング関係を使用した、シミュレートされたクロスプレミス仮想ネットワーク テスト環境のフェーズ 2](../media/simulated-cross-premises-microsoft-365-enterprise/cac5e999-69c7-4f4c-bfce-a7f4006115ef.png)
  
## <a name="phase-3-configure-dc2"></a><span data-ttu-id="2b9c9-141">フェーズ 3: DC2 を構成する</span><span class="sxs-lookup"><span data-stu-id="2b9c9-141">Phase 3: Configure DC2</span></span>

<span data-ttu-id="2b9c9-142">このフェーズでは、XPrem 仮想ネットワークにおいて DC2 仮想マシンを作成し、それをレプリカ ドメイン コントローラーとして構成します。</span><span class="sxs-lookup"><span data-stu-id="2b9c9-142">In this phase, you create the DC2 virtual machine in the XPrem virtual network and then configure it as a replica domain controller.</span></span>
  
<span data-ttu-id="2b9c9-143">First, create a virtual machine for DC2.</span><span class="sxs-lookup"><span data-stu-id="2b9c9-143">First, create a virtual machine for DC2.</span></span> <span data-ttu-id="2b9c9-144">Run these commands at the Azure PowerShell command prompt on your local computer.</span><span class="sxs-lookup"><span data-stu-id="2b9c9-144">Run these commands at the Azure PowerShell command prompt on your local computer.</span></span>
  
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

<span data-ttu-id="2b9c9-145">次に、ローカル管理者のアカウント名とパスワードを使用して、[Azure portal](https://portal.azure.com) から新しい DC2 仮想マシンに接続します。</span><span class="sxs-lookup"><span data-stu-id="2b9c9-145">Next, connect to the new DC2 virtual machine from the [Azure portal](https://portal.azure.com) using its local administrator account name and password.</span></span>
  
<span data-ttu-id="2b9c9-146">Next, configure a Windows Firewall rule to allow traffic for basic connectivity testing.</span><span class="sxs-lookup"><span data-stu-id="2b9c9-146">Next, configure a Windows Firewall rule to allow traffic for basic connectivity testing.</span></span> <span data-ttu-id="2b9c9-147">From an administrator-level Windows PowerShell command prompt on DC2, run these commands.</span><span class="sxs-lookup"><span data-stu-id="2b9c9-147">From an administrator-level Windows PowerShell command prompt on DC2, run these commands.</span></span> 
  
```powershell
Set-NetFirewallRule -DisplayName "File and Printer Sharing (Echo Request - ICMPv4-In)" -enabled True
ping dc1.corp.contoso.com
```

<span data-ttu-id="2b9c9-148">The ping command should result in four successful replies from IP address 10.0.0.4.</span><span class="sxs-lookup"><span data-stu-id="2b9c9-148">The ping command should result in four successful replies from IP address 10.0.0.4.</span></span> <span data-ttu-id="2b9c9-149">This is a test of traffic across the VNet peering relationship.</span><span class="sxs-lookup"><span data-stu-id="2b9c9-149">This is a test of traffic across the VNet peering relationship.</span></span> 
  
<span data-ttu-id="2b9c9-150">次に、DC2 の Windows PowerShell コマンド プロンプトから次のコマンドを使用して、新しいボリュームとして別のデータ ディスクをドライブ文字 F: で追加します。</span><span class="sxs-lookup"><span data-stu-id="2b9c9-150">Next, add the extra data disk as a new volume with the drive letter F: with this command from the Windows PowerShell command prompt on DC2.</span></span>
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

<span data-ttu-id="2b9c9-151">Next, configure DC2 as a replica domain controller for the corp.contoso.com domain.</span><span class="sxs-lookup"><span data-stu-id="2b9c9-151">Next, configure DC2 as a replica domain controller for the corp.contoso.com domain.</span></span> <span data-ttu-id="2b9c9-152">Run these commands from the Windows PowerShell command prompt on DC2.</span><span class="sxs-lookup"><span data-stu-id="2b9c9-152">Run these commands from the Windows PowerShell command prompt on DC2.</span></span>
  
```powershell
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSDomainController -Credential (Get-Credential CORP\User1) -DomainName "corp.contoso.com" -InstallDns:$true -DatabasePath "F:\NTDS" -LogPath "F:\Logs" -SysvolPath "F:\SYSVOL"
```

<span data-ttu-id="2b9c9-153">CORP\\User1 パスワードおよびディレクトリ サービス復元モード (DSRM) パスワードの両方の入力、ならびに DC2 の再起動が必要となる点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="2b9c9-153">Note that you are prompted to supply both the CORP\\User1 password and a Directory Services Restore Mode (DSRM) password, and to restart DC2.</span></span> 
  
<span data-ttu-id="2b9c9-154">Now that the XPrem virtual network has its own DNS server (DC2), you must configure the XPrem virtual network to use this DNS server.</span><span class="sxs-lookup"><span data-stu-id="2b9c9-154">Now that the XPrem virtual network has its own DNS server (DC2), you must configure the XPrem virtual network to use this DNS server.</span></span> <span data-ttu-id="2b9c9-155">Run these commands from the Azure PowerShell command prompt on your local computer.</span><span class="sxs-lookup"><span data-stu-id="2b9c9-155">Run these commands from the Azure PowerShell command prompt on your local computer.</span></span>
  
```powershell
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -name "XPrem"
$vnet.DhcpOptions.DnsServers="192.168.0.4" 
Set-AzVirtualNetwork -VirtualNetwork $vnet
Restart-AzVM -ResourceGroupName $rgName -Name "DC2"
```

<span data-ttu-id="2b9c9-156">From the Azure portal on your local computer, connect to DC1 with the CORP\\User1 credentials.</span><span class="sxs-lookup"><span data-stu-id="2b9c9-156">From the Azure portal on your local computer, connect to DC1 with the CORP\\User1 credentials.</span></span> <span data-ttu-id="2b9c9-157">To configure the CORP domain so that computers and users use their local domain controller for authentication, run these commands from an administrator-level Windows PowerShell command prompt on DC1.</span><span class="sxs-lookup"><span data-stu-id="2b9c9-157">To configure the CORP domain so that computers and users use their local domain controller for authentication, run these commands from an administrator-level Windows PowerShell command prompt on DC1.</span></span>
  
```powershell
New-ADReplicationSite -Name "TestLab" 
New-ADReplicationSite -Name "XPrem"
New-ADReplicationSubnet -Name "10.0.0.0/8" -Site "TestLab"
New-ADReplicationSubnet -Name "192.168.0.0/16" -Site "XPrem"
```

<span data-ttu-id="2b9c9-158">こちらが現在の構成です。</span><span class="sxs-lookup"><span data-stu-id="2b9c9-158">This is your current configuration.</span></span> 
  
![XPrem VNet の DC2 仮想マシンを使用した、シミュレートされたクロスプレミス仮想ネットワーク テスト環境のフェーズ 3](../media/simulated-cross-premises-microsoft-365-enterprise/df458c56-022b-4688-ab18-056c3fd776b4.png)
  
<span data-ttu-id="2b9c9-160">シミュレートされた Azure ハイブリッド クラウド環境をテストする準備ができました。</span><span class="sxs-lookup"><span data-stu-id="2b9c9-160">Your simulated Azure hybrid cloud environment is now ready for testing.</span></span>
  
<span data-ttu-id="2b9c9-161">これで、[Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise) の追加機能を試せるようになりました。</span><span class="sxs-lookup"><span data-stu-id="2b9c9-161">You are now ready to experiment with additional features of [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="2b9c9-162">次の手順</span><span class="sxs-lookup"><span data-stu-id="2b9c9-162">Next steps</span></span>

<span data-ttu-id="2b9c9-163">こうした追加のテスト ラボ ガイドについて説明します。</span><span class="sxs-lookup"><span data-stu-id="2b9c9-163">Explore these additional sets of Test Lab Guides:</span></span>
  
- [<span data-ttu-id="2b9c9-164">ID</span><span class="sxs-lookup"><span data-stu-id="2b9c9-164">Identity</span></span>](m365-enterprise-test-lab-guides.md#identity)
- [<span data-ttu-id="2b9c9-165">モバイル デバイス管理</span><span class="sxs-lookup"><span data-stu-id="2b9c9-165">Mobile device management</span></span>](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [<span data-ttu-id="2b9c9-166">情報保護</span><span class="sxs-lookup"><span data-stu-id="2b9c9-166">Information protection</span></span>](m365-enterprise-test-lab-guides.md#information-protection)

## <a name="see-also"></a><span data-ttu-id="2b9c9-167">関連項目</span><span class="sxs-lookup"><span data-stu-id="2b9c9-167">See also</span></span>

[<span data-ttu-id="2b9c9-168">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="2b9c9-168">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="2b9c9-169">Microsoft 365 Enterprise を展開する</span><span class="sxs-lookup"><span data-stu-id="2b9c9-169">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="2b9c9-170">Microsoft 365 Enterprise のドキュメントとリソース</span><span class="sxs-lookup"><span data-stu-id="2b9c9-170">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
