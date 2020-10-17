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
# <a name="federated-identity-for-your-microsoft-365-test-environment"></a>Microsoft 365 テスト環境のフェデレーション ID

*このテストラボガイドは、Microsoft 365 for enterprise および Office 365 エンタープライズテスト環境の両方で使用できます。*

Microsoft 365 は、フェデレーション ID をサポートします。つまり、資格情報自体の検証を実行する代わりに、Microsoft 365 は、接続しようとしているユーザーを、Microsoft 365 が信頼するフェデレーション認証サーバーに照会します。ユーザーの資格情報が正しい場合、フェデレーション認証サーバーはセキュリティ トークンを発行し、次いでクライアントは認証の証明としてそのセキュリティ トークンを Microsoft 365 に送信します。フェデレーション ID を使用すると、Microsoft 365 サブスクリプションの認証のオフロードとスケールアップや、認証とセキュリティの高度なシナリオが可能になります。
  
この記事では、Microsoft 365 テスト環境のフェデレーション認証を構成する方法について説明します。その結果、次のようになります。

![Microsoft 365 テスト環境のフェデレーション認証](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase3.png)
  
この構成は、次の内容で構成されます:
  
- Microsoft 365 E5 試用版または運用版サブスクリプション。
    
- インターネットに接続された単純な組織イントラネット。 Azure 仮想ネットワークのサブネット上にある5つの仮想マシン (DC1、ADFS1、CLIENT1、、および PROXY1) で構成されます。 Azure AD Connect は、Office Outlook で実行して、Active Directory ドメインサービスドメイン内のアカウントの一覧を Microsoft 365 に同期します。 PROXY1 は、受信認証要求を受信します。 ADFS1 は、DC1 および問題のセキュリティトークンを使用して資格情報を検証します。
    
