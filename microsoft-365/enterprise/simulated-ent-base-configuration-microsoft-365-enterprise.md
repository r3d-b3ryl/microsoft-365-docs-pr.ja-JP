---
title: Microsoft 365 用のシミュレートされたエンタープライズ基本構成
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/15/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
ms.assetid: 6f916a77-301c-4be2-b407-6cec4d80df76
description: このテスト ラボ ガイドを使用して、Microsoft 365 Enterprise 用にシミュレートされたエンタープライズ テスト環境を作成します。
ms.openlocfilehash: 7c16f6fee480e883f7bf87d3b03441cf18e8f73f
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32290838"
---
# <a name="the-simulated-enterprise-base-configuration"></a><span data-ttu-id="e339a-103">シミュレートされたエンタープライズ基本構成</span><span class="sxs-lookup"><span data-stu-id="e339a-103">The simulated enterprise base configuration</span></span>

<span data-ttu-id="e339a-104">この記事では、次のものを含む Microsoft 365 Enterprise のシンプルな環境を作成するための詳しい手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="e339a-104">This article provides you with step-by-step instructions to create a simplified environment for Microsoft 365 Enterprise that includes:</span></span>

- <span data-ttu-id="e339a-105">Office 365 E5 および EMS E5 の試用版サブスクリプションまたは有料サブスクリプション。</span><span class="sxs-lookup"><span data-stu-id="e339a-105">Office 365 E5 and EMS E5 trial or paid subscriptions.</span></span>
- <span data-ttu-id="e339a-106">インターネットに接続している組織の簡易型イントラネット。Azure 仮想ネットワーク上に配置された 3 つの仮想マシン (DC1、APP1、および CLIENT1) で構成されます。</span><span class="sxs-lookup"><span data-stu-id="e339a-106">A simplified organization intranet connected to the Internet, consisting of three virtual machines on an Azure virtual network (DC1, APP1, and CLIENT1).</span></span>
 
![シミュレートされたエンタープライズ基本構成](media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase4.png)

<span data-ttu-id="e339a-108">完成した環境は、その他の [テスト ラボ ガイド](m365-enterprise-test-lab-guides.md)や各自の実験で、[Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise) の機能をテストするために使用できます。</span><span class="sxs-lookup"><span data-stu-id="e339a-108">You can use the resulting environment to test the features and functionality of [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise) with additional [Test Lab Guides](m365-enterprise-test-lab-guides.md) or on your own.</span></span>

