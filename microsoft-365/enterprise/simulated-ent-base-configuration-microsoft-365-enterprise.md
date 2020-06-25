---
title: Microsoft 365 用のシミュレートされたエンタープライズ基本構成
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/21/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: 6f916a77-301c-4be2-b407-6cec4d80df76
description: このテスト ラボ ガイドを使用して、Microsoft 365 Enterprise 用にシミュレートされたエンタープライズ テスト環境を作成します。
ms.openlocfilehash: 486429bf9e1c0a88c9beb01a092f968256c1fa77
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818497"
---
# <a name="the-simulated-enterprise-base-configuration"></a><span data-ttu-id="884eb-103">シミュレートされたエンタープライズ基本構成</span><span class="sxs-lookup"><span data-stu-id="884eb-103">The simulated enterprise base configuration</span></span>

<span data-ttu-id="884eb-104">*このテストラボ ガイドは、Microsoft 365 Enterprise および Office 365 Enterprise テスト環境に使用できます。*</span><span class="sxs-lookup"><span data-stu-id="884eb-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="884eb-105">この記事では、次のものを含む Microsoft 365 Enterprise のシンプルな環境を作成するための詳しい手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="884eb-105">This article provides you with step-by-step instructions to create a simplified environment for Microsoft 365 Enterprise that includes:</span></span>

- <span data-ttu-id="884eb-106">Microsoft 365 E5 の試用版または有料サブスクリプション。</span><span class="sxs-lookup"><span data-stu-id="884eb-106">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="884eb-107">インターネットに接続している組織の簡易型イントラネット。Azure 仮想ネットワーク上に配置された 3 つの仮想マシン (DC1、APP1、および CLIENT1) で構成されます。</span><span class="sxs-lookup"><span data-stu-id="884eb-107">A simplified organization intranet connected to the Internet, consisting of three virtual machines on an Azure virtual network (DC1, APP1, and CLIENT1).</span></span>
 
![シミュレートされたエンタープライズ基本構成](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase4.png)

<span data-ttu-id="884eb-109">完成した環境は、その他の [テスト ラボ ガイド](m365-enterprise-test-lab-guides.md)や各自の実験で、[Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise) の機能をテストするために使用できます。</span><span class="sxs-lookup"><span data-stu-id="884eb-109">You can use the resulting environment to test the features and functionality of [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise) with additional [Test Lab Guides](m365-enterprise-test-lab-guides.md) or on your own.</span></span>

