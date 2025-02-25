---
title: 高可用性フェデレーション認証フェーズ 2 ドメイン コントローラーの構成
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 11/25/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Ent_Solutions
ms.assetid: 6b0eff4c-2c5e-4581-8393-a36f7b36a72f
description: '概要: Microsoft Azure で Microsoft 365 の高可用性フェデレーション認証用にドメイン コントローラーとディレクトリ同期サーバーを構成します。'
ms.openlocfilehash: 765ccb0aaf2611947f505b53b5689009dadd5148
ms.sourcegitcommit: 61bdfa84f2d6ce0b61ba5df39dcde58df6b3b59d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2022
ms.locfileid: "65940692"
---
# <a name="high-availability-federated-authentication-phase-2-configure-domain-controllers"></a>高可用性フェデレーション認証のフェーズ 2: ドメイン コントローラーを構成する

Azure インフラストラクチャ サービスに Microsoft 365 フェデレーション認証の高可用性をデプロイするこのフェーズでは、2 つのドメイン コントローラーと、Azure 仮想ネットワーク内のディレクトリ同期サーバーを構成します。 オンプレミス ネットワークへのサイト間 VPN 接続を経由して認証トラフィックを送信するのではなく、Azure 仮想ネットワーク内で認証に対するクライアント Web 要求を認証できます。
  
> [!NOTE]
> Active Directory フェデレーション サービス (AD FS) は、Active Directory Domain Services (AD DS) ドメイン コントローラーの代わりに Azure Active Directory (Azure AD) を使用できません。 
  
フェーズ [3: AD FS サーバーの構成](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md)に進む前に、このフェーズを完了する必要があります。 すべてのフェーズについては、「 [Azure で Microsoft 365 の高可用性フェデレーション認証をデプロイ](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) する」を参照してください。
  
## <a name="create-the-domain-controller-virtual-machines-in-azure"></a>Azure にドメイン コントローラー仮想マシンを作成する

まず、「表 M」の「 **仮想マシン名** 」列に必要事項を入力し、必要に応じて、「 **最小サイズ** 」列で仮想マシンのサイズを変更します。
  
|**アイテム**|**仮想マシン名**|**ギャラリー イメージ**|**ストレージの種類**|**最小サイズ**|
|:-----|:-----|:-----|:-----|:-----|
|1.  <br/> |![行。](../media/Common-Images/TableLine.png)  (最初のドメイン コントローラー。例: DC1)  <br/> |Windows Server 2016 Datacenter  <br/> |Standard_LRS  <br/> |Standard_D2  <br/> |
|2。  <br/> |![行。](../media/Common-Images/TableLine.png)  (2 番目のドメイン コントローラー。例: DC2)  <br/> |Windows Server 2016 Datacenter  <br/> |Standard_LRS  <br/> |Standard_D2  <br/> |
|3。  <br/> |![行。](../media/Common-Images/TableLine.png) (ディレクトリ同期サーバー、DS1 の例)  <br/> |Windows Server 2016 Datacenter  <br/> |Standard_LRS  <br/> |Standard_D2  <br/> |
|4.  <br/> |![行。](../media/Common-Images/TableLine.png) (最初の AD FS サーバー、ADFS1 の例)  <br/> |Windows Server 2016 Datacenter  <br/> |Standard_LRS  <br/> |Standard_D2  <br/> |
|5.  <br/> |![行。](../media/Common-Images/TableLine.png) (2 つ目の AD FS サーバー、ADFS2 の例)  <br/> |Windows Server 2016 Datacenter  <br/> |Standard_LRS  <br/> |Standard_D2  <br/> |
|6.  <br/> |![行。](../media/Common-Images/TableLine.png) (最初の Web アプリケーション プロキシ サーバー、WEB1 の例)  <br/> |Windows Server 2016 Datacenter  <br/> |Standard_LRS  <br/> |Standard_D2  <br/> |
|7.  <br/> |![行。](../media/Common-Images/TableLine.png) (2 つ目の Web アプリケーション プロキシ サーバー、WEB2 の例)  <br/> |Windows Server 2016 Datacenter  <br/> |Standard_LRS  <br/> |Standard_D2  <br/> |
   
 **表 M - Azure での Microsoft 365 の高可用性フェデレーション認証用の仮想マシン**
  
仮想マシンのサイズの一覧については、「[Azure の仮想マシンのサイズ](/azure/virtual-machines/sizes)」を参照してください。
  