![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="e339a-110">[ここ](https://aka.ms/m365etlgstack)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事のビジュアル マップを確認してください。</span><span class="sxs-lookup"><span data-stu-id="e339a-110">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-create-a-simulated-intranet"></a><span data-ttu-id="e339a-111">フェーズ 1: シミュレートされたイントラネットを作成する</span><span class="sxs-lookup"><span data-stu-id="e339a-111">Phase 1: Create a simulated intranet</span></span>

<span data-ttu-id="e339a-112">このフェーズでは、Active Directory Domain Services (AD DS) ドメイン コントローラー、アプリケーション サーバー、クライアント コンピューターを含むシミュレートされたイントラネットを Azure インフラストラクチャ サービスに作成します。</span><span class="sxs-lookup"><span data-stu-id="e339a-112">In this phase, you build a simulated intranet in Azure infrastructure services that includes a Windows Server Active Directory domain controller, an application server, and a client computer.</span></span> 

<span data-ttu-id="e339a-113">こうしたコンピューターは、他の [Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)でハイブリッド ID およびその他の機能の構成とデモンストレーションのために使用します。</span><span class="sxs-lookup"><span data-stu-id="e339a-113">You'll use these computers in additional [Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md) to configure and demonstrate hybrid identity and other capabilities.</span></span>

### <a name="method-1-build-your-simulated-intranet-with-an-azure-resource-manager-template"></a><span data-ttu-id="e339a-114">方法 1: Azure Resource Manager テンプレートを使用して、シミュレートされたイントラネットを構築する</span><span class="sxs-lookup"><span data-stu-id="e339a-114">Method 1: Build your simulated intranet with an Azure Resource Manager template</span></span>

<span data-ttu-id="e339a-p101">この方法では、Azure Resource Manager (ARM) テンプレートを使用してシミュレートされたイントラネットを構築します。ARM テンプレートには、Azure ネットワーク インフラストラクチャおよび仮想マシンを作成するためのすべての手順およびそれらの構成が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e339a-p101">In this method, you use an Azure Resource Manager (ARM) template to build out the simulated intranet. ARM templates contain all of the instructions to create the Azure networking infrastructure, the virtual machines, and their configuration.</span></span>

<span data-ttu-id="e339a-117">テンプレートを展開する前に「[テンプレートのReadme ページ](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems)」を確認し、次の情報をご用意ください。</span><span class="sxs-lookup"><span data-stu-id="e339a-117">Prior to deploying the template, read through the [template README page](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) and have the following information ready:</span></span>

- <span data-ttu-id="e339a-p102">テスト環境のパブリック DNS ドメイン名 (testlab.\<your public domain>)。[**カスタム デプロイ**] ページの [**ドメイン名**] フィールドにこの名前を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e339a-p102">The public DNS domain name of your test environment (testlab.\<your public domain>). You’ll need to enter this name in the **Domain Name field** of the **Custom deployment** page.</span></span>
- <span data-ttu-id="e339a-p103">仮想マシンのパブリック IP アドレスの URL の DNS ラベル プレフィックス。[**カスタム デプロイ**] ページの [**DNS ラベル プレフィックス**] フィールドにこのラベルを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e339a-p103">A DNS label prefix for the URLs of the public IP addresses of your virtual machines. You’ll need to enter this label in the **Dns Label Prefix** field of the **Custom deployment** page.</span></span>

<span data-ttu-id="e339a-122">手順をすべて確認したら、[[テンプレートの Readme ページ](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems)] で [**Azure に展開**] をクリックして展開を開始します。</span><span class="sxs-lookup"><span data-stu-id="e339a-122">After reading through the instructions, click **Deploy to Azure** on the [template README page](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) to get started.</span></span>

>[!Note]
><span data-ttu-id="e339a-123">ARM テンプレートで作成されたシミュレートされたイントラネットでは、Azure の有料サブスクリプションが必要です。</span><span class="sxs-lookup"><span data-stu-id="e339a-123">The simulated intranet built by the ARM template requires a paid Azure subscription.</span></span>
>

<span data-ttu-id="e339a-124">こちらがテンプレート完了後の構成です。</span><span class="sxs-lookup"><span data-stu-id="e339a-124">Here is your configuration after the template is complete.</span></span>

![Azure インフラストラクチャ サービスでのシミュレートされたイントラネット](media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase3.png)

### <a name="method-2-build-your-simulated-intranet-with-azure-powershell"></a><span data-ttu-id="e339a-126">方法 2: Azure PowerShell を使用してシミュレートされたイントラネットを構築する</span><span class="sxs-lookup"><span data-stu-id="e339a-126">Method 2: Build your simulated intranet with Azure PowerShell</span></span>

<span data-ttu-id="e339a-127">この方法では、Windows PowerShell と Azure PowerShell モジュールを使用してネットワーク インフラストラクチャ、仮想マシン、およびその構成を構築します。</span><span class="sxs-lookup"><span data-stu-id="e339a-127">In this method, you use Windows PowerShell and the Azure PowerShell module to build out the networking infrastructure, the virtual machines, and their configuration.</span></span>

<span data-ttu-id="e339a-p104">Azure インフラストラクチャの要素を作成する作業を、PowerShell を使って 1 つずつ手順を進める方法で経験してみたいという場合は、この方法をお使いください。その後、Azure で他の仮想マシンを展開するために PowerShell コマンドのブロックをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="e339a-p104">Use this method if you want to get experience creating elements of Azure infrastructure one step at a time with PowerShell. You can then customize the PowerShell command blocks for your own deployment of other virtual machines in Azure.</span></span>

#### <a name="step-1-create-dc1"></a><span data-ttu-id="e339a-130">ステップ 1: DC1 を作成する</span><span class="sxs-lookup"><span data-stu-id="e339a-130">Step 1: Create DC1</span></span>

<span data-ttu-id="e339a-131">このステップでは、Azure 仮想ネットワークを作成し、DC1 (AD DS ドメインのドメイン コントローラーである仮想マシン) を追加します。</span><span class="sxs-lookup"><span data-stu-id="e339a-131">In this step, we create an Azure virtual network and add DC1, a virtual machine that is a domain controller for a Windows Server Active Directory (AD) domain.</span></span>

<span data-ttu-id="e339a-132">最初に、ローカル コンピューターで Windows PowerShell コマンド プロンプトを起動します。</span><span class="sxs-lookup"><span data-stu-id="e339a-132">First, start a Windows PowerShell command prompt on your local computer.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e339a-p105">次のコマンド セットは、Azure PowerShell の最新版を使用します。「[Azure の PowerShell コマンドレットを使う](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e339a-p105">The following command sets use the latest version of Azure PowerShell. See [Get started with Azure PowerShell cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/).</span></span> 
  
<span data-ttu-id="e339a-135">次のコマンドを使用して Azure アカウントにログインします。</span><span class="sxs-lookup"><span data-stu-id="e339a-135">Sign in to your Azure account with the following command.</span></span>
  
```
Connect-AzAccount
```

<span data-ttu-id="e339a-136">次のコマンドを使用して、サブスクリプションの名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="e339a-136">Get your subscription name using the following command.</span></span>
  
```
Get-AzSubscription | Sort Name | Select Name
```

<span data-ttu-id="e339a-p106">Azure サブスクリプションを設定します。二重引用符内のすべて (「<」と「>」の文字を含む) を正しい名前に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="e339a-p106">Set your Azure subscription. Replace everything within the quotes, including the < and > characters, with the correct name.</span></span>
  
```
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

<span data-ttu-id="e339a-p107">次に、シミュレートされたエンタープライズ テスト ラボ用の新しいリソース グループを作成します。一意のリソース グループ名を決定するには、このコマンドを使用して既存のリソース グループの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="e339a-p107">Next, create a new resource group for your simulated enterprise test lab. To determine a unique resource group name, use this command to list your existing resource groups.</span></span>
  
```
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

<span data-ttu-id="e339a-p108">これらのコマンドを使用して、新しいリソース グループを作成します。二重引用符内のすべて (< 文字と > 文字を含む) を正しい名前に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="e339a-p108">Create your new resource group with these commands. Replace everything within the quotes, including the < and > characters, with the correct names.</span></span>
  
```
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

<span data-ttu-id="e339a-p109">次に、シミュレートされたエンタープライズ環境の Corpnet サブネットをホストする TestLab 仮想ネットワークを作成し、ネットワーク セキュリティ グループで保護します。リソース グループの名前を入力し、これらのコマンドをローカル コンピューターの PowerShell コマンド プロンプトで実行します。</span><span class="sxs-lookup"><span data-stu-id="e339a-p109">Next, you create the TestLab virtual network that will host the Corpnet subnet of the simulated enterprise environment and protect it with a network security group. Fill in the name of your resource group and run these commands at the PowerShell command prompt on your local computer.</span></span>
  
```
$rgName="<name of your new resource group>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$corpnetSubnet=New-AzVirtualNetworkSubnetConfig -Name Corpnet -AddressPrefix 10.0.0.0/24
New-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName -Location $locName -AddressPrefix 10.0.0.0/8 -Subnet $corpnetSubnet -DNSServer 10.0.0.4
$rule1=New-AzNetworkSecurityRuleConfig -Name "RDPTraffic" -Description "Allow RDP to all VMs on the subnet" -Access Allow -Protocol Tcp -Direction Inbound -Priority 100 -SourceAddressPrefix Internet -SourcePortRange * -DestinationAddressPrefix * -DestinationPortRange 3389
New-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName -Location $locName -SecurityRules $rule1
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name TestLab
$nsg=Get-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name Corpnet -AddressPrefix "10.0.0.0/24" -NetworkSecurityGroup $nsg
```

<span data-ttu-id="e339a-p110">次に、DC1 仮想マシンを作成し、TestLab 仮想ネットワークの仮想マシン用の **testlab.**\<パブリック ドメイン> Active Directory Domain Services (AD DS) と DNS サーバーのドメイン コントローラーとして構成します。たとえば、パブリック ドメイン名が **<span>contoso</span>.com** の場合、DC1 仮想マシンは **<span>testlab</span>.contoso.com** ドメインのドメイン コントローラーになります。</span><span class="sxs-lookup"><span data-stu-id="e339a-p110">Next, you create the DC1 virtual machine and configure it as a domain controller for the **testlab.**\<your public domain> Windows Server AD domain and a DNS server for the virtual machines of the TestLab virtual network. For example, if your public domain name is **<span>contoso</span>.com**, the DC1 virtual machine will be a domain controller for the **<span>testlab</span>.contoso.com** domain.</span></span>
  
<span data-ttu-id="e339a-147">DC1 用の Azure 仮想マシンを作成するには、リソース グループの名前を入力して、次に示すコマンドをローカル コンピューターの PowerShell コマンド プロンプトから実行します。</span><span class="sxs-lookup"><span data-stu-id="e339a-147">To create an Azure virtual machine for DC1, fill in the name of your resource group and run these commands at the PowerShell command prompt on your local computer.</span></span>
  
```
$rgName="<resource group name>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName
$pip=New-AzPublicIpAddress -Name DC1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name DC1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id -PrivateIpAddress 10.0.0.4
$vm=New-AzVMConfig -VMName DC1 -VMSize Standard_A1
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

<span data-ttu-id="e339a-p111">DC1 のローカル管理者アカウントのユーザー名とパスワードを入力するようダイアログが表示されます。強力なパスワードを使用して、安全な場所に名前とパスワードの両方を記録します。</span><span class="sxs-lookup"><span data-stu-id="e339a-p111">You will be prompted for a user name and password for the local administrator account on DC1. Use a strong password and record both the name and password in a secure location.</span></span>
  
<span data-ttu-id="e339a-150">次に、DC1 仮想マシンに接続します。</span><span class="sxs-lookup"><span data-stu-id="e339a-150">Next, connect to the DC1 virtual machine.</span></span>
  
1. <span data-ttu-id="e339a-151">[Azure portal](https://portal.azure.com) で、**[リソース グループ] >**「新しいリソース グループの名前」\*\* > [DC1] > [接続]\*\* の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="e339a-151">In the [Azure portal](https://portal.azure.com), click **Resource Groups >** [the name of your new resource group] **> DC1 > Connect**.</span></span>
    
2. <span data-ttu-id="e339a-p112">起動ウィンドウで **[RDP ファイルのダウンロード]** をクリックします。ダウンロードされる DC1.rdp ファイルを開いてから、**[接続]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e339a-p112">In the open pane, click **Download RDP file**. Open the DC1.rdp file that is downloaded, and then click **Connect**.</span></span>
    
3. <span data-ttu-id="e339a-154">DC1 のローカル管理者アカウント名を指定します。</span><span class="sxs-lookup"><span data-stu-id="e339a-154">Specify the DC1 local administrator account name:</span></span>
    
   - <span data-ttu-id="e339a-155">Windows 7 の場合:</span><span class="sxs-lookup"><span data-stu-id="e339a-155">For Windows 7:</span></span>
    
     <span data-ttu-id="e339a-p113">**[Windows セキュリティ]** ダイアログ ボックスで、**[別のアカウントを使用]** をクリックします。**[ユーザー名]** に「**DC1\\**[ローカル管理者アカウント名]」を入力します。</span><span class="sxs-lookup"><span data-stu-id="e339a-p113">In the **Windows Security** dialog box, click **Use another account**. In **User name**, type **DC1\\**[Local administrator account name].</span></span>
    
   - <span data-ttu-id="e339a-158">Windows 8 または Windows 10 の場合:</span><span class="sxs-lookup"><span data-stu-id="e339a-158">For Windows 8 or Windows 10:</span></span>
    
     <span data-ttu-id="e339a-p114">**[Windows セキュリティ]** ダイアログ ボックスで、**[その他]** をクリックし、**[別のアカウントを使用する]** をクリックします。**[ユーザー名]** に、「**DC1\\**[ローカル管理者アカウント名]」を入力します。</span><span class="sxs-lookup"><span data-stu-id="e339a-p114">In the **Windows Security** dialog box, click **More choices**, and then click **Use a different account**. In **User name**, type **DC1\\**[Local administrator account name].</span></span>
    
4. <span data-ttu-id="e339a-161">**[パスワード]** にローカル管理者アカウントのパスワードを入力して、**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e339a-161">In **Password**, type the password of the local administrator account, and then click **OK**.</span></span>
    
5. <span data-ttu-id="e339a-162">ダイアログが表示されたら、**[はい]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e339a-162">When prompted, click **Yes**.</span></span>
    
<span data-ttu-id="e339a-163">次に、DC1 の管理者レベルの Windows PowerShell コマンド プロンプトで次のコマンドを使用して、新しいボリュームとして別のデータ ディスク (ドライブ文字 F:) を追加します。</span><span class="sxs-lookup"><span data-stu-id="e339a-163">Next, add an extra data disk as a new volume with the drive letter F: with this command at an administrator-level Windows PowerShell command prompt on DC1.</span></span>
  
```
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

<span data-ttu-id="e339a-p115">次に、DC1 を **testlab.**\<パブリック ドメイン> ドメインのドメイン コントローラーと DNS サーバーとして構成します。パブリック ドメイン名を指定し、\< および > 文字を削除します。DC1 の管理者レベルの Windows PowerShell コマンド プロンプトで、これらのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e339a-p115">Next, configure DC1 as a domain controller and DNS server for the **testlab.**\<your public domain> domain. Specify your public domain name, remove the \< and > characters, and then run these commands at an administrator-level Windows PowerShell command prompt on DC1.</span></span>
  
```
$yourDomain="<your public domain>"
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSForest -DomainName testlab.$yourDomain -DatabasePath "F:\NTDS" -SysvolPath "F:\SYSVOL" -LogPath "F:\Logs"
```
<span data-ttu-id="e339a-p116">セーフ モードの管理者パスワードを指定する必要があります。このパスワードは安全な場所に保管してください。</span><span class="sxs-lookup"><span data-stu-id="e339a-p116">You will need to specify a safe mode administrator password. Store this password in a secure location.</span></span>
  
<span data-ttu-id="e339a-168">これらのコマンドの完了には数分かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="e339a-168">Note that these commands can take a few minutes to complete.</span></span>
  
<span data-ttu-id="e339a-169">DC1 の再起動後に、DC1 仮想マシンに再接続します。</span><span class="sxs-lookup"><span data-stu-id="e339a-169">After DC1 restarts, reconnect to the DC1 virtual machine.</span></span>
  
1. <span data-ttu-id="e339a-170">[Azure portal](https://portal.azure.com) で、**[リソース グループ] >**「リソース グループ名」\*\* > [DC1] > [接続]\*\* をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e339a-170">In the [Azure portal](https://portal.azure.com), click **Resource Groups >** [your resource group name] **> DC1 > Connect**.</span></span>
    
2. <span data-ttu-id="e339a-171">ダウンロードされる DC1.rdp ファイルを実行して、**[接続]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e339a-171">Run the DC1.rdp file that is downloaded, and then click **Connect**.</span></span>
    
3. <span data-ttu-id="e339a-p117">**[Windows セキュリティ]** で **[別のアカウントを使用]** をクリックします。**[ユーザー名]** に「**TESTLAB\\**[ローカル管理者アカウント名]」を入力します。</span><span class="sxs-lookup"><span data-stu-id="e339a-p117">In **Windows Security**, click **Use another account**. In **User name**, type **TESTLAB\\**[Local administrator account name].</span></span>
    
4. <span data-ttu-id="e339a-174">**[パスワード]** にローカル管理者アカウントのパスワードを入力して、**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e339a-174">In **Password**, type the password of the local administrator account, and then click **OK**.</span></span>
    
5. <span data-ttu-id="e339a-175">ダイアログが表示されたら、**[はい]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e339a-175">When prompted, click **Yes**.</span></span>
    
<span data-ttu-id="e339a-p118">次に、TESTLAB ドメイン メンバー コンピューターにログインするときに使用する、Active Directory のユーザー アカウントを作成します。管理者レベルの Windows PowerShell コマンド プロンプトで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e339a-p118">Next, create a user account in Active Directory that will be used when logging in to TESTLAB domain member computers. Run this command at an administrator-level Windows PowerShell command prompt.</span></span>
  
```
New-ADUser -SamAccountName User1 -AccountPassword (read-host "Set user password" -assecurestring) -name "User1" -enabled $true -PasswordNeverExpires $true -ChangePasswordAtLogon $false
```

<span data-ttu-id="e339a-p119">このコマンドでは、User1 アカウントのパスワードを入力するよう求められることに注意してください。このアカウントは、すべての TESTLAB ドメイン メンバー コンピューターのリモート デスクトップ接続に使用するため、強力なパスワードを選択してください。User1 アカウントのパスワードを記録し、セキュリティで保護された場所に保管します。</span><span class="sxs-lookup"><span data-stu-id="e339a-p119">Note that this command prompts you to supply the User1 account password. Because this account will be used for remote desktop connections for all TESTLAB domain member computers, choose a strong password. Record the User1 account password and store it in a secured location.</span></span>
  
<span data-ttu-id="e339a-p120">次に、ドメイン、エンタープライズ、およびスキーマ管理者として新しい User1 のアカウントを構成します。管理者レベルの Windows PowerShell コマンド プロンプトで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e339a-p120">Next, configure the new User1 account as a domain, enterprise, and schema administrator. Run this command at the administrator-level Windows PowerShell command prompt.</span></span>
  
```
$yourDomain="<your public domain>"
$domainName = "testlab"+$yourDomain
$userName="user1@" + $domainName
$userSID=(New-Object System.Security.Principal.NTAccount($userName)).Translate([System.Security.Principal.SecurityIdentifier]).Value
$groupNames=@("Domain Admins","Enterprise Admins","Schema Admins")
ForEach ($name in $groupNames) {Add-ADPrincipalGroupMembership -Identity $userSID -MemberOf (Get-ADGroup -Identity $name).SID.Value}
```

<span data-ttu-id="e339a-183">DC1 とのリモート デスクトップ セッションを終了し、TESTLAB\\User1 のアカウントを使用して再接続します。</span><span class="sxs-lookup"><span data-stu-id="e339a-183">Close the Remote Desktop session with DC1 and then reconnect using the TESTLAB\\User1 account.</span></span>
  
<span data-ttu-id="e339a-184">次に、Ping ツールのトラフィックを許可するため、管理者レベルの Windows PowerShell コマンド プロンプトで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e339a-184">Next, to allow traffic for the Ping tool, run this command at an administrator-level Windows PowerShell command prompt.</span></span>
  
```
Set-NetFirewallRule -DisplayName "File and Printer Sharing (Echo Request - ICMPv4-In)" -enabled True
```

<span data-ttu-id="e339a-185">こちらが現在の構成です。</span><span class="sxs-lookup"><span data-stu-id="e339a-185">This is your current configuration.</span></span>
  
![シミュレートされたエンタープライズ基本構成のステップ 1](media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase1.png)
  
#### <a name="step-2-configure-app1"></a><span data-ttu-id="e339a-187">ステップ 2: APP1 を構成する</span><span class="sxs-lookup"><span data-stu-id="e339a-187">Step 2: Configure APP1</span></span>

<span data-ttu-id="e339a-188">このステップでは、最初にWeb およびファイル共有サービスを提供するアプリケーション サーバーである APP1 を作成して構成します。</span><span class="sxs-lookup"><span data-stu-id="e339a-188">In this step, you create and configure APP1, which is an application server that initially provides web and file sharing services.</span></span>

<span data-ttu-id="e339a-189">APP1 用の Azure 仮想マシンを作成するには、リソース グループの名前を入力して、次に示すコマンドをローカル コンピューターのコマンド プロンプトから実行します。</span><span class="sxs-lookup"><span data-stu-id="e339a-189">To create an Azure Virtual Machine for APP1, fill in the name of your resource group and run these commands at the  command prompt on your local computer.</span></span>
  
```
$rgName="<resource group name>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName
$pip=New-AzPublicIpAddress -Name APP1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name APP1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id
$vm=New-AzVMConfig -VMName APP1 -VMSize Standard_A1
$cred=Get-Credential -Message "Type the name and password of the local administrator account for APP1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName APP1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "APP1-OS" -DiskSizeInGB 128 -CreateOption FromImage
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

<span data-ttu-id="e339a-190">次に、APP1 のローカル管理者アカウント名とパスワードを使用して APP1 仮想マシンに接続し、Windows PowerShell コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="e339a-190">Next, connect to the APP1 virtual machine using the APP1 local administrator account name and password, and then open a Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="e339a-191">APP1 と DC1 の間の名前の解決とネットワーク通信を確認するには、**ping dc1.testlab.**\<パブリック ドメイン名> コマンドを実行し、4 つの応答があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e339a-191">To check name resolution and network communication between APP1 and DC1, run the **ping dc1.testlab.**\<your public domain name> command and verify that there are four replies.</span></span>
  
<span data-ttu-id="e339a-192">次に、Windows PowerShell プロンプトでこれらのコマンドを使用して、APP1 仮想マシンを TESTLAB ドメインに参加させます。</span><span class="sxs-lookup"><span data-stu-id="e339a-192">Next, join the APP1 virtual machine to the TESTLAB domain with these commands at the Windows PowerShell prompt.</span></span>
  
```
$yourDomain="<your public domain name>"
Add-Computer -DomainName ("testlab" + $yourDomain)
Restart-Computer
```

<span data-ttu-id="e339a-193">**Add-Computer** コマンドの実行後には、TESTLAB\\User1 ドメイン アカウントの資格情報を入力する必要がある点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="e339a-193">Note that you must supply the TESTLAB\\User1 domain account credentials after running the **Add-Computer** command.</span></span>
  
<span data-ttu-id="e339a-194">APP1 の再起動後に、TESTLAB\\User1 のアカウントを使用して接続し、管理者レベルの Windows PowerShell コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="e339a-194">After APP1 restarts, connect to it using the TESTLAB\\User1 account, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="e339a-195">次に、このコマンドを APP1 の管理者レベルの Windows PowerShell コマンド プロンプトで使用して、APP1 を Web サーバーにします。</span><span class="sxs-lookup"><span data-stu-id="e339a-195">Next, make APP1 a web server with this command at an administrator-level Windows PowerShell command prompt on APP1.</span></span>
  
```
Install-WindowsFeature Web-WebServer -IncludeManagementTools
```

<span data-ttu-id="e339a-196">次に、以下の PowerShell コマンドを使用して APP1 で共有フォルダーを作成し、そのフォルダー内にテキスト ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="e339a-196">Next, create a shared folder and a text file within the folder on APP1 with these PowerShell commands.</span></span>
  
```
New-Item -path c:\files -type directory
Write-Output "This is a shared file." | out-file c:\files\example.txt
New-SmbShare -name files -path c:\files -changeaccess TESTLAB\User1
```

<span data-ttu-id="e339a-197">こちらが現在の構成です。</span><span class="sxs-lookup"><span data-stu-id="e339a-197">This is your current configuration.</span></span>
  
![シミュレートされたエンタープライズ基本構成のステップ 2](media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase2.png)
  
#### <a name="step-3-configure-client1"></a><span data-ttu-id="e339a-199">ステップ 3: CLIENT1 を構成する</span><span class="sxs-lookup"><span data-stu-id="e339a-199">Step 3: Configure CLIENT1</span></span>

<span data-ttu-id="e339a-200">このステップでは、イントラネット上の一般的なラップトップ、タブレット、またはデスクトップ コンピューターとして機能する CLIENT1 を作成して構成します。</span><span class="sxs-lookup"><span data-stu-id="e339a-200">In this step, you create and configure CLIENT1, which acts as a typical laptop, tablet, or desktop computer on the intranet.</span></span>

> [!NOTE]  
> <span data-ttu-id="e339a-p121">次のコマンド セットでは、Windows Server 2016 Datacenter を実行する CLIENT1 を作成します。これは、すべての Azure サブスクリプションのタイプに対して実行できます。Visual Studio ベースの Azure サブスクリプションがある場合は、[Azure portal](https://portal.azure.com) で、Windows 10 を実行する CLIENT1 を作成できます。</span><span class="sxs-lookup"><span data-stu-id="e339a-p121">The following command set creates CLIENT1 running Windows Server 2016 Datacenter, which can be done for all types of Azure subscriptions. If you have an Visual Studio-based Azure subscription, you can create CLIENT1 running Windows 10 with the [Azure portal](https://portal.azure.com).</span></span> 
  
<span data-ttu-id="e339a-203">CLIENT1 用の Azure 仮想マシンを作成するには、リソース グループの名前を入力して、次に示すコマンドをローカル コンピューターのコマンド プロンプトから実行します。</span><span class="sxs-lookup"><span data-stu-id="e339a-203">To create an Azure Virtual Machine for CLIENT1, fill in the name of your resource group and run these commands at the  command prompt on your local computer.</span></span>
  
```
$rgName="<resource group name>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName
$pip=New-AzPublicIpAddress -Name CLIENT1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name CLIENT1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id
$vm=New-AzVMConfig -VMName CLIENT1 -VMSize Standard_A1
$cred=Get-Credential -Message "Type the name and password of the local administrator account for CLIENT1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName CLIENT1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "CLIENT1-OS" -DiskSizeInGB 128 -CreateOption FromImage
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

<span data-ttu-id="e339a-204">次に、CLIENT1 のローカル管理者アカウント名とパスワードを使用して、CLIENT1 仮想マシンに接続し、管理者レベルの Windows PowerShell コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="e339a-204">Next, connect to the CLIENT1 virtual machine using the CLIENT1 local administrator account name and password, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="e339a-205">CLIENT1 と DC1 の間の名前の解決とネットワーク通信を確認するには、Windows PowerShell コマンド プロンプトで **ping dc1.testlab.**\<パブリック ドメイン名> コマンドを実行し、4 つの応答があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e339a-205">To check name resolution and network communication between CLIENT1 and DC1, run the **ping dc1.testlab.**\<your public domain name> command at a Windows PowerShell command prompt and verify that there are four replies.</span></span>
  
<span data-ttu-id="e339a-206">次に、Windows PowerShell プロンプトでこれらのコマンドを使用して、CLIENT1 仮想マシンを TESTLAB ドメインに参加させます。</span><span class="sxs-lookup"><span data-stu-id="e339a-206">Next, join the CLIENT1 virtual machine to the TESTLAB domain with these commands at the Windows PowerShell prompt.</span></span>
  
```
$yourDomain="<your public domain name>"
Add-Computer -DomainName ("testlab" + $yourDomain)
Restart-Computer
```

<span data-ttu-id="e339a-207">**Add-Computer** コマンドの実行後に、TESTLAB\\User1 ドメイン アカウントの資格情報を入力する必要がある点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="e339a-207">Note that you must supply your TESTLAB\\User1 domain account credentials after running the **Add-Computer** command.</span></span>
  
<span data-ttu-id="e339a-208">CLIENT1 の再起動後に、TESTLAB\\User1 のアカウント名とパスワードを使用して接続し、管理者レベルの Windows PowerShell コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="e339a-208">After CLIENT1 restarts, connect to it using the TESTLAB\\User1 account name and password, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="e339a-209">次に、CLIENT1 から APP1 の Web リソースおよびファイル共有リソースにアクセスできることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e339a-209">Next, verify that you can access web and file share resources on APP1 from CLIENT1.</span></span>
  
1. <span data-ttu-id="e339a-210">サーバー マネージャーのツリー ウィンドウで、**[ローカル サーバー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e339a-210">In Server Manager, in the tree pane, click **Local Server**.</span></span>
    
2. <span data-ttu-id="e339a-211">**[CLIENT1 のプロパティ]** で、**[IE セキュリティ強化の構成]** の横にある **[オン]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e339a-211">In **Properties for CLIENT1**, click **On** next to **IE Enhanced Security Configuration**.</span></span>
    
3. <span data-ttu-id="e339a-212">**[Internet Explorer セキュリティ強化の構成]** で、**[管理者]** と **[ユーザー]** の **[オフ]** をクリックしてから、**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e339a-212">In **Internet Explorer Enhanced Security Configuration**, click **Off** for **Administrators** and **Users**, and then click **OK**.</span></span>
    
4. <span data-ttu-id="e339a-213">スタート画面で、**[Internet Explorer]** をクリックし、**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e339a-213">From the Start screen, click **Internet Explorer**, and then click **OK**.</span></span>
    
5. <span data-ttu-id="e339a-p122">アドレス バーに「**http<span>://</span>app1.testab.**\<パブリック ドメイン名>**/**」と入力し、ENTER キーを押します。APP1 の既定のインターネット インフォメーション サービスの Web ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e339a-p122">In the Address bar, type **http<span>://</span>app1.testab.**\<your public domain name>**/**, and then press ENTER. You should see the default Internet Information Services web page for APP1.</span></span>
    
6. <span data-ttu-id="e339a-216">デスクトップのタスクバーで、[エクスプローラー] アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e339a-216">From the desktop taskbar, click the File Explorer icon.</span></span>
    
7. <span data-ttu-id="e339a-p123">アドレス バーに「**\\\\app1\\Files**」と入力して、ENTER キーを押します。フォルダー ウィンドウにファイルの共有フォルダーのコンテンツが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e339a-p123">In the address bar, type **\\\\app1\\Files**, and then press ENTER. You should see a folder window with the contents of the Files shared folder.</span></span>
    
8. <span data-ttu-id="e339a-p124">**[ファイル]** の共有フォルダー ウィンドウで、**[Example.txt]** ファイルをダブルクリックします。Example.txt ファイルのコンテンツが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e339a-p124">In the **Files** shared folder window, double-click the **Example.txt** file. You should see the contents of the Example.txt file.</span></span>
    
9. <span data-ttu-id="e339a-221">**[example.txt - メモ帳]** と **[ファイル]** の共有フォルダーのウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="e339a-221">Close the **example.txt - Notepad** and the **Files** shared folder windows.</span></span>
    
<span data-ttu-id="e339a-222">こちらが現在の構成です。</span><span class="sxs-lookup"><span data-stu-id="e339a-222">This is your current configuration.</span></span>
  
![シミュレートされたエンタープライズ基本構成のステップ 3](media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase3.png)


## <a name="phase-2-create-your-office-365-e5-and-ems-e5-subscriptions"></a><span data-ttu-id="e339a-224">フェーズ 2: Office 365 E5 および EMS E5 のサブスクリプションを作成する</span><span class="sxs-lookup"><span data-stu-id="e339a-224">Phase 2: Create your Office 365 E5 and EMS E5 subscriptions</span></span>

<span data-ttu-id="e339a-p125">このフェーズでは、新しい共通の Azure AD テナントを使用する Office 365 E5 および EMS E5 サブスクリプション (運用サブスクリプションとは別のもの) を作成します。これは、次の 2 つの方法で作成できます。</span><span class="sxs-lookup"><span data-stu-id="e339a-p125">In this phase, you create new Office 365 E5 and EMS E5 subscriptions that use a new and common Azure AD tenant, one that is separate from your production subscription. You can do this in two ways:</span></span>

- <span data-ttu-id="e339a-227">Office 365 E5 および EMS E5 の試用版サブスクリプションを使用する。</span><span class="sxs-lookup"><span data-stu-id="e339a-227">Use trial subscriptions of Office 365 E5 and EMS E5.</span></span> 

  <span data-ttu-id="e339a-p126">Office 365 E5 の試用版サブスクリプションは 30 日間有効です。この有効期間は、簡単に 60 日間延長できます。EMS E5 試用版サブスクリプションは 90 日間有効です。試用版サブスクリプションの有効期限が切れたときには、有料版のサブスクリプションに切り替えるか、新しい試用版サブスクリプションを作成する必要があります。新しい試用版サブスクリプションを作成すると、複雑なシナリオが含まれていることもある構成を放置することになります。</span><span class="sxs-lookup"><span data-stu-id="e339a-p126">The Office 365 E5 trial subscription is 30 days, which can be easily extended to 60 days. The EMS E5 trial subscription is 90 days. When the trial subscriptions expire, you must either convert them to paid subscriptions or create new trial subscriptions. Creating new trial subscriptions means you will leave your configuration, which could include complex scenarios, behind.</span></span>  
- <span data-ttu-id="e339a-232">ライセンス数の少ない Microsoft 365 Enterprise の個別の運用サブスクリプションを使用する。</span><span class="sxs-lookup"><span data-stu-id="e339a-232">Use a separate production subscription of Microsoft 365 Enterprise with a small number of licenses.</span></span>

  <span data-ttu-id="e339a-p127">これには追加のコストが発生しますが、機能、構成、およびシナリオをテストするための期限切れのない実働テスト環境を確実に保持できます。この 1 つのテスト環境は、概念実証、同僚や経営者に向けたデモンストレーション、およびアプリケーションの開発とテストのために長期にわたって使用できます。この方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e339a-p127">This is an additional cost, but ensures that you have a working test environment to try features, configurations, and scenarios that does not expire. You can use the same test environment over the long term for proofs of concept, demonstration to peers and management, and application development and testing. This is the recommended method.</span></span>

### <a name="use-trial-subscriptions"></a><span data-ttu-id="e339a-236">試用版サブスクリプションの使用</span><span class="sxs-lookup"><span data-stu-id="e339a-236">Use trial subscriptions</span></span>

<span data-ttu-id="e339a-237">試用版サブスクリプションを使用する必要がある場合は、「[Office 365 開発/テスト環境](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment)」のフェーズ 2 とフェーズ 3 の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e339a-237">If you must use trial subscriptions, follow the steps in Phase 2 and Phase 3 of the [Office 365 dev/test environment](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment).</span></span>
  
<span data-ttu-id="e339a-238">次に、EMS E5 試用版サブスクリプションにサインアップして、Office 365 E5 サブスクリプションと同じ組織に追加します。</span><span class="sxs-lookup"><span data-stu-id="e339a-238">Next, you sign up for the EMS E5 trial subscription and add it to the same organization as your Office 365 E5 subscription.</span></span>
  
<span data-ttu-id="e339a-239">最初に、EMS E5 試用版サブスクリプションを追加して、EMS ライセンスを全体管理者アカウントに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="e339a-239">First, add the EMS E5 trial subscription and assign an EMS license to your global administrator account.</span></span>
  
1. <span data-ttu-id="e339a-p128">インターネット ブラウザーのプライベート インスタンスで、全体管理者アカウントの資格情報を使用して、Office ポータルにサインインします。ヘルプについては、「[Office 365 にサインインする場所](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e339a-p128">With a private instance of an Internet browser, sign in to the Office portal with your global administrator account credentials. For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="e339a-242">**[管理者]** タイルをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e339a-242">Click the **Admin** tile.</span></span>
    
3. <span data-ttu-id="e339a-243">ブラウザーの **[Microsoft 365 管理センター]** タブの、左側のナビゲーションで **[請求] > [サービスを購入する]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="e339a-243">On the **Office Admin center** tab in your browser, in the left navigation, click **Billing > Purchase services**.</span></span>
    
4. <span data-ttu-id="e339a-p129">**[サービスを購入]** ページで、 **[Enterprise Mobility + Security E5]** 項目を探します。その項目の上にマウス ポインターを移動させ、 **[無料試用版を起動する]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e339a-p129">On the **Purchase services** page, find the **Enterprise Mobility + Security E5** item. Hover your mouse pointer over it and click **Start free trial**.</span></span>
    
5. <span data-ttu-id="e339a-246">**[注文の確認]** ページで、 **[今すぐ実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e339a-246">On the **Confirm your order** page, click **Try now**.</span></span>
    
6. <span data-ttu-id="e339a-247">**[注文の受領書]** ページで、**[続行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e339a-247">On the **Order receipt** page, click **Continue**.</span></span>
    
7. <span data-ttu-id="e339a-248">ブラウザーの **[Office 365 管理センター]** タブの左側のナビゲーションで **[ユーザー] > [アクティブなユーザー]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="e339a-248">On the **Office 365 Admin center** tab in your browser, in the left navigation, click **Users > Active users**.</span></span>
    
8. <span data-ttu-id="e339a-249">全体管理者アカウントをクリックしてから、 **[製品ライセンス]** で **[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e339a-249">Click your global administrator account, and then click **Edit** for **Product licenses**.</span></span>
    
9. <span data-ttu-id="e339a-250">**[製品ライセンス]** ウィンドウで、 **Enterprise Mobility + Security E5** の製品ライセンスを **[オン]** にして、 **[保存]** をクリックしてから、 **[閉じる]** を 2 回クリックします。</span><span class="sxs-lookup"><span data-stu-id="e339a-250">On the **Product licenses** pane, turn the product license for **Enterprise Mobility + Security E5** to **On**, click **Save,** and then click **Close** twice.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="e339a-251">永続的なテスト環境では、少数のライセンスを使用して新しい有料サブスクリプションを作成します。</span><span class="sxs-lookup"><span data-stu-id="e339a-251">For a permanent test environment, create a new permanent subscription with a small number of licenses.</span></span> 
  
<span data-ttu-id="e339a-252">次に、その他のすべてのアカウント (User 2、User 3、User 4、および User 5) に前述の手順 8 と手順 9 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="e339a-252">Next, repeat steps 8 and 9 of the previous procedure for all of your other accounts (User 2, User 3, User 4, and User 5).</span></span>
  
### <a name="results"></a><span data-ttu-id="e339a-253">結果</span><span class="sxs-lookup"><span data-stu-id="e339a-253">Results</span></span>

<span data-ttu-id="e339a-254">テスト環境は、次のようになっています。</span><span class="sxs-lookup"><span data-stu-id="e339a-254">Your test environment now has:</span></span>
  
- <span data-ttu-id="e339a-255">Office 365 E5 Enterprise と EMS E5 の試用版サブスクリプションが、ユーザー アカウントの一覧と同じ Azure AD テナントを共有している。</span><span class="sxs-lookup"><span data-stu-id="e339a-255">Office 365 E5 Enterprise and EMS E5 trial subscriptions sharing the same Azure AD tenant with your list of user accounts.</span></span>
- <span data-ttu-id="e339a-256">すべての適切なアカウント (全体管理者のみまたは 5 つすべてのユーザー アカウントのどちらか) が、Office 365 E5 と EMS E5 を使用できるようになっている。</span><span class="sxs-lookup"><span data-stu-id="e339a-256">All your appropriate user accounts (either just the global administrator or all five user accounts) are enabled to use Office 365 E5 and EMS E5.</span></span>
    
<span data-ttu-id="e339a-257">これは、最終的な構成です。</span><span class="sxs-lookup"><span data-stu-id="e339a-257">This is your final configuration.</span></span>
  
![シミュレートされたエンタープライズ基本構成のフェーズ 4](media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase4.png)
  
<span data-ttu-id="e339a-259">これで、[Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise) の追加機能を試せるようになりました。</span><span class="sxs-lookup"><span data-stu-id="e339a-259">You are now ready to experiment with additional features of [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="e339a-260">次の手順</span><span class="sxs-lookup"><span data-stu-id="e339a-260">Next steps</span></span>

<span data-ttu-id="e339a-261">こうした追加のテスト ラボ ガイドについて説明します。</span><span class="sxs-lookup"><span data-stu-id="e339a-261">Explore these additional sets of Test Lab Guides:</span></span>
  
- [<span data-ttu-id="e339a-262">ID</span><span class="sxs-lookup"><span data-stu-id="e339a-262">Identity</span></span>](m365-enterprise-test-lab-guides.md#identity)
- [<span data-ttu-id="e339a-263">モバイル デバイス管理</span><span class="sxs-lookup"><span data-stu-id="e339a-263">Mobile device management</span></span>](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [<span data-ttu-id="e339a-264">情報保護</span><span class="sxs-lookup"><span data-stu-id="e339a-264">Information protection</span></span>](m365-enterprise-test-lab-guides.md#information-protection)

## <a name="see-also"></a><span data-ttu-id="e339a-265">関連項目</span><span class="sxs-lookup"><span data-stu-id="e339a-265">See also</span></span>

[<span data-ttu-id="e339a-266">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="e339a-266">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="e339a-267">Microsoft 365 Enterprise を展開する</span><span class="sxs-lookup"><span data-stu-id="e339a-267">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="e339a-268">Microsoft 365 Enterprise のドキュメントとリソース</span><span class="sxs-lookup"><span data-stu-id="e339a-268">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
