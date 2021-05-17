---
title: Microsoft 365 テスト環境のフェデレーション ID
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/26/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- TLG
- Ent_TLGs
ms.assetid: 65a6d687-a16a-4415-9fd5-011ba9c5fd80
description: '概要: Microsoft 365 テスト環境用にフェデレーション認証を構成します。'
ms.openlocfilehash: 0fb8c55f5b7291cdc6bcec636981a9d31015e723
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487686"
---
# <a name="federated-identity-for-your-microsoft-365-test-environment"></a><span data-ttu-id="a5937-103">Microsoft 365 テスト環境のフェデレーション ID</span><span class="sxs-lookup"><span data-stu-id="a5937-103">Federated identity for your Microsoft 365 test environment</span></span>

<span data-ttu-id="a5937-104">*このテスト ラボ ガイドは、エンタープライズ環境とテスト環境Microsoft 365両方Office 365 Enterprise使用できます。*</span><span class="sxs-lookup"><span data-stu-id="a5937-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="a5937-p101">Microsoft 365 は、フェデレーション ID をサポートします。つまり、資格情報自体の検証を実行する代わりに、Microsoft 365 は、接続しようとしているユーザーを、Microsoft 365 が信頼するフェデレーション認証サーバーに照会します。ユーザーの資格情報が正しい場合、フェデレーション認証サーバーはセキュリティ トークンを発行し、次いでクライアントは認証の証明としてそのセキュリティ トークンを Microsoft 365 に送信します。フェデレーション ID を使用すると、Microsoft 365 サブスクリプションの認証のオフロードとスケールアップや、認証とセキュリティの高度なシナリオが可能になります。</span><span class="sxs-lookup"><span data-stu-id="a5937-p101">Microsoft 365 supports federated identity. This means that instead of performing the validation of credentials itself, Microsoft 365 refers the connecting user to a federated authentication server that Microsoft 365 trusts. If the user's credentials are correct, the federated authentication server issues a security token that the client then sends to Microsoft 365 as proof of authentication. Federated identity allows for the offloading and scaling up of authentication for a Microsoft 365 subscription and advanced authentication and security scenarios.</span></span>
  
<span data-ttu-id="a5937-109">この記事では、テスト環境に対してフェデレーション認証を構成するMicrosoft 365、次の結果について説明します。</span><span class="sxs-lookup"><span data-stu-id="a5937-109">This article describes how to configure federated authentication for your Microsoft 365 test environment, resulting in the following:</span></span>

![Microsoft 365 テスト環境のフェデレーション認証](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase3.png)
  
<span data-ttu-id="a5937-111">この構成は、次の内容で構成されます:</span><span class="sxs-lookup"><span data-stu-id="a5937-111">This configuration consists of:</span></span>
  
- <span data-ttu-id="a5937-112">試用版Microsoft 365 E5のサブスクリプション。</span><span class="sxs-lookup"><span data-stu-id="a5937-112">A Microsoft 365 E5 trial or production subscription.</span></span>
    
- <span data-ttu-id="a5937-113">インターネットに接続された簡略化された組織イントラネットで、Azure 仮想ネットワークのサブネット上の 5 つの仮想マシン (DC1、APP1、CLIENT1、ADFS1、および PROXY1) で構成されます。</span><span class="sxs-lookup"><span data-stu-id="a5937-113">A simplified organization intranet connected to the internet, consisting of five virtual machines on a subnet of an Azure virtual network (DC1, APP1, CLIENT1, ADFS1, and PROXY1).</span></span> <span data-ttu-id="a5937-114">Azure AD Connect APP1 で実行して、Active Directory ドメイン サービス ドメイン内のアカウントの一覧をユーザーに同期Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="a5937-114">Azure AD Connect runs on APP1 to synchronize the list of accounts in the Active Directory Domain Services domain to Microsoft 365.</span></span> <span data-ttu-id="a5937-115">PROXY1 は、受信認証要求を受信します。</span><span class="sxs-lookup"><span data-stu-id="a5937-115">PROXY1 receives the incoming authentication requests.</span></span> <span data-ttu-id="a5937-116">ADFS1 は DC1 を使用して資格情報を検証し、セキュリティ トークンを発行します。</span><span class="sxs-lookup"><span data-stu-id="a5937-116">ADFS1 validates credentials with DC1 and issues security tokens.</span></span>
    