次に示す Azure PowerShell コマンド ブロックは、2 つのドメイン コントローラー用の仮想マシンを作成します。 変数の値を指定し、文字を \< and > 削除します。 なお、この Azure PowerShell コマンド ブロックは、次の表の値を使用します。
  
- 表 M: 仮想マシン用
    
- 表 R: リソース グループ用
    
- 表 V: 仮想ネットワークの設定用
    
- 表 S: サブネット用
    
- 表 I: 静的 IP アドレス用
    
- 表 A: 可用性セット用
    
[フェーズ 1: Azure の構成](high-availability-federated-authentication-phase-1-configure-azure.md)でテーブル R、V、S、I、A を定義したことを思い出してください。
  
> [!NOTE]
> 次のコマンド セットは、Azure PowerShell の最新版を使用します。 [Azure PowerShell の概要に](/powershell/azure/get-started-azureps)関するページを参照してください。 
  
すべてに適切な値を指定したら、その結果のブロックを Azure PowerShell プロンプト、またはローカル コンピューターの PowerShell 統合スクリプト環境 (ISE) で実行します。
  
> [!TIP]
> カスタム設定に基づいてすぐに実行できる PowerShell コマンド ブロックを生成するには、この [Microsoft Excel 構成ブック](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx)を使用します。 

