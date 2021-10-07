---
title: Microsoft 365 テスト環境でのシミュレートされたクロスプレミスの仮想ネットワーク
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 11/14/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: seo-marvel-apr2020
description: '概要: Microsoft 365 テスト環境として、シミュレートされたクロスプレミスの仮想ネットワークを Microsoft Azure に作成します。'
ms.openlocfilehash: 0d0e22b5c9a12f4757a6dff5892ef72a757d2bda
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60202849"
---
# <a name="simulated-cross-premises-virtual-network-in-a-microsoft-365-test-environment"></a>Microsoft 365 テスト環境でのシミュレートされたクロスプレミスの仮想ネットワーク

*このテスト ラボ ガイドは、エンタープライズ環境とテスト環境Microsoft 365両方Office 365 Enterprise使用できます。*

この記事では、2 つの Azure 仮想ネットワークを使用した、Microsoft Azure でのシミュレートされたハイブリッド クラウド環境の作成について順を追って説明します。最終的な構成は、次のようになります。 
  
![XPrem VNet の DC2 仮想マシンを使用して、シミュレートされたクロスプレム仮想ネットワーク テスト環境のフェーズ 3。](../media/simulated-cross-premises-microsoft-365-enterprise/df458c56-022b-4688-ab18-056c3fd776b4.png)
  
これは Azure IaaS ハイブリッド クラウド運用環境をシミュレートするもので、次のもので構成されます。
  
- Azure 仮想ネットワークでホストされる、シミュレートおよび単純化されたオンプレミス ネットワーク (TestLab 仮想ネットワーク)。
    
- Azure でホストされる、シミュレートされたクロスプレミスの仮想ネットワーク (XPrem)。
    
- 2 つの仮想ネットワーク間の VNet ピアリング関係。
    
- XPrem 仮想ネットワークのセカンダリ ドメイン コントローラー。
    
これは次のことを行うための基礎および共通の開始点となります。 
  
- シミュレートされた Azure IaaS ハイブリッド クラウド環境におけるアプリケーションの開発およびテスト。
    
- ハイブリッド クラウドベース IT ワークロードをシミュレートするための、コンピューターのテスト構成の作成 (TestLab 仮想ネットワーク内、および XPrem 仮想ネットワーク内)。
    
このテスト環境のセットアップには、3 つの主要なフェーズが存在します。
  
1. TestLab 仮想ネットワークを構成します。
    
2. クロスプレミスの仮想ネットワークを作成します。
    
3. DC2 を構成します。
    
> [!NOTE]
> この構成では、有料版の Azure サブスクリプションが必要です。 

