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
description: このテストラボガイドを使用して、エンタープライズ向けの Microsoft 365 をテストするための軽量なテスト環境を作成します。
ms.openlocfilehash: 2b8505e142c3c1b87578db7342ed299b95d8c049
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487390"
---
# <a name="the-lightweight-base-configuration"></a>軽量な基本構成

*このテストラボガイドは、Microsoft 365 for enterprise および Office 365 エンタープライズテスト環境の両方で使用できます。*

この記事では、Microsoft 365 E5 サブスクリプションと Windows 10 Enterprise を実行しているコンピューターを使用して、簡略化された環境を作成する方法について説明します。

![軽量な Microsoft 365 Enterprise テスト環境](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

軽量なテスト環境を作成するには、次の5つのフェーズが必要です。
- [フェーズ 1: Microsoft 365 E5 サブスクリプションを作成する](#phase-1-create-your-microsoft-365-e5-subscription)
- [フェーズ 2: Office 365 試用版サブスクリプションを構成する](#phase-2-configure-your-office-365-trial-subscription)
- [フェーズ 3: Microsoft 365 E5 の試用版サブスクリプションを追加する](#phase-3-add-a-microsoft-365-e5-trial-subscription)
- [フェーズ 4: Windows 10 Enterprise コンピューターを作成する](#phase-4-create-a-windows-10-enterprise-computer)
- [フェーズ 5: Windows 10 のコンピューターを Azure AD に参加させる](#phase-5-join-your-windows-10-computer-to-azure-ad)

生成された環境を使用して、 [Microsoft 365 for enterprise](https://www.microsoft.com/microsoft-365/enterprise)の機能をテストします。

![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> Microsoft 365 for enterprise のテストラボガイドスタックに含まれるすべての記事のビジュアルマップについては、「 [microsoft 365 for enterprise のテストラボガイドスタック](../downloads/Microsoft365EnterpriseTLGStack.pdf)」を参照してください。

>[!NOTE]
>この記事を印刷しておき、30 日間の Office 365 試用版サブスクリプションの終了後にこの環境で必要になる特定の情報を記録しておくことをお勧めします。 試用版サブスクリプションは、追加で 30 日間まで簡単に延長できます。 永続的なテスト環境の場合は、別個の Azure AD テナントと少数のライセンスを使用して、新しい有料サブスクリプションを作成します。

## <a name="phase-1-create-your-microsoft-365-e5-subscription"></a>フェーズ 1: Microsoft 365 E5 サブスクリプションを作成する

Microsoft 365 E5 試用版サブスクリプションから始めて、Microsoft 365 E5 サブスクリプションを追加します。

>[!NOTE]
>Office 365 の試用版サブスクリプションを作成することをお勧めします。これにより、現在所有している有料サブスクリプションとは別の Azure AD テナントがテスト環境に存在するようになります。 このような分離により、運用サブスクリプションに影響を与えることなく、テストテナントでユーザーとグループを追加および削除することができます。

Microsoft 365 E5 試用版サブスクリプションを開始するには、最初に、架空の会社名と新しい Microsoft アカウントが必要になります。
  
1. この会社名には、会社名 Contoso のバリエーションを使用するようお勧めします (必須ではありません)。Contoso は、Microsoft のサンプル コンテンツで使用される架空の会社名です。ここに架空の会社名を記録してください: ![線](../media/Common-Images/TableLine.png)
    
2. 新しい Microsoft アカウントにサインアップするには、[https://outlook.com](https://outlook.com) に移動して、新しい電子メール アカウントとアドレスでアカウントを作成します。このアカウントを使用して、Office 365 にサインアップします。
    
    - ここに新しいアカウントの姓名を記録してください: ![線](../media/Common-Images/TableLine.png)
    
    - 新しいメール アカウント アドレスをここに記録します。 ![線](../media/Common-Images/TableLine.png)@outlook.com
    
### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a>Office 365 E5 試用版サブスクリプションにサインアップする

1. ブラウザーで、に移動 [https://aka.ms/e5trial](https://aka.ms/e5trial) します。
    
2. [ **Office 365 E5 を選択していただきありがとうござい** ます] ページの手順1で、新しい電子メールアカウントのアドレスを入力します。
3. トレイルサブスクリプションプロセスのステップ2で、要求された情報を入力し、確認を行います。
4. 手順3で、組織名を入力してから、サブスクリプションのグローバル管理者になるアカウント名を入力します。
5. 手順 4 では、ここにサインイン ページを記録します (選択してコピー): ![線](../media/Common-Images/TableLine.png)
6. ここにユーザー ID を記録します: ![Line](../media/Common-Images/TableLine.png).onmicrosoft.com  
   入力したパスワードを安全な場所に記録します。
   この値を**全体管理者名**と呼ぶことにします。
7. [ **セットアップに移動**] を選択します。
8. Office 365 E5 セットアップで、[ **onmicrosoft.com を*your organization*使用してメールおよびサインイン**] を選択し、[終了] を選択して、**後で続行**します。

Microsoft 365 管理センターが表示されます。
    
## <a name="phase-2-configure-your-office-365-trial-subscription"></a>フェーズ 2: Office 365 試用版サブスクリプションを構成する

このフェーズでは、サブスクリプションを構成してユーザーを追加し、Office 365 E5 ライセンスを割り当てます。
  
コンピューターから Graph モジュールの Azure Active Directory PowerShell でサブスクリプションに接続するには、「 [PowerShell を使用した Microsoft 365 への接続](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)」の手順を使用します。
    
[ **Windows PowerShell 資格情報の要求** ] ダイアログボックスで、グローバル管理者名 (たとえば、 *jdoe@contosotoycompany.onmicrosoft.com*) とパスワードを入力します。
  
組織名 (たとえば、 *contosotoycompany*)、場所の2文字の国コード、および共通のアカウントパスワードを入力し、次のコマンドを PowerShell プロンプトから実行します。

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

これらの値を記録していない場合は、次のように記録してください。
  
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

Office 365 テスト環境のみが必要な場合は、この記事の残りの部分を読む必要はありません。

Office 365 と Microsoft 365 の両方に適用されるその他のテストラボガイドについては、「 [microsoft 365 for Enterprise Test Lab ガイド](m365-enterprise-test-lab-guides.md)」を参照してください。
  
## <a name="phase-3-add-a-microsoft-365-e5-trial-subscription"></a>フェーズ 3: Microsoft 365 E5 の試用版サブスクリプションを追加する

このフェーズでは、Microsoft 365 E5 試用版サブスクリプションにサインアップして、Office 365 E5 試用版サブスクリプションと同じ組織に追加します。
  
まず、Microsoft 365 E5 試用版サブスクリプションを追加して、新しい Microsoft 365 ライセンスを全体管理者アカウントに割り当てます。
  
1. インターネットブラウザーのプライベートウィンドウで、全体管理者アカウントの資格情報を使用して、Microsoft 365 管理センターにサインインし [https://admin.microsoft.com](https://admin.microsoft.com) ます。
    
2. [ **Microsoft 365 管理センター** ] ページの左側のナビゲーションで、[ **課金 > 購入サービス**] を選択します。
    
3. [ **サービスを購入** する] ページで、[ **Microsoft 365 E5**] を選択し、[ **無料試用版の取得**] を選択します。

4. **Microsoft 365 E5 試用版**ページで、テキストメッセージまたは電話を受信することを決定し、電話番号を入力して、[**テキスト**の選択] または [**呼び出し**] を選択します。 検証を実行します。

5. [ **注文の確認** ] ページで、[ **今すぐ試行**] を選択します。

6. [ **注文の受領書** ] ページで、[ **続行**] を選択します。

7. Microsoft 365 管理センターで、[ **ユーザー > アクティブユーザー**] を選択します。

8. [ **アクティブなユーザー**] で、管理者アカウントを選択します。

9. [ **ライセンスとアプリ**] を選択します。

10. Office 365 Enterprise E5 のライセンスを無効にして、Microsoft 365 E5 のライセンスを有効にします。

11. [ **変更の保存**] を選択し、[ユーザーアカウント情報] ウィンドウを閉じます。

次に、その他のすべてのアカウント (User 2、User 3、User 4、および User 5) に前述の手順 8 から 11 を繰り返します。
  
> [!NOTE]
> Microsoft 365 E5 試用版サブスクリプションの期間は30日です。 永続的なテスト環境の場合は、少数のライセンスを使用して、この試用版のサブスクリプションを有料サブスクリプションに変換します。
  
テスト環境は、次のようになっています。
  
- Microsoft 365 E5 の試用版サブスクリプション。
- すべての適切なユーザー アカウント (全体管理者のみまたは 5 つすべてのユーザー アカウントのどちらか) が、Microsoft 365 E5 を使用できるようになっている。
    
最終的な構成では、Microsoft 365 E5 が追加されます。次のようになります。
  
![Microsoft 365 Enterprise テスト環境のフェーズ 3](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase2.png)
  
## <a name="phase-4-create-a-windows-10-enterprise-computer"></a>フェーズ 4: Windows 10 Enterprise コンピューターを作成する

このフェーズでは、物理コンピューター、仮想マシン、Azure 仮想マシンのいずれかとして Windows 10 Enterprise を実行するスタンドアロン コンピューターを作成します。
  
### <a name="physical-computer"></a>物理コンピューター

パーソナルコンピューターで、Windows 10 Enterprise をインストールします。 [ここで](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise)は、Windows 10 Enterprise 試用版をダウンロードできます。
  
### <a name="virtual-machine"></a>仮想マシン

任意のハイパーバイザーを使用して仮想マシンを作成し、それに Windows 10 Enterprise をインストールします。 [ここで](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise)は、Windows 10 Enterprise 試用版をダウンロードできます。
  
### <a name="virtual-machine-in-azure"></a>Azure での仮想マシン

Microsoft Azure で Windows 10 の仮想マシンを作成するには、***Visual Studio ベースのサブスクリプションが必要***です。このサブスクリプションにより、Windows 10 Enterprise のイメージにアクセスできます。試用版や有料のサブスクリプションなど、その他の種類の Azure サブスクリプションでは、このイメージにアクセスできません。最新情報については、「[Azure で Windows クライアントを開発/テスト シナリオに使用する](https://docs.microsoft.com/azure/virtual-machines/windows/client-images)」を参照してください。
  
> [!NOTE]
> 次のコマンド セットは、Azure PowerShell の最新版を使用します。 「[Azure PowerShell の概要](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/)」を参照してください。 これらのコマンドセットは、WIN10 という名前の Windows 10 Enterprise 仮想マシンと、リソースグループ、ストレージアカウント、仮想ネットワークを含むすべての必要なインフラストラクチャを構築します。 Azure インフラストラクチャサービスについて既に理解している場合は、現在展開されているインフラストラクチャに合わせて、次の手順に従ってください。
  
最初に、Microsoft PowerShell プロンプトを起動します。
  
このコマンドを使用して Azure アカウントにサインインします。
  
```powershell
Connect-AzAccount
```

このコマンドを使用して、サブスクリプション名を取得します。
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

Azure サブスクリプションを設定します。 二重引用符内のすべての内容を、 \< and > 文字を含めて正しい名前で置換します。
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

次に、新しいリソース グループを作成します。 一意のリソース グループ名を決定するには、このコマンドを使用して既存のリソース グループを一覧表示します。
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

これらのコマンドを使用して、新しいリソース グループを作成します。 二重引用符内のすべての内容を、 \< and > 文字を含めて正しい名前で置換します。
  
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
> Azure の仮想マシンに接続するには、  [次の手順](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon) を使用します。
  
次に、WIN10 コンピューターを Microsoft 365 E5 サブスクリプションの Azure AD テナントに参加させます。
  
1. WIN10 コンピューターのデスクトップで、[> の設定の開始] を選択して、[ **Access work or school > Connect] > アカウント >** します。
    
2. [ **職場または学校アカウントの設定** ] ダイアログボックスで、[ **このデバイスを Azure Active Directory に参加させる**] を選択します。
    
3. [ **職場または学校のアカウント**] で、Microsoft 365 E5 サブスクリプションのグローバル管理者アカウント名を入力し、[ **次へ**] を選択します。
    
4. [ **パスワードの入力**] に全体管理者アカウントのパスワードを入力し、[ **サインイン**] を選択します。
    
5. 組織であることを確認するメッセージが表示されたら、[ **参加**] を選択して、[ **完了**] を選択します。
    
6. [設定] ウィンドウを閉じます。
    
次に、Microsoft 365 Apps for enterprise を WIN10 コンピューターにインストールします。
  
1. Microsoft Edge ブラウザーを開き、全体管理者アカウントの資格情報を使用して [microsoft 365 管理センター](https://admin.microsoft.com) にサインインします。
    
2. [ **Microsoft Office Home** ] タブで、[ **office のインストール**] を選択します。
    
3. 何を行うかを確認するメッセージが表示されたら、[**実行**] を選択して、[**ユーザーアカウント制御**] で [**はい]** を選択します。
    
4. Office のインストールが完了するまで待ちます。 **すべての設定が完了**したら、[**閉じる**] を2回選択します。
    
その結果、環境は次のようになります。

![Microsoft 365 Enterprise テスト環境のフェーズ 5](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

これには、以下を備えた WIN10 コンピューターが含まれます。

- Microsoft 365 E5 サブスクリプションの Azure AD テナントに参加している。
- Microsoft Intune (EMS) で Azure AD デバイスとして登録されている。
- Microsoft 365 enterprise 用アプリがインストールされています。
  
これで、 [Microsoft 365 for enterprise](https://www.microsoft.com/microsoft-365/enterprise)の追加機能を試す準備ができました。
  
## <a name="next-steps"></a>次の手順

こうした追加のテスト ラボ ガイドについて説明します。
  
- [ID](m365-enterprise-test-lab-guides.md#identity)
- [モバイル デバイス管理](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [情報保護](m365-enterprise-test-lab-guides.md#information-protection)
   

## <a name="see-also"></a>関連項目

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)

[Microsoft 365 for enterprise の概要](microsoft-365-overview.md)

[エンタープライズドキュメントの Microsoft 365](https://docs.microsoft.com/microsoft-365-enterprise/)