```powershell
# Set up variables common to both virtual machines
$locName="<your Azure location>"
$vnetName="<Table V - Item 1 - Value column>"
$subnetName="<Table S - Item 1 - Value column>"
$avName="<Table A - Item 1 - Availability set name column>"
$rgNameTier="<Table R - Item 1 - Resource group name column>"
$rgNameInfra="<Table R - Item 4 - Resource group name column>"

$rgName=$rgNameInfra
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$subnet=Get-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $subnetName

$rgName=$rgNameTier
$avSet=Get-AzAvailabilitySet -Name $avName -ResourceGroupName $rgName 

# Create the first domain controller
$vmName="<Table M - Item 1 - Virtual machine name column>"
$vmSize="<Table M - Item 1 - Minimum size column>"
$staticIP="<Table I - Item 1 - Value column>"
$diskStorageType="<Table M - Item 1 - Storage type column>"
$diskSize=<size of the extra disk for Active Directory Domain Services (AD DS) data in GB>

$nic=New-AzNetworkInterface -Name ($vmName +"-NIC") -ResourceGroupName $rgName -Location $locName -Subnet $subnet -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName $vmName -VMSize $vmSize -AvailabilitySetId $avset.Id
$vm=Set-AzVMOSDisk -VM $vm -Name ($vmName +"-OS") -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType $diskStorageType
$diskConfig=New-AzDiskConfig -AccountType $diskStorageType -Location $locName -CreateOption Empty -DiskSizeGB $diskSize
$dataDisk1=New-AzDisk -DiskName ($vmName + "-DataDisk1") -Disk $diskConfig -ResourceGroupName $rgName
$vm=Add-AzVMDataDisk -VM $vm -Name ($vmName + "-DataDisk1") -CreateOption Attach -ManagedDiskId $dataDisk1.Id -Lun 1
$cred=Get-Credential -Message "Type the name and password of the local administrator account for the first domain controller." 
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName $vmName -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm

# Create the second domain controller
$vmName="<Table M - Item 2 - Virtual machine name column>"
$vmSize="<Table M - Item 2 - Minimum size column>"
$staticIP="<Table I - Item 2 - Value column>"
$diskStorageType="<Table M - Item 2 - Storage type column>"
$diskSize=<size of the extra disk for AD DS data in GB>

$nic=New-AzNetworkInterface -Name ($vmName +"-NIC") -ResourceGroupName $rgName -Location $locName -Subnet $subnet -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName $vmName -VMSize $vmSize -AvailabilitySetId $avset.Id
$vm=Set-AzVMOSDisk -VM $vm -Name ($vmName +"-OS") -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType $diskStorageType
$diskConfig=New-AzDiskConfig -AccountType $diskStorageType -Location $locName -CreateOption Empty -DiskSizeGB $diskSize
$dataDisk1=New-AzDisk -DiskName ($vmName + "-DataDisk1") -Disk $diskConfig -ResourceGroupName $rgName
$vm=Add-AzVMDataDisk -VM $vm -Name ($vmName + "-DataDisk1") -CreateOption Attach -ManagedDiskId $dataDisk1.Id -Lun 1
$cred=Get-Credential -Message "Type the name and password of the local administrator account for the second domain controller." 
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName $vmName -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm

# Create the directory synchronization server
$vmName="<Table M - Item 3 - Virtual machine name column>"
$vmSize="<Table M - Item 3 - Minimum size column>"
$staticIP="<Table I - Item 3 - Value column>"
$diskStorageType="<Table M - Item 3 - Storage type column>"

$nic=New-AzNetworkInterface -Name ($vmName +"-NIC") -ResourceGroupName $rgName -Location $locName -Subnet $subnet -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName $vmName -VMSize $vmSize

$cred=Get-Credential -Message "Type the name and password of the local administrator account for the directory synchronization server." 
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName $vmName -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name ($vmName +"-OS") -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType $diskStorageType
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

> [!NOTE]
> これらの仮想マシンはイントラネット アプリケーション向けのため、パブリック IP アドレスや DNS ドメイン名のラベルが割り当てられていません。また、インターネットに公開もされていません。ただし、これは Azure ポータルから接続できないことも意味します。仮想マシンのプロパティを表示したときに、**[接続]** オプションは使用できない状態になります。リモート デスクトップ接続アクセサリなどのリモート デスクトップ ツールを使用して、仮想マシンのプライベート IP アドレスまたはイントラネット DNS 名で仮想マシンに接続します。
  
## <a name="configure-the-first-domain-controller"></a>最初のドメイン コントローラーを構成する

任意のリモート デスクトップ クライアントを使用して、最初のドメイン コント ローラー仮想マシンへのリモート デスクトップ接続を作成します。イントラネット DNS を使用するか、ローカル管理者アカウントのコンピューター名と資格情報を使用します。
  
次に、最初のドメイン コントローラー仮想マシンの Windows PowerShell コマンド プロンプトから次のコマンドを使用して、 **最初のドメイン コントローラーに追加の** データ ディスクを追加します。
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

次に、最初のドメイン コントローラーから組織ネットワーク上の場所への接続をテストします。テストには、組織ネットワーク上のリソースの名前と IP アドレスを探索する **ping** コマンドを使用します。
  
この手順により、DNS の名前解決が正常に動作していること (仮想マシンがオンプレミスの DNS サーバーで正しく構成されていること) を確認します。また、クロスプレミスの仮想ネットワークでパケットが送受信できることを確認します。この基本的なテストに失敗した場合は、IT 部門に問い合わせて、DNS の名前解決とパケット配信に関する問題のトラブルシューティングを実施してください。
  
次に、最初のドメイン コントローラーの Windows PowerShell コマンド プロンプトで、次に示すコマンドを実行します。
  
```powershell
$domname="<DNS domain name of the domain for which this computer will be a domain controller, such as corp.contoso.com>"
$cred = Get-Credential -Message "Enter credentials of an account with permission to join a new domain controller to the domain"
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSDomainController -InstallDns -DomainName $domname  -DatabasePath "F:\NTDS" -SysvolPath "F:\SYSVOL" -LogPath "F:\Logs" -Credential $cred
```

ドメイン管理者アカウントの資格情報の入力を求めるダイアログが表示されます。コンピューターが再起動されます。
  
## <a name="configure-the-second-domain-controller"></a>2 番目のドメイン コントローラーを構成する

任意のリモート デスクトップ クライアントを使用して、2 番目のドメイン コント ローラー仮想マシンへのリモート デスクトップ接続を作成します。イントラネット DNS を使用するか、ローカル管理者アカウントのコンピューター名と資格情報を使用します。
  
次に、2 つ目のドメイン コントローラー仮想マシンの Windows PowerShell コマンド プロンプトから次のコマンドを使用して、 **2 つ目のドメイン コントローラーに** 余分なデータ ディスクを追加する必要があります。
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

次に、以下のコマンドを実行します。
  
```powershell
$domname="<DNS domain name of the domain for which this computer will be a domain controller, such as corp.contoso.com>"
$cred = Get-Credential -Message "Enter credentials of an account with permission to join a new domain controller to the domain"
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSDomainController -InstallDns -DomainName $domname  -DatabasePath "F:\NTDS" -SysvolPath "F:\SYSVOL" -LogPath "F:\Logs" -Credential $cred

