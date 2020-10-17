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
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: 6f916a77-301c-4be2-b407-6cec4d80df76
description: このテストラボガイドを使用して、エンタープライズ向けの Microsoft 365 用にシミュレートされたエンタープライズテスト環境を作成します。
ms.openlocfilehash: e66ec8c48e309daeb15aad5fcc475edcb2b8bb35
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487662"
---
# <a name="the-simulated-enterprise-base-configuration"></a><span data-ttu-id="e7d34-103">シミュレートされたエンタープライズ基本構成</span><span class="sxs-lookup"><span data-stu-id="e7d34-103">The simulated enterprise base configuration</span></span>

<span data-ttu-id="e7d34-104">*このテストラボガイドは、Microsoft 365 for enterprise および Office 365 エンタープライズテスト環境の両方で使用できます。*</span><span class="sxs-lookup"><span data-stu-id="e7d34-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="e7d34-105">この記事では、次のものを含む、Microsoft 365 for enterprise の簡略化された環境を作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e7d34-105">This article describes how to create a simplified environment for Microsoft 365 for enterprise that includes:</span></span>

- <span data-ttu-id="e7d34-106">Microsoft 365 E5 の試用版または有料サブスクリプション。</span><span class="sxs-lookup"><span data-stu-id="e7d34-106">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="e7d34-107">インターネットに接続された、シンプルな組織イントラネット。 Azure 仮想ネットワーク上の3つの仮想マシン (DC1、CLIENT1、および CLIENT1) で構成されます。</span><span class="sxs-lookup"><span data-stu-id="e7d34-107">A simplified organization intranet connected to the internet, consisting of three virtual machines on an Azure virtual network (DC1, APP1, and CLIENT1).</span></span>
 
![シミュレートされたエンタープライズ基本構成](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase4.png)