結果の環境を使用して、追加のテスト ラボ ガイド[を](https://www.microsoft.com/microsoft-365/enterprise)使用して、Microsoft 365の機能を[](m365-enterprise-test-lab-guides.md)テストできます。

![Microsoft クラウドのテスト ラボ ガイド。](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> エンタープライズ テスト[Microsoft 365](../downloads/Microsoft365EnterpriseTLGStack.pdf)ガイド スタックに移動し、エンタープライズ テスト ラボ ガイド スタックの Microsoft 365記事のビジュアル マップを表示します。

## <a name="phase-1-configure-the-testlab-virtual-network"></a>フェーズ 1: TestLab 仮想ネットワークを構成する

[シミュレートされたエンタープライズ基本構成](simulated-ent-base-configuration-microsoft-365-enterprise.md)の **フェーズ 1** の手順により、TestLab という名前の Azure 仮想ネットワークに DC1、APP1、CLIENT1 コンピューターを構成します。
  
こちらが現在の構成です。 
  
![Azure のシミュレートされたエンタープライズ ベース構成。](../media/simulated-cross-premises-microsoft-365-enterprise/25a010a6-c870-4690-b8f3-84421f8bc5c7.png)
  
## <a name="phase-2-create-the-xprem-virtual-network"></a>フェーズ 2: XPrem 仮想ネットワークを作成する

このフェーズでは、新しい XPrem 仮想ネットワークを作成および構成し、それを VNet ピアリングで TestLab 仮想ネットワークに接続します。
  
最初に、ローカル コンピューターで Azure PowerShell プロンプトを起動します。
  
> [!NOTE]
> 次のコマンド セットは、Azure PowerShell の最新版を使用します。「[Azure の PowerShell コマンドレットを使う](/powershell/azureps-cmdlets-docs/)」を参照してください。 
  
このコマンドを使用して Azure アカウントにサインインします。
  
```powershell
Connect-AzAccount
```

このコマンドを使用して、サブスクリプションの名前を取得します。
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

Azure サブスクリプションを設定します。 \< and >文字を含む引用符で囲まれたすべての内容を正しい名前に置き換えます。
  
```powershell
$subscrName="<subscription name>"
Select-AzSubscription -SubscriptionName $subscrName
```

次に、これらのコマンドを使用して、XPrem 仮想ネットワークを作成し、ネットワーク セキュリティ グループで保護します。
  
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

次に、これらのコマンドを使用して、TestLab と XPrem VNet 間の VNet ピアリング関係を作成します。
  
```powershell
$rgName="<name of the resource group that you used for your TestLab virtual network>"
$vnet1=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name TestLab
$vnet2=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name XPrem
Add-AzVirtualNetworkPeering -Name TestLab2XPrem -VirtualNetwork $vnet1 -RemoteVirtualNetworkId $vnet2.Id
Add-AzVirtualNetworkPeering -Name XPrem2TestLab -VirtualNetwork $vnet2 -RemoteVirtualNetworkId $vnet1.Id
```

こちらが現在の構成です。 
  
![XPrem VNet と VNet ピアリング関係を持つ、シミュレートされたクロスプレム仮想ネットワーク テスト環境のフェーズ 2。](../media/simulated-cross-premises-microsoft-365-enterprise/cac5e999-69c7-4f4c-bfce-a7f4006115ef.png)
  
## <a name="phase-3-configure-dc2"></a>フェーズ 3: DC2 を構成する

このフェーズでは、XPrem 仮想ネットワークにおいて DC2 仮想マシンを作成し、それをレプリカ ドメイン コントローラーとして構成します。
  
まず、DC2 用の仮想マシンを作成します。自分のローカル コンピューターの Azure PowerShell コマンド プロンプトで、これらのコマンドを実行します。
  
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

次に、ローカル管理者のアカウント名とパスワードを使用して、[Azure portal](https://portal.azure.com) から新しい DC2 仮想マシンに接続します。
  
次に、Windows ファイアウォール ルールを構成して、基本的な接続テストのトラフィックを許可します。DC2 の管理者レベルの Windows PowerShell コマンド プロンプトから、これらのコマンドを実行します。 
  
```powershell
Set-NetFirewallRule -DisplayName "File and Printer Sharing (Echo Request - ICMPv4-In)" -enabled True
ping dc1.corp.contoso.com
```

ping コマンドを実行すると、IP アドレス 10.0.0.4 から 4 つの正常な応答があります。これは、VNet ピアリング関係間のトラフィックのテストです。 
  
次に、DC2 の Windows PowerShell コマンド プロンプトから次のコマンドを使用して、新しいボリュームとして別のデータ ディスクをドライブ文字 F: で追加します。
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

次に corp.contoso.com ドメインのレプリカ ドメイン コントローラーとして DC2 を構成します。DC2 の Windows PowerShell コマンド プロンプトから次のコマンドを実行します。
  
```powershell
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSDomainController -Credential (Get-Credential CORP\User1) -DomainName "corp.contoso.com" -InstallDns:$true -DatabasePath "F:\NTDS" -LogPath "F:\Logs" -SysvolPath "F:\SYSVOL"
```

CORP\\User1 パスワードおよびディレクトリ サービス復元モード (DSRM) パスワードの両方の入力、ならびに DC2 の再起動が必要となる点に注意してください。 
  
XPrem 仮想ネットワーク独自の DNS サーバー (DC2) の準備が整ったので、この DNS サーバーを使用するよう XPrem 仮想ネットワークを構成する必要があります。自分のローカル コンピューターの Azure PowerShell コマンド プロンプトから、これらのコマンドを実行します。
  
```powershell
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -name "XPrem"
$vnet.DhcpOptions.DnsServers="192.168.0.4" 
Set-AzVirtualNetwork -VirtualNetwork $vnet
Restart-AzVM -ResourceGroupName $rgName -Name "DC2"
```

ローカル コンピューター上の Azure portal から、CORP\\User1 の資格情報を使用して DC1 に接続します。コンピューターおよびユーザーがローカルのドメイン コントローラーを使用して認証を行うように CORP ドメインを構成するには、DC1 の管理者レベルの Windows PowerShell コマンド プロンプトから次のコマンドを実行します。
  
```powershell
New-ADReplicationSite -Name "TestLab" 
New-ADReplicationSite -Name "XPrem"
New-ADReplicationSubnet -Name "10.0.0.0/8" -Site "TestLab"
New-ADReplicationSubnet -Name "192.168.0.0/16" -Site "XPrem"
```

こちらが現在の構成です。 
  
![XPrem VNet の DC2 仮想マシンを使用して、シミュレートされたクロスプレム仮想ネットワーク テスト環境のフェーズ 3。](../media/simulated-cross-premises-microsoft-365-enterprise/df458c56-022b-4688-ab18-056c3fd776b4.png)
  
シミュレートされた Azure ハイブリッド クラウド環境をテストする準備ができました。
  
これで、エンタープライズ向けアプリケーションの追加機能をMicrosoft 365[準備ができました](https://www.microsoft.com/microsoft-365/enterprise)。
  
## <a name="next-steps"></a>次の手順

こうした追加のテスト ラボ ガイドについて説明します。
  
- [ID](m365-enterprise-test-lab-guides.md#identity)
- [モバイル デバイス管理](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [情報保護](m365-enterprise-test-lab-guides.md#information-protection)

## <a name="see-also"></a>関連項目

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)

[Microsoft 365 for Enterprise の概要](microsoft-365-overview.md)

[Microsoft 365 for enterprise のドキュメント](/microsoft-365-enterprise/)