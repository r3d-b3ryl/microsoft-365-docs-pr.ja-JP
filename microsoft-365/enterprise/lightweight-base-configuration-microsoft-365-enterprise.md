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
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: 6f916a77-301c-4be2-b407-6cec4d80df76
description: このテスト ラボ ガイドを使用して、Microsoft 365 Enterprise をテストするための軽量なテスト環境を作成します。
ms.openlocfilehash: 7a4800d374416a1e197536bc1a867d3fbc4b1243
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818755"
---
# <a name="the-lightweight-base-configuration"></a>軽量な基本構成

*このテストラボ ガイドは、Microsoft 365 Enterprise および Office 365 Enterprise テスト環境に使用できます。*

この記事は、Microsoft 365 E5 サブスクリプションと、Windows 10 Enterprise を実行しているコンピューターを使用して、簡略化された環境を作成する詳細な手順を説明します。 

![軽量な Microsoft 365 Enterprise テスト環境](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

作成された環境を使用して、[Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise) のフィーチャーと機能をテストします。

![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> Microsoft 365 Enterprise テスト ラボガイド内のすべての記事への視覚的なマップについては、[Microsoft 365 Enterprise テスト ラボガイド スタック](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)に移動して探します。

## <a name="phase-1-create-your-office-365-e5-subscription"></a>フェーズ 1: Office 365 E5 サブスクリプションを作成する

まず、Office 365 E5 試用版サブスクリプションを使用して、Microsoft 365 E5 サブスクリプションを追加します。

Office 365 E5 試用版サブスクリプションを開始するには、最初に、架空の会社名と新しい Microsoft アカウントが必要になります。
  
1. We recommend that you use a variant of the company name Contoso for your company name, which is a fictitious company used in Microsoft sample content, but it isn't required. Record your fictitious company name here: ![線](../media/Common-Images/TableLine.png)
    
2. To sign up for a new Microsoft account, go to [https://outlook.com](https://outlook.com) and create an account with a new email account and address. You will use this account to sign up for Office 365.
    
  - ここに新しいアカウントの姓名を記録してください: ![線](../media/Common-Images/TableLine.png)
    
  - 新しいメール アカウント アドレスをここに記録します。 ![線](../media/Common-Images/TableLine.png)@outlook.com
    
### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a>Office 365 E5 試用版サブスクリプションにサインアップする

1. コンピューターでインターネット ブラウザーを開き、[https://aka.ms/e5trial](https://aka.ms/e5trial) に移動します。
    
2. 「**Office 365 E5 をお選び頂き、ありがとうございます**」ページで、手順 1 の新しいメール アカウントのアドレスを明記します。
3. 試用版サブスクリプション プロセスの手順 2 で、必要な情報を入力して、検証を実行します。
4. 手順 3 では、組織名を入力して、サブスクリプション用の全体管理者になるアカウント名を入力します。 
5. 手順 4 では、ここにサインイン ページを記録します (選択してコピー): ![線](../media/Common-Images/TableLine.png) 
6. ここにユーザー ID を記録します: ![Line](../media/Common-Images/TableLine.png).onmicrosoft.com  
   入力したパスワードを安全な場所に記録してください。
   この値を**全体管理者名**と呼ぶことにします。
8. [**セットアップに移動**] をクリックします。
9. Office 365 E5 のセットアップで、**メールとサインイン用に組織の .onmicrosoft.com* を [* 引き続き続行する**] をクリックして、[**終了して後で続行する**] をクリックします。

Microsoft 365 管理センターが表示されます。
  
現在お持ちの有料サブスクリプションとは別の Azure AD テナントをテスト環境で保持できるように、Office 365 の試用版サブスクリプションを作成します。 このように分離することにより、運用サブスクリプションに影響を与えることなく、テスト テナントでのユーザーとグループの追加と削除が可能になります。
    
## <a name="phase-2-configure-your-office-365-trial-subscription"></a>フェーズ 2: Office 365 試用版サブスクリプションを構成する

このフェーズでは、サブスクリプションを構成してユーザーを追加し、Office 365 E5 ライセンスを割り当てます。
  
「[Office 365 PowerShell への接続](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)」の手順を使用して、コンピューターから Azure Active Directory PowerShell for Graph モジュールでサブスクリプションに接続します。
    
**[Windows PowerShell 資格情報の要求]** ダイアログ ボックスで、全体管理者名 (例: jdoe@contosotoycompany.onmicrosoft.com) およびパスワードを入力します。
  
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
> ここで共通のパスワードを使用するのは、自動化およびテスト環境の構成を容易にするためです。 運用環境のサブスクリプションは避けるように強くお勧めします。 

### <a name="record-key-information-for-future-reference"></a>将来の参照のために重要な情報を記録する

この記事を印刷しておき、30 日間の Office 365 試用版サブスクリプションの終了後にこの環境で必要になる特定の情報を記録しておくことをお勧めします。 試用版サブスクリプションは、追加で 30 日間まで簡単に延長できます。 永続的なテスト環境の場合は、別個の Azure AD テナントと少数のライセンスを使用して、新しい有料サブスクリプションを作成します。

これらの値を記録する:
  
- 全体管理者名: ![線](../media/Common-Images/TableLine.png).onmicrosoft.com (フェーズ 1 のステップ 6 から)
    
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

Office 365 のテスト環境だけが必要な場合は、ここで終了します。 

Office 365 と Microsoft 365 の両方に適用される追加のテスト ラボ ガイドについては、「[Microsoft 365 エンタープライズ テスト ラボ ガイド](m365-enterprise-test-lab-guides.md)」を参照してください。
  
## <a name="phase-3-add-a-microsoft-365-e5-trial-subscription"></a>フェーズ 3: Microsoft 365 E5 の試用版サブスクリプションを追加する

このフェーズでは、Microsoft 365 E5 試用版サブスクリプションにサインアップして、Office 365 E5 試用版サブスクリプションと同じ組織に追加します。
  
まず、Microsoft 365 E5 試用版サブスクリプションを追加して、新しい Microsoft 365 ライセンスを全体管理者アカウントに割り当てます。
  
1. インターネット ブラウザーのプライベート インスタンスで、全体管理者アカウントの資格情報を使用して、Microsoft 365 管理センター ([https://admin.microsoft.com](https://admin.microsoft.com)) にサインインします。
    
2. **[Microsoft 365 管理センター]** ページの左側のナビゲーションで **[請求]、[サービスを購入する]** の順にクリックします。
    
3. **[サービスを購入する]** ページで、**[Microsoft 365 E5]**、**[無料試用版を取得]** の順にクリックします。

4. **[Microsoft 365 E5 試用版]** ページで、テキスト メッセージを受信するか電話を受けるかを選択し、電話番号を入力して、**[テキスト メッセージを送信する]** または **[電話する]** をクリックします。 検証を実行します。

5. **[注文の確認]** ページで、 **[今すぐ実行]** をクリックします。

6. **[注文の受領書]** ページで、**[続行]** をクリックします。

7. Microsoft 365 管理センターで、**[ユーザー]、[アクティブなユーザー]** の順にクリックします。

8. **アクティブ ユーザー** で、自分の管理者アカウントをクリックします。

9. **[ライセンスとアプリ]** をクリックします。

10. Office 365 Enterprise E5 のライセンスを無効にして、Microsoft 365 E5 のライセンスを有効にします。

11. **[変更を保存]** をクリックして、ユーザー アカウント情報ウィンドウを閉じます。

次に、その他のすべてのアカウント (User 2、User 3、User 4、および User 5) に前述の手順 8 から 11 を繰り返します。
  
> [!NOTE]
> Microsoft 365 E5 の試用版サブスクリプションは 30 日間有効です。 永続的なテスト環境の場合は、少数のライセンスを使用して、この試用版のサブスクリプションを有料サブスクリプションに変換します。 
  
テスト環境は、次のようになっています。
  
- Microsoft 365 E5 の試用版サブスクリプション。
- すべての適切なユーザー アカウント (全体管理者のみまたは 5 つすべてのユーザー アカウントのどちらか) が、Microsoft 365 E5 を使用できるようになっている。
    
Office 365 と Enterprise Security + Management (EMS) の両方を含む Microsoft 365 E5 を追加した最終的な構成をここに示します。
  
![Microsoft 365 Enterprise テスト環境のフェーズ 3](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase2.png)
  
## <a name="phase-4-create-a-windows-10-enterprise-computer"></a>フェーズ 4: Windows 10 Enterprise コンピューターを作成する

このフェーズでは、物理コンピューター、仮想マシン、Azure 仮想マシンのいずれかとして Windows 10 Enterprise を実行するスタンドアロン コンピューターを作成します。
  
### <a name="physical-computer"></a>物理コンピューター

Obtain a personal computer and install Windows 10 Enterprise on it. You can download the Windows 10 Enterprise trial [here](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).
  
### <a name="virtual-machine"></a>仮想マシン

Create a virtual machine using the hypervisor of your choice and install Windows 10 Enterprise on it. You can download the Windows 10 Enterprise trial [here](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).
  
### <a name="virtual-machine-in-azure"></a>Azure での仮想マシン

To create a Windows 10 virtual machine in Microsoft Azure, ***you must have a Visual Studio-based subscription***, which has access to the image for Windows 10 Enterprise. Other types of Azure subscriptions, such as trial and paid subscriptions, do not have access to this image. For the latest information, see [Use Windows client in Azure for dev/test scenarios](https://docs.microsoft.com/azure/virtual-machines/windows/client-images).
  
> [!NOTE]
> The following command sets use the latest version of Azure PowerShell. See [Get started with Azure PowerShell cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/). These command sets build a Windows 10 Enterprise virtual machine named WIN10 and all of its required infrastructure, including a resource group, a storage account, and a virtual network. If you are already familiar with Azure infrastructure services, please adapt these instructions to suit your currently deployed infrastructure. 
  
最初に、Microsoft PowerShell プロンプトを起動します。
  
次のコマンドを使用して Azure アカウントにログインします。
  
```powershell
Connect-AzAccount
```

次のコマンドを使用して、サブスクリプションの名前を取得します。
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

Set your Azure subscription. Replace everything within the quotes, including the \< and > characters, with the correct name.
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

Next, create a new resource group. To determine a unique resource group name, use this command to list your existing resource groups.
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

Create your new resource group with these commands. Replace everything within the quotes, including the \< and > characters, with the correct names.
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

Next, you create a new virtual network and the WIN10 virtual machine with these commands. When prompted, provide the name and password of the local administrator account for WIN10 and store these in a secure location.
  
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
> Azure の仮想マシンの場合は、[この手順](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon)に従います。
  
次に、WIN10 コンピューターを Microsoft 365 E5 サブスクリプションの Azure AD テナントに参加させます。
  
1. WIN10 コンピューターのデスクトップで、**[スタート] > [設定] > [アカウント] > [職場または学校にアクセスする] > [接続]** の順にクリックします。
    
2. **[職場または学校アカウントの設定]** ダイアログ ボックスで、**[このデバイスを Azure Active Directory に参加させる]** をクリックします。
    
3. **[職場または学校アカウント]** に Microsoft 365 E5 サブスクリプションの全体管理者のアカウント名を入力して、**[次へ]** をクリックします。
    
4. **[パスワードの入力]** に全体管理者アカウントのパスワードを入力して、**[サインイン]** をクリックします。
    
5. この組織で合っているか確認するダイアログ ボックスが表示されたら、**[参加]** をクリックしてから **[完了]** をクリックします。
    
6. [設定] ウィンドウを閉じます。
    
次に、Microsoft 365 Apps for enterprise を WIN10 コンピューターにインストールします。
  
1. Microsoft Edge ブラウザーを開いて、グローバル管理者アカウントの認証資格情報を使用して、Office ポータルにサインインします。 詳細については、「[一般法人向け Office 365 にサインインする場所](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4)」を参照してください。
    
2. **[Microsoft Office Home]** タブで、**[Office のインストール]** をクリックします。
    
3. 操作内容を確認するダイアログ ボックスが表示されたら、**[実行]** をクリックし、**[ユーザー アカウント制御]** の **[はい]** をクリックします。
    
4. Wait for Office to complete its installation. When you see **You're all set!**, click **Close** twice.
    
最終的な環境をここに示します。

![Microsoft 365 Enterprise テスト環境のフェーズ 5](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

これには、以下を備えた WIN10 コンピューターが含まれます。

- Microsoft 365 E5 サブスクリプションの Azure AD テナントに参加している。
- Microsoft Intune (EMS) で Azure AD デバイスとして登録されている。
- Microsoft 365 Apps for enterprise がインストールされている。
  
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