このテスト環境の設定には、次の5つのフェーズが含まれます。
- [フェーズ 1: Microsoft 365 テスト環境のパスワード ハッシュ同期を構成する](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [フェーズ 2: AD FS サーバーを作成する](#phase-2-create-the-ad-fs-server)
- [フェーズ 3：Web プロキシ サーバーを作成する](#phase-3-create-the-web-proxy-server)
- [フェーズ 4:自己署名証明書を作成し、ADFS1 と PROXY1 を構成する](#phase-4-create-a-self-signed-certificate-and-configure-adfs1-and-proxy1)
- [フェーズ 5: フェデレーション ID に対応するよう Microsoft 365 を構成する](#phase-5-configure-microsoft-365-for-federated-identity)
    
> [!NOTE]
> このテスト環境は、Azure の試用版サブスクリプションを使用して構成することはできません。
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>フェーズ 1: Microsoft 365 テスト環境のパスワード ハッシュ同期を構成する

「 [Microsoft 365 のパスワードハッシュ同期](password-hash-sync-m365-ent-test-environment.md)」の手順に従います。 結果の構成は次のようになります。
  
![パスワード ハッシュ同期を実装するシミュレーション エンタープライズ テスト環境](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase1.png)
  
この構成は、次の内容で成立します。
  
- Microsoft 365 E5 試用版または有料版サブスクリプション。
- インターネットに接続された、シンプルな組織のイントラネット。 Azure 仮想ネットワークのサブネット上にある DC1、CLIENT1、および CLIENT1 の仮想マシンで構成されます。 Azure AD Connect は、Office Outlook で実行して、TESTLAB Active Directory ドメインサービス (AD DS) ドメインと Microsoft 365 サブスクリプションの Azure AD テナントを定期的に同期します。

## <a name="phase-2-create-the-ad-fs-server"></a>フェーズ 2: AD FS サーバーを作成する

AD FS サーバーは、Microsoft 365 と、DC1 でホストされている corp.contoso.com ドメイン内のアカウントとの間でのフェデレーション認証を提供します。
  
ADFS1 用の Azure 仮想マシンを作成するには、基本構成のサブスクリプション名、リソース グループ名、Azure の場所を入力して、次のコマンドをローカル コンピューターの Azure PowerShell コマンド プロンプトで実行します。
  
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

次に、[Azure portal](https://portal.azure.com) で、ADFS1 のローカル管理者アカウント名とパスワードを使用して ADFS1 仮想マシンに接続し、Windows PowerShell コマンド プロンプトを開きます。
  
ADFS1 と DC1 の間の名前の解決とネットワーク通信を確認するには、**ping dc1.corp.contoso.com** コマンドを実行し、4 つの応答があることを確認します。
  
次に、ADFS1 の Windows PowerShell プロンプトで次のコマンドを使用して、ADFS1 仮想マシンを CORP ドメインに参加させます。
  
```powershell
$cred=Get-Credential -UserName "CORP\User1" -Message "Type the User1 account password."
Add-Computer -DomainName corp.contoso.com -Credential $cred
Restart-Computer
```

結果の構成は次のようになります。
  
![Microsoft 365 テスト環境の DirSync に追加された AD FS サーバー](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase2.png)
  
## <a name="phase-3-create-the-web-proxy-server"></a>フェーズ 3：Web プロキシ サーバーを作成する

PROXY1 は、認証しようとするユーザーと ADFS1 との間の認証メッセージのプロキシを提供します。
  
PROXY1 用の Azure 仮想マシンを作成するには、リソース グループ名と Azure の場所を入力し、次のコマンドをローカル コンピューターの Azure PowerShell コマンド プロンプトで実行します。
  
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
> PROXY1 には静的パブリック IP アドレスが割り当てられます。この IP アドレスを指すパブリック DNS レコードが作成され、PROXY1 仮想マシンを再起動するときにこの IP アドレスを変更することはできないためです。
  
次に、社内のサブネットのネットワークセキュリティグループにルールを追加して、インターネットから PROXY1's のプライベート IP アドレスおよび TCP ポート443への未承諾の受信トラフィックを許可します。 ローカル コンピューターの Azure PowerShell コマンド プロンプトで、次のコマンドを実行します。
  
```powershell
$rgName="<the resource group name of your Base Configuration>"
Get-AzNetworkSecurityGroup -Name CorpNet -ResourceGroupName $rgName | Add-AzNetworkSecurityRuleConfig -Name "HTTPS-to-PROXY1" -Description "Allow TCP 443 to PROXY1" -Access "Allow" -Protocol "Tcp" -Direction "Inbound" -Priority 101 -SourceAddressPrefix "Internet" -SourcePortRange "*" -DestinationAddressPrefix "10.0.0.101" -DestinationPortRange "443" | Set-AzNetworkSecurityGroup
```

次に、[Azure portal](https://portal.azure.com) で、PROXY1 のローカル管理者アカウント名とパスワードを使用して PROXY1 仮想マシンに接続し、PROXY1 で Windows PowerShell コマンド プロンプトを開きます。
  
PROXY1 と DC1 の間の名前の解決とネットワーク通信を確認するには、**ping dc1.corp.contoso.com** コマンドを実行し、4 つの応答があることを確認します。
  
次に、PROXY1 の Windows PowerShell プロンプトで次のコマンドを使用して、PROXY1 仮想マシンを CORP ドメインに参加させます。
  
```powershell
$cred=Get-Credential -UserName "CORP\User1" -Message "Type the User1 account password."
Add-Computer -DomainName corp.contoso.com -Credential $cred
Restart-Computer
```

ローカルコンピューターにこれらの Azure PowerShell コマンドを使用して、PROXY1 のパブリック IP アドレスを表示します。
  
```powershell
Write-Host (Get-AzPublicIpaddress -Name "PROXY1-PIP" -ResourceGroup $rgName).IPAddress
```

次に、パブリック DNS プロバイダーを操作して、**Write-Host** コマンドで表示される IP アドレスに解決される、**fs.testlab.**\<*your DNS domain name*> 用の新しいパブリック DNS A レコードを作成します。これ以降、**fs.testlab.**\<*your DNS domain name*> を*フェデレーション サービス FQDN* と呼びます。
  
次に、[Azure portal](https://portal.azure.com) で、CORP\\User1 の資格情報を使用して DC1 仮想マシンに接続し、管理者レベルの Windows PowerShell コマンド プロンプトで次のコマンドを実行します。
  
```powershell
Add-DnsServerPrimaryZone -Name corp.contoso.com -ZoneFile corp.contoso.com.dns
Add-DnsServerResourceRecordA -Name "fs" -ZoneName corp.contoso.com -AllowUpdateAny -IPv4Address "10.0.0.100" -TimeToLive 01:00:00
```
これらのコマンドは、内部 DNS A レコードを作成し、Azure 仮想ネットワーク上の仮想マシンが内部フェデレーションサービス FQDN を ADFS1's プライベート IP アドレスに解決できるようにします。
  
結果の構成は次のようになります。
  
![Microsoft 365 テスト環境の DirSync に追加された Web アプリケーション プロキシ サーバー](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase3.png)
  
## <a name="phase-4-create-a-self-signed-certificate-and-configure-adfs1-and-proxy1"></a>フェーズ 4:自己署名証明書を作成し、ADFS1 と PROXY1 を構成する

このフェーズでは、フェデレーション サービス FQDN 用の自己署名入りデジタル証明書を作成し、ADFS1 と PROXY1 を AD FS ファームとして構成します。
  
まず、[Azure portal](https://portal.azure.com) で、CORP\\User1 の資格情報を使用して DC1 仮想マシンに接続し、管理者レベルの Windows PowerShell コマンド プロンプトを開きます。 
  
次に、DC1 の Windows PowerShell コマンドプロンプトで、次のコマンドを使用して AD FS サービスアカウントを作成します。
  
```powershell
New-ADUser -SamAccountName ADFS-Service -AccountPassword (read-host "Set user password" -assecurestring) -name "ADFS-Service" -enabled $true -PasswordNeverExpires $true -ChangePasswordAtLogon $false
```
このコマンドでは、アカウントのパスワードを入力するよう求められることにご注意ください。 強力なパスワードを選択して、安全な場所に記録してください。 このフェーズとフェーズ5で必要になります。
  
[Azure portal](https://portal.azure.com) で CORP\\User1 の資格情報を使用して、ADFS1 仮想マシンに接続します。ADFS1 で管理者レベルの Windows PowerShell コマンド プロンプトを開き、フェデレーション サービス FQDN を入力し、次のコマンドを実行して自己署名証明書を作成します。
  
```powershell
$fedServiceFQDN="<federation service FQDN>"
New-SelfSignedCertificate -DnsName $fedServiceFQDN -CertStoreLocation "cert:\LocalMachine\My"
New-Item -path c:\Certs -type directory
New-SmbShare -name Certs -path c:\Certs -changeaccess CORP\User1
```

その次に、次の手順を使用して新しい自己署名証明書をファイルとして保存します。
  
1. [ **スタート**] ボタンをクリックし **mmc.exe**を入力し、 **enter キーを**押します。
    
2. [**ファイル**  >  の**追加と削除] スナップ**インを選択します。
    
3. [ **スナップインの追加と削除**] で、使用可能なスナップインの一覧の [ **証明書** ] をダブルクリックし、[ **コンピューターアカウント**] を選択して、[ **次へ**] を選択します。
    
4. [ **コンピューターの選択**] で、[ **完了**] を選択し、[ **OK]** を選択します。
    
5. ツリー ウィンドウで、**[証明書 (ローカル コンピューター)] > [個人] > [証明書]** の順に開きます。
    
6. フェデレーションサービス FQDN を使用して証明書を選択して保持 (または右クリック) し、[ **すべてのタスク**] を選択して、[ **エクスポート**] を選択します。
    
7. [ **ようこそ** ] ページで、[ **次へ**] を選択します。
    
8. [ **秘密キーのエクスポート** ] ページで、[ **はい**] を選択し、[ **次へ**] を選択します。
    
9. [ **エクスポートファイルの形式** ] ページで、[ **すべての拡張プロパティをエクスポート**する] を選択し、[ **次へ**] を選択します。
    
10. [ **セキュリティ** ] ページで、[ **パスワード** ] を選択し、パスワードを **入力して** パスワードを **確認します。**
    
11. [ **エクスポートするファイル** ] ページで、[ **参照**] を選択します。
    
12. **C: \\ cert**フォルダーに移動し、[**ファイル名**] に「 **SSL** 」と入力してから、[保存] を選択し**ます。**
    
13. [ **エクスポートするファイル** ] ページで、[ **次へ**] を選択します。
    
14. [ **証明書のエクスポートウィザードの完了** ] ページで、[ **完了**] を選択します。 メッセージが表示されたら、[ **OK]** を選択します。
    
次に、ADFS1 の Windows PowerShell コマンド プロンプトで次のコマンドを使用して、AD FS サービスをインストールします。
  
```powershell
Install-WindowsFeature ADFS-Federation -IncludeManagementTools
```

インストールが完了するまで待ちます。
  
次いで、次の手順で AD FS サービスを構成します。
  
1. [ **スタート**] をクリックし、[ **サーバーマネージャー** ] アイコンを選択します。
    
2. サーバーマネージャーのツリーウィンドウで、[ **AD FS**] を選択します。
    
3. 上部のツールバーで、オレンジ色の警告記号を選択し、[ **このサーバー上でフェデレーションサービスを構成する**] を選択します。
    
4. Active Directory フェデレーションサービス構成ウィザードの [ **ようこそ** ] ページで、[ **次へ**] を選択します。
    
5. [ **AD DS に接続** ] ページで、[ **次へ**] を選択します。
    
6. **[サービスのプロパティの指定]** ページで、次の操作を実行します。
    
  - [ **SSL 証明書**] で、下矢印を選択し、フェデレーションサービス FQDN の名前を持つ証明書を選択します。
    
  - [ **フェデレーションサービスの表示名**] に架空の組織の名前を入力します。
    
  - [**次へ**] を選択します。
    
7. [**サービスアカウントの指定**] ページで、[**アカウント名** **] の [選択**] を選択します。
    
8. **[ユーザーまたはサービスアカウントの選択**] で、「 **ADFS-サービス**」と入力し、[**名前の確認**] を選択して、[ **OK]** を選択します。
    
9. [ **アカウントパスワード**] に ADFS-Service アカウントのパスワードを入力し、[ **次へ**] を選択します。
    
10. [ **構成データベースの指定** ] ページで、[ **次へ**] を選択します。
    
11. [ **オプションの確認** ] ページで、[ **次へ**] を選択します。
    
12. [ **前提条件の確認** ] ページで、[ **構成**] を選択します。

13. [ **結果** ] ページで、[ **閉じる**] を選択します。
    
14. [ **スタート**] ボタンをクリックし、[電源] アイコンを選択し、[ **再起動**] を選択して、[ **続行**] を選択します。
    
[Azure portal](https://portal.azure.com) から、CORP\\User1 アカウントの資格情報を使用して PROXY1 に接続します。
  
その次に、次の手順を使用して、**PROXY1 と APP1 の両方**に自己署名証明書をインストールします。
  
1. [ **スタート**] ボタンをクリックし **mmc.exe**を入力し、 **enter キーを**押します。
    
2. [ **ファイル > スナップインの追加と削除**] を選択します。
    
3. [ **スナップインの追加と削除**] で、使用可能なスナップインの一覧の [ **証明書** ] をダブルクリックし、[ **コンピューターアカウント**] を選択して、[ **次へ**] を選択します。
    
4. [ **コンピューターの選択**] で、[ **完了**] を選択し、[ **OK]** を選択します。
    
5. ツリーウィンドウで、[**証明書 (ローカルコンピューター)**  >  **個人**  >  **証明書**] を開きます。
    
6. [ **個人**] を選択して、ホールド (または右クリック) し、[ **すべてのタスク**] を選択して、[ **インポート**] を選択します。
    
7. [ **ようこそ** ] ページで、[ **次へ**] を選択します。
    
8. [**インポートするファイル**] ページで、「 ** \\ \\ adfs1 \\ cert \\ ssl .pfx**」と入力し、[**次へ**] を選択します。
    
9. [ **秘密キーの保護** ] ページで、[ **パスワード**] に証明書のパスワードを入力し、[次へ] を選択し **ます。**
    
10. [ **証明書ストア** ] ページで、[次へ] を選択し **ます。**
    
11. [ **完了** ] ページで、[ **完了**] を選択します。
    
12. [ **証明書ストア** ] ページで、[ **次へ**] を選択します。
    
13. メッセージが表示されたら、[ **OK]** を選択します。
    
14. ツリーウィンドウで、[ **証明書**] を選択します。
    
15. 証明書を選択して保持する (または右クリック) して、[ **コピー**] を選択します。
    
16. ツリーウィンドウで、[**信頼されたルート証明機関**の  >  **証明書**] を開きます。
    
17. インストールされている証明書の一覧の下にマウスポインターを移動し、選択してホールド (または右クリック) し、[ **貼り付け**] を選択します。
    
管理者レベルの PowerShell コマンド プロンプトを開き、次のコマンドを実行します。
  
```powershell
Install-WindowsFeature Web-Application-Proxy -IncludeManagementTools
```

インストールが完了するまで待ちます。
  
次の手順を使用して、Web アプリケーション プロキシ サービスを構成し、そのフェデレーション サーバーとして ADFS1 を使用します。
  
1. [ **スタート**] を選択し、[ **サーバーマネージャー**] を選択します。
    
2. ツリーウィンドウで、[ **リモートアクセス**] を選択します。
    
3. 上部のツールバーで、オレンジ色の警告記号を選択し、[ **Web アプリケーションプロキシウィザードを開く**] を選択します。
    
4. Web アプリケーションプロキシ構成ウィザードの [ **ようこそ** ] ページで、[ **次へ**] を選択します。
    
5. **[フェデレーション サーバー]** ページで、次の操作を実行します。
    
  - [ **フェデレーションサービス名** ] ボックスに、フェデレーションサービスの FQDN を入力します。
    
  - [ **ユーザー名** ] ボックスに「 **CORP \\ User1**」と入力します。
    
  - [ **パスワード** ] ボックスに、User1 アカウントのパスワードを入力します。
    
  - [**次へ**] を選択します。
    
6. [ **AD FS プロキシ証明書** ] ページで、下矢印を選択し、フェデレーションサービス FQDN を含む証明書を選択して、[ **次へ**] を選択します。
    
7. [ **確認** ] ページで、[ **構成**] を選択します。
    
8. [ **結果** ] ページで、[ **閉じる**] を選択します。
    
## <a name="phase-5-configure-microsoft-365-for-federated-identity"></a>フェーズ 5: フェデレーション ID に対応するよう Microsoft 365 を構成する

[Azure portal](https://portal.azure.com) を使用して、CORP\\User1 アカウントの資格情報で APP1 仮想マシンに接続します。
  
次の手順を使用して、フェデレーション認証に対応するように Azure AD Connect と Microsoft 365 サブスクリプションを構成します。
  
1. デスクトップで、**[Azure AD Connect]** をダブルクリックします。
    
2. [ **AZURE AD Connect へようこそ** ] ページで、[ **構成**] を選択します。
    
3. [ **追加のタスク** ] ページで、[ユーザーの **サインインを変更**する] を選択し、[ **次へ**] を選択します。
    
4. [ **AZURE AD に接続** ] ページで、全体管理者のアカウント名とパスワードを入力し、[ **次へ**] を選択します。
    
5. [ **ユーザーサインイン** ] ページで、[ **AD FS とのフェデレーション**] を選択し、[ **次へ**] を選択します。
    
6. [ **AD fs ファーム**] ページで、 **[既存の ad Fs ファームを使用する**] を選択し、[**サーバー名**] ボックスに「 **ADFS1** 」と入力して、[**次へ**] を選択します。
    
7. サーバーの資格情報の入力を求められたら、CORP User1 アカウントの資格情報を入力して、[ \\ **OK]** を選択します。
    
8. [**ドメイン管理者**の資格情報] ページで、[**ユーザー名**] ボックスに「 **CORP \\ User1** 」と入力し、[**パスワード**] ボックスにアカウントのパスワードを入力して、[**次へ**] を選択します。
    
9. [ **AD FS サービスアカウント**] ページで、[**ドメインユーザー名**] ボックスに「 **CORP \\ ADFS-サービス**」と入力し、[ **domain User password** ] ボックスにアカウントのパスワードを入力して、[**次へ**] を選択します。
    
10. [ **AZURE AD ドメイン** ] ページの [ **ドメイン**] で、[フェーズ 1] で事前に作成してサブスクリプションに追加したドメインの名前を選択し、[ **次へ**] を選択します。
    
11. [ **構成の準備完了** ] ページで、[ **構成**] を選択します。
    
12. [ **インストールの完了** ] ページで、[ **確認**] を選択します。
    
    イントラネットとインターネットの両方の構成が確認されたことを示すメッセージが表示されます。
    
13. [ **インストールの完了** ] ページで、[ **終了**] を選択します。
    
フェデレーション認証が機能していることを実証するには、次の操作を実行します。
  
1. ローカル コンピューター上でブラウザーの新しいプライベート インスタンスを開き、[https://admin.microsoft.com](https://admin.microsoft.com) にアクセスします。
    
2. サインイン資格情報については、 **user1@** 入力して \<*the domain created in Phase 1*> ください。
    
    たとえば、テストドメインが **testlab.contoso.com**の場合は、「user1@testlab.contoso.com」と入力します。 **Tab**キーを押すか、Microsoft 365 に自動的にリダイレクトすることを許可します。
    
    **[この接続ではプライバシーが保護されません]** ページが表示されます。 これが表示されるのは、デスクトップコンピューターが検証できない自己署名証明書を ADFS1 にインストールしたためです。 フェデレーション認証の運用環境デプロイメントでは、信頼された証明機関からの証明書を使用するため、ユーザーにこのページは表示されません。
    
3. [**接続はプライベートではありません**] ページで、[**詳細設定**] を選択し、[**続行 \<*your federation service FQDN*> **] を選択します。 
    
4. 架空の組織名のページで、次を使用してサインインします。
    
  - 名前: **CORP\\User1**
    
  - User1 アカウントのパスワード
    
    **[Microsoft Office Home]** ページが表示されます。
    
次の手順で、試用版サブスクリプションが、DC1 上でホストされている AD DS corp.contoso.com ドメインとフェデレーションされていることを実証します。認証プロセスに関する基本事項を以下に示します。
  
1. フェーズ 1 で作成したフェデレーション ドメインをサインイン アカウント名で使用すると、Microsoft 365 はブラウザーをフェデレーション サービス FQDN と PROXY1 にリダイレクトします。
    
2. PROXY1 は、ローカル コンピューターに架空の会社のサインイン ページを送信します。
    
3. CORP\\User1 とパスワードを PROXY1 に送信すると、それらは ADFS1 に転送されます。
    
4. ADFS1 は、DC1 を使用して CORP\\User1 とパスワードを検証し、ローカル コンピューターにセキュリティ トークンを送信します。
    
5. ローカル コンピューターは、セキュリティ トークンを Microsoft 365 に送信します。
    
6. Microsoft 365 は、セキュリティ トークンが ADFS1 によって作成されたことを検証して、アクセスを許可します。
    
これで、試用版のサブスクリプションがフェデレーション認証を行うように構成されました。この開発/テスト環境は、高度な認証シナリオで使用できます。
  
## <a name="next-step"></a>次の手順

Azure での Microsoft 365 について、運用に対応した高可用性フェデレーション認証を展開する準備ができたら、「 [microsoft 365 の高可用性フェデレーション認証を azure に展開](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)する」を参照してください。
  
