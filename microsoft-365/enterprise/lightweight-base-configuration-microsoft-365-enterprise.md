---
title: 軽量な基本構成
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2019
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
description: このテスト ラボ ガイドを使用して、Microsoft 365 for enterprise をテストする軽量なテスト環境を作成します。
ms.openlocfilehash: 2de0760cef7339f62229575b1e0a54b3c67a4e9f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909708"
---
# <a name="the-lightweight-base-configuration"></a>軽量な基本構成

*このテスト ラボ ガイドは、Microsoft 365 for enterprise と 365 Enterprise テストOffice両方に使用できます。*

この記事では、Microsoft 365 E5 サブスクリプションと Windows 10 Enterprise を実行しているコンピューターを使用して簡略化された環境を作成する方法について説明します。

![軽量な Microsoft 365 Enterprise テスト環境](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

軽量なテスト環境を作成するには、次の 5 つのフェーズが必要です。
- [フェーズ 1: Microsoft 365 E5 サブスクリプションを作成する](#phase-1-create-your-microsoft-365-e5-subscription)
- [フェーズ 2: Office 365 試用版サブスクリプションを構成する](#phase-2-configure-your-office-365-trial-subscription)
- [フェーズ 3: Microsoft 365 E5 の試用版サブスクリプションを追加する](#phase-3-add-a-microsoft-365-e5-trial-subscription)
- [フェーズ 4: Windows 10 Enterprise コンピューターを作成する](#phase-4-create-a-windows-10-enterprise-computer)
- [フェーズ 5: Windows 10 のコンピューターを Azure AD に参加させる](#phase-5-join-your-windows-10-computer-to-azure-ad)

結果の環境を使用して [、Microsoft 365 for](https://www.microsoft.com/microsoft-365/enterprise)enterprise の機能をテストします。

![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> Microsoft 365 for enterprise Test Lab Guide スタックのすべての記事への視覚的なマップについては [、「Microsoft 365 for enterprise Test Lab Guide Stack」を参照してください](../downloads/Microsoft365EnterpriseTLGStack.pdf)。

>[!NOTE]
>この記事を印刷しておき、30 日間の Office 365 試用版サブスクリプションの終了後にこの環境で必要になる特定の情報を記録しておくことをお勧めします。 試用版サブスクリプションは、追加で 30 日間まで簡単に延長できます。 永続的なテスト環境の場合は、別個の Azure AD テナントと少数のライセンスを使用して、新しい有料サブスクリプションを作成します。

## <a name="phase-1-create-your-microsoft-365-e5-subscription"></a>フェーズ 1: Microsoft 365 E5 サブスクリプションを作成する

Microsoft 365 E5 試用版サブスクリプションから始め、Microsoft 365 E5 サブスクリプションを追加します。

>[!NOTE]
>テスト環境が現在持っている有料サブスクリプションとは別の Azure AD テナントを持つOffice 365 の試用版サブスクリプションを作成することをお勧めします。 この分離により、テスト テナント内のユーザーとグループを追加および削除して、実稼働サブスクリプションに影響を与えることなく行えるという意味です。

Microsoft 365 E5 試用版サブスクリプションを開始するには、最初に、架空の会社名と新しい Microsoft アカウントが必要になります。
  
1. この会社名には、会社名 Contoso のバリエーションを使用するようお勧めします (必須ではありません)。Contoso は、Microsoft のサンプル コンテンツで使用される架空の会社名です。ここに架空の会社名を記録してください: ![線](../media/Common-Images/TableLine.png)
    
2. 新しい Microsoft アカウントにサインアップするには、[https://outlook.com](https://outlook.com) に移動して、新しい電子メール アカウントとアドレスでアカウントを作成します。このアカウントを使用して、Office 365 にサインアップします。
    
    - ここに新しいアカウントの姓名を記録してください: ![線](../media/Common-Images/TableLine.png)
    
    - 新しいメール アカウント アドレスをここに記録します。 ![線](../media/Common-Images/TableLine.png)@outlook.com
    
### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a>Office 365 E5 試用版サブスクリプションにサインアップする

1. ブラウザーで、 に移動します [https://aka.ms/e5trial](https://aka.ms/e5trial) 。
    
2. **[365 E5 365 E5]** ページOfficeの手順 1 で、新しいメール アカウント のアドレスを入力します。
3. 証跡サブスクリプション プロセスの手順 2 で、要求された情報を入力し、検証を実行します。
4. 手順 3 で、組織名を入力し、サブスクリプションのグローバル管理者になるアカウント名を入力します。
5. 手順 4 では、ここにサインイン ページを記録します (選択してコピー): ![線](../media/Common-Images/TableLine.png)
6. ここにユーザー ID を記録します: ![Line](../media/Common-Images/TableLine.png).onmicrosoft.com  
   安全な場所に入力したパスワードを記録します。
   この値を **全体管理者名** と呼ぶことにします。
7. [セットアップ **に移動] を選択します**。
8. [Office 365 E5 セットアップ] で、[組織 **の .onmicrosoft.com** を使用してメールとサインインを続行する] を選択し、[終了して後で続行する] を選択 **します**。

Microsoft 365 管理センターが表示されます。
    
## <a name="phase-2-configure-your-office-365-trial-subscription"></a>フェーズ 2: Office 365 試用版サブスクリプションを構成する

このフェーズでは、サブスクリプションを構成してユーザーを追加し、Office 365 E5 ライセンスを割り当てます。
  
コンピューターから Azure Active Directory PowerShell for Graph モジュールを使用してサブスクリプションに接続するには、「PowerShell を使用して [Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)に接続する」の手順を使用します。
    
[資格情報 **Windows PowerShell] ダイアログ** ボックスで、グローバル管理者名 (たとえば、jdoe@contosotoycompany.onmicrosoft.com) *と* パスワードを入力します。
  
組織名 *(contosotoycompany* など)、場所の 2 文字の国コード、共通のアカウント パスワードを入力し、PowerShell プロンプトから次のコマンドを実行します。

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
> ここで共通のパスワードを使用するのは、自動化およびテスト環境の構成を容易にするためです。 運用環境のサブスクリプションは避けるように強くお勧めします。 

### <a name="record-key-information-for-future-reference"></a>将来の参照のために重要な情報を記録する

これらの値をまだ記録していない場合は、次の値を記録します。
  
- グローバル管理者名: ![線](../media/Common-Images/TableLine.png).onmicrosoft.com (フェーズ 1 のステップ 6 から)
    
    このアカウントのパスワードも安全な場所に記録してください。
    
- 試用版サブスクリプションの組織名: ![線](../media/Common-Images/TableLine.png) (フェーズ 1 のステップ 4 から)
    
- User 2、User 3、User 4、および User 5 のアカウントを一覧表示するには、次に示すコマンドを Windows PowerShell 用 Microsoft Azure Active Directory モジュールのプロンプトから実行します。
    
  ```powershell
  Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName
  ```

    ここにアカウント名を記録してください:
    
  - ユーザー 2 アカウント名: user2@![線](../media/Common-Images/TableLine.png).onmicrosoft.com
    
  - ユーザー 3 アカウント名: user3@![線](../media/Common-Images/TableLine.png).onmicrosoft.com
    
  - ユーザー 4 アカウント名: user4@![線](../media/Common-Images/TableLine.png).onmicrosoft.com
    
  - ユーザー 5 アカウント名: user5@![線](../media/Common-Images/TableLine.png).onmicrosoft.com
    
    これらのアカウントの共通パスワードも安全な場所に記録してください。
   
### <a name="using-an-office-365-test-environment"></a>Office 365 テスト環境を使用する

365 テスト環境Office必要な場合は、この記事の残りの部分を読む必要があります。

Office 365 と Microsoft 365 の両方に適用される追加のテスト ラボ ガイドについては [、「Microsoft 365 for enterprise Test Lab Guides」を参照してください](m365-enterprise-test-lab-guides.md)。
  
## <a name="phase-3-add-a-microsoft-365-e5-trial-subscription"></a>フェーズ 3: Microsoft 365 E5 の試用版サブスクリプションを追加する

このフェーズでは、Microsoft 365 E5 試用版サブスクリプションにサインアップして、Office 365 E5 試用版サブスクリプションと同じ組織に追加します。
  
まず、Microsoft 365 E5 試用版サブスクリプションを追加して、新しい Microsoft 365 ライセンスを全体管理者アカウントに割り当てます。
  
1. インターネット ブラウザーのプライベート ウィンドウで、グローバル管理者アカウントの資格情報を使用して、 で Microsoft 365 管理センターにサインインします [https://admin.microsoft.com](https://admin.microsoft.com) 。
    
2. **[Microsoft 365 管理** センター] ページの左側のナビゲーションで、[課金と購入サービス>**選択します**。
    
3. [サービスの **購入] ページで****、[Microsoft 365 E5]** を選択し、[無料試用版の取得 **] を選択します**。

4. **[Microsoft 365 E5 試用版**] ページで、テキスト メッセージまたは電話を受け取り、電話番号を入力し、[テキスト] または [電話] を選択 **します。** 検証を実行します。

5. [注文の **確認] ページで** 、[今すぐ試す] **を選択します**。

6. [注文受領 **書] ページで** 、[続行] を **選択します**。

7. Microsoft 365 管理センターで、[アクティブ ユーザー] を **選択>選択します**。

8. [ **アクティブ なユーザー]** で、管理者アカウントを選択します。

9. [ライセンス **とアプリ] を選択します**。

10. Office 365 Enterprise E5 のライセンスを無効にして、Microsoft 365 E5 のライセンスを有効にします。

11. [変更 **の保存]** を選択し、ユーザー アカウント情報ウィンドウを閉じます。

次に、その他のすべてのアカウント (User 2、User 3、User 4、および User 5) に前述の手順 8 から 11 を繰り返します。
  
> [!NOTE]
> Microsoft 365 E5 試用版サブスクリプションの長さは 30 日間です。 永続的なテスト環境の場合は、少数のライセンスを使用して、この試用版のサブスクリプションを有料サブスクリプションに変換します。
  
テスト環境は、次のようになっています。
  
- Microsoft 365 E5 の試用版サブスクリプション。
- すべての適切なユーザー アカウント (全体管理者のみまたは 5 つすべてのユーザー アカウントのどちらか) が、Microsoft 365 E5 を使用できるようになっている。
    
Microsoft 365 E5 を追加する結果の構成は、次のように表示されます。
  
![Microsoft 365 Enterprise テスト環境のフェーズ 3](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase2.png)
  
## <a name="phase-4-create-a-windows-10-enterprise-computer"></a>フェーズ 4: Windows 10 Enterprise コンピューターを作成する

このフェーズでは、物理コンピューター、仮想マシン、Azure 仮想マシンのいずれかとして Windows 10 Enterprise を実行するスタンドアロン コンピューターを作成します。
  
### <a name="physical-computer"></a>物理コンピューター

個人用コンピューターで、Windows 10 Enterprise をインストールします。 Windows 10 Enterprise 試用版は、こちらからダウンロード [できます](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise)。
  
### <a name="virtual-machine"></a>仮想マシン

選択したハイパーバイザーを使用して仮想マシンを作成し、Windows 10 Enterprise をインストールします。 Windows 10 Enterprise 試用版は、こちらからダウンロード [できます](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise)。
  
### <a name="virtual-machine-in-azure"></a>Azure での仮想マシン

Microsoft Azure で Windows 10 の仮想マシンを作成するには、***Visual Studio ベースのサブスクリプションが必要*** です。このサブスクリプションにより、Windows 10 Enterprise のイメージにアクセスできます。試用版や有料のサブスクリプションなど、その他の種類の Azure サブスクリプションでは、このイメージにアクセスできません。最新情報については、「[Azure で Windows クライアントを開発/テスト シナリオに使用する](/azure/virtual-machines/windows/client-images)」を参照してください。
  
> [!NOTE]
> 次のコマンド セットは、Azure PowerShell の最新版を使用します。 「[Azure PowerShell の概要](/powershell/azureps-cmdlets-docs/)」を参照してください。 これらのコマンドは、WIN10 という名前の Windows 10 Enterprise 仮想マシンと、リソース グループ、ストレージ アカウント、仮想ネットワークなど、必要なすべてのインフラストラクチャを構築します。 Azure インフラストラクチャ サービスについて既に理解している場合は、これらの手順を現在展開されているインフラストラクチャに合わせて調整します。
  
最初に、Microsoft PowerShell プロンプトを起動します。
  
このコマンドを使用して Azure アカウントにサインインします。
  
```powershell
Connect-AzAccount
```

このコマンドを使用してサブスクリプション名を取得します。
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

Azure サブスクリプションを設定します。 文字を含む引用符内のすべてを正しい \< and > 名前に置き換える。
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

次に、新しいリソース グループを作成します。 一意のリソース グループ名を決定するには、このコマンドを使用して既存のリソース グループを一覧表示します。
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

これらのコマンドを使用して、新しいリソース グループを作成します。 文字を含む引用符内のすべてを正しい \< and > 名前に置き換える。
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

次に、これらのコマンドを使用して、新しい仮想ネットワークと WIN10 仮想マシンを作成します。 ダイアログ ボックスが表示されたら、WIN10 の名前とローカル管理者アカウントのパスワードを指定し、これらを安全な場所に保存します。
  
```powershell
$corpnetSubnet=New-AzVirtualNetworkSubnetConfig -Name Corpnet -AddressPrefix 10.0.0.0/24
New-AzVirtualNetwork -Name "M365Ent-TestLab" -ResourceGroupName $rgName -Location $locName -AddressPrefix 10.0.0.0/8 -Subnet $corpnetSubnet
$rule1=New-AzNetworkSecurityRuleConfig -Name "RDPTraffic" -Description "Allow RDP to all VMs on the subnet" -Access Allow -Protocol Tcp -Direction Inbound -Priority 100 -SourceAddressPrefix Internet -SourcePortRange * -DestinationAddressPrefix * -DestinationPortRange 3389
New-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName -Location $locName -SecurityRules $rule1
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name "M365Ent-TestLab"
$nsg=Get-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name Corpnet -AddressPrefix "10.0.0.0/24" -NetworkSecurityGroup $nsg
$vnet | Set-AzVirtualNetwork
$pip=New-AzPublicIpAddress -Name WIN10-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name WIN10-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id
$vm=New-AzVMConfig -VMName WIN10 -VMSize Standard_A2_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for WIN10."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName WIN10 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsDesktop -Offer Windows-10 -Skus RS3-Pro -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name WIN10-TestLab-OSDisk -DiskSizeInGB 128 -CreateOption FromImage
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

## <a name="phase-5-join-your-windows-10-computer-to-azure-ad"></a>フェーズ 5: Windows 10 のコンピューターを Azure AD に参加させる

Windows 10 Enterprise の物理マシンまたは仮想マシンの作成後、ローカル管理者アカウントでサインインします。
  
> [!NOTE]
> Azure の仮想マシンの場合は、次の  [手順を使用して](/azure/virtual-machines/windows/connect-logon) 接続します。
  
次に、WIN10 コンピューターを Microsoft 365 E5 サブスクリプションの Azure AD テナントに参加させます。
  
1. WIN10 コンピューターのデスクトップで、[スタート] > **[>** アカウント>アクセス] を>します。
    
2. [仕事 **用アカウントまたは学校アカウントの設定]** ダイアログ ボックスで、[このデバイスを Azure Active Directory に **参加する] を選択します**。
    
3. [ **仕事または学校のアカウント]** で、Microsoft 365 E5 サブスクリプションのグローバル管理者アカウント名を入力し、[次へ] を **選択します**。
    
4. [ **パスワードの入力]** で、グローバル管理者アカウントのパスワードを入力し、[サインイン] **を選択します**。
    
5. これが組織である必要がある場合は、[参加] を選択し、[完了] を選択 **します**。
    
6. [設定] ウィンドウを閉じます。
    
次に、WIN10 コンピューターに Microsoft 365 Apps for enterprise をインストールします。
  
1. Microsoft Edge ブラウザーを開き、グローバル管理者アカウント資格情報を使用して [Microsoft 365](https://admin.microsoft.com) 管理センターにサインインします。
    
2. [ホーム]**タブMicrosoft Office、[** インストール]**を選択Office。**
    
3. 操作を求めるメッセージが表示されたら、[**実行**] を選択し、[ユーザー アカウント制御]**で [は****い] を選択します**。
    
4. Office のインストールが完了するまで待ちます。 [すべて設定 **されている] が表示された場合は、[** 閉じる] **を 2 回** 選択します。
    
結果の環境は次のように表示されます。

![Microsoft 365 Enterprise テスト環境のフェーズ 5](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

これには、以下を備えた WIN10 コンピューターが含まれます。

- Microsoft 365 E5 サブスクリプションの Azure AD テナントに参加している。
- Microsoft Intune (EMS) で Azure AD デバイスとして登録されている。
- Microsoft 365 Apps for enterprise がインストールされています。
  
これで、エンタープライズ向け [Microsoft 365 の追加機能を試す準備ができました](https://www.microsoft.com/microsoft-365/enterprise)。
  
## <a name="next-steps"></a>次の手順

こうした追加のテスト ラボ ガイドについて説明します。
  
- [ID](m365-enterprise-test-lab-guides.md#identity)
- [モバイル デバイス管理](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [情報保護](m365-enterprise-test-lab-guides.md#information-protection)
   

## <a name="see-also"></a>関連項目

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)

[Microsoft 365 for enterprise の概要](microsoft-365-overview.md)

[Microsoft 365 for enterprise のドキュメント](/microsoft-365-enterprise/)