![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="884eb-111">Microsoft 365 Enterprise のテスト ラボ ガイド スタック内のすべての記事のビジュアル マップについては、[Microsoft 365 Enterprise のテスト ラボ ガイド スタック](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="884eb-111">Go to [Microsoft 365 Enterprise Test Lab Guide Stack](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-create-a-simulated-intranet"></a><span data-ttu-id="884eb-112">フェーズ 1: シミュレートされたイントラネットを作成する</span><span class="sxs-lookup"><span data-stu-id="884eb-112">Phase 1: Create a simulated intranet</span></span>

<span data-ttu-id="884eb-113">このフェーズでは、Active Directory Domain Services (AD DS) ドメイン コントローラー、アプリケーション サーバー、クライアント コンピューターを含むシミュレートされたイントラネットを Azure インフラストラクチャ サービスに作成します。</span><span class="sxs-lookup"><span data-stu-id="884eb-113">In this phase, you build a simulated intranet in Azure infrastructure services that includes an Active Directory Domain Services (AD DS) domain controller, an application server, and a client computer.</span></span> 

<span data-ttu-id="884eb-114">こうしたコンピューターは、他の [Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)でハイブリッド ID およびその他の機能の構成とデモンストレーションのために使用します。</span><span class="sxs-lookup"><span data-stu-id="884eb-114">You'll use these computers in additional [Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md) to configure and demonstrate hybrid identity and other capabilities.</span></span>

### <a name="method-1-build-your-simulated-intranet-with-an-azure-resource-manager-template"></a><span data-ttu-id="884eb-115">方法 1: Azure Resource Manager テンプレートを使用して、シミュレートされたイントラネットを構築する</span><span class="sxs-lookup"><span data-stu-id="884eb-115">Method 1: Build your simulated intranet with an Azure Resource Manager template</span></span>

<span data-ttu-id="884eb-116">In this method, you use an Azure Resource Manager (ARM) template to build out the simulated intranet.</span><span class="sxs-lookup"><span data-stu-id="884eb-116">In this method, you use an Azure Resource Manager (ARM) template to build out the simulated intranet.</span></span> <span data-ttu-id="884eb-117">ARM templates contain all of the instructions to create the Azure networking infrastructure, the virtual machines, and their configuration.</span><span class="sxs-lookup"><span data-stu-id="884eb-117">ARM templates contain all of the instructions to create the Azure networking infrastructure, the virtual machines, and their configuration.</span></span>

<span data-ttu-id="884eb-118">テンプレートを展開する前に「[テンプレートのReadme ページ](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems)」を確認し、次の情報をご用意ください。</span><span class="sxs-lookup"><span data-stu-id="884eb-118">Prior to deploying the template, read through the [template README page](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) and have the following information ready:</span></span>

- <span data-ttu-id="884eb-119">The public DNS domain name of your test environment (testlab.\<your public domain>).</span><span class="sxs-lookup"><span data-stu-id="884eb-119">The public DNS domain name of your test environment (testlab.\<your public domain>).</span></span> <span data-ttu-id="884eb-120">You'll need to enter this name in the **Domain Name field** of the **Custom deployment** page.</span><span class="sxs-lookup"><span data-stu-id="884eb-120">You'll need to enter this name in the **Domain Name field** of the **Custom deployment** page.</span></span>
- <span data-ttu-id="884eb-121">A DNS label prefix for the URLs of the public IP addresses of your virtual machines.</span><span class="sxs-lookup"><span data-stu-id="884eb-121">A DNS label prefix for the URLs of the public IP addresses of your virtual machines.</span></span> <span data-ttu-id="884eb-122">You'll need to enter this label in the **Dns Label Prefix** field of the **Custom deployment** page.</span><span class="sxs-lookup"><span data-stu-id="884eb-122">You'll need to enter this label in the **Dns Label Prefix** field of the **Custom deployment** page.</span></span>

<span data-ttu-id="884eb-123">手順をすべて確認したら、[[テンプレートの Readme ページ](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems)] で [**Azure に展開**] をクリックして展開を開始します。</span><span class="sxs-lookup"><span data-stu-id="884eb-123">After reading through the instructions, click **Deploy to Azure** on the [template README page](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) to get started.</span></span>

>[!Note]
><span data-ttu-id="884eb-124">ARM テンプレートで作成されたシミュレートされたイントラネットでは、Azure の有料サブスクリプションが必要です。</span><span class="sxs-lookup"><span data-stu-id="884eb-124">The simulated intranet built by the ARM template requires a paid Azure subscription.</span></span>
>

<span data-ttu-id="884eb-125">こちらがテンプレート完了後の構成です。</span><span class="sxs-lookup"><span data-stu-id="884eb-125">Here is your configuration after the template is complete.</span></span>

![Azure インフラストラクチャ サービスでのシミュレートされたイントラネット](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase3.png)

### <a name="method-2-build-your-simulated-intranet-with-azure-powershell"></a><span data-ttu-id="884eb-127">方法 2: Azure PowerShell を使用してシミュレートされたイントラネットを構築する</span><span class="sxs-lookup"><span data-stu-id="884eb-127">Method 2: Build your simulated intranet with Azure PowerShell</span></span>

<span data-ttu-id="884eb-128">この方法では、Windows PowerShell と Azure PowerShell モジュールを使用してネットワーク インフラストラクチャ、仮想マシン、およびその構成を構築します。</span><span class="sxs-lookup"><span data-stu-id="884eb-128">In this method, you use Windows PowerShell and the Azure PowerShell module to build out the networking infrastructure, the virtual machines, and their configuration.</span></span>

<span data-ttu-id="884eb-129">Use this method if you want to get experience creating elements of Azure infrastructure one step at a time with PowerShell.</span><span class="sxs-lookup"><span data-stu-id="884eb-129">Use this method if you want to get experience creating elements of Azure infrastructure one step at a time with PowerShell.</span></span> <span data-ttu-id="884eb-130">You can then customize the PowerShell command blocks for your own deployment of other virtual machines in Azure.</span><span class="sxs-lookup"><span data-stu-id="884eb-130">You can then customize the PowerShell command blocks for your own deployment of other virtual machines in Azure.</span></span>

#### <a name="step-1-create-dc1"></a><span data-ttu-id="884eb-131">ステップ 1: DC1 を作成する</span><span class="sxs-lookup"><span data-stu-id="884eb-131">Step 1: Create DC1</span></span>

<span data-ttu-id="884eb-132">このステップでは、Azure 仮想ネットワークを作成し、DC1 (AD DS ドメインのドメイン コントローラーである仮想マシン) を追加します。</span><span class="sxs-lookup"><span data-stu-id="884eb-132">In this step, we create an Azure virtual network and add DC1, a virtual machine that is a domain controller for an AD DS domain.</span></span>

<span data-ttu-id="884eb-133">最初に、ローカル コンピューターで Windows PowerShell コマンド プロンプトを起動します。</span><span class="sxs-lookup"><span data-stu-id="884eb-133">First, start a Windows PowerShell command prompt on your local computer.</span></span>
  
> [!NOTE]
> <span data-ttu-id="884eb-134">The following command sets use the latest version of Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="884eb-134">The following command sets use the latest version of Azure PowerShell.</span></span> <span data-ttu-id="884eb-135">See [Get started with Azure PowerShell cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/).</span><span class="sxs-lookup"><span data-stu-id="884eb-135">See [Get started with Azure PowerShell cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/).</span></span> 
  
<span data-ttu-id="884eb-136">次のコマンドを使用して Azure アカウントにログインします。</span><span class="sxs-lookup"><span data-stu-id="884eb-136">Sign in to your Azure account with the following command.</span></span>
  
```powershell
Connect-AzAccount
```

<span data-ttu-id="884eb-137">次のコマンドを使用して、サブスクリプションの名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="884eb-137">Get your subscription name using the following command.</span></span>
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

<span data-ttu-id="884eb-138">Set your Azure subscription.</span><span class="sxs-lookup"><span data-stu-id="884eb-138">Set your Azure subscription.</span></span> <span data-ttu-id="884eb-139">Replace everything within the quotes, including the < and > characters, with the correct name.</span><span class="sxs-lookup"><span data-stu-id="884eb-139">Replace everything within the quotes, including the < and > characters, with the correct name.</span></span>
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

<span data-ttu-id="884eb-140">Next, create a new resource group for your simulated enterprise test lab.</span><span class="sxs-lookup"><span data-stu-id="884eb-140">Next, create a new resource group for your simulated enterprise test lab.</span></span> <span data-ttu-id="884eb-141">To determine a unique resource group name, use this command to list your existing resource groups.</span><span class="sxs-lookup"><span data-stu-id="884eb-141">To determine a unique resource group name, use this command to list your existing resource groups.</span></span>
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

<span data-ttu-id="884eb-142">Create your new resource group with these commands.</span><span class="sxs-lookup"><span data-stu-id="884eb-142">Create your new resource group with these commands.</span></span> <span data-ttu-id="884eb-143">Replace everything within the quotes, including the < and > characters, with the correct names.</span><span class="sxs-lookup"><span data-stu-id="884eb-143">Replace everything within the quotes, including the < and > characters, with the correct names.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

<span data-ttu-id="884eb-144">Next, you create the TestLab virtual network that will host the Corpnet subnet of the simulated enterprise environment and protect it with a network security group.</span><span class="sxs-lookup"><span data-stu-id="884eb-144">Next, you create the TestLab virtual network that will host the Corpnet subnet of the simulated enterprise environment and protect it with a network security group.</span></span> <span data-ttu-id="884eb-145">Fill in the name of your resource group and run these commands at the PowerShell command prompt on your local computer.</span><span class="sxs-lookup"><span data-stu-id="884eb-145">Fill in the name of your resource group and run these commands at the PowerShell command prompt on your local computer.</span></span>
  
```powershell
$rgName="<name of your new resource group>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$corpnetSubnet=New-AzVirtualNetworkSubnetConfig -Name Corpnet -AddressPrefix 10.0.0.0/24
New-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName -Location $locName -AddressPrefix 10.0.0.0/8 -Subnet $corpnetSubnet -DNSServer 10.0.0.4
$rule1=New-AzNetworkSecurityRuleConfig -Name "RDPTraffic" -Description "Allow RDP to all VMs on the subnet" -Access Allow -Protocol Tcp -Direction Inbound -Priority 100 -SourceAddressPrefix Internet -SourcePortRange * -DestinationAddressPrefix * -DestinationPortRange 3389
New-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName -Location $locName -SecurityRules $rule1
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name TestLab
$nsg=Get-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name Corpnet -AddressPrefix "10.0.0.0/24" -NetworkSecurityGroup $nsg
$vnet | Set-AzVirtualNetwork
```

<span data-ttu-id="884eb-146">Next, you create the DC1 virtual machine and configure it as a domain controller for the **testlab.**\<your public domain></span><span class="sxs-lookup"><span data-stu-id="884eb-146">Next, you create the DC1 virtual machine and configure it as a domain controller for the **testlab.**\<your public domain></span></span> <span data-ttu-id="884eb-147">AD DS domain and a DNS server for the virtual machines of the TestLab virtual network.</span><span class="sxs-lookup"><span data-stu-id="884eb-147">AD DS domain and a DNS server for the virtual machines of the TestLab virtual network.</span></span> <span data-ttu-id="884eb-148">For example, if your public domain name is **<span>contoso</span>.com**, the DC1 virtual machine will be a domain controller for the **<span>testlab</span>.contoso.com** domain.</span><span class="sxs-lookup"><span data-stu-id="884eb-148">For example, if your public domain name is **<span>contoso</span>.com**, the DC1 virtual machine will be a domain controller for the **<span>testlab</span>.contoso.com** domain.</span></span>
  
<span data-ttu-id="884eb-149">DC1 用の Azure 仮想マシンを作成するには、リソース グループの名前を入力して、次に示すコマンドをローカル コンピューターの PowerShell コマンド プロンプトから実行します。</span><span class="sxs-lookup"><span data-stu-id="884eb-149">To create an Azure virtual machine for DC1, fill in the name of your resource group and run these commands at the PowerShell command prompt on your local computer.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName
$pip=New-AzPublicIpAddress -Name DC1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name DC1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id -PrivateIpAddress 10.0.0.4
$vm=New-AzVMConfig -VMName DC1 -VMSize Standard_A2_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for DC1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName DC1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "DC1-OS" -DiskSizeInGB 128 -CreateOption FromImage
$diskConfig=New-AzDiskConfig -AccountType "Standard_LRS" -Location $locName -CreateOption Empty -DiskSizeGB 20
$dataDisk1=New-AzDisk -DiskName "DC1-DataDisk1" -Disk $diskConfig -ResourceGroupName $rgName
$vm=Add-AzVMDataDisk -VM $vm -Name "DC1-DataDisk1" -CreateOption Attach -ManagedDiskId $dataDisk1.Id -Lun 1
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

<span data-ttu-id="884eb-150">You will be prompted for a user name and password for the local administrator account on DC1.</span><span class="sxs-lookup"><span data-stu-id="884eb-150">You will be prompted for a user name and password for the local administrator account on DC1.</span></span> <span data-ttu-id="884eb-151">Use a strong password and record both the name and password in a secure location.</span><span class="sxs-lookup"><span data-stu-id="884eb-151">Use a strong password and record both the name and password in a secure location.</span></span>
  
<span data-ttu-id="884eb-152">次に、DC1 仮想マシンに接続します。</span><span class="sxs-lookup"><span data-stu-id="884eb-152">Next, connect to the DC1 virtual machine.</span></span>
  
1. <span data-ttu-id="884eb-153">[Azure portal](https://portal.azure.com) で、**[リソース グループ] >**「新しいリソース グループの名前」\*\* > [DC1] > [接続]\*\* の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="884eb-153">In the [Azure portal](https://portal.azure.com), click **Resource Groups >** [the name of your new resource group] **> DC1 > Connect**.</span></span>
    
2. <span data-ttu-id="884eb-154">In the open pane, click **Download RDP file**.</span><span class="sxs-lookup"><span data-stu-id="884eb-154">In the open pane, click **Download RDP file**.</span></span> <span data-ttu-id="884eb-155">Open the DC1.rdp file that is downloaded, and then click **Connect**.</span><span class="sxs-lookup"><span data-stu-id="884eb-155">Open the DC1.rdp file that is downloaded, and then click **Connect**.</span></span>
    
3. <span data-ttu-id="884eb-156">DC1 のローカル管理者アカウント名を指定します。</span><span class="sxs-lookup"><span data-stu-id="884eb-156">Specify the DC1 local administrator account name:</span></span>
    
   - <span data-ttu-id="884eb-157">Windows 7 の場合:</span><span class="sxs-lookup"><span data-stu-id="884eb-157">For Windows 7:</span></span>
    
     <span data-ttu-id="884eb-158">In the **Windows Security** dialog box, click **Use another account**.</span><span class="sxs-lookup"><span data-stu-id="884eb-158">In the **Windows Security** dialog box, click **Use another account**.</span></span> <span data-ttu-id="884eb-159">In **User name**, type **DC1\\**[Local administrator account name].</span><span class="sxs-lookup"><span data-stu-id="884eb-159">In **User name**, type **DC1\\**[Local administrator account name].</span></span>
    
   - <span data-ttu-id="884eb-160">Windows 8 または Windows 10 の場合:</span><span class="sxs-lookup"><span data-stu-id="884eb-160">For Windows 8 or Windows 10:</span></span>
    
     <span data-ttu-id="884eb-161">In the **Windows Security** dialog box, click **More choices**, and then click **Use a different account**.</span><span class="sxs-lookup"><span data-stu-id="884eb-161">In the **Windows Security** dialog box, click **More choices**, and then click **Use a different account**.</span></span> <span data-ttu-id="884eb-162">In **User name**, type **DC1\\**[Local administrator account name].</span><span class="sxs-lookup"><span data-stu-id="884eb-162">In **User name**, type **DC1\\**[Local administrator account name].</span></span>
    
4. <span data-ttu-id="884eb-163">**[パスワード]** にローカル管理者アカウントのパスワードを入力して、**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="884eb-163">In **Password**, type the password of the local administrator account, and then click **OK**.</span></span>
    
5. <span data-ttu-id="884eb-164">ダイアログが表示されたら、**[はい]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="884eb-164">When prompted, click **Yes**.</span></span>
    
<span data-ttu-id="884eb-165">次に、DC1 の管理者レベルの Windows PowerShell コマンド プロンプトで次のコマンドを使用して、新しいボリュームとして別のデータ ディスク (ドライブ文字 F:) を追加します。</span><span class="sxs-lookup"><span data-stu-id="884eb-165">Next, add an extra data disk as a new volume with the drive letter F: with this command at an administrator-level Windows PowerShell command prompt on DC1.</span></span>
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

<span data-ttu-id="884eb-166">次に **testlab.**\<your public domain></span><span class="sxs-lookup"><span data-stu-id="884eb-166">Next, configure DC1 as a domain controller and DNS server for the **testlab.**\<your public domain></span></span> <span data-ttu-id="884eb-167">ドメインのドメイン コントローラーおよび DNS サーバーとして DC1 を構成します。</span><span class="sxs-lookup"><span data-stu-id="884eb-167">domain.</span></span> <span data-ttu-id="884eb-168">パブリック ドメイン名を指定して \< and > 文字を削除し、DC1の管理者レベルの Windows PowerShellコマンド プロンプトでこれらのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="884eb-168">Specify your public domain name, remove the \< and > characters, and then run these commands at an administrator-level Windows PowerShell command prompt on DC1.</span></span>
  
```powershell
$yourDomain="<your public domain>"
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSForest -DomainName testlab.$yourDomain -DatabasePath "F:\NTDS" -SysvolPath "F:\SYSVOL" -LogPath "F:\Logs"
```
<span data-ttu-id="884eb-169">You will need to specify a safe mode administrator password.</span><span class="sxs-lookup"><span data-stu-id="884eb-169">You will need to specify a safe mode administrator password.</span></span> <span data-ttu-id="884eb-170">Store this password in a secure location.</span><span class="sxs-lookup"><span data-stu-id="884eb-170">Store this password in a secure location.</span></span>
  
<span data-ttu-id="884eb-171">これらのコマンドの完了には数分かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="884eb-171">Note that these commands can take a few minutes to complete.</span></span>
  
<span data-ttu-id="884eb-172">DC1 の再起動後に、DC1 仮想マシンに再接続します。</span><span class="sxs-lookup"><span data-stu-id="884eb-172">After DC1 restarts, reconnect to the DC1 virtual machine.</span></span>
  
1. <span data-ttu-id="884eb-173">[Azure portal](https://portal.azure.com) で、**[リソース グループ] >**「リソース グループ名」\*\* > [DC1] > [接続]\*\* をクリックします。</span><span class="sxs-lookup"><span data-stu-id="884eb-173">In the [Azure portal](https://portal.azure.com), click **Resource Groups >** [your resource group name] **> DC1 > Connect**.</span></span>
    
2. <span data-ttu-id="884eb-174">ダウンロードされる DC1.rdp ファイルを実行して、**[接続]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="884eb-174">Run the DC1.rdp file that is downloaded, and then click **Connect**.</span></span>
    
3. <span data-ttu-id="884eb-175">In **Windows Security**, click **Use another account**.</span><span class="sxs-lookup"><span data-stu-id="884eb-175">In **Windows Security**, click **Use another account**.</span></span> <span data-ttu-id="884eb-176">In **User name**, type **TESTLAB\\**[Local administrator account name].</span><span class="sxs-lookup"><span data-stu-id="884eb-176">In **User name**, type **TESTLAB\\**[Local administrator account name].</span></span>
    
4. <span data-ttu-id="884eb-177">**[パスワード]** にローカル管理者アカウントのパスワードを入力して、**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="884eb-177">In **Password**, type the password of the local administrator account, and then click **OK**.</span></span>
    
5. <span data-ttu-id="884eb-178">ダイアログが表示されたら、**[はい]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="884eb-178">When prompted, click **Yes**.</span></span>
    
<span data-ttu-id="884eb-179">Next, create a user account in Active Directory that will be used when logging in to TESTLAB domain member computers.</span><span class="sxs-lookup"><span data-stu-id="884eb-179">Next, create a user account in Active Directory that will be used when logging in to TESTLAB domain member computers.</span></span> <span data-ttu-id="884eb-180">Run this command at an administrator-level Windows PowerShell command prompt.</span><span class="sxs-lookup"><span data-stu-id="884eb-180">Run this command at an administrator-level Windows PowerShell command prompt.</span></span>
  
```powershell
New-ADUser -SamAccountName User1 -AccountPassword (read-host "Set user password" -assecurestring) -name "User1" -enabled $true -PasswordNeverExpires $true -ChangePasswordAtLogon $false
```

<span data-ttu-id="884eb-181">Note that this command prompts you to supply the User1 account password.</span><span class="sxs-lookup"><span data-stu-id="884eb-181">Note that this command prompts you to supply the User1 account password.</span></span> <span data-ttu-id="884eb-182">Because this account will be used for remote desktop connections for all TESTLAB domain member computers, choose a strong password.</span><span class="sxs-lookup"><span data-stu-id="884eb-182">Because this account will be used for remote desktop connections for all TESTLAB domain member computers, choose a strong password.</span></span> <span data-ttu-id="884eb-183">Record the User1 account password and store it in a secured location.</span><span class="sxs-lookup"><span data-stu-id="884eb-183">Record the User1 account password and store it in a secured location.</span></span>
  
<span data-ttu-id="884eb-184">Next, configure the new User1 account as a domain, enterprise, and schema administrator.</span><span class="sxs-lookup"><span data-stu-id="884eb-184">Next, configure the new User1 account as a domain, enterprise, and schema administrator.</span></span> <span data-ttu-id="884eb-185">Run this command at the administrator-level Windows PowerShell command prompt.</span><span class="sxs-lookup"><span data-stu-id="884eb-185">Run this command at the administrator-level Windows PowerShell command prompt.</span></span>
  
```powershell
$yourDomain="<your public domain>"
$domainName = "testlab."+$yourDomain
$userName="user1@" + $domainName
$userSID=(New-Object System.Security.Principal.NTAccount($userName)).Translate([System.Security.Principal.SecurityIdentifier]).Value
$groupNames=@("Domain Admins","Enterprise Admins","Schema Admins")
ForEach ($name in $groupNames) {Add-ADPrincipalGroupMembership -Identity $userSID -MemberOf (Get-ADGroup -Identity $name).SID.Value}
```

<span data-ttu-id="884eb-186">DC1 とのリモート デスクトップ セッションを終了し、TESTLAB\\User1 のアカウントを使用して再接続します。</span><span class="sxs-lookup"><span data-stu-id="884eb-186">Close the Remote Desktop session with DC1 and then reconnect using the TESTLAB\\User1 account.</span></span>
  
<span data-ttu-id="884eb-187">次に、Ping ツールのトラフィックを許可するため、管理者レベルの Windows PowerShell コマンド プロンプトで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="884eb-187">Next, to allow traffic for the Ping tool, run this command at an administrator-level Windows PowerShell command prompt.</span></span>
  
```powershell
Set-NetFirewallRule -DisplayName "File and Printer Sharing (Echo Request - ICMPv4-In)" -enabled True
```

<span data-ttu-id="884eb-188">こちらが現在の構成です。</span><span class="sxs-lookup"><span data-stu-id="884eb-188">This is your current configuration.</span></span>
  
![シミュレートされたエンタープライズ基本構成のステップ 1](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase1.png)
  
#### <a name="step-2-configure-app1"></a><span data-ttu-id="884eb-190">ステップ 2: APP1 を構成する</span><span class="sxs-lookup"><span data-stu-id="884eb-190">Step 2: Configure APP1</span></span>

<span data-ttu-id="884eb-191">このステップでは、最初にWeb およびファイル共有サービスを提供するアプリケーション サーバーである APP1 を作成して構成します。</span><span class="sxs-lookup"><span data-stu-id="884eb-191">In this step, you create and configure APP1, which is an application server that initially provides web and file sharing services.</span></span>

<span data-ttu-id="884eb-192">APP1 用の Azure 仮想マシンを作成するには、リソース グループの名前を入力して、次に示すコマンドをローカル コンピューターのコマンド プロンプトから実行します。</span><span class="sxs-lookup"><span data-stu-id="884eb-192">To create an Azure Virtual Machine for APP1, fill in the name of your resource group and run these commands at the  command prompt on your local computer.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName
$pip=New-AzPublicIpAddress -Name APP1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name APP1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id
$vm=New-AzVMConfig -VMName APP1 -VMSize Standard_A2_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for APP1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName APP1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "APP1-OS" -DiskSizeInGB 128 -CreateOption FromImage
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

<span data-ttu-id="884eb-193">次に、APP1 のローカル管理者アカウント名とパスワードを使用して APP1 仮想マシンに接続し、Windows PowerShell コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="884eb-193">Next, connect to the APP1 virtual machine using the APP1 local administrator account name and password, and then open a Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="884eb-194">APP1 と DC1 間の名前解決とネットワーク通信を確認するには、**ping dc1.testlab.**\<your public domain name></span><span class="sxs-lookup"><span data-stu-id="884eb-194">To check name resolution and network communication between APP1 and DC1, run the **ping dc1.testlab.**\<your public domain name></span></span> <span data-ttu-id="884eb-195">コマンドを実行し、返信が 4 つあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="884eb-195">command and verify that there are four replies.</span></span>
  
<span data-ttu-id="884eb-196">次に、Windows PowerShell プロンプトでこれらのコマンドを使用して、APP1 仮想マシンを TESTLAB ドメインに参加させます。</span><span class="sxs-lookup"><span data-stu-id="884eb-196">Next, join the APP1 virtual machine to the TESTLAB domain with these commands at the Windows PowerShell prompt.</span></span>
  
```powershell
$yourDomain="<your public domain name>"
Add-Computer -DomainName ("testlab." + $yourDomain)
Restart-Computer
```

<span data-ttu-id="884eb-197">**Add-Computer** コマンドの実行後には、TESTLAB\\User1 ドメイン アカウントの資格情報を入力する必要がある点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="884eb-197">Note that you must supply the TESTLAB\\User1 domain account credentials after running the **Add-Computer** command.</span></span>
  
<span data-ttu-id="884eb-198">APP1 の再起動後に、TESTLAB\\User1 のアカウントを使用して接続し、管理者レベルの Windows PowerShell コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="884eb-198">After APP1 restarts, connect to it using the TESTLAB\\User1 account, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="884eb-199">次に、このコマンドを APP1 の管理者レベルの Windows PowerShell コマンド プロンプトで使用して、APP1 を Web サーバーにします。</span><span class="sxs-lookup"><span data-stu-id="884eb-199">Next, make APP1 a web server with this command at an administrator-level Windows PowerShell command prompt on APP1.</span></span>
  
```powershell
Install-WindowsFeature Web-WebServer -IncludeManagementTools
```

<span data-ttu-id="884eb-200">次に、以下の PowerShell コマンドを使用して APP1 で共有フォルダーを作成し、そのフォルダー内にテキスト ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="884eb-200">Next, create a shared folder and a text file within the folder on APP1 with these PowerShell commands.</span></span>
  
```powershell
New-Item -path c:\files -type directory
Write-Output "This is a shared file." | out-file c:\files\example.txt
New-SmbShare -name files -path c:\files -changeaccess TESTLAB\User1
```

<span data-ttu-id="884eb-201">こちらが現在の構成です。</span><span class="sxs-lookup"><span data-stu-id="884eb-201">This is your current configuration.</span></span>
  
![シミュレートされたエンタープライズ基本構成のステップ 2](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase2.png)
  
#### <a name="step-3-configure-client1"></a><span data-ttu-id="884eb-203">ステップ 3: CLIENT1 を構成する</span><span class="sxs-lookup"><span data-stu-id="884eb-203">Step 3: Configure CLIENT1</span></span>

<span data-ttu-id="884eb-204">このステップでは、イントラネット上の一般的なラップトップ、タブレット、またはデスクトップ コンピューターとして機能する CLIENT1 を作成して構成します。</span><span class="sxs-lookup"><span data-stu-id="884eb-204">In this step, you create and configure CLIENT1, which acts as a typical laptop, tablet, or desktop computer on the intranet.</span></span>

> [!NOTE]  
> <span data-ttu-id="884eb-205">The following command set creates CLIENT1 running Windows Server 2016 Datacenter, which can be done for all types of Azure subscriptions.</span><span class="sxs-lookup"><span data-stu-id="884eb-205">The following command set creates CLIENT1 running Windows Server 2016 Datacenter, which can be done for all types of Azure subscriptions.</span></span> <span data-ttu-id="884eb-206">If you have a Visual Studio-based Azure subscription, you can create CLIENT1 running Windows 10 with the [Azure portal](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="884eb-206">If you have a Visual Studio-based Azure subscription, you can create CLIENT1 running Windows 10 with the [Azure portal](https://portal.azure.com).</span></span> 
  
<span data-ttu-id="884eb-207">CLIENT1 用の Azure 仮想マシンを作成するには、リソース グループの名前を入力して、次に示すコマンドをローカル コンピューターのコマンド プロンプトから実行します。</span><span class="sxs-lookup"><span data-stu-id="884eb-207">To create an Azure Virtual Machine for CLIENT1, fill in the name of your resource group and run these commands at the  command prompt on your local computer.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName
$pip=New-AzPublicIpAddress -Name CLIENT1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name CLIENT1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id
$vm=New-AzVMConfig -VMName CLIENT1 -VMSize Standard_A2_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for CLIENT1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName CLIENT1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "CLIENT1-OS" -DiskSizeInGB 128 -CreateOption FromImage
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

<span data-ttu-id="884eb-208">次に、CLIENT1 のローカル管理者アカウント名とパスワードを使用して、CLIENT1 仮想マシンに接続し、管理者レベルの Windows PowerShell コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="884eb-208">Next, connect to the CLIENT1 virtual machine using the CLIENT1 local administrator account name and password, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="884eb-209">CLIENT1 と DC1 間の名前解決とネットワーク通信を確認するには、**ping dc1.testlab.**\<your public domain name></span><span class="sxs-lookup"><span data-stu-id="884eb-209">To check name resolution and network communication between CLIENT1 and DC1, run the **ping dc1.testlab.**\<your public domain name></span></span> <span data-ttu-id="884eb-210">コマンドを Windows PowerShell コマンド プロンプトで実行し、返信が 4 つあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="884eb-210">command at a Windows PowerShell command prompt and verify that there are four replies.</span></span>
  
<span data-ttu-id="884eb-211">次に、Windows PowerShell プロンプトでこれらのコマンドを使用して、CLIENT1 仮想マシンを TESTLAB ドメインに参加させます。</span><span class="sxs-lookup"><span data-stu-id="884eb-211">Next, join the CLIENT1 virtual machine to the TESTLAB domain with these commands at the Windows PowerShell prompt.</span></span>
  
```powershell
$yourDomain="<your public domain name>"
Add-Computer -DomainName ("testlab." + $yourDomain)
Restart-Computer
```

<span data-ttu-id="884eb-212">**Add-Computer** コマンドの実行後に、TESTLAB\\User1 ドメイン アカウントの資格情報を入力する必要がある点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="884eb-212">Note that you must supply your TESTLAB\\User1 domain account credentials after running the **Add-Computer** command.</span></span>
  
<span data-ttu-id="884eb-213">CLIENT1 の再起動後に、TESTLAB\\User1 のアカウント名とパスワードを使用して接続し、管理者レベルの Windows PowerShell コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="884eb-213">After CLIENT1 restarts, connect to it using the TESTLAB\\User1 account name and password, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="884eb-214">次に、CLIENT1 から APP1 の Web リソースおよびファイル共有リソースにアクセスできることを確認します。</span><span class="sxs-lookup"><span data-stu-id="884eb-214">Next, verify that you can access web and file share resources on APP1 from CLIENT1.</span></span>
  
1. <span data-ttu-id="884eb-215">サーバー マネージャーのツリー ウィンドウで、**[ローカル サーバー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="884eb-215">In Server Manager, in the tree pane, click **Local Server**.</span></span>
    
2. <span data-ttu-id="884eb-216">**[CLIENT1 のプロパティ]** で、**[IE セキュリティ強化の構成]** の横にある **[オン]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="884eb-216">In **Properties for CLIENT1**, click **On** next to **IE Enhanced Security Configuration**.</span></span>
    
3. <span data-ttu-id="884eb-217">**[Internet Explorer セキュリティ強化の構成]** で、**[管理者]** と **[ユーザー]** の **[オフ]** をクリックしてから、**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="884eb-217">In **Internet Explorer Enhanced Security Configuration**, click **Off** for **Administrators** and **Users**, and then click **OK**.</span></span>
    
4. <span data-ttu-id="884eb-218">スタート画面で、**[Internet Explorer]** をクリックし、**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="884eb-218">From the Start screen, click **Internet Explorer**, and then click **OK**.</span></span>
    
5. <span data-ttu-id="884eb-219">アドレス バーに「**http<span>://</span>app1.testab.**\<your public domain name>**/**」と入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="884eb-219">In the Address bar, type **http<span>://</span>app1.testab.**\<your public domain name>**/**, and then press ENTER.</span></span> <span data-ttu-id="884eb-220">APP1 の既定のインターネット インフォメーション サービスの Web ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="884eb-220">You should see the default Internet Information Services web page for APP1.</span></span>
    
6. <span data-ttu-id="884eb-221">デスクトップのタスクバーで、[エクスプローラー] アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="884eb-221">From the desktop taskbar, click the File Explorer icon.</span></span>
    
7. <span data-ttu-id="884eb-222">In the address bar, type **\\\\app1\\Files**, and then press ENTER.</span><span class="sxs-lookup"><span data-stu-id="884eb-222">In the address bar, type **\\\\app1\\Files**, and then press ENTER.</span></span> <span data-ttu-id="884eb-223">You should see a folder window with the contents of the Files shared folder.</span><span class="sxs-lookup"><span data-stu-id="884eb-223">You should see a folder window with the contents of the Files shared folder.</span></span>
    
8. <span data-ttu-id="884eb-224">In the **Files** shared folder window, double-click the **Example.txt** file.</span><span class="sxs-lookup"><span data-stu-id="884eb-224">In the **Files** shared folder window, double-click the **Example.txt** file.</span></span> <span data-ttu-id="884eb-225">You should see the contents of the Example.txt file.</span><span class="sxs-lookup"><span data-stu-id="884eb-225">You should see the contents of the Example.txt file.</span></span>
    
9. <span data-ttu-id="884eb-226">**[example.txt - メモ帳]** と **[ファイル]** の共有フォルダーのウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="884eb-226">Close the **example.txt - Notepad** and the **Files** shared folder windows.</span></span>
    
<span data-ttu-id="884eb-227">こちらが現在の構成です。</span><span class="sxs-lookup"><span data-stu-id="884eb-227">This is your current configuration.</span></span>
  
![シミュレートされたエンタープライズ基本構成のステップ 3](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase3.png)


## <a name="phase-2-create-your-microsoft-365-e5-subscription"></a><span data-ttu-id="884eb-229">フェーズ 2: Microsoft 365 E5 サブスクリプションを作成する</span><span class="sxs-lookup"><span data-stu-id="884eb-229">Phase 2: Create your Microsoft 365 E5 subscription</span></span>

<span data-ttu-id="884eb-230">In this phase, you create a new Microsoft 365 E5 subscription that uses a new Azure AD tenant, one that is separate from your production subscription.</span><span class="sxs-lookup"><span data-stu-id="884eb-230">In this phase, you create a new Microsoft 365 E5 subscription that uses a new Azure AD tenant, one that is separate from your production subscription.</span></span> <span data-ttu-id="884eb-231">You can do this in two ways:</span><span class="sxs-lookup"><span data-stu-id="884eb-231">You can do this in two ways:</span></span>

- <span data-ttu-id="884eb-232">Microsoft 365 E5 の試用版サブスクリプションを使用する。</span><span class="sxs-lookup"><span data-stu-id="884eb-232">Use a trial subscription of Microsoft 365 E5.</span></span> 

  <span data-ttu-id="884eb-233">The Microsoft 365 E5 trial subscription is 30 days, which can be easily extended to 60 days.</span><span class="sxs-lookup"><span data-stu-id="884eb-233">The Microsoft 365 E5 trial subscription is 30 days, which can be easily extended to 60 days.</span></span> <span data-ttu-id="884eb-234">When the trial subscription expires, you must either convert it to a paid subscription or create a new trial subscription.</span><span class="sxs-lookup"><span data-stu-id="884eb-234">When the trial subscription expires, you must either convert it to a paid subscription or create a new trial subscription.</span></span> <span data-ttu-id="884eb-235">Creating new trial subscriptions means you will leave your configuration, which could include complex scenarios, behind.</span><span class="sxs-lookup"><span data-stu-id="884eb-235">Creating new trial subscriptions means you will leave your configuration, which could include complex scenarios, behind.</span></span>  

- <span data-ttu-id="884eb-236">ライセンス数の少ない Microsoft 365 E5 の個別の運用サブスクリプションを使用する。</span><span class="sxs-lookup"><span data-stu-id="884eb-236">Use a separate production subscription of Microsoft 365 E5 with a small number of licenses.</span></span>

  <span data-ttu-id="884eb-237">This is an additional cost, but ensures that you have a working test environment to try features, configurations, and scenarios that does not expire.</span><span class="sxs-lookup"><span data-stu-id="884eb-237">This is an additional cost, but ensures that you have a working test environment to try features, configurations, and scenarios that does not expire.</span></span> <span data-ttu-id="884eb-238">You can use the same test environment over the long term for proofs of concept, demonstration to peers and management, and application development and testing.</span><span class="sxs-lookup"><span data-stu-id="884eb-238">You can use the same test environment over the long term for proofs of concept, demonstration to peers and management, and application development and testing.</span></span> <span data-ttu-id="884eb-239">This is the recommended method.</span><span class="sxs-lookup"><span data-stu-id="884eb-239">This is the recommended method.</span></span>

### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a><span data-ttu-id="884eb-240">Office 365 E5 試用版サブスクリプションにサインアップする</span><span class="sxs-lookup"><span data-stu-id="884eb-240">Sign up for an Office 365 E5 trial subscription</span></span>

<span data-ttu-id="884eb-241">Azure ポータルから、CORP\User1 アカウントを使用して CLIENT1 に接続します。</span><span class="sxs-lookup"><span data-stu-id="884eb-241">Connect to CLIENT1 with the CORP\User1 account from the Azure portal.</span></span>

<span data-ttu-id="884eb-242">新しい Office 365 E5 試用版のサブスクリプションを作成するには、「軽量な基本構成」のテスト ラボ ガイドの [フェーズ 1](lightweight-base-configuration-microsoft-365-enterprise.md#phase-1-create-your-office-365-e5-subscription) にある手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="884eb-242">To create a new Office 365 E5 trial subscription, perform the instructions in [Phase 1](lightweight-base-configuration-microsoft-365-enterprise.md#phase-1-create-your-office-365-e5-subscription) of the lightweight base configuration Test Lab Guide.</span></span>

<span data-ttu-id="884eb-243">新しい Office 365 E5 試用版のサブスクリプションを構成するには、「軽量な基本構成」のテスト ラボ ガイドの [フェーズ 2](lightweight-base-configuration-microsoft-365-enterprise.md#phase-2-configure-your-office-365-trial-subscription) にある手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="884eb-243">To configure your new Office 365 E5 trial subscription, perform the instructions in [Phase 2](lightweight-base-configuration-microsoft-365-enterprise.md#phase-2-configure-your-office-365-trial-subscription) of the lightweight base configuration Test Lab Guide.</span></span>

#### <a name="using-an-office-365-e5-test-environment"></a><span data-ttu-id="884eb-244">Office 365 E5 のテスト環境を使用する</span><span class="sxs-lookup"><span data-stu-id="884eb-244">Using an Office 365 E5 test environment</span></span>

<span data-ttu-id="884eb-245">Office 365 のテスト環境だけが必要な場合は、ここで終了します。</span><span class="sxs-lookup"><span data-stu-id="884eb-245">If all you need is an Office 365 test environment, you can stop here.</span></span> 

<span data-ttu-id="884eb-246">Office 365 と Microsoft 365 の両方に適用される追加のテスト ラボ ガイドについては、「[Microsoft 365 エンタープライズ テスト ラボ ガイド](m365-enterprise-test-lab-guides.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="884eb-246">See [Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md) for additional Test Lab Guides that apply to both Office 365 and Microsoft 365.</span></span>

### <a name="add-a-microsoft-365-e5-trial-subscription"></a><span data-ttu-id="884eb-247">Microsoft 365 E5 の試用版サブスクリプションを追加する</span><span class="sxs-lookup"><span data-stu-id="884eb-247">Add a Microsoft 365 E5 trial subscription</span></span>

<span data-ttu-id="884eb-248">ライセンスを使用して、Office 365 E5 試用版のサブスクリプションのユーザー アカウントを構成するには、「軽量な基本構成」のテスト ラボ ガイドの [フェーズ 3](lightweight-base-configuration-microsoft-365-enterprise.md#phase-3-add-a-microsoft-365-e5-trial-subscription) にある手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="884eb-248">To a Microsoft 365 E5 trial subscription and configure your users accounts with licenses, perform the instructions in [Phase 3](lightweight-base-configuration-microsoft-365-enterprise.md#phase-3-add-a-microsoft-365-e5-trial-subscription) of the lightweight base configuration Test Lab Guide.</span></span>

  
## <a name="results"></a><span data-ttu-id="884eb-249">結果</span><span class="sxs-lookup"><span data-stu-id="884eb-249">Results</span></span>

<span data-ttu-id="884eb-250">テスト環境は、次のようになっています。</span><span class="sxs-lookup"><span data-stu-id="884eb-250">Your test environment now has:</span></span>
  
- <span data-ttu-id="884eb-251">Microsoft 365 E5 の試用版サブスクリプション。</span><span class="sxs-lookup"><span data-stu-id="884eb-251">Microsoft 365 E5 trial subscription.</span></span>
- <span data-ttu-id="884eb-252">すべての適切なユーザー アカウントが Microsoft 365 E5 を使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="884eb-252">All your appropriate user accounts are enabled to use Microsoft 365 E5.</span></span>
- <span data-ttu-id="884eb-253">シミュレートおよび簡略化されたイントラネット。</span><span class="sxs-lookup"><span data-stu-id="884eb-253">A simulated and simplified intranet.</span></span>
    
<span data-ttu-id="884eb-254">これは、最終的な構成です。</span><span class="sxs-lookup"><span data-stu-id="884eb-254">This is your final configuration.</span></span>
  
![シミュレートされたエンタープライズ基本構成のフェーズ 2](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase4.png)
  
<span data-ttu-id="884eb-256">これで、[Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise) の追加機能を試せるようになりました。</span><span class="sxs-lookup"><span data-stu-id="884eb-256">You are now ready to experiment with additional features of [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="884eb-257">次の手順</span><span class="sxs-lookup"><span data-stu-id="884eb-257">Next steps</span></span>

<span data-ttu-id="884eb-258">こうした追加のテスト ラボ ガイドについて説明します。</span><span class="sxs-lookup"><span data-stu-id="884eb-258">Explore these additional sets of Test Lab Guides:</span></span>
  
- [<span data-ttu-id="884eb-259">ID</span><span class="sxs-lookup"><span data-stu-id="884eb-259">Identity</span></span>](m365-enterprise-test-lab-guides.md#identity)
- [<span data-ttu-id="884eb-260">モバイル デバイス管理</span><span class="sxs-lookup"><span data-stu-id="884eb-260">Mobile device management</span></span>](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [<span data-ttu-id="884eb-261">情報保護</span><span class="sxs-lookup"><span data-stu-id="884eb-261">Information protection</span></span>](m365-enterprise-test-lab-guides.md#information-protection)

## <a name="see-also"></a><span data-ttu-id="884eb-262">関連項目</span><span class="sxs-lookup"><span data-stu-id="884eb-262">See also</span></span>

[<span data-ttu-id="884eb-263">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="884eb-263">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="884eb-264">Microsoft 365 Enterprise を展開する</span><span class="sxs-lookup"><span data-stu-id="884eb-264">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="884eb-265">Microsoft 365 Enterprise のドキュメントとリソース</span><span class="sxs-lookup"><span data-stu-id="884eb-265">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