<span data-ttu-id="a5937-117">このテスト環境のセットアップには、次の 5 つのフェーズがあります。</span><span class="sxs-lookup"><span data-stu-id="a5937-117">Setting up this test environment involves five phases:</span></span>
- [<span data-ttu-id="a5937-118">フェーズ 1: Microsoft 365 テスト環境のパスワード ハッシュ同期を構成する</span><span class="sxs-lookup"><span data-stu-id="a5937-118">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [<span data-ttu-id="a5937-119">フェーズ 2: AD FS サーバーを作成する</span><span class="sxs-lookup"><span data-stu-id="a5937-119">Phase 2: Create the AD FS server</span></span>](#phase-2-create-the-ad-fs-server)
- [<span data-ttu-id="a5937-120">フェーズ 3：Web プロキシ サーバーを作成する</span><span class="sxs-lookup"><span data-stu-id="a5937-120">Phase 3: Create the web proxy server</span></span>](#phase-3-create-the-web-proxy-server)
- [<span data-ttu-id="a5937-121">フェーズ 4:自己署名証明書を作成し、ADFS1 と PROXY1 を構成する</span><span class="sxs-lookup"><span data-stu-id="a5937-121">Phase 4: Create a self-signed certificate and configure ADFS1 and PROXY1</span></span>](#phase-4-create-a-self-signed-certificate-and-configure-adfs1-and-proxy1)
- [<span data-ttu-id="a5937-122">フェーズ 5: フェデレーション ID に対応するよう Microsoft 365 を構成する</span><span class="sxs-lookup"><span data-stu-id="a5937-122">Phase 5: Configure Microsoft 365 for federated identity</span></span>](#phase-5-configure-microsoft-365-for-federated-identity)
    
> [!NOTE]
> <span data-ttu-id="a5937-123">Azure Trial サブスクリプションでは、このテスト環境を構成できない。</span><span class="sxs-lookup"><span data-stu-id="a5937-123">You can't configure this test environment with an Azure Trial subscription.</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="a5937-124">フェーズ 1: Microsoft 365 テスト環境のパスワード ハッシュ同期を構成する</span><span class="sxs-lookup"><span data-stu-id="a5937-124">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="a5937-125">パスワード ハッシュ同期の手順[に従](password-hash-sync-m365-ent-test-environment.md)って、Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="a5937-125">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md).</span></span> <span data-ttu-id="a5937-126">結果の構成は次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="a5937-126">Your resulting configuration looks like this:</span></span>
  
![パスワード ハッシュ同期を実装するシミュレーション エンタープライズ テスト環境](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase1.png)
  
<span data-ttu-id="a5937-128">この構成は、次の内容で成立します。</span><span class="sxs-lookup"><span data-stu-id="a5937-128">This configuration consists of:</span></span>
  
- <span data-ttu-id="a5937-129">試用版Microsoft 365 E5有料サブスクリプション。</span><span class="sxs-lookup"><span data-stu-id="a5937-129">A Microsoft 365 E5 trial or paid subscriptions.</span></span>
- <span data-ttu-id="a5937-130">Azure 仮想ネットワークのサブネット上の DC1、APP1、および CLIENT1 仮想マシンで構成される、インターネットに接続された簡略化された組織イントラネット。</span><span class="sxs-lookup"><span data-stu-id="a5937-130">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> <span data-ttu-id="a5937-131">Azure AD Connect APP1 で実行して、TESTLAB Active Directory ドメイン サービス (AD DS) ドメインを定期的に Microsoft 365 サブスクリプションの Azure AD テナントに同期します。</span><span class="sxs-lookup"><span data-stu-id="a5937-131">Azure AD Connect runs on APP1 to synchronize the TESTLAB Active Directory Domain Services (AD DS) domain to the Azure AD tenant of your Microsoft 365 subscriptions periodically.</span></span>

## <a name="phase-2-create-the-ad-fs-server"></a><span data-ttu-id="a5937-132">フェーズ 2: AD FS サーバーを作成する</span><span class="sxs-lookup"><span data-stu-id="a5937-132">Phase 2: Create the AD FS server</span></span>

<span data-ttu-id="a5937-133">AD FS サーバーは、Microsoft 365 と、DC1 でホストされている corp.contoso.com ドメイン内のアカウントとの間でのフェデレーション認証を提供します。</span><span class="sxs-lookup"><span data-stu-id="a5937-133">An AD FS server provides federated authentication between Microsoft 365 and the accounts in the corp.contoso.com domain hosted on DC1.</span></span>
  
<span data-ttu-id="a5937-134">ADFS1 用の Azure 仮想マシンを作成するには、基本構成のサブスクリプション名、リソース グループ名、Azure の場所を入力して、次のコマンドをローカル コンピューターの Azure PowerShell コマンド プロンプトで実行します。</span><span class="sxs-lookup"><span data-stu-id="a5937-134">To create an Azure virtual machine for ADFS1, fill in the name of your subscription and the resource group and Azure location for your Base Configuration, and then run these commands at the Azure PowerShell command prompt on your local computer.</span></span>
  
```powershell
$subscrName="<your Azure subscription name>"
$rgName="<the resource group name of your Base Configuration>"
$vnetName="TlgBaseConfig-01-VNET"
# NOTE: If you built your simulated intranet with Azure PowerShell, comment the previous line with a "#" and remove the "#" from the next line.
#$vnetName="TestLab"
Connect-AzAccount
Select-AzSubscription -SubscriptionName $subscrName
$staticIP="10.0.0.100"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$pip = New-AzPublicIpAddress -Name ADFS1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic = New-AzNetworkInterface -Name ADFS1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName ADFS1 -VMSize Standard_D2_v2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for ADFS1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName ADFS1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "ADFS-OS" -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType "Standard_LRS"
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

<span data-ttu-id="a5937-135">次に、[Azure portal](https://portal.azure.com) で、ADFS1 のローカル管理者アカウント名とパスワードを使用して ADFS1 仮想マシンに接続し、Windows PowerShell コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="a5937-135">Next, use the [Azure portal](https://portal.azure.com) to connect to the ADFS1 virtual machine using the ADFS1 local administrator account name and password, and then open a Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="a5937-136">ADFS1 と DC1 の間の名前の解決とネットワーク通信を確認するには、**ping dc1.corp.contoso.com** コマンドを実行し、4 つの応答があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a5937-136">To check name resolution and network communication between ADFS1 and DC1, run the **ping dc1.corp.contoso.com** command and check that there are four replies.</span></span>
  
<span data-ttu-id="a5937-137">次に、ADFS1 の Windows PowerShell プロンプトで次のコマンドを使用して、ADFS1 仮想マシンを CORP ドメインに参加させます。</span><span class="sxs-lookup"><span data-stu-id="a5937-137">Next, join the ADFS1 virtual machine to the CORP domain with these commands at the Windows PowerShell prompt on ADFS1.</span></span>
  
```powershell
$cred=Get-Credential -UserName "CORP\User1" -Message "Type the User1 account password."
Add-Computer -DomainName corp.contoso.com -Credential $cred
Restart-Computer
```

<span data-ttu-id="a5937-138">結果の構成は次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="a5937-138">Your resulting configuration looks like this:</span></span>
  
![Microsoft 365 テスト環境の DirSync に追加された AD FS サーバー](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase2.png)
  
## <a name="phase-3-create-the-web-proxy-server"></a><span data-ttu-id="a5937-140">フェーズ 3：Web プロキシ サーバーを作成する</span><span class="sxs-lookup"><span data-stu-id="a5937-140">Phase 3: Create the web proxy server</span></span>

<span data-ttu-id="a5937-141">PROXY1 は、認証しようとするユーザーと ADFS1 との間の認証メッセージのプロキシを提供します。</span><span class="sxs-lookup"><span data-stu-id="a5937-141">PROXY1 provides proxying of authentication messages between users trying to authenticate and ADFS1.</span></span>
  
<span data-ttu-id="a5937-142">PROXY1 用の Azure 仮想マシンを作成するには、リソース グループ名と Azure の場所を入力し、次のコマンドをローカル コンピューターの Azure PowerShell コマンド プロンプトで実行します。</span><span class="sxs-lookup"><span data-stu-id="a5937-142">To create an Azure virtual machine for PROXY1, fill in the name of your resource group and Azure location, and then run these commands at the Azure PowerShell command prompt on your local computer.</span></span>
  
```powershell
$rgName="<the resource group name of your Base Configuration>"
$vnetName="TlgBaseConfig-01-VNET"
# NOTE: If you built your simulated intranet with Azure PowerShell, comment the previous line with a "#" and remove the "#" from the next line.
#$vnetName="TestLab"
$staticIP="10.0.0.101"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$pip = New-AzPublicIpAddress -Name PROXY1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Static
$nic = New-AzNetworkInterface -Name PROXY1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName PROXY1 -VMSize Standard_D2_v2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for PROXY1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName PROXY1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "PROXY1-OS" -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType "Standard_LRS"
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

> [!NOTE]
> <span data-ttu-id="a5937-143">PROXY1 には静的パブリック IP アドレスが割り当てられます。この IP アドレスを指すパブリック DNS レコードが作成され、PROXY1 仮想マシンを再起動するときにこの IP アドレスを変更することはできないためです。</span><span class="sxs-lookup"><span data-stu-id="a5937-143">PROXY1 is assigned a static public IP address because you will create a public DNS record that points to it and it must not change when you restart the PROXY1 virtual machine.</span></span>
  
<span data-ttu-id="a5937-144">次に、CorpNet サブネットのネットワーク セキュリティ グループにルールを追加して、インターネットから PROXY1 のプライベート IP アドレスと TCP ポート 443 への未承諾の受信トラフィックを許可します。</span><span class="sxs-lookup"><span data-stu-id="a5937-144">Next, add a rule to the network security group for the CorpNet subnet to allow unsolicited inbound traffic from the internet to PROXY1's private IP address and TCP port 443.</span></span> <span data-ttu-id="a5937-145">ローカル コンピューターの Azure PowerShell コマンド プロンプトで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a5937-145">Run these commands at the Azure PowerShell command prompt on your local computer.</span></span>
  
```powershell
$rgName="<the resource group name of your Base Configuration>"
Get-AzNetworkSecurityGroup -Name CorpNet -ResourceGroupName $rgName | Add-AzNetworkSecurityRuleConfig -Name "HTTPS-to-PROXY1" -Description "Allow TCP 443 to PROXY1" -Access "Allow" -Protocol "Tcp" -Direction "Inbound" -Priority 101 -SourceAddressPrefix "Internet" -SourcePortRange "*" -DestinationAddressPrefix "10.0.0.101" -DestinationPortRange "443" | Set-AzNetworkSecurityGroup
```

<span data-ttu-id="a5937-146">次に、[Azure portal](https://portal.azure.com) で、PROXY1 のローカル管理者アカウント名とパスワードを使用して PROXY1 仮想マシンに接続し、PROXY1 で Windows PowerShell コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="a5937-146">Next, use the [Azure portal](https://portal.azure.com) to connect to the PROXY1 virtual machine using the PROXY1 local administrator account name and password, and then open a Windows PowerShell command prompt on PROXY1.</span></span>
  
<span data-ttu-id="a5937-147">PROXY1 と DC1 の間の名前の解決とネットワーク通信を確認するには、**ping dc1.corp.contoso.com** コマンドを実行し、4 つの応答があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a5937-147">To check name resolution and network communication between PROXY1 and DC1, run the **ping dc1.corp.contoso.com** command and check that there are four replies.</span></span>
  
<span data-ttu-id="a5937-148">次に、PROXY1 の Windows PowerShell プロンプトで次のコマンドを使用して、PROXY1 仮想マシンを CORP ドメインに参加させます。</span><span class="sxs-lookup"><span data-stu-id="a5937-148">Next, join the PROXY1 virtual machine to the CORP domain with these commands at the Windows PowerShell prompt on PROXY1.</span></span>
  
```powershell
$cred=Get-Credential -UserName "CORP\User1" -Message "Type the User1 account password."
Add-Computer -DomainName corp.contoso.com -Credential $cred
Restart-Computer
```

<span data-ttu-id="a5937-149">ローカル コンピューターでこれらのコマンドを使用して PROXY1 のAzure PowerShell IP アドレスを表示します。</span><span class="sxs-lookup"><span data-stu-id="a5937-149">Display the public IP address of PROXY1 with these Azure PowerShell commands on your local computer.</span></span>
  
```powershell
Write-Host (Get-AzPublicIpaddress -Name "PROXY1-PIP" -ResourceGroup $rgName).IPAddress
```

<span data-ttu-id="a5937-p106">次に、パブリック DNS プロバイダーを操作して、**Write-Host** コマンドで表示される IP アドレスに解決される、**fs.testlab.**\<*your DNS domain name*> 用の新しいパブリック DNS A レコードを作成します。これ以降、**fs.testlab.**\<*your DNS domain name*> を *フェデレーション サービス FQDN* と呼びます。</span><span class="sxs-lookup"><span data-stu-id="a5937-p106">Next, work with your public DNS provider and create a new public DNS A record for **fs.testlab.**\<*your DNS domain name*> that resolves to the IP address displayed by the **Write-Host** command. The **fs.testlab.**\<*your DNS domain name*> is hereafter referred to as the  *federation service FQDN*.</span></span>
  
<span data-ttu-id="a5937-154">次に、[Azure portal](https://portal.azure.com) で、CORP\\User1 の資格情報を使用して DC1 仮想マシンに接続し、管理者レベルの Windows PowerShell コマンド プロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a5937-154">Next, use the [Azure portal](https://portal.azure.com) to connect to the DC1 virtual machine using the CORP\\User1 credentials, and then run the following commands at an administrator-level Windows PowerShell command prompt:</span></span>
  
```powershell
Add-DnsServerPrimaryZone -Name corp.contoso.com -ZoneFile corp.contoso.com.dns
Add-DnsServerResourceRecordA -Name "fs" -ZoneName corp.contoso.com -AllowUpdateAny -IPv4Address "10.0.0.100" -TimeToLive 01:00:00
```
<span data-ttu-id="a5937-155">これらのコマンドは、Azure 仮想ネットワーク上の仮想マシンが内部フェデレーション サービス FQDN を ADFS1 のプライベート IP アドレスに解決できるよう、内部 DNS A レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="a5937-155">These commands create an internal DNS A record so that virtual machines on the Azure virtual network can resolve the internal federation service FQDN to ADFS1's private IP address.</span></span>
  
<span data-ttu-id="a5937-156">結果の構成は次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="a5937-156">Your resulting configuration looks like this:</span></span>
  
![Microsoft 365 テスト環境の DirSync に追加された Web アプリケーション プロキシ サーバー](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase3.png)
  
## <a name="phase-4-create-a-self-signed-certificate-and-configure-adfs1-and-proxy1"></a><span data-ttu-id="a5937-158">フェーズ 4:自己署名証明書を作成し、ADFS1 と PROXY1 を構成する</span><span class="sxs-lookup"><span data-stu-id="a5937-158">Phase 4: Create a self-signed certificate and configure ADFS1 and PROXY1</span></span>

<span data-ttu-id="a5937-159">このフェーズでは、フェデレーション サービス FQDN 用の自己署名入りデジタル証明書を作成し、ADFS1 と PROXY1 を AD FS ファームとして構成します。</span><span class="sxs-lookup"><span data-stu-id="a5937-159">In this phase, you create a self-signed digital certificate for your federation service FQDN and configure ADFS1 and PROXY1 as an AD FS farm.</span></span>
  
<span data-ttu-id="a5937-160">まず、[Azure portal](https://portal.azure.com) で、CORP\\User1 の資格情報を使用して DC1 仮想マシンに接続し、管理者レベルの Windows PowerShell コマンド プロンプトを開きます。 </span><span class="sxs-lookup"><span data-stu-id="a5937-160">First, use the [Azure portal](https://portal.azure.com) to connect to the DC1 virtual machine using the CORP\\User1 credentials, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="a5937-161">次に、DC1 ADコマンド プロンプトで次のコマンドを使用して、Windows PowerShell FS サービス アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="a5937-161">Next, create an AD FS service account with this command at the Windows PowerShell command prompt on DC1:</span></span>
  
```powershell
New-ADUser -SamAccountName ADFS-Service -AccountPassword (read-host "Set user password" -assecurestring) -name "ADFS-Service" -enabled $true -PasswordNeverExpires $true -ChangePasswordAtLogon $false
```
<span data-ttu-id="a5937-162">このコマンドでは、アカウントのパスワードを入力するよう求められることにご注意ください。</span><span class="sxs-lookup"><span data-stu-id="a5937-162">Note that this command prompts you to supply the account password.</span></span> <span data-ttu-id="a5937-163">強力なパスワードを選択して、安全な場所に記録してください。</span><span class="sxs-lookup"><span data-stu-id="a5937-163">Choose a strong password and record it in a secured location.</span></span> <span data-ttu-id="a5937-164">このフェーズとフェーズ 5 には必要です。</span><span class="sxs-lookup"><span data-stu-id="a5937-164">You will need it for this phase and for Phase 5.</span></span>
  
<span data-ttu-id="a5937-p108">[Azure portal](https://portal.azure.com) で CORP\\User1 の資格情報を使用して、ADFS1 仮想マシンに接続します。ADFS1 で管理者レベルの Windows PowerShell コマンド プロンプトを開き、フェデレーション サービス FQDN を入力し、次のコマンドを実行して自己署名証明書を作成します。</span><span class="sxs-lookup"><span data-stu-id="a5937-p108">Use the [Azure portal](https://portal.azure.com) to connect to the ADFS1 virtual machine using the CORP\\User1 credentials. Open an administrator-level Windows PowerShell command prompt on ADFS1, fill in your federation service FQDN, and then run these commands to create a self-signed certificate:</span></span>
  
```powershell
$fedServiceFQDN="<federation service FQDN>"
New-SelfSignedCertificate -DnsName $fedServiceFQDN -CertStoreLocation "cert:\LocalMachine\My"
New-Item -path c:\Certs -type directory
New-SmbShare -name Certs -path c:\Certs -changeaccess CORP\User1
```

<span data-ttu-id="a5937-167">その次に、次の手順を使用して新しい自己署名証明書をファイルとして保存します。</span><span class="sxs-lookup"><span data-stu-id="a5937-167">Next, use these steps to save the new self-signed certificate as a file.</span></span>
  
1. <span data-ttu-id="a5937-168">[ **スタート] を** 選択し、mmc.exe入力し **、Enter** キーを **押します**。</span><span class="sxs-lookup"><span data-stu-id="a5937-168">Select **Start**, enter **mmc.exe**, and then press **Enter**.</span></span>
    
2. <span data-ttu-id="a5937-169">[**ファイル**  >  **の追加と削除] スナップを選択します**。</span><span class="sxs-lookup"><span data-stu-id="a5937-169">Select **File** > **Add/Remove Snap-in**.</span></span>
    
3. <span data-ttu-id="a5937-170">[**アドインの追加とスナップ]** で、使用可能なスナップインの一覧で [証明書] をダブルクリックし、[**コンピューター** アカウント] を選択し、[次へ] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="a5937-170">In **Add or Remove Snap-ins**, double-click **Certificates** in the list of available snap-ins, select **Computer account**, and then select **Next**.</span></span>
    
4. <span data-ttu-id="a5937-171">[ **コンピューターの選択]** で、[ **完了] を選択** し **、[OK] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a5937-171">In **Select Computer**, select **Finish**, and then select **OK**.</span></span>
    
5. <span data-ttu-id="a5937-172">ツリー ウィンドウで、**[証明書 (ローカル コンピューター)] > [個人] > [証明書]** の順に開きます。</span><span class="sxs-lookup"><span data-stu-id="a5937-172">In the tree pane, open **Certificates (Local Computer) > Personal > Certificates**.</span></span>
    
6. <span data-ttu-id="a5937-173">フェデレーション サービス FQDN を使用して証明書を選択して保持 (または右クリック) し、[すべてのタスク] を選択し、[エクスポート] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="a5937-173">Select and hold (or right-click) the certificate with your federation service FQDN, select **All tasks**, and then select **Export**.</span></span>
    
7. <span data-ttu-id="a5937-174">[ようこそ] **ページで** 、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="a5937-174">On the **Welcome** page, select **Next**.</span></span>
    
8. <span data-ttu-id="a5937-175">[プライベート キー **のエクスポート] ページで** 、[はい] **を選択し**、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="a5937-175">On the **Export Private Key** page, select **Yes**, and then select **Next**.</span></span>
    
9. <span data-ttu-id="a5937-176">[ファイル形式 **のエクスポート] ページで** 、[すべての拡張プロパティをエクスポートする] **を選択** し、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="a5937-176">On the **Export File Format** page, select **Export all extended properties**, and then select **Next**.</span></span>
    
10. <span data-ttu-id="a5937-177">[セキュリティ **] ページで**、[パスワード]**を選択し**、[パスワード] と [パスワードの確認 **] にパスワード\*\*\*\*を入力します。**</span><span class="sxs-lookup"><span data-stu-id="a5937-177">On the **Security** page, select **Password** and enter a password in **Password** and **Confirm password.**</span></span>
    
11. <span data-ttu-id="a5937-178">[エクスポートする **ファイル] ページで、[** 参照] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="a5937-178">On the **File to Export** page, select **Browse**.</span></span>
    
12. <span data-ttu-id="a5937-179">**C: \\ Certs フォルダーを参照** し、[ファイル名] に **SSL** と **入力** し、[保存] を **選択します。**</span><span class="sxs-lookup"><span data-stu-id="a5937-179">Browse to the **C:\\Certs** folder, enter **SSL** in **File name**, and then select **Save.**</span></span>
    
13. <span data-ttu-id="a5937-180">[エクスポートする **ファイル] ページで、[** 次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="a5937-180">On the **File to Export** page, select **Next**.</span></span>
    
14. <span data-ttu-id="a5937-181">[証明書の **エクスポート ウィザードの完了] ページで、[** 完了] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="a5937-181">On the **Completing the Certificate Export Wizard** page, select **Finish**.</span></span> <span data-ttu-id="a5937-182">プロンプトが表示されたら **、[OK] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a5937-182">When prompted, select **OK**.</span></span>
    
<span data-ttu-id="a5937-183">次に、ADFS1 の Windows PowerShell コマンド プロンプトで次のコマンドを使用して、AD FS サービスをインストールします。</span><span class="sxs-lookup"><span data-stu-id="a5937-183">Next, install the AD FS service with this command at the Windows PowerShell command prompt on ADFS1:</span></span>
  
```powershell
Install-WindowsFeature ADFS-Federation -IncludeManagementTools
```

<span data-ttu-id="a5937-184">インストールが完了するまで待ちます。</span><span class="sxs-lookup"><span data-stu-id="a5937-184">Wait for the installation to complete.</span></span>
  
<span data-ttu-id="a5937-185">次いで、次の手順で AD FS サービスを構成します。</span><span class="sxs-lookup"><span data-stu-id="a5937-185">Next, configure the AD FS service with these steps:</span></span>
  
1. <span data-ttu-id="a5937-186">[ **スタート] を** 選択し、[サーバー マネージャー] **アイコンを選択** します。</span><span class="sxs-lookup"><span data-stu-id="a5937-186">Select **Start**, and then select the **Server Manager** icon.</span></span>
    
2. <span data-ttu-id="a5937-187">サーバー マネージャーのツリー ウィンドウで、[FS] を **ADします**。</span><span class="sxs-lookup"><span data-stu-id="a5937-187">In the tree pane of Server Manager, select **AD FS**.</span></span>
    
3. <span data-ttu-id="a5937-188">上部のツール バーでオレンジ色の注意記号を選択し、[このサーバーでフェデレーション サービスを構成する **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a5937-188">In the tool bar at the top, select the orange caution symbol, and then select **Configure the federation service on this server**.</span></span>
    
4. <span data-ttu-id="a5937-189">Active Directory **フェデレーション サービス** 構成ウィザードの [ようこそ] ページで、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="a5937-189">On the **Welcome** page of the Active Directory Federation Services Configuration Wizard, select **Next**.</span></span>
    
5. <span data-ttu-id="a5937-190">[DS を **ConnectするAD] ページで、[** 次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="a5937-190">On the **Connect to AD DS** page, select **Next**.</span></span>
    
6. <span data-ttu-id="a5937-191">**[サービスのプロパティの指定]** ページで、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="a5937-191">On the **Specify Service Properties** page:</span></span>
    
  - <span data-ttu-id="a5937-192">[SSL **証明書]** で下矢印を選択し、フェデレーション サービス FQDN の名前を持つ証明書を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5937-192">For **SSL Certificate**, select the down arrow, and then select the certificate with the name of your federation service FQDN.</span></span>
    
  - <span data-ttu-id="a5937-193">[ **フェデレーション サービスの表示名]** に、架空の組織の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="a5937-193">In **Federation Service Display Name**, enter the name of your fictional organization.</span></span>
    
  - <span data-ttu-id="a5937-194">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5937-194">Select **Next**.</span></span>
    
7. <span data-ttu-id="a5937-195">[サービス アカウント **の指定] ページで** 、[アカウント **名の選択]** **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a5937-195">On the **Specify Service Account** page, select **Select** for **Account name**.</span></span>
    
8. <span data-ttu-id="a5937-196">[**ユーザーまたはサービス アカウントの選択]** で **、ADFS-Service** と入力し、[名前の確認] を選択し **、[OK] を選択します**。 </span><span class="sxs-lookup"><span data-stu-id="a5937-196">In **Select User or Service Account**, enter **ADFS-Service**, select **Check Names**, and then select **OK**.</span></span>
    
9. <span data-ttu-id="a5937-197">[ **アカウント パスワード]** で、アカウントのパスワードをADFS-Serviceし、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="a5937-197">In **Account Password**, enter the password for the ADFS-Service account, and then select **Next**.</span></span>
    
10. <span data-ttu-id="a5937-198">[構成データベース **の指定] ページで** 、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="a5937-198">On the **Specify Configuration Database** page, select **Next**.</span></span>
    
11. <span data-ttu-id="a5937-199">[オプションの **確認] ページで** 、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="a5937-199">On the **Review Options** page, select **Next**.</span></span>
    
12. <span data-ttu-id="a5937-200">[前提条件 **のチェック] ページで、[** 構成] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="a5937-200">On the **Pre-requisite Checks** page, select **Configure**.</span></span>

13. <span data-ttu-id="a5937-201">[結果] **ページで** 、[閉じる] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a5937-201">On the **Results** page, select **Close**.</span></span>
    
14. <span data-ttu-id="a5937-202">[ **スタート] を** 選択し、電源アイコンを選択し、[再起動] **を選択し**、[続行] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="a5937-202">Select **Start**, select the power icon, select **Restart**, and then select **Continue**.</span></span>
    
<span data-ttu-id="a5937-203">[Azure portal](https://portal.azure.com) から、CORP\\User1 アカウントの資格情報を使用して PROXY1 に接続します。</span><span class="sxs-lookup"><span data-stu-id="a5937-203">From the [Azure portal](https://portal.azure.com), connect to PROXY1 with the CORP\\User1 account credentials.</span></span>
  
<span data-ttu-id="a5937-204">その次に、次の手順を使用して、**PROXY1 と APP1 の両方** に自己署名証明書をインストールします。</span><span class="sxs-lookup"><span data-stu-id="a5937-204">Next, use these steps to install the self-signed certificate on **both PROXY1 and APP1**.</span></span>
  
1. <span data-ttu-id="a5937-205">[ **スタート] を** 選択し、mmc.exe入力し **、Enter** キーを **押します**。</span><span class="sxs-lookup"><span data-stu-id="a5937-205">Select **Start**, enter **mmc.exe**, and then press **Enter**.</span></span>
    
2. <span data-ttu-id="a5937-206">[**ファイル] >アドインの追加と削除スナップ選択します**。</span><span class="sxs-lookup"><span data-stu-id="a5937-206">Select **File > Add/Remove Snap-in**.</span></span>
    
3. <span data-ttu-id="a5937-207">[**アドインの追加とスナップ]** で、使用可能なスナップインの一覧で [証明書] をダブルクリックし、[**コンピューター** アカウント] を選択し、[次へ] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="a5937-207">In **Add or Remove Snap-ins**, double-click **Certificates** in the list of available snap-ins, select **Computer account**, and then select **Next**.</span></span>
    
4. <span data-ttu-id="a5937-208">[ **コンピューターの選択]** で、[ **完了] を選択** し **、[OK] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a5937-208">In **Select Computer**, select **Finish**, and then select **OK**.</span></span>
    
5. <span data-ttu-id="a5937-209">ツリー ウィンドウで、[証明書 (**ローカル コンピューター) 個人用証明書]**  >  **を**  >  **開きます**。</span><span class="sxs-lookup"><span data-stu-id="a5937-209">In the tree pane, open **Certificates (Local Computer)** > **Personal** > **Certificates**.</span></span>
    
6. <span data-ttu-id="a5937-210">[個人] を選択して保持 (または右クリック)**し、[** すべてのタスク] を選択し、[インポート] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="a5937-210">Select and hold (or right-click) **Personal**, select **All tasks**, and then select **Import**.</span></span>
    
7. <span data-ttu-id="a5937-211">[ようこそ] **ページで** 、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="a5937-211">On the **Welcome** page, select **Next**.</span></span>
    
8. <span data-ttu-id="a5937-212">[インポート **するファイル] ページで\*\*\*\*\\ \\ 、adfs1 \\ certs \\ ssl.pfx と** 入力し、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="a5937-212">On the **File to Import** page, enter **\\\\adfs1\\certs\\ssl.pfx**, and then select **Next**.</span></span>
    
9. <span data-ttu-id="a5937-213">[プライベート **キー保護] ページで**、[パスワード]に証明書パスワードを入力し、[次へ] を選択 **します。**</span><span class="sxs-lookup"><span data-stu-id="a5937-213">On the **Private key protection** page, enter the certificate password in **Password**, and then select **Next.**</span></span>
    
10. <span data-ttu-id="a5937-214">[証明書ストア **] ページで、[** 次へ] を **選択します。**</span><span class="sxs-lookup"><span data-stu-id="a5937-214">On the **Certificate store** page, select **Next.**</span></span>
    
11. <span data-ttu-id="a5937-215">[完了] **ページで、[** 完了] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="a5937-215">On the **Completing** page, select **Finish**.</span></span>
    
12. <span data-ttu-id="a5937-216">[証明書ストア **] ページで、[** 次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="a5937-216">On the **Certificate Store** page, select **Next**.</span></span>
    
13. <span data-ttu-id="a5937-217">プロンプトが表示されたら **、[OK] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a5937-217">When prompted, select **OK**.</span></span>
    
14. <span data-ttu-id="a5937-218">ツリー ウィンドウで、[証明書] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a5937-218">In the tree pane, select **Certificates**.</span></span>
    
15. <span data-ttu-id="a5937-219">証明書を選択して保持 (または右クリック) し、[コピー] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="a5937-219">Select and hold (or right-click) the certificate, and then select **Copy**.</span></span>
    
16. <span data-ttu-id="a5937-220">ツリー ウィンドウで、[信頼されたルート証明機関 **の証明書] を**  >  **開きます**。</span><span class="sxs-lookup"><span data-stu-id="a5937-220">In the tree pane, open **Trusted Root Certification Authorities** > **Certificates**.</span></span>
    
17. <span data-ttu-id="a5937-221">インストールされている証明書の一覧の下にマウス ポインターを移動し、長押し (または右クリック) し、[貼り付け] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="a5937-221">Move your mouse pointer below the list of installed certificates, select and hold (or right-click), and then select **Paste**.</span></span>
    
<span data-ttu-id="a5937-222">管理者レベルの PowerShell コマンド プロンプトを開き、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a5937-222">Open an administrator-level PowerShell command prompt and run the following command:</span></span>
  
```powershell
Install-WindowsFeature Web-Application-Proxy -IncludeManagementTools
```

<span data-ttu-id="a5937-223">インストールが完了するまで待ちます。</span><span class="sxs-lookup"><span data-stu-id="a5937-223">Wait for the installation to complete.</span></span>
  
<span data-ttu-id="a5937-224">次の手順を使用して、Web アプリケーション プロキシ サービスを構成し、そのフェデレーション サーバーとして ADFS1 を使用します。</span><span class="sxs-lookup"><span data-stu-id="a5937-224">Use these steps to configure the web application proxy service to use ADFS1 as its federation server:</span></span>
  
1. <span data-ttu-id="a5937-225">[スタート **] を** 選択し、[サーバー マネージャー] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a5937-225">Select **Start**, and then select **Server Manager**.</span></span>
    
2. <span data-ttu-id="a5937-226">ツリー ウィンドウで、[リモート アクセス] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a5937-226">In the tree pane, select **Remote Access**.</span></span>
    
3. <span data-ttu-id="a5937-227">上部のツール バーでオレンジ色の注意記号を選択し、[Web アプリケーション プロキシ ウィザードを開く **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a5937-227">In the tool bar at the top, select the orange caution symbol, and then select **Open the Web Application Proxy Wizard**.</span></span>
    
4. <span data-ttu-id="a5937-228">Web アプリケーション **プロキシ構成** ウィザードの [ようこそ] ページで、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="a5937-228">On the **Welcome** page of the Web Application Proxy Configuration Wizard, select **Next**.</span></span>
    
5. <span data-ttu-id="a5937-229">**[フェデレーション サーバー]** ページで、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="a5937-229">On the **Federation Server** page:</span></span>
    
  - <span data-ttu-id="a5937-230">[フェデレーション **サービス名] ボックス** に、フェデレーション サービス FQDN を入力します。</span><span class="sxs-lookup"><span data-stu-id="a5937-230">In the **Federation service name** box, enter your federation service FQDN.</span></span>
    
  - <span data-ttu-id="a5937-231">[ユーザー名 **] ボックスに\*\*\*\*「CORP \\ User1」と入力します**。</span><span class="sxs-lookup"><span data-stu-id="a5937-231">In the **User name** box, enter **CORP\\User1**.</span></span>
    
  - <span data-ttu-id="a5937-232">[パスワード **] ボックス** に、User1 アカウントのパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="a5937-232">In the **Password** box, enter the password for the User1 account.</span></span>
    
  - <span data-ttu-id="a5937-233">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5937-233">Select **Next**.</span></span>
    
6. <span data-ttu-id="a5937-234">[FS **プロキシAD]** ページで、下矢印を選択し、フェデレーション サービス FQDN の証明書を選択し、[次へ] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="a5937-234">On the **AD FS Proxy Certificate** page, select the down arrow, select the certificate with your federation service FQDN, and then select **Next**.</span></span>
    
7. <span data-ttu-id="a5937-235">[確認] **ページで** 、[構成] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="a5937-235">On the **Confirmation** page, select **Configure**.</span></span>
    
8. <span data-ttu-id="a5937-236">[結果] **ページで** 、[閉じる] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a5937-236">On the **Results** page, select **Close**.</span></span>
    
## <a name="phase-5-configure-microsoft-365-for-federated-identity"></a><span data-ttu-id="a5937-237">フェーズ 5: フェデレーション ID に対応するよう Microsoft 365 を構成する</span><span class="sxs-lookup"><span data-stu-id="a5937-237">Phase 5: Configure Microsoft 365 for federated identity</span></span>

<span data-ttu-id="a5937-238">[Azure portal](https://portal.azure.com) を使用して、CORP\\User1 アカウントの資格情報で APP1 仮想マシンに接続します。</span><span class="sxs-lookup"><span data-stu-id="a5937-238">Use the [Azure portal](https://portal.azure.com) to connect to the APP1 virtual machine with the CORP\\User1 account credentials.</span></span>
  
<span data-ttu-id="a5937-239">次の手順を使用して、フェデレーション認証に対応するように Azure AD Connect と Microsoft 365 サブスクリプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="a5937-239">Use these steps to configure Azure AD Connect and your Microsoft 365 subscription for federated authentication:</span></span>
  
1. <span data-ttu-id="a5937-240">デスクトップで、**[Azure AD Connect]** をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5937-240">From the desktop, double-click **Azure AD Connect**.</span></span>
    
2. <span data-ttu-id="a5937-241">[Azure **へようこそ] ページで、[構成AD Connect** を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="a5937-241">On the **Welcome to Azure AD Connect** page, select **Configure**.</span></span>
    
3. <span data-ttu-id="a5937-242">[追加タスク **] ページで** 、[ユーザー サインインの変更] **を** 選択し、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="a5937-242">On the **Additional tasks** page, select **Change user sign-in**, and then select **Next**.</span></span>
    
4. <span data-ttu-id="a5937-243">[Azure **Connect] ページAD、** グローバル管理者アカウント名とパスワードを入力し、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="a5937-243">On the **Connect to Azure AD** page, enter your global administrator account name and password, and then select **Next**.</span></span>
    
5. <span data-ttu-id="a5937-244">[ユーザー サインイン **] ページで、[FS** とのフェデレーション] を選択 **AD、[次** へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="a5937-244">On the **User sign-in** page, select **Federation with AD FS**, and then select **Next**.</span></span>
    
6. <span data-ttu-id="a5937-245">[FS ファーム **AD]** ページで、[既存の FS ファームAD使用する] を選択し、[サーバー名] ボックスに **「ADFS1」** と **入力** し、[次へ] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="a5937-245">On the **AD FS farm** page, select **Use an existing AD FS farm**, enter **ADFS1** in the **Server Name** box, and then select **Next**.</span></span>
    
7. <span data-ttu-id="a5937-246">サーバー資格情報の入力を求めるメッセージが表示されたら、CORP User1 アカウントの資格情報を入力し \\ **、[OK] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a5937-246">When prompted for server credentials, enter the credentials of the CORP\\User1 account, and then select **OK**.</span></span>
    
8. <span data-ttu-id="a5937-247">[ドメイン **管理者の資格情報]** ページで、[ユーザー名]ボックスに **「CORP \\ User1」** と入力し、[パスワード] ボックスにアカウント パスワードを **入力** し、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="a5937-247">On the **Domain Administrator** credentials page, enter **CORP\\User1** in the **Username** box, enter the account password in the **Password** box, and then select **Next**.</span></span>
    
9. <span data-ttu-id="a5937-248">[AD **FS** サービス アカウント] ページで、[ドメイン ユーザー名]ボックスに **\\ 「CORP ADFS-Service」** と入力し、[ドメイン ユーザー パスワード] ボックスにアカウント パスワードを **入力** し、[次へ] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="a5937-248">On the **AD FS service account** page, enter **CORP\\ADFS-Service** in the **Domain Username** box, enter the account password in the **Domain User Password** box, and then select **Next**.</span></span>
    
10. <span data-ttu-id="a5937-249">**[Azure AD ドメイン**] ページの [**ドメイン]** で、フェーズ 1 で以前に作成してサブスクリプションに追加したドメインの名前を選択し、[次へ] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="a5937-249">On the **Azure AD Domain** page, in **Domain**, select the name of the domain that you previously created and added to your subscription in Phase 1, and then select **Next**.</span></span>
    
11. <span data-ttu-id="a5937-250">[構成の **準備完了] ページで、[** 構成] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="a5937-250">On the **Ready to configure** page, select **Configure**.</span></span>
    
12. <span data-ttu-id="a5937-251">[インストールの **完了] ページで** 、[確認] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="a5937-251">On the **Installation complete** page, select **Verify**.</span></span>
    
    <span data-ttu-id="a5937-252">イントラネットとインターネットの構成の両方が確認されたことを示すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a5937-252">You should see messages indicating that both the intranet and internet configuration was verified.</span></span>
    
13. <span data-ttu-id="a5937-253">[インストールの **完了] ページで** 、[終了] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="a5937-253">On the **Installation complete** page, select **Exit**.</span></span>
    
<span data-ttu-id="a5937-254">フェデレーション認証が機能していることを実証するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="a5937-254">To demonstrate that federated authentication is working:</span></span>
  
1. <span data-ttu-id="a5937-255">ローカル コンピューター上でブラウザーの新しいプライベート インスタンスを開き、[https://admin.microsoft.com](https://admin.microsoft.com) にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="a5937-255">Open a new private instance of your browser on your local computer and go to [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
    
2. <span data-ttu-id="a5937-256">サインイン資格情報に「user1@」**と入力します** \<*the domain created in Phase 1*> 。</span><span class="sxs-lookup"><span data-stu-id="a5937-256">For the sign-in credentials, enter **user1@**\<*the domain created in Phase 1*>.</span></span>
    
    <span data-ttu-id="a5937-257">たとえば、テスト ドメインが testlab.contoso.com **場合は**、「user1@testlab.contoso.com」 と入力します。</span><span class="sxs-lookup"><span data-stu-id="a5937-257">For example, if your test domain is **testlab.contoso.com**, you would enter "user1@testlab.contoso.com".</span></span> <span data-ttu-id="a5937-258">Tab キー **を押** するか、自動的にリダイレクトMicrosoft 365を許可します。</span><span class="sxs-lookup"><span data-stu-id="a5937-258">Press the **Tab** key or allow Microsoft 365 to automatically redirect you.</span></span>
    
    <span data-ttu-id="a5937-259">**[この接続ではプライバシーが保護されません]** ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a5937-259">You should now see a **Your connection is not private** page.</span></span> <span data-ttu-id="a5937-260">これは、デスクトップ コンピューターで検証できない自己署名証明書を ADFS1 にインストールしたためです。</span><span class="sxs-lookup"><span data-stu-id="a5937-260">You are seeing this because you installed a self-signed certificate on ADFS1 that your desktop computer can't validate.</span></span> <span data-ttu-id="a5937-261">フェデレーション認証の運用環境デプロイメントでは、信頼された証明機関からの証明書を使用するため、ユーザーにこのページは表示されません。</span><span class="sxs-lookup"><span data-stu-id="a5937-261">In a production deployment of federated authentication, you would use a certificate from a trusted certification authority and your users would not see this page.</span></span>
    
3. <span data-ttu-id="a5937-262">[接続が **プライベートではない] ページで、[** 詳細設定] を選択 **し**、[続行]**を選択します \<*your federation service FQDN*>**。</span><span class="sxs-lookup"><span data-stu-id="a5937-262">On the **Your connection is not private** page, select **Advanced**, and then select **Proceed to \<*your federation service FQDN*>**.</span></span> 
    
4. <span data-ttu-id="a5937-263">架空の組織名のページで、次を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="a5937-263">On the page with the name of your fictional organization, sign in with the following:</span></span>
    
  - <span data-ttu-id="a5937-264">名前: **CORP\\User1**</span><span class="sxs-lookup"><span data-stu-id="a5937-264">**CORP\\User1** for the name</span></span>
    
  - <span data-ttu-id="a5937-265">User1 アカウントのパスワード</span><span class="sxs-lookup"><span data-stu-id="a5937-265">The password for the User1 account</span></span>
    
    <span data-ttu-id="a5937-266">**[Microsoft Office Home]** ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a5937-266">You should see the **Microsoft Office Home** page.</span></span>
    
<span data-ttu-id="a5937-p112">次の手順で、試用版サブスクリプションが、DC1 上でホストされている AD DS corp.contoso.com ドメインとフェデレーションされていることを実証します。認証プロセスに関する基本事項を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="a5937-p112">This procedure demonstrates that your trial subscription is federated with the AD DS corp.contoso.com domain hosted on DC1. Here are the basics of the authentication process:</span></span>
  
1. <span data-ttu-id="a5937-269">フェーズ 1 で作成したフェデレーション ドメインをサインイン アカウント名で使用すると、Microsoft 365 はブラウザーをフェデレーション サービス FQDN と PROXY1 にリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="a5937-269">When you use the federated domain that you created in Phase 1 within the sign-in account name, Microsoft 365 redirects your browser to your federation service FQDN and PROXY1.</span></span>
    
2. <span data-ttu-id="a5937-270">PROXY1 は、ローカル コンピューターに架空の会社のサインイン ページを送信します。</span><span class="sxs-lookup"><span data-stu-id="a5937-270">PROXY1 sends your local computer the fictional company sign-in page.</span></span>
    
3. <span data-ttu-id="a5937-271">CORP\\User1 とパスワードを PROXY1 に送信すると、それらは ADFS1 に転送されます。</span><span class="sxs-lookup"><span data-stu-id="a5937-271">When you send CORP\\User1 and the password to PROXY1, it forwards them to ADFS1.</span></span>
    
4. <span data-ttu-id="a5937-272">ADFS1 は、DC1 を使用して CORP\\User1 とパスワードを検証し、ローカル コンピューターにセキュリティ トークンを送信します。</span><span class="sxs-lookup"><span data-stu-id="a5937-272">ADFS1 validates CORP\\User1 and the password with DC1 and sends your local computer a security token.</span></span>
    
5. <span data-ttu-id="a5937-273">ローカル コンピューターは、セキュリティ トークンを Microsoft 365 に送信します。</span><span class="sxs-lookup"><span data-stu-id="a5937-273">Your local computer sends the security token to Microsoft 365.</span></span>
    
6. <span data-ttu-id="a5937-274">Microsoft 365 は、セキュリティ トークンが ADFS1 によって作成されたことを検証して、アクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="a5937-274">Microsoft 365 validates that the security token was created by ADFS1 and allows access.</span></span>
    
<span data-ttu-id="a5937-p113">これで、試用版のサブスクリプションがフェデレーション認証を行うように構成されました。この開発/テスト環境は、高度な認証シナリオで使用できます。</span><span class="sxs-lookup"><span data-stu-id="a5937-p113">Your trial subscription is now configured with federated authentication. You can use this dev/test environment for advanced authentication scenarios.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="a5937-277">次の手順</span><span class="sxs-lookup"><span data-stu-id="a5937-277">Next step</span></span>

<span data-ttu-id="a5937-278">Azure で Microsoft 365 用の実稼働対応の高可用性フェデレーション認証を展開する準備ができたら、「Azure での高可用性フェデレーション認証の展開Microsoft 365」を[参照してください](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)。</span><span class="sxs-lookup"><span data-stu-id="a5937-278">When you are ready to deploy production-ready, high availability federated authentication for Microsoft 365 in Azure, see [Deploy high availability federated authentication for Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md).</span></span>
  
