---
title: Microsoft 365 用のシミュレートされたエンタープライズ基本構成
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2019
audience: ITPro
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
ms.openlocfilehash: 98eb336a0f63f47b4b79de44c46fcd81f1d9c9f6
ms.sourcegitcommit: 2bdd7b535a7d2a4896df130b7047f8c85f4d47b4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2019
ms.locfileid: "38711881"
---
# <a name="the-simulated-enterprise-base-configuration"></a>シミュレートされたエンタープライズ基本構成

*このテストラボ ガイドは、Microsoft 365 Enterprise および Office 365 Enterprise テスト環境に使用できます。*

この記事では、次のものを含む Microsoft 365 Enterprise のシンプルな環境を作成するための詳しい手順について説明します。

- Microsoft 365 E5 の試用版または有料サブスクリプション。
- インターネットに接続している組織の簡易型イントラネット。Azure 仮想ネットワーク上に配置された 3 つの仮想マシン (DC1、APP1、および CLIENT1) で構成されます。
 
![シミュレートされたエンタープライズ基本構成](media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase4.png)

完成した環境は、その他の [テスト ラボ ガイド](m365-enterprise-test-lab-guides.md)や各自の実験で、[Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise) の機能をテストするために使用できます。

![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> [ここ](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事のビジュアル マップを確認してください。

## <a name="phase-1-create-a-simulated-intranet"></a>フェーズ 1: シミュレートされたイントラネットを作成する

このフェーズでは、Active Directory Domain Services (AD DS) ドメイン コントローラー、アプリケーション サーバー、クライアント コンピューターを含むシミュレートされたイントラネットを Azure インフラストラクチャ サービスに作成します。 

こうしたコンピューターは、他の [Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)でハイブリッド ID およびその他の機能の構成とデモンストレーションのために使用します。

### <a name="method-1-build-your-simulated-intranet-with-an-azure-resource-manager-template"></a>方法 1: Azure Resource Manager テンプレートを使用して、シミュレートされたイントラネットを構築する

この方法では、Azure Resource Manager (ARM) テンプレートを使用してシミュレートされたイントラネットを構築します。ARM テンプレートには、Azure ネットワーク インフラストラクチャおよび仮想マシンを作成するためのすべての手順およびそれらの構成が含まれています。

テンプレートを展開する前に「[テンプレートのReadme ページ](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems)」を確認し、次の情報をご用意ください。

- テスト環境のパブリック DNS ドメイン名 (testlab.\<your public domain>)。[**カスタム デプロイ**] ページの [**ドメイン名**] フィールドにこの名前を入力する必要があります。
- 仮想マシンのパブリック IP アドレスの URL の DNS ラベル プレフィックス。[**カスタム デプロイ**] ページの [**DNS ラベル プレフィックス**] フィールドにこのラベルを入力する必要があります。

手順をすべて確認したら、[[テンプレートの Readme ページ](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems)] で [**Azure に展開**] をクリックして展開を開始します。

>[!Note]
>ARM テンプレートで作成されたシミュレートされたイントラネットでは、Azure の有料サブスクリプションが必要です。
>

こちらがテンプレート完了後の構成です。

![Azure インフラストラクチャ サービスでのシミュレートされたイントラネット](media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase3.png)

### <a name="method-2-build-your-simulated-intranet-with-azure-powershell"></a>方法 2: Azure PowerShell を使用してシミュレートされたイントラネットを構築する

この方法では、Windows PowerShell と Azure PowerShell モジュールを使用してネットワーク インフラストラクチャ、仮想マシン、およびその構成を構築します。

Azure インフラストラクチャの要素を作成する作業を、PowerShell を使って 1 つずつ手順を進める方法で経験してみたいという場合は、この方法をお使いください。その後、Azure で他の仮想マシンを展開するために PowerShell コマンドのブロックをカスタマイズできます。

#### <a name="step-1-create-dc1"></a>ステップ 1: DC1 を作成する

このステップでは、Azure 仮想ネットワークを作成し、DC1 (AD DS ドメインのドメイン コントローラーである仮想マシン) を追加します。

最初に、ローカル コンピューターで Windows PowerShell コマンド プロンプトを起動します。
  
> [!NOTE]
> 次のコマンド セットは、Azure PowerShell の最新版を使用します。「[Azure の PowerShell コマンドレットを使う](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/)」を参照してください。 
  
次のコマンドを使用して Azure アカウントにログインします。
  
```powershell
Connect-AzAccount
```

次のコマンドを使用して、サブスクリプションの名前を取得します。
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

Azure サブスクリプションを設定します。二重引用符内のすべて (「<」と「>」の文字を含む) を正しい名前に置き換えます。
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

次に、シミュレートされたエンタープライズ テスト ラボ用の新しいリソース グループを作成します。一意のリソース グループ名を決定するには、このコマンドを使用して既存のリソース グループの一覧を表示します。
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

これらのコマンドを使用して、新しいリソース グループを作成します。二重引用符内のすべて (< 文字と > 文字を含む) を正しい名前に置き換えます。
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

次に、シミュレートされたエンタープライズ環境の Corpnet サブネットをホストする TestLab 仮想ネットワークを作成し、ネットワーク セキュリティ グループで保護します。リソース グループの名前を入力し、これらのコマンドをローカル コンピューターの PowerShell コマンド プロンプトで実行します。
  
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

次に、DC1 仮想マシンを作成し、Testlab 仮想ネットワークの仮想マシン用の **testlab.**\<パブリック ドメイン> AD DS ドメインと DNS サーバーのドメイン コントローラーとして構成します。たとえば、パブリック ドメイン名が **<span>contoso</span>.com** の場合、DC1 仮想マシンは **<span>testlab</span>.contoso.com** ドメインのドメイン コントローラーになります。
  
DC1 用の Azure 仮想マシンを作成するには、リソース グループの名前を入力して、次に示すコマンドをローカル コンピューターの PowerShell コマンド プロンプトから実行します。
  
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

DC1 のローカル管理者アカウントのユーザー名とパスワードを入力するようダイアログが表示されます。強力なパスワードを使用して、安全な場所に名前とパスワードの両方を記録します。
  
次に、DC1 仮想マシンに接続します。
  
1. [Azure portal](https://portal.azure.com) で、**[リソース グループ] >**「新しいリソース グループの名前」** > [DC1] > [接続]** の順にクリックします。
    
2. 起動ウィンドウで **[RDP ファイルのダウンロード]** をクリックします。ダウンロードされる DC1.rdp ファイルを開いてから、**[接続]** をクリックします。
    
3. DC1 のローカル管理者アカウント名を指定します。
    
   - Windows 7 の場合:
    
     **[Windows セキュリティ]** ダイアログ ボックスで、**[別のアカウントを使用]** をクリックします。**[ユーザー名]** に「**DC1\\**[ローカル管理者アカウント名]」を入力します。
    
   - Windows 8 または Windows 10 の場合:
    
     **[Windows セキュリティ]** ダイアログ ボックスで、**[その他]** をクリックし、**[別のアカウントを使用する]** をクリックします。**[ユーザー名]** に、「**DC1\\**[ローカル管理者アカウント名]」を入力します。
    
4. **[パスワード]** にローカル管理者アカウントのパスワードを入力して、**[OK]** をクリックします。
    
5. ダイアログが表示されたら、**[はい]** をクリックします。
    
次に、DC1 の管理者レベルの Windows PowerShell コマンド プロンプトで次のコマンドを使用して、新しいボリュームとして別のデータ ディスク (ドライブ文字 F:) を追加します。
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

次に、DC1 を **testlab.**\<パブリック ドメイン> ドメインのドメイン コントローラーと DNS サーバーとして構成します。パブリック ドメイン名を指定し、\< および > 文字を削除します。DC1 の管理者レベルの Windows PowerShell コマンド プロンプトで、これらのコマンドを実行します。
  
```powershell
$yourDomain="<your public domain>"
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSForest -DomainName testlab.$yourDomain -DatabasePath "F:\NTDS" -SysvolPath "F:\SYSVOL" -LogPath "F:\Logs"
```
セーフ モードの管理者パスワードを指定する必要があります。このパスワードは安全な場所に保管してください。
  
これらのコマンドの完了には数分かかることがあります。
  
DC1 の再起動後に、DC1 仮想マシンに再接続します。
  
1. [Azure portal](https://portal.azure.com) で、**[リソース グループ] >**「リソース グループ名」** > [DC1] > [接続]** をクリックします。
    
2. ダウンロードされる DC1.rdp ファイルを実行して、**[接続]** をクリックします。
    
3. **[Windows セキュリティ]** で **[別のアカウントを使用]** をクリックします。**[ユーザー名]** に「**TESTLAB\\**[ローカル管理者アカウント名]」を入力します。
    
4. **[パスワード]** にローカル管理者アカウントのパスワードを入力して、**[OK]** をクリックします。
    
5. ダイアログが表示されたら、**[はい]** をクリックします。
    
次に、TESTLAB ドメイン メンバー コンピューターにログインするときに使用する、Active Directory のユーザー アカウントを作成します。管理者レベルの Windows PowerShell コマンド プロンプトで、次のコマンドを実行します。
  
```powershell
New-ADUser -SamAccountName User1 -AccountPassword (read-host "Set user password" -assecurestring) -name "User1" -enabled $true -PasswordNeverExpires $true -ChangePasswordAtLogon $false
```

このコマンドでは、User1 アカウントのパスワードを入力するよう求められることに注意してください。このアカウントは、すべての TESTLAB ドメイン メンバー コンピューターのリモート デスクトップ接続に使用するため、強力なパスワードを選択してください。User1 アカウントのパスワードを記録し、セキュリティで保護された場所に保管します。
  
次に、ドメイン、エンタープライズ、およびスキーマ管理者として新しい User1 のアカウントを構成します。管理者レベルの Windows PowerShell コマンド プロンプトで、次のコマンドを実行します。
  
```powershell
$yourDomain="<your public domain>"
$domainName = "testlab."+$yourDomain
$userName="user1@" + $domainName
$userSID=(New-Object System.Security.Principal.NTAccount($userName)).Translate([System.Security.Principal.SecurityIdentifier]).Value
$groupNames=@("Domain Admins","Enterprise Admins","Schema Admins")
ForEach ($name in $groupNames) {Add-ADPrincipalGroupMembership -Identity $userSID -MemberOf (Get-ADGroup -Identity $name).SID.Value}
```

DC1 とのリモート デスクトップ セッションを終了し、TESTLAB\\User1 のアカウントを使用して再接続します。
  
次に、Ping ツールのトラフィックを許可するため、管理者レベルの Windows PowerShell コマンド プロンプトで、次のコマンドを実行します。
  
```powershell
Set-NetFirewallRule -DisplayName "File and Printer Sharing (Echo Request - ICMPv4-In)" -enabled True
```

こちらが現在の構成です。
  
![シミュレートされたエンタープライズ基本構成のステップ 1](media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase1.png)
  
#### <a name="step-2-configure-app1"></a>ステップ 2: APP1 を構成する

このステップでは、最初にWeb およびファイル共有サービスを提供するアプリケーション サーバーである APP1 を作成して構成します。

APP1 用の Azure 仮想マシンを作成するには、リソース グループの名前を入力して、次に示すコマンドをローカル コンピューターのコマンド プロンプトから実行します。
  
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

次に、APP1 のローカル管理者アカウント名とパスワードを使用して APP1 仮想マシンに接続し、Windows PowerShell コマンド プロンプトを開きます。
  
APP1 と DC1 の間の名前の解決とネットワーク通信を確認するには、**ping dc1.testlab.**\<パブリック ドメイン名> コマンドを実行し、4 つの応答があることを確認します。
  
次に、Windows PowerShell プロンプトでこれらのコマンドを使用して、APP1 仮想マシンを TESTLAB ドメインに参加させます。
  
```powershell
$yourDomain="<your public domain name>"
Add-Computer -DomainName ("testlab" + $yourDomain)
Restart-Computer
```

**Add-Computer** コマンドの実行後には、TESTLAB\\User1 ドメイン アカウントの資格情報を入力する必要がある点に注意してください。
  
APP1 の再起動後に、TESTLAB\\User1 のアカウントを使用して接続し、管理者レベルの Windows PowerShell コマンド プロンプトを開きます。
  
次に、このコマンドを APP1 の管理者レベルの Windows PowerShell コマンド プロンプトで使用して、APP1 を Web サーバーにします。
  
```powershell
Install-WindowsFeature Web-WebServer -IncludeManagementTools
```

次に、以下の PowerShell コマンドを使用して APP1 で共有フォルダーを作成し、そのフォルダー内にテキスト ファイルを作成します。
  
```powershell
New-Item -path c:\files -type directory
Write-Output "This is a shared file." | out-file c:\files\example.txt
New-SmbShare -name files -path c:\files -changeaccess TESTLAB\User1
```

こちらが現在の構成です。
  
![シミュレートされたエンタープライズ基本構成のステップ 2](media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase2.png)
  
#### <a name="step-3-configure-client1"></a>ステップ 3: CLIENT1 を構成する

このステップでは、イントラネット上の一般的なラップトップ、タブレット、またはデスクトップ コンピューターとして機能する CLIENT1 を作成して構成します。

> [!NOTE]  
> 次のコマンド セットでは、Windows Server 2016 Datacenter を実行する CLIENT1 を作成します。これは、すべての Azure サブスクリプションのタイプに対して実行できます。Visual Studio ベースの Azure サブスクリプションがある場合は、[Azure portal](https://portal.azure.com) で、Windows 10 を実行する CLIENT1 を作成できます。 
  
CLIENT1 用の Azure 仮想マシンを作成するには、リソース グループの名前を入力して、次に示すコマンドをローカル コンピューターのコマンド プロンプトから実行します。
  
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

次に、CLIENT1 のローカル管理者アカウント名とパスワードを使用して、CLIENT1 仮想マシンに接続し、管理者レベルの Windows PowerShell コマンド プロンプトを開きます。
  
CLIENT1 と DC1 の間の名前の解決とネットワーク通信を確認するには、Windows PowerShell コマンド プロンプトで **ping dc1.testlab.**\<パブリック ドメイン名> コマンドを実行し、4 つの応答があることを確認します。
  
次に、Windows PowerShell プロンプトでこれらのコマンドを使用して、CLIENT1 仮想マシンを TESTLAB ドメインに参加させます。
  
```powershell
$yourDomain="<your public domain name>"
Add-Computer -DomainName ("testlab" + $yourDomain)
Restart-Computer
```

**Add-Computer** コマンドの実行後に、TESTLAB\\User1 ドメイン アカウントの資格情報を入力する必要がある点に注意してください。
  
CLIENT1 の再起動後に、TESTLAB\\User1 のアカウント名とパスワードを使用して接続し、管理者レベルの Windows PowerShell コマンド プロンプトを開きます。
  
次に、CLIENT1 から APP1 の Web リソースおよびファイル共有リソースにアクセスできることを確認します。
  
1. サーバー マネージャーのツリー ウィンドウで、**[ローカル サーバー]** をクリックします。
    
2. **[CLIENT1 のプロパティ]** で、**[IE セキュリティ強化の構成]** の横にある **[オン]** をクリックします。
    
3. **[Internet Explorer セキュリティ強化の構成]** で、**[管理者]** と **[ユーザー]** の **[オフ]** をクリックしてから、**[OK]** をクリックします。
    
4. スタート画面で、**[Internet Explorer]** をクリックし、**[OK]** をクリックします。
    
5. アドレス バーに「**http<span>://</span>app1.testab.**\<パブリック ドメイン名>**/**」と入力し、ENTER キーを押します。APP1 の既定のインターネット インフォメーション サービスの Web ページが表示されます。
    
6. デスクトップのタスクバーで、[エクスプローラー] アイコンをクリックします。
    
7. アドレス バーに「**\\\\app1\\Files**」と入力して、ENTER キーを押します。フォルダー ウィンドウにファイルの共有フォルダーのコンテンツが表示されます。
    
8. **[ファイル]** の共有フォルダー ウィンドウで、**[Example.txt]** ファイルをダブルクリックします。Example.txt ファイルのコンテンツが表示されます。
    
9. **[example.txt - メモ帳]** と **[ファイル]** の共有フォルダーのウィンドウを閉じます。
    
こちらが現在の構成です。
  
![シミュレートされたエンタープライズ基本構成のステップ 3](media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase3.png)


## <a name="phase-2-create-your-microsoft-365-e5-subscription"></a>フェーズ 2: Microsoft 365 E5 サブスクリプションを作成する

このフェーズでは、新しい Azure AD テナントを使用する Microsoft 365 E5 サブスクリプション (運用サブスクリプションとは別のもの) を作成します。これは、次の 2 つの方法で作成できます。

- Microsoft 365 E5 の試用版サブスクリプションを使用する。 

  Microsoft 365 E5 の試用版サブスクリプションは 30 日間有効です。この有効期間は、簡単に 60 日間延長できます。試用版サブスクリプションの有効期限が切れたときには、有料版のサブスクリプションに切り替えるか、新しい試用版サブスクリプションを作成する必要があります。新しい試用版サブスクリプションを作成すると、複雑なシナリオが含まれていることもある構成を放置することになります。  

- ライセンス数の少ない Microsoft 365 E5 の個別の運用サブスクリプションを使用する。

  これには追加のコストが発生しますが、機能、構成、およびシナリオをテストするための期限切れのない実働テスト環境を確実に保持できます。この 1 つのテスト環境は、概念実証、同僚や経営者に向けたデモンストレーション、およびアプリケーションの開発とテストのために長期にわたって使用できます。この方法をお勧めします。

Microsoft 365 E5 試用版サブスクリプションを開始するには、最初に、架空の会社名と新しい Microsoft アカウントが必要になります。
  
1. この会社名には、会社名 Contoso のバリエーションを使用するようお勧めします (必須ではありません)。Contoso は、Microsoft のサンプル コンテンツで使用される架空の会社名です。ここに架空の会社名を記録してください: ![](./media/Common-Images/TableLine.png)
    
2. 新しい Microsoft アカウントにサインアップするには、[https://outlook.com](https://outlook.com) に移動して、新しい電子メール アカウントとアドレスでアカウントを作成します。このアカウントを使用して、Office 365 にサインアップします。
    
  - ここに新しいアカウントの姓名を記録してください: ![](./media/Common-Images/TableLine.png)
    
  - ここに新しい電子メール アカウントのアドレスを記録してください: ![](./media/Common-Images/TableLine.png)@outlook.com
    
### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a>Office 365 E5 試用版サブスクリプションにサインアップする

まず、Office 365 E5 試用版サブスクリプションを使用して、Microsoft 365 E5 サブスクリプションを追加します。

1. シミュレーションのエンタープライズ Office 365 開発/テスト環境の場合は、Azure portal から CORP\User1 アカウントを使用して CLIENT1 に接続します。  スタート画面から Microsoft Edge を起動して、[https://aka.ms/e5trial](https://aka.ms/e5trial) に移動します。
    
2. **[ようこそ、必要事項をご記入ください]** ページで、次に示す項目を指定します。
    
  - 所在地
    
  - 新しい Microsoft アカウントの姓名
    
  - 新しい電子メール アドレス
    
  - 勤務先電話番号
    
  - 架空の会社名
    
  - 組織の規模に [250-999 人]
    
3. **[手順はあと 1 つだけです]** をクリックします。
    
4. **[ユーザー ID の作成]** ページで、新しい電子メール アドレスに応じたユーザー名を入力し、@ 記号の後に架空の会社名を入力します (名前に含まれる空白はすべて削除します)。次に、この新しい Office 365 アカウントのパスワードを 2 回入力します。 
    
    入力したパスワードを安全な場所に記録してください。
    
    架空の会社名を記録してください (この名前を**組織名**と呼ぶことにします): ![](./media/Common-Images/TableLine.png)
    
5. **[アカウントの作成]** をクリックします。
    
6. **[ロボットではないことを証明してください]** ページで、テキスト対応の電話の電話番号を入力して、**[自分にテキスト送信]** をクリックします。
    
7. 受信したテキスト メッセージの認証コードを入力して、**[次へ]** をクリックします。
    
8. ここにサインイン ページの URL を記録してください (選択してコピー): ![](./media/Common-Images/TableLine.png)
    
9. ここにユーザー ID を記録してください (選択してコピー): ![](./media/Common-Images/TableLine.png).onmicrosoft.com
    
    この値を**Office 365 全体管理者名**と呼ぶことにします。
    
10. **[準備が整いました]** が表示されたら、その表示をクリックします。
    
11. 次のページで、Office 365 のセットアップが完了して、すべてのタイルが使用できるようになるまで待機します。
    
Office 365 ポータルのメイン ページが表示されます。このページから、Office のサービスと Microsoft 365 管理センターにアクセスできます。
  
開発/テスト環境に現在お持ちの有料サブスクリプションとは別の Azure AD テナントが存在するように、Office 365 の試用版サブスクリプションを作成します。 このように分離することにより、運用サブスクリプションに影響を与えることなく、テスト テナントでのユーザーとグループの追加と削除が可能になります。
    
### <a name="configure-your-office-365-e5-trial-subscription"></a>Office 365 E5 試用版サブスクリプションを構成する

次に、追加のユーザーで Office 365 E5 のサブスクリプションを構成し、Office 365 E5 ライセンスを割り当てます。
  
「[Office 365 PowerShell への接続](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)」の手順を使用して、CLIENT1 仮想マシンの Azure Active Directory PowerShell for Graph モジュールで Office 365 のサブスクリプションに接続します。
    
[Windows PowerShell 資格情報の要求] ダイアログ ボックスで、Office 365 全体管理者名 (例: jdoe@contosotoycompany.onmicrosoft.com) とパスワードを入力します。
  
組織名 (例: contosotoycompany)、所属地域に該当する 2 文字の国別コード、共通のアカウント パスワードを入力して、PowerShellのプロンプトから次のコマンドを実行します。

```powershell
$orgName="<organization name>"
$loc="<two-character country code, such as US>"
$commonPW="<common user account password>"
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password=$commonPW

$userUPN= "user2@" + $orgName + ".onmicrosoft.com"
New-AzureADUser -DisplayName "User 2" -GivenName User -SurName 2 -UserPrincipalName $userUPN -UsageLocation $loc -AccountEnabled $true -PasswordProfile $PasswordProfile -MailNickName "user2"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value "ENTERPRISEPREMIUM" -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign

$userUPN= "user3@" + $orgName + ".onmicrosoft.com"
New-AzureADUser -DisplayName "User 3" -GivenName User -SurName 3 -UserPrincipalName $userUPN -UsageLocation $loc -AccountEnabled $true -PasswordProfile $PasswordProfile -MailNickName "user3"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value "ENTERPRISEPREMIUM" -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign

$userUPN= "user4@" + $orgName + ".onmicrosoft.com"
New-AzureADUser -DisplayName "User 4" -GivenName User -SurName 4 -UserPrincipalName $userUPN -UsageLocation $loc -AccountEnabled $true -PasswordProfile $PasswordProfile -MailNickName "user4"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value "ENTERPRISEPREMIUM" -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign
```
> [!NOTE]
> ここで共通のパスワードを使用することで、自動化と、開発/テスト環境の構成を容易にします。 運用環境のサブスクリプションは避けるように強くお勧めします。 

#### <a name="record-key-information-for-future-reference"></a>将来の参照のために重要な情報を記録する

この記事を印刷しておき、30 日間の Office 365 試用版サブスクリプションの終了後にこの環境で必要になる特定の情報を記録しておくことをお勧めします。 試用版サブスクリプションは、追加で 30 日間まで簡単に延長できます。 永続的な開発/テスト環境では、別個の Azure AD テナントと少数のライセンスを使用して新しい有料サブスクリプションを作成します。

これらの値を記録する:
  
- Office 365 全体管理者名: ![](./media/Common-Images/TableLine.png).onmicrosoft.com (フェーズ 2 の手順 9 で入力したもの)
    
    このアカウントのパスワードも安全な場所に記録してください。
    
- 試用版サブスクリプションの組織名: ![](./media/Common-Images/TableLine.png) (フェーズ 2 の手順 4 で入力したもの)
    
- User 2、User 3、User 4、および User 5 のアカウントを一覧表示するには、次に示すコマンドを Windows PowerShell 用 Microsoft Azure Active Directory モジュールのプロンプトから実行します。
    
  ```powershell
  Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName
  ```

    ここにアカウント名を記録してください:
    
  - User 2 のアカウント名: user2@![](./media/Common-Images/TableLine.png).onmicrosoft.com
    
  - User 3 のアカウント名: user3@![](./media/Common-Images/TableLine.png).onmicrosoft.com
    
  - User 4 のアカウント名: user4@![](./media/Common-Images/TableLine.png).onmicrosoft.com
    
  - User 5 のアカウント名: user5@![](./media/Common-Images/TableLine.png).onmicrosoft.com
    
    これらのアカウントの共通パスワードも安全な場所に記録してください。
   

#### <a name="using-an-office-365-e5-devtest-environment"></a>Office 365 E5 の開発/テスト環境を使用する

Office 365 の開発/テスト環境だけが必要な場合は、ここで終了します。 

Office 365 と Microsoft 365 の両方に適用される追加のテスト ラボ ガイドについては、「[Microsoft 365 エンタープライズ テスト ラボ ガイド](m365-enterprise-test-lab-guides.md)」を参照してください。
  
### <a name="add-a-microsoft-365-e5-trial-subscription"></a>Microsoft 365 E5 の試用版サブスクリプションを追加する

次に、Microsoft 365 E5 試用版サブスクリプションにサインアップして、Office 365 E5 試用版サブスクリプションと同じ組織に追加します。
  
まず最初に、Microsoft 365 E5 試用版サブスクリプションを追加して、Microsoft 365 ライセンスを全体管理者アカウントに割り当てます。
  
1. インターネット ブラウザーのプライベート インスタンスで、全体管理者アカウントの資格情報を使用して、Microsoft 365 管理センター ([https://admin.microsoft.com](https://admin.microsoft.com)) にサインインします。
    
2. **[Microsoft 365 管理センター]** ページの左側のナビゲーションで **[請求]、[サービスを購入する]** の順にクリックします。
    
3. **[サービスを購入する]** ページで、**Microsoft 365 E5** 項目を見つけます。 その項目の上にマウス ポインターを移動させ、**[無料試用版を起動する]** をクリックします。

4. **[Microsoft 365 E5 試用版]** ページで、テキスト メッセージを受信するか電話を受けるかを選択し、電話番号を入力して、**[テキスト メッセージを送信する]** または **[電話する]** をクリックします。

5. **[注文の確認]** ページで、 **[今すぐ実行]** をクリックします。

6. **[注文の受領書]** ページで、**[続行]** をクリックします。

7. Microsoft 365 管理センターで、**[アクティブ ユーザー]** をクリックしてから、管理者アカウントをクリックします。

8. **[製品ライセンス]** の **[編集]** をクリックします。

9. Office 365 Enterprise E5 のライセンスをオフにして、Microsoft 365 E5 のライセンスをオンにします。

10. **[保存]、[閉じる]、[閉じる]** の順にクリックします。

次に、その他のすべてのアカウント (User 2、User 3、User 4、および User 5) に前述の手順 8 から 11 を繰り返します。
  
> [!NOTE]
> Microsoft 365 E5 の試用版サブスクリプションは 30 日間有効です。 永続的なテスト環境では、少数のライセンスを使用して、この試用版のサブスクリプションを有料サブスクリプションに変換します。 
  
### <a name="results"></a>結果

テスト環境は、次のようになっています。
  
- Microsoft 365 E5 の試用版サブスクリプション。
- すべての適切なユーザー アカウントが Microsoft 365 E5 を使用できるようになります。
- シミュレートおよび簡略化されたイントラネット。
    
これは、最終的な構成です。
  
![シミュレートされたエンタープライズ基本構成のフェーズ 2](media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase4.png)
  
これで、[Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise) の追加機能を試せるようになりました。
  
## <a name="next-steps"></a>次の手順

こうした追加のテスト ラボ ガイドについて説明します。
  
- [ID](m365-enterprise-test-lab-guides.md#identity)
- [モバイル デバイス管理](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [情報保護](m365-enterprise-test-lab-guides.md#information-protection)

## <a name="see-also"></a>関連項目

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Enterprise を展開する](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise のドキュメントとリソース](https://docs.microsoft.com/microsoft-365-enterprise/)