<span data-ttu-id="e7d34-109">簡単なテスト環境を作成するには、次の2つのフェーズが必要です。</span><span class="sxs-lookup"><span data-stu-id="e7d34-109">Creating a simplified test environment involves two phases:</span></span>
- [<span data-ttu-id="e7d34-110">フェーズ 1: シミュレートされたイントラネットを作成する</span><span class="sxs-lookup"><span data-stu-id="e7d34-110">Phase 1: Create a simulated intranet</span></span>](#phase-1-create-a-simulated-intranet)
- [<span data-ttu-id="e7d34-111">フェーズ 2: Microsoft 365 E5 サブスクリプションを作成する</span><span class="sxs-lookup"><span data-stu-id="e7d34-111">Phase 2: Create your Microsoft 365 E5 subscription</span></span>](#phase-2-create-your-microsoft-365-e5-subscription)

<span data-ttu-id="e7d34-112">結果として得られた環境を使用して、 [Microsoft 365 for enterprise](https://www.microsoft.com/microsoft-365/enterprise) の機能を、追加の [テストラボガイド](m365-enterprise-test-lab-guides.md) または独自にテストすることができます。</span><span class="sxs-lookup"><span data-stu-id="e7d34-112">You can use the resulting environment to test the features and functionality of [Microsoft 365 for enterprise](https://www.microsoft.com/microsoft-365/enterprise) with additional [Test Lab Guides](m365-enterprise-test-lab-guides.md) or on your own.</span></span>

![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="e7d34-114">Microsoft 365 for enterprise のテストラボガイドスタックに含まれるすべての記事のビジュアルマップについては、「 [microsoft 365 for enterprise のテストラボガイドスタック](../downloads/Microsoft365EnterpriseTLGStack.pdf)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7d34-114">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-create-a-simulated-intranet"></a><span data-ttu-id="e7d34-115">フェーズ 1: シミュレートされたイントラネットを作成する</span><span class="sxs-lookup"><span data-stu-id="e7d34-115">Phase 1: Create a simulated intranet</span></span>

<span data-ttu-id="e7d34-116">このフェーズでは、Active Directory ドメインサービス (AD DS) ドメインコントローラー、アプリケーションサーバー、およびクライアントコンピューターを含む、Azure インフラストラクチャサービスでシミュレートされたイントラネットを構築します。</span><span class="sxs-lookup"><span data-stu-id="e7d34-116">In this phase, build a simulated intranet in Azure infrastructure services that includes an Active Directory Domain Services (AD DS) domain controller, an application server, and a client computer.</span></span>

<span data-ttu-id="e7d34-117">ハイブリッド id およびその他の機能を構成してデモンストレーションするには、これらのコンピューターを追加 [の Microsoft 365 for enterprise のテストラボガイド](m365-enterprise-test-lab-guides.md) に使用します。</span><span class="sxs-lookup"><span data-stu-id="e7d34-117">You'll use these computers in additional [Microsoft 365 for enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md) to configure and demonstrate hybrid identity and other capabilities.</span></span>

### <a name="method-1-build-your-simulated-intranet-with-an-azure-resource-manager-template"></a><span data-ttu-id="e7d34-118">方法 1: Azure Resource Manager テンプレートを使用して、シミュレートされたイントラネットを構築する</span><span class="sxs-lookup"><span data-stu-id="e7d34-118">Method 1: Build your simulated intranet with an Azure Resource Manager template</span></span>

<span data-ttu-id="e7d34-119">この方法では、Azure Resource Manager テンプレートを使用して、シミュレートされたイントラネットを構築します。</span><span class="sxs-lookup"><span data-stu-id="e7d34-119">In this method, you use an Azure Resource Manager template to build out the simulated intranet.</span></span> <span data-ttu-id="e7d34-120">Azure リソースマネージャーテンプレートには、Azure ネットワークインフラストラクチャ、仮想マシン、およびそれらの構成を作成するためのすべての手順が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e7d34-120">Azure Resource Manager templates contain all of the instructions to create the Azure networking infrastructure, the virtual machines, and their configuration.</span></span>

<span data-ttu-id="e7d34-121">テンプレートを展開する前に、 [テンプレートの README ページ](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) に目を通し、次の情報を準備しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7d34-121">Before deploying the template, read through the [template README page](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) and have the following information ready:</span></span>

- <span data-ttu-id="e7d34-122">テスト環境のパブリック DNS ドメイン名 (testlab. \<*your public domain*> )。</span><span class="sxs-lookup"><span data-stu-id="e7d34-122">The public DNS domain name of your test environment (testlab.\<*your public domain*>).</span></span> <span data-ttu-id="e7d34-123">この名前は、[**カスタム展開**] ページの [**ドメイン名**] フィールドに入力します。</span><span class="sxs-lookup"><span data-stu-id="e7d34-123">You'll enter this name in the **Domain Name** field of the **Custom deployment** page.</span></span>
- <span data-ttu-id="e7d34-p103">仮想マシンのパブリック IP アドレスの URL の DNS ラベル プレフィックス。[**カスタム デプロイ**] ページの [**DNS ラベル プレフィックス**] フィールドにこのラベルを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7d34-p103">A DNS label prefix for the URLs of the public IP addresses of your virtual machines. You'll need to enter this label in the **Dns Label Prefix** field of the **Custom deployment** page.</span></span>

<span data-ttu-id="e7d34-126">指示に従って読み終えたら、[テンプレートの README ページ](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems)にある [ **Azure に展開**する] を選択して開始します。</span><span class="sxs-lookup"><span data-stu-id="e7d34-126">After you read through the instructions, select **Deploy to Azure** on the [template README page](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) to get started.</span></span>

>[!Note]
><span data-ttu-id="e7d34-127">Azure Resource Manager テンプレートによって作成されたシミュレートされたイントラネットには、Azure の有料サブスクリプションが必要です。</span><span class="sxs-lookup"><span data-stu-id="e7d34-127">The simulated intranet built by the Azure Resource Manager template requires a paid Azure subscription.</span></span>

<span data-ttu-id="e7d34-128">テンプレートが完成すると、構成は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="e7d34-128">After the template is complete, your configuration looks like this:</span></span>

![Azure インフラストラクチャ サービスでのシミュレートされたイントラネット](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase3.png)

### <a name="method-2-build-your-simulated-intranet-with-azure-powershell"></a><span data-ttu-id="e7d34-130">方法 2: Azure PowerShell を使用してシミュレートされたイントラネットを構築する</span><span class="sxs-lookup"><span data-stu-id="e7d34-130">Method 2: Build your simulated intranet with Azure PowerShell</span></span>

<span data-ttu-id="e7d34-131">この方法では、Windows PowerShell と Azure PowerShell モジュールを使用してネットワーク インフラストラクチャ、仮想マシン、およびその構成を構築します。</span><span class="sxs-lookup"><span data-stu-id="e7d34-131">In this method, you use Windows PowerShell and the Azure PowerShell module to build out the networking infrastructure, the virtual machines, and their configuration.</span></span>

<span data-ttu-id="e7d34-p104">Azure インフラストラクチャの要素を作成する作業を、PowerShell を使って 1 つずつ手順を進める方法で経験してみたいという場合は、この方法をお使いください。その後、Azure で他の仮想マシンを展開するために PowerShell コマンドのブロックをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="e7d34-p104">Use this method if you want to get experience creating elements of Azure infrastructure one step at a time with PowerShell. You can then customize the PowerShell command blocks for your own deployment of other virtual machines in Azure.</span></span>

#### <a name="step-1-create-dc1"></a><span data-ttu-id="e7d34-134">ステップ 1: DC1 を作成する</span><span class="sxs-lookup"><span data-stu-id="e7d34-134">Step 1: Create DC1</span></span>

<span data-ttu-id="e7d34-135">この手順では、Azure 仮想ネットワークを作成し、DC1 (AD DS ドメインのドメインコントローラーである仮想マシン) を追加します。</span><span class="sxs-lookup"><span data-stu-id="e7d34-135">In this step, you create an Azure virtual network and add DC1, a virtual machine that is a domain controller for an AD DS domain.</span></span>

<span data-ttu-id="e7d34-136">最初に、ローカル コンピューターで Windows PowerShell コマンド プロンプトを起動します。</span><span class="sxs-lookup"><span data-stu-id="e7d34-136">First, start a Windows PowerShell command prompt on your local computer.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e7d34-p105">次のコマンド セットは、Azure PowerShell の最新版を使用します。「[Azure の PowerShell コマンドレットを使う](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7d34-p105">The following command sets use the latest version of Azure PowerShell. See [Get started with Azure PowerShell cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/).</span></span> 
  
<span data-ttu-id="e7d34-139">次のコマンドを使用して Azure アカウントにログインします。</span><span class="sxs-lookup"><span data-stu-id="e7d34-139">Sign in to your Azure account with the following command.</span></span>
  
```powershell
Connect-AzAccount
```

<span data-ttu-id="e7d34-140">次のコマンドを使用して、サブスクリプションの名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="e7d34-140">Get your subscription name using the following command.</span></span>
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

<span data-ttu-id="e7d34-141">Azure サブスクリプションを設定します。</span><span class="sxs-lookup"><span data-stu-id="e7d34-141">Set your Azure subscription.</span></span> <span data-ttu-id="e7d34-142">二重引用符で囲まれたすべての要素 ("<" と ">") が正しい名前に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="e7d34-142">Replace everything within the quotation marks, including the angle brackets ("<" and ">"), with the correct name.</span></span>
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

<span data-ttu-id="e7d34-p107">次に、シミュレートされたエンタープライズ テスト ラボ用の新しいリソース グループを作成します。一意のリソース グループ名を決定するには、このコマンドを使用して既存のリソース グループの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="e7d34-p107">Next, create a new resource group for your simulated enterprise test lab. To determine a unique resource group name, use this command to list your existing resource groups.</span></span>
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

<span data-ttu-id="e7d34-145">これらのコマンドを使用して、新しいリソース グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="e7d34-145">Create your new resource group with these commands.</span></span> <span data-ttu-id="e7d34-146">二重引用符で囲まれたすべての要素を正しい名前で置き換えます。</span><span class="sxs-lookup"><span data-stu-id="e7d34-146">Replace everything within the quotation marks, including the angle brackets, with the correct names.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

<span data-ttu-id="e7d34-147">次に、シミュレートされたエンタープライズ環境の企業ネットワークサブネットをホストする TestLab 仮想ネットワークを作成し、ネットワークセキュリティグループで保護します。</span><span class="sxs-lookup"><span data-stu-id="e7d34-147">Next, create the TestLab virtual network that will host the corporate network subnet of the simulated enterprise environment and protect it with a network security group.</span></span> <span data-ttu-id="e7d34-148">リソースグループの名前を入力し、ローカルコンピューターの PowerShell コマンドプロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e7d34-148">Fill in the name of your resource group and run these commands at the PowerShell command prompt on your local computer.</span></span>
  
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

<span data-ttu-id="e7d34-p110">次に、DC1 仮想マシンを作成し、Testlab 仮想ネットワークの仮想マシン用の **testlab.**\<your public domain> AD DS ドメインと DNS サーバーのドメイン コントローラーとして構成します。たとえば、パブリック ドメイン名が **<span>contoso</span>.com** の場合、DC1 仮想マシンは **<span>testlab</span>.contoso.com** ドメインのドメイン コントローラーになります。</span><span class="sxs-lookup"><span data-stu-id="e7d34-p110">Next, you create the DC1 virtual machine and configure it as a domain controller for the **testlab.**\<your public domain> AD DS domain and a DNS server for the virtual machines of the TestLab virtual network. For example, if your public domain name is **<span>contoso</span>.com**, the DC1 virtual machine will be a domain controller for the **<span>testlab</span>.contoso.com** domain.</span></span>
  
<span data-ttu-id="e7d34-152">DC1 用の Azure 仮想マシンを作成するには、リソース グループの名前を入力して、次に示すコマンドをローカル コンピューターの PowerShell コマンド プロンプトから実行します。</span><span class="sxs-lookup"><span data-stu-id="e7d34-152">To create an Azure virtual machine for DC1, fill in the name of your resource group and run these commands at the PowerShell command prompt on your local computer.</span></span>
  
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

<span data-ttu-id="e7d34-p111">DC1 のローカル管理者アカウントのユーザー名とパスワードを入力するようダイアログが表示されます。強力なパスワードを使用して、安全な場所に名前とパスワードの両方を記録します。</span><span class="sxs-lookup"><span data-stu-id="e7d34-p111">You will be prompted for a user name and password for the local administrator account on DC1. Use a strong password and record both the name and password in a secure location.</span></span>
  
<span data-ttu-id="e7d34-155">次に、DC1 仮想マシンに接続します。</span><span class="sxs-lookup"><span data-stu-id="e7d34-155">Next, connect to the DC1 virtual machine:</span></span>
  
1. <span data-ttu-id="e7d34-156">[Azure portal](https://portal.azure.com)で、[**リソースグループ**] を選択し、***新しいリソースグループの名前*** > <**DC1**  >  **Connect**> > します。</span><span class="sxs-lookup"><span data-stu-id="e7d34-156">In the [Azure portal](https://portal.azure.com), select **Resource Groups** > <***the name of your new resource group***> > **DC1** > **Connect**.</span></span>
    
2. <span data-ttu-id="e7d34-157">[開く] ウィンドウで、[ **RDP ファイルのダウンロード**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7d34-157">In the open pane, select **Download RDP file**.</span></span> <span data-ttu-id="e7d34-158">ダウンロードされた DC1 ファイルを開き、[ **接続**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7d34-158">Open the DC1.rdp file that is downloaded, and then select **Connect**.</span></span>
    
3. <span data-ttu-id="e7d34-159">DC1 のローカル管理者アカウント名を指定します。</span><span class="sxs-lookup"><span data-stu-id="e7d34-159">Specify the DC1 local administrator account name:</span></span>
    
   - <span data-ttu-id="e7d34-160">Windows 7 の場合:</span><span class="sxs-lookup"><span data-stu-id="e7d34-160">For Windows 7:</span></span>
    
     <span data-ttu-id="e7d34-161">[ **Windows セキュリティ** ] ダイアログボックスで、[ **別のアカウントを使用する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7d34-161">In the **Windows Security** dialog box, select **Use another account**.</span></span> <span data-ttu-id="e7d34-162">[**ユーザー名**] に、「 \*\*DC1 \\ \*\* < *local administrator account name*>」と入力します。</span><span class="sxs-lookup"><span data-stu-id="e7d34-162">In **User name**, enter **DC1\\**<*local administrator account name*>.</span></span>
    
   - <span data-ttu-id="e7d34-163">Windows 8 または Windows 10 の場合:</span><span class="sxs-lookup"><span data-stu-id="e7d34-163">For Windows 8 or Windows 10:</span></span>
    
     <span data-ttu-id="e7d34-164">[ **Windows セキュリティ** ] ダイアログボックスで、[ **その他のオプション**] を選択し、[ **別のアカウントを使用**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7d34-164">In the **Windows Security** dialog box, select **More choices**, and then select **Use a different account**.</span></span> <span data-ttu-id="e7d34-165">[**ユーザー名**] に、「 \*\*DC1 \\ \*\* < *local administrator account name*>」と入力します。</span><span class="sxs-lookup"><span data-stu-id="e7d34-165">In **User name**, enter **DC1\\**<*local administrator account name*>.</span></span>
    
4. <span data-ttu-id="e7d34-166">[ **パスワード**] にローカル管理者アカウントのパスワードを入力し、[ **OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7d34-166">In **Password**, enter the password of the local administrator account, and then select **OK**.</span></span>
    
5. <span data-ttu-id="e7d34-167">メッセージが表示されたら、[ **はい]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7d34-167">When prompted, select **Yes**.</span></span>
    
<span data-ttu-id="e7d34-168">次に、DC1 の管理者レベルの Windows PowerShell コマンド プロンプトで次のコマンドを使用して、新しいボリュームとして別のデータ ディスク (ドライブ文字 F:) を追加します。</span><span class="sxs-lookup"><span data-stu-id="e7d34-168">Next, add an extra data disk as a new volume with the drive letter F: with this command at an administrator-level Windows PowerShell command prompt on DC1.</span></span>
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

<span data-ttu-id="e7d34-169">次に **testlab.**\<*your public domain*></span><span class="sxs-lookup"><span data-stu-id="e7d34-169">Next, configure DC1 as a domain controller and DNS server for the **testlab.**\<*your public domain*></span></span> <span data-ttu-id="e7d34-170">ドメインのドメイン コントローラーおよび DNS サーバーとして DC1 を構成します。</span><span class="sxs-lookup"><span data-stu-id="e7d34-170">domain.</span></span> <span data-ttu-id="e7d34-171">パブリックドメイン名を指定し、山形かっこを削除してから、DC1 上の管理者レベルの Windows PowerShell コマンドプロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e7d34-171">Specify your public domain name, remove the angle brackets, and then run these commands at an administrator-level Windows PowerShell command prompt on DC1.</span></span>
  
```powershell
$yourDomain="<your public domain>"
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSForest -DomainName testlab.$yourDomain -DatabasePath "F:\NTDS" -SysvolPath "F:\SYSVOL" -LogPath "F:\Logs"
```
<span data-ttu-id="e7d34-p116">セーフ モードの管理者パスワードを指定する必要があります。このパスワードは安全な場所に保管してください。</span><span class="sxs-lookup"><span data-stu-id="e7d34-p116">You will need to specify a safe mode administrator password. Store this password in a secure location.</span></span>
  
<span data-ttu-id="e7d34-174">これらのコマンドの完了には数分かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="e7d34-174">Note that these commands can take a few minutes to complete.</span></span>
  
<span data-ttu-id="e7d34-175">DC1 の再起動後に、DC1 仮想マシンに再接続します。</span><span class="sxs-lookup"><span data-stu-id="e7d34-175">After DC1 restarts, reconnect to the DC1 virtual machine.</span></span>
  
1. <span data-ttu-id="e7d34-176">[Azure portal](https://portal.azure.com)で、リソース*グループ名* > <[**リソースグループ**] を選択し> > **DC1**Connect] をクリックし  >  **Connect**ます。</span><span class="sxs-lookup"><span data-stu-id="e7d34-176">In the [Azure portal](https://portal.azure.com), select **Resource Groups** > <*your resource group name*> > **DC1** > **Connect**.</span></span>
    
2. <span data-ttu-id="e7d34-177">ダウンロードされた DC1 ファイルを実行し、[ **接続**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7d34-177">Run the DC1.rdp file that is downloaded, and then select **Connect**.</span></span>
    
3. <span data-ttu-id="e7d34-178">[ **Windows セキュリティ**] で、[ **別のアカウントを使用する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7d34-178">In **Windows Security**, select **Use another account**.</span></span> <span data-ttu-id="e7d34-179">[**ユーザー名**] に、「 \*\*testlab \\ \*\* < *ローカル管理者アカウント名*>」と入力します。</span><span class="sxs-lookup"><span data-stu-id="e7d34-179">In **User name**, enter **TESTLAB\\**<*local administrator account name*>.</span></span>
    
4. <span data-ttu-id="e7d34-180">[ **パスワード** ] ボックスに、ローカル管理者アカウントのパスワードを入力し、[ **OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7d34-180">In the **Password** box, enter the password of the local administrator account, and then select **OK**.</span></span>
    
5. <span data-ttu-id="e7d34-181">メッセージが表示されたら、[ **はい]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7d34-181">When prompted, select **Yes**.</span></span>
    
<span data-ttu-id="e7d34-182">次に、TESTLAB ドメインメンバーコンピューターにサインインするときに使用する Active Directory のユーザーアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="e7d34-182">Next, create a user account in Active Directory that will be used when signing in to TESTLAB domain member computers.</span></span> <span data-ttu-id="e7d34-183">管理者レベルの Windows PowerShell コマンド プロンプトで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e7d34-183">Run this command at an administrator-level Windows PowerShell command prompt.</span></span>
  
```powershell
New-ADUser -SamAccountName User1 -AccountPassword (read-host "Set user password" -assecurestring) -name "User1" -enabled $true -PasswordNeverExpires $true -ChangePasswordAtLogon $false
```

<span data-ttu-id="e7d34-184">このコマンドでは、User1 アカウントのパスワードを入力するよう求められることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e7d34-184">Note that this command prompts you to supply the User1 account password.</span></span> <span data-ttu-id="e7d34-185">このアカウントは、すべての TESTLAB ドメインメンバーコンピューターのリモートデスクトップ接続に使用されるので、強力なパスワードを選択します。</span><span class="sxs-lookup"><span data-stu-id="e7d34-185">This account will be used for remote desktop connections for all TESTLAB domain member computers, so choose a strong password.</span></span> <span data-ttu-id="e7d34-186">User1 アカウントのパスワードを記録し、セキュリティで保護された場所に保管します。</span><span class="sxs-lookup"><span data-stu-id="e7d34-186">Record the User1 account password and store it in a secured location.</span></span>
  
<span data-ttu-id="e7d34-p120">次に、ドメイン、エンタープライズ、およびスキーマ管理者として新しい User1 のアカウントを構成します。管理者レベルの Windows PowerShell コマンド プロンプトで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e7d34-p120">Next, configure the new User1 account as a domain, enterprise, and schema administrator. Run this command at the administrator-level Windows PowerShell command prompt.</span></span>
  
```powershell
$yourDomain="<your public domain>"
$domainName = "testlab."+$yourDomain
$userName="user1@" + $domainName
$userSID=(New-Object System.Security.Principal.NTAccount($userName)).Translate([System.Security.Principal.SecurityIdentifier]).Value
$groupNames=@("Domain Admins","Enterprise Admins","Schema Admins")
ForEach ($name in $groupNames) {Add-ADPrincipalGroupMembership -Identity $userSID -MemberOf (Get-ADGroup -Identity $name).SID.Value}
```

<span data-ttu-id="e7d34-189">DC1 とのリモート デスクトップ セッションを終了し、TESTLAB\\User1 のアカウントを使用して再接続します。</span><span class="sxs-lookup"><span data-stu-id="e7d34-189">Close the Remote Desktop session with DC1 and then reconnect using the TESTLAB\\User1 account.</span></span>
  
<span data-ttu-id="e7d34-190">次に、Ping ツールのトラフィックを許可するため、管理者レベルの Windows PowerShell コマンド プロンプトで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e7d34-190">Next, to allow traffic for the Ping tool, run this command at an administrator-level Windows PowerShell command prompt.</span></span>
  
```powershell
Set-NetFirewallRule -DisplayName "File and Printer Sharing (Echo Request - ICMPv4-In)" -enabled True
```

<span data-ttu-id="e7d34-191">現在の構成は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="e7d34-191">Your current configuration looks like this:</span></span>
  
![シミュレートされたエンタープライズ基本構成のステップ 1](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase1.png)
  
#### <a name="step-2-configure-app1"></a><span data-ttu-id="e7d34-193">ステップ 2: APP1 を構成する</span><span class="sxs-lookup"><span data-stu-id="e7d34-193">Step 2: Configure APP1</span></span>

<span data-ttu-id="e7d34-194">このステップでは、最初にWeb およびファイル共有サービスを提供するアプリケーション サーバーである APP1 を作成して構成します。</span><span class="sxs-lookup"><span data-stu-id="e7d34-194">In this step, you create and configure APP1, which is an application server that initially provides web and file sharing services.</span></span>

<span data-ttu-id="e7d34-195">APP1 用の Azure 仮想マシンを作成するには、リソース グループの名前を入力して、次に示すコマンドをローカル コンピューターのコマンド プロンプトから実行します。</span><span class="sxs-lookup"><span data-stu-id="e7d34-195">To create an Azure Virtual Machine for APP1, fill in the name of your resource group and run these commands at the  command prompt on your local computer.</span></span>
  
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

<span data-ttu-id="e7d34-196">次に、APP1 のローカル管理者アカウント名とパスワードを使用して APP1 仮想マシンに接続し、Windows PowerShell コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="e7d34-196">Next, connect to the APP1 virtual machine using the APP1 local administrator account name and password, and then open a Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="e7d34-197">APP1 と DC1 間の名前解決とネットワーク通信を確認するには、**ping dc1.testlab.**\<*your public domain name*></span><span class="sxs-lookup"><span data-stu-id="e7d34-197">To check name resolution and network communication between APP1 and DC1, run the **ping dc1.testlab.**\<*your public domain name*></span></span> <span data-ttu-id="e7d34-198">コマンドを実行し、返信が 4 つあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e7d34-198">command and verify that there are four replies.</span></span>
  
<span data-ttu-id="e7d34-199">次に、Windows PowerShell プロンプトでこれらのコマンドを使用して、APP1 仮想マシンを TESTLAB ドメインに参加させます。</span><span class="sxs-lookup"><span data-stu-id="e7d34-199">Next, join the APP1 virtual machine to the TESTLAB domain with these commands at the Windows PowerShell prompt.</span></span>
  
```powershell
$yourDomain="<your public domain name>"
Add-Computer -DomainName ("testlab." + $yourDomain)
Restart-Computer
```

<span data-ttu-id="e7d34-200">[ **コンピューターの追加** ] コマンドを実行した後、testlab \\ User1 のドメインアカウントの資格情報を指定する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e7d34-200">Note that you after you run the **Add-Computer** command, you must supply the TESTLAB\\User1 domain account credentials.</span></span>
  
<span data-ttu-id="e7d34-201">APP1 の再起動後に、TESTLAB\\User1 のアカウントを使用して接続し、管理者レベルの Windows PowerShell コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="e7d34-201">After APP1 restarts, connect to it using the TESTLAB\\User1 account, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="e7d34-202">次に、このコマンドを APP1 の管理者レベルの Windows PowerShell コマンド プロンプトで使用して、APP1 を Web サーバーにします。</span><span class="sxs-lookup"><span data-stu-id="e7d34-202">Next, make APP1 a web server with this command at an administrator-level Windows PowerShell command prompt on APP1.</span></span>
  
```powershell
Install-WindowsFeature Web-WebServer -IncludeManagementTools
```

<span data-ttu-id="e7d34-203">次に、以下の PowerShell コマンドを使用して APP1 で共有フォルダーを作成し、そのフォルダー内にテキスト ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="e7d34-203">Next, create a shared folder and a text file within the folder on APP1 with these PowerShell commands.</span></span>
  
```powershell
New-Item -path c:\files -type directory
Write-Output "This is a shared file." | out-file c:\files\example.txt
New-SmbShare -name files -path c:\files -changeaccess TESTLAB\User1
```

<span data-ttu-id="e7d34-204">現在の構成は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="e7d34-204">Your current configuration looks like this:</span></span>
  
![シミュレートされたエンタープライズ基本構成のステップ 2](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase2.png)
  
#### <a name="step-3-configure-client1"></a><span data-ttu-id="e7d34-206">ステップ 3: CLIENT1 を構成する</span><span class="sxs-lookup"><span data-stu-id="e7d34-206">Step 3: Configure CLIENT1</span></span>

<span data-ttu-id="e7d34-207">このステップでは、イントラネット上の一般的なラップトップ、タブレット、またはデスクトップ コンピューターとして機能する CLIENT1 を作成して構成します。</span><span class="sxs-lookup"><span data-stu-id="e7d34-207">In this step, you create and configure CLIENT1, which acts as a typical laptop, tablet, or desktop computer on the intranet.</span></span>

> [!NOTE]  
> <span data-ttu-id="e7d34-p122">次のコマンド セットでは、Windows Server 2016 Datacenter を実行する CLIENT1 を作成します。これは、すべての Azure サブスクリプションのタイプに対して実行できます。Visual Studio ベースの Azure サブスクリプションがある場合は、[Azure portal](https://portal.azure.com) で、Windows 10 を実行する CLIENT1 を作成できます。</span><span class="sxs-lookup"><span data-stu-id="e7d34-p122">The following command set creates CLIENT1 running Windows Server 2016 Datacenter, which can be done for all types of Azure subscriptions. If you have a Visual Studio-based Azure subscription, you can create CLIENT1 running Windows 10 with the [Azure portal](https://portal.azure.com).</span></span>
  
<span data-ttu-id="e7d34-210">CLIENT1 用の Azure 仮想マシンを作成するには、リソースグループの名前を入力して、ローカルコンピューターのコマンドプロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e7d34-210">To create an Azure Virtual Machine for CLIENT1, fill in the name of your resource group and run these commands at the command prompt on your local computer.</span></span>
  
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

<span data-ttu-id="e7d34-211">次に、CLIENT1 のローカル管理者アカウント名とパスワードを使用して、CLIENT1 仮想マシンに接続し、管理者レベルの Windows PowerShell コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="e7d34-211">Next, connect to the CLIENT1 virtual machine using the CLIENT1 local administrator account name and password, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="e7d34-212">CLIENT1 と DC1 間の名前解決とネットワーク通信を確認するには、**ping dc1.testlab.**\<*your public domain name*></span><span class="sxs-lookup"><span data-stu-id="e7d34-212">To check name resolution and network communication between CLIENT1 and DC1, run the **ping dc1.testlab.**\<*your public domain name*></span></span> <span data-ttu-id="e7d34-213">コマンドを Windows PowerShell コマンド プロンプトで実行し、返信が 4 つあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e7d34-213">command at a Windows PowerShell command prompt and verify that there are four replies.</span></span>
  
<span data-ttu-id="e7d34-214">次に、Windows PowerShell プロンプトでこれらのコマンドを使用して、CLIENT1 仮想マシンを TESTLAB ドメインに参加させます。</span><span class="sxs-lookup"><span data-stu-id="e7d34-214">Next, join the CLIENT1 virtual machine to the TESTLAB domain with these commands at the Windows PowerShell prompt.</span></span>
  
```powershell
$yourDomain="<your public domain name>"
Add-Computer -DomainName ("testlab." + $yourDomain)
Restart-Computer
```

<span data-ttu-id="e7d34-215">**Add-Computer** コマンドの実行後に、TESTLAB\\User1 ドメイン アカウントの資格情報を入力する必要がある点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="e7d34-215">Note that you must supply your TESTLAB\\User1 domain account credentials after running the **Add-Computer** command.</span></span>
  
<span data-ttu-id="e7d34-216">CLIENT1 の再起動後に、TESTLAB\\User1 のアカウント名とパスワードを使用して接続し、管理者レベルの Windows PowerShell コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="e7d34-216">After CLIENT1 restarts, connect to it using the TESTLAB\\User1 account name and password, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="e7d34-217">次に、CLIENT1 から APP1 の Web リソースおよびファイル共有リソースにアクセスできることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e7d34-217">Next, verify that you can access web and file share resources on APP1 from CLIENT1.</span></span>
  
1. <span data-ttu-id="e7d34-218">サーバーマネージャーのツリーウィンドウで、[ **ローカルサーバー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7d34-218">In Server Manager, in the tree pane, select **Local Server**.</span></span>
    
2. <span data-ttu-id="e7d34-219">[ **CLIENT1 のプロパティ**] で、[ **IE セキュリティ強化の構成**] の横に**ある**[オン] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7d34-219">In **Properties for CLIENT1**, select **On** next to **IE Enhanced Security Configuration**.</span></span>
    
3. <span data-ttu-id="e7d34-220">[ **Internet Explorer セキュリティ強化の構成**] で、[**管理者**と**ユーザー**の場合は**オフ**] を選択し、[ **OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7d34-220">In **Internet Explorer Enhanced Security Configuration**, select **Off** for **Administrators** and **Users**, and then select **OK**.</span></span>
    
4. <span data-ttu-id="e7d34-221">[スタート] 画面で、[ **Internet Explorer**] を選択し、[ **OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7d34-221">From the Start screen, select **Internet Explorer**, and then select **OK**.</span></span>
    
5. <span data-ttu-id="e7d34-222">アドレスバーに「 **http<span>://</span>**:」と入力し、enter \<*your public domain name*> **/** キーを押します**Enter**。</span><span class="sxs-lookup"><span data-stu-id="e7d34-222">In the address bar, enter **http<span>://</span>app1.testab.**\<*your public domain name*>**/**, and then press **Enter**.</span></span> <span data-ttu-id="e7d34-223">APP1 の既定のインターネット インフォメーション サービスの Web ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e7d34-223">You should see the default Internet Information Services web page for APP1.</span></span>
    
6. <span data-ttu-id="e7d34-224">デスクトップのタスクバーで、[エクスプローラー] アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="e7d34-224">On the desktop taskbar, select the File Explorer icon.</span></span>
    
7. <span data-ttu-id="e7d34-225">アドレスバーに「 \*\* \\ \\ \\ ファイル**」**と入力し、enter キーを\*\*押します。</span><span class="sxs-lookup"><span data-stu-id="e7d34-225">In the address bar, enter **\\\\app1\\Files**, and then press **Enter**.</span></span> <span data-ttu-id="e7d34-226">フォルダー ウィンドウにファイルの共有フォルダーのコンテンツが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e7d34-226">You should see a folder window with the contents of the Files shared folder.</span></span>
    
8. <span data-ttu-id="e7d34-p126">**[ファイル]** の共有フォルダー ウィンドウで、**[Example.txt]** ファイルをダブルクリックします。Example.txt ファイルのコンテンツが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e7d34-p126">In the **Files** shared folder window, double-click the **Example.txt** file. You should see the contents of the Example.txt file.</span></span>
    
9. <span data-ttu-id="e7d34-229">**[example.txt - メモ帳]** と **[ファイル]** の共有フォルダーのウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="e7d34-229">Close the **example.txt - Notepad** and the **Files** shared folder windows.</span></span>
    
<span data-ttu-id="e7d34-230">現在の構成は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="e7d34-230">Your current configuration looks like this:</span></span>
  
![シミュレートされたエンタープライズ基本構成のステップ 3](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase3.png)

## <a name="phase-2-create-your-microsoft-365-e5-subscription"></a><span data-ttu-id="e7d34-232">フェーズ 2: Microsoft 365 E5 サブスクリプションを作成する</span><span class="sxs-lookup"><span data-stu-id="e7d34-232">Phase 2: Create your Microsoft 365 E5 subscription</span></span>

<span data-ttu-id="e7d34-p127">このフェーズでは、新しい Azure AD テナントを使用する Microsoft 365 E5 サブスクリプション (運用サブスクリプションとは別のもの) を作成します。これは、次の 2 つの方法で作成できます。</span><span class="sxs-lookup"><span data-stu-id="e7d34-p127">In this phase, you create a new Microsoft 365 E5 subscription that uses a new Azure AD tenant, one that is separate from your production subscription. You can do this in two ways:</span></span>

- <span data-ttu-id="e7d34-235">Microsoft 365 E5 の試用版サブスクリプションを使用する。</span><span class="sxs-lookup"><span data-stu-id="e7d34-235">Use a trial subscription of Microsoft 365 E5.</span></span>

  <span data-ttu-id="e7d34-p128">Microsoft 365 E5 の試用版サブスクリプションは 30 日間有効です。この有効期間は、簡単に 60 日間延長できます。試用版サブスクリプションの有効期限が切れたときには、有料版のサブスクリプションに切り替えるか、新しい試用版サブスクリプションを作成する必要があります。新しい試用版サブスクリプションを作成すると、複雑なシナリオが含まれていることもある構成を放置することになります。</span><span class="sxs-lookup"><span data-stu-id="e7d34-p128">The Microsoft 365 E5 trial subscription is 30 days, which can be easily extended to 60 days. When the trial subscription expires, you must either convert it to a paid subscription or create a new trial subscription. Creating new trial subscriptions means you will leave your configuration, which could include complex scenarios, behind.</span></span>  

- <span data-ttu-id="e7d34-239">ライセンス数の少ない Microsoft 365 E5 の個別の運用サブスクリプションを使用する。</span><span class="sxs-lookup"><span data-stu-id="e7d34-239">Use a separate production subscription of Microsoft 365 E5 with a small number of licenses.</span></span>

  <span data-ttu-id="e7d34-240">これは追加の費用ですが、有効期限が切れない正常なテスト環境があることが保証されます。これで、機能、構成、およびシナリオを試すことができます。</span><span class="sxs-lookup"><span data-stu-id="e7d34-240">This is an additional cost, but ensures that you have a working test environment that doesn't expire; in it, you can try features, configurations, and scenarios.</span></span> <span data-ttu-id="e7d34-241">概念実証、同僚と管理、およびアプリケーション開発とテストのために、長期間にわたって同じテスト環境を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="e7d34-241">You can use the same test environment over the long term for proofs of concept, demonstration to peers and management, and application development and testing.</span></span> <span data-ttu-id="e7d34-242">この方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e7d34-242">This is the recommended method.</span></span>

### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a><span data-ttu-id="e7d34-243">Office 365 E5 試用版サブスクリプションにサインアップする</span><span class="sxs-lookup"><span data-stu-id="e7d34-243">Sign up for an Office 365 E5 trial subscription</span></span>

<span data-ttu-id="e7d34-244">Azure portal から、CORP\User1 アカウントを使用して CLIENT1 に接続します。</span><span class="sxs-lookup"><span data-stu-id="e7d34-244">From the Azure portal, connect to CLIENT1 with the CORP\User1 account.</span></span>

<span data-ttu-id="e7d34-245">新しい Office 365 E5 試用版のサブスクリプションを作成するには、「軽量な基本構成」のテスト ラボ ガイドの [フェーズ 1](lightweight-base-configuration-microsoft-365-enterprise.md#phase-1-create-your-microsoft-365-e5-subscription) にある手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e7d34-245">To create a new Office 365 E5 trial subscription, perform the instructions in [Phase 1](lightweight-base-configuration-microsoft-365-enterprise.md#phase-1-create-your-microsoft-365-e5-subscription) of the lightweight base configuration Test Lab Guide.</span></span>

<span data-ttu-id="e7d34-246">新しい Office 365 E5 試用版のサブスクリプションを構成するには、「軽量な基本構成」のテスト ラボ ガイドの [フェーズ 2](lightweight-base-configuration-microsoft-365-enterprise.md#phase-2-configure-your-office-365-trial-subscription) にある手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e7d34-246">To configure your new Office 365 E5 trial subscription, perform the instructions in [Phase 2](lightweight-base-configuration-microsoft-365-enterprise.md#phase-2-configure-your-office-365-trial-subscription) of the lightweight base configuration Test Lab Guide.</span></span>

#### <a name="using-an-office-365-e5-test-environment"></a><span data-ttu-id="e7d34-247">Office 365 E5 のテスト環境を使用する</span><span class="sxs-lookup"><span data-stu-id="e7d34-247">Using an Office 365 E5 test environment</span></span>

<span data-ttu-id="e7d34-248">Office 365 テスト環境のみが必要な場合は、この記事の残りの部分を読む必要はありません。</span><span class="sxs-lookup"><span data-stu-id="e7d34-248">If you need only an Office 365 test environment, you do not need to read the rest of this article.</span></span>

<span data-ttu-id="e7d34-249">Microsoft 365 と Office 365 の両方に適用されるその他のテストラボガイドについては、「 [microsoft 365 for Enterprise Test Lab ガイド](m365-enterprise-test-lab-guides.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7d34-249">For additional Test Lab Guides that apply to both Microsoft 365 and Office 365, see [Microsoft 365 for enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>

### <a name="add-a-microsoft-365-e5-trial-subscription"></a><span data-ttu-id="e7d34-250">Microsoft 365 E5 の試用版サブスクリプションを追加する</span><span class="sxs-lookup"><span data-stu-id="e7d34-250">Add a Microsoft 365 E5 trial subscription</span></span>

<span data-ttu-id="e7d34-251">Microsoft 365 E5 試用版サブスクリプションを追加し、ライセンスを使用してユーザーアカウントを構成するには、「 [フェーズ 3](lightweight-base-configuration-microsoft-365-enterprise.md#phase-3-add-a-microsoft-365-e5-trial-subscription) の軽量な基本構成テストラボガイド」の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e7d34-251">To add a Microsoft 365 E5 trial subscription and configure your users accounts with licenses, perform the instructions in [Phase 3](lightweight-base-configuration-microsoft-365-enterprise.md#phase-3-add-a-microsoft-365-e5-trial-subscription) of the lightweight base configuration Test Lab Guide.</span></span>

  
## <a name="results"></a><span data-ttu-id="e7d34-252">結果</span><span class="sxs-lookup"><span data-stu-id="e7d34-252">Results</span></span>

<span data-ttu-id="e7d34-253">テスト環境は、次のようになっています。</span><span class="sxs-lookup"><span data-stu-id="e7d34-253">Your test environment now has:</span></span>
  
- <span data-ttu-id="e7d34-254">Microsoft 365 E5 の試用版サブスクリプション。</span><span class="sxs-lookup"><span data-stu-id="e7d34-254">Microsoft 365 E5 trial subscription.</span></span>
- <span data-ttu-id="e7d34-255">すべての適切なユーザー アカウントが Microsoft 365 E5 を使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="e7d34-255">All your appropriate user accounts are enabled to use Microsoft 365 E5.</span></span>
- <span data-ttu-id="e7d34-256">シミュレートおよび簡略化されたイントラネット。</span><span class="sxs-lookup"><span data-stu-id="e7d34-256">A simulated and simplified intranet.</span></span>
    
<span data-ttu-id="e7d34-257">最終的な構成は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="e7d34-257">Your final configuration looks like this:</span></span>
  
![シミュレートされたエンタープライズ基本構成のフェーズ 2](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase4.png)
  
<span data-ttu-id="e7d34-259">これで、 [Microsoft 365 for enterprise](https://www.microsoft.com/microsoft-365/enterprise)の追加機能を試す準備ができました。</span><span class="sxs-lookup"><span data-stu-id="e7d34-259">You are now ready to experiment with additional features of [Microsoft 365 for enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="e7d34-260">次の手順</span><span class="sxs-lookup"><span data-stu-id="e7d34-260">Next steps</span></span>

<span data-ttu-id="e7d34-261">こうした追加のテスト ラボ ガイドについて説明します。</span><span class="sxs-lookup"><span data-stu-id="e7d34-261">Explore these additional sets of Test Lab Guides:</span></span>
  
- [<span data-ttu-id="e7d34-262">ID</span><span class="sxs-lookup"><span data-stu-id="e7d34-262">Identity</span></span>](m365-enterprise-test-lab-guides.md#identity)
- [<span data-ttu-id="e7d34-263">モバイル デバイス管理</span><span class="sxs-lookup"><span data-stu-id="e7d34-263">Mobile device management</span></span>](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [<span data-ttu-id="e7d34-264">情報保護</span><span class="sxs-lookup"><span data-stu-id="e7d34-264">Information protection</span></span>](m365-enterprise-test-lab-guides.md#information-protection)

## <a name="see-also"></a><span data-ttu-id="e7d34-265">関連項目</span><span class="sxs-lookup"><span data-stu-id="e7d34-265">See also</span></span>

[<span data-ttu-id="e7d34-266">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="e7d34-266">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="e7d34-267">Microsoft 365 for enterprise の概要</span><span class="sxs-lookup"><span data-stu-id="e7d34-267">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="e7d34-268">エンタープライズドキュメントの Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e7d34-268">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