```

ドメイン管理者アカウントの資格情報の入力を求めるダイアログが表示されます。コンピューターが再起動されます。
  
次に、DNS サーバーとして使用する 2 つの新しいドメイン コントローラーの IP アドレスを Azure が仮想マシンに割り当てるように、仮想ネットワークの DNS サーバーを更新する必要があります。 変数を入力し、ローカル コンピューターで Windows PowerShell コマンド プロンプトから次のコマンドを実行します。
  
```powershell
$rgName="<Table R - Item 4 - Resource group name column>"
$adrgName="<Table R - Item 1 - Resource group name column>"
$locName="<your Azure location>"
$vnetName="<Table V - Item 1 - Value column>"
$onpremDNSIP1="<Table D - Item 1 - DNS server IP address column>"
$onpremDNSIP2="<Table D - Item 2 - DNS server IP address column>"
$staticIP1="<Table I - Item 1 - Value column>"
$staticIP2="<Table I - Item 2 - Value column>"
$firstDCName="<Table M - Item 1 - Virtual machine name column>"
$secondDCName="<Table M - Item 2 - Virtual machine name column>"

$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name $vnetName
$vnet.DhcpOptions.DnsServers.Add($staticIP1)
$vnet.DhcpOptions.DnsServers.Add($staticIP2) 
$vnet.DhcpOptions.DnsServers.Remove($onpremDNSIP1)
$vnet.DhcpOptions.DnsServers.Remove($onpremDNSIP2) 
Set-AzVirtualNetwork -VirtualNetwork $vnet
Restart-AzVM -ResourceGroupName $adrgName -Name $firstDCName
Restart-AzVM -ResourceGroupName $adrgName -Name $secondDCName
```

2 つのドメイン コントローラーを再起動して、これらが DNS サーバーとしてオンプレミスの DNS サーバーで構成されないようにします。これらはいずれも DNS サーバーなので、ドメイン コントローラーに昇格されたときに、自動的に DNS フォワーダーとして、オンプレミスの DNS サーバーで構成されていました。
  
次に、Active Directory のレプリケーション サイトを作成して、Azure 仮想ネットワークのサーバーがローカル ドメイン コントローラーを使用するようにする必要があります。ドメイン管理者アカウントを使用してどちらかのドメイン コントローラーに接続し、管理者レベルの Windows PowerShell プロンプトから次に示すコマンドを実行します。
  
```powershell
$vnet="<Table V - Item 1 - Value column>"
$vnetSpace="<Table V - Item 4 - Value column>"
New-ADReplicationSite -Name $vnet 
New-ADReplicationSubnet -Name $vnetSpace -Site $vnet
```

## <a name="configure-the-directory-synchronization-server"></a>ディレクトリ同期サーバーを構成する

任意のリモート デスクトップ クライアントを使用し、ディレクトリ同期サーバー仮想マシンへのリモート デスクトップ接続を作成します。 イントラネット DNS を使用するか、ローカル管理者アカウントのコンピューター名と資格情報を使用します。
  
次に、Windows PowerShell プロンプトでこれらのコマンドを使用して、適切な AD DS ドメインに参加させます。
  
```powershell
$domName="<AD DS domain name to join, such as corp.contoso.com>"
$cred=Get-Credential -Message "Type the name and password of a domain acccount."
Add-Computer -DomainName $domName -Credential $cred
Restart-Computer
```

次に、このフェーズが正常に完了した結果の構成を示します。コンピューター名にはプレース ホルダーを使用しています。
  
**フェーズ 2: Azure の高可用性フェデレーション認証インフラストラクチャ用のドメイン コントローラーとディレクトリ同期サーバー**

![Azure の高可用性 Microsoft 365 フェデレーション認証インフラストラクチャとドメイン コントローラーのフェーズ 2。](../media/b0c1013b-3fb4-499e-93c1-bf310d8f4c32.png)
  
## <a name="next-step"></a>次の手順

[フェーズ 3 を使用する: この](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md)ワークロードを引き続き構成するように AD FS サーバーを構成します。
  
## <a name="see-also"></a>関連項目

[Azure に Microsoft 365 の高可用性フェデレーション認証を展開する](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[Microsoft 365 開発/テスト環境のフェデレーション ID](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
[Microsoft 365 ソリューションおよびアーキテクチャ センター](../solutions/index.yml)