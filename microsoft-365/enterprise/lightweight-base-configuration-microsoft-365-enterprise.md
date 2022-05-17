---
title: 軽量な基本構成
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 11/14/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
- admindeeplinkMAC
ms.assetid: 6f916a77-301c-4be2-b407-6cec4d80df76
description: このテスト ラボ ガイドを使用して、エンタープライズ向けのMicrosoft 365をテストするための軽量のテスト環境を作成します。
ms.openlocfilehash: 0da4a38ad951d30a536e653336571e7bad04a889
ms.sourcegitcommit: 9255a7e8b398f92d8dae09886ae95dc8577bf29a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2022
ms.locfileid: "65435305"
---
# <a name="the-lightweight-base-configuration"></a>軽量な基本構成

*このテスト ラボ ガイドは、エンタープライズ環境とOffice 365 Enterpriseテスト環境の両方のMicrosoft 365に使用できます。*

この記事では、Microsoft 365 E5 サブスクリプションとWindows 10 Enterpriseを実行しているコンピューターを使用して簡略化された環境を作成する方法について説明します。

![軽量の Microsoft 3656 Enterpriseテスト環境。](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

軽量テスト環境の作成には、次の 5 つのフェーズがあります。
- [フェーズ 1: Microsoft 365 E5 サブスクリプションを作成する](#phase-1-create-your-microsoft-365-e5-subscription)
- [フェーズ 2: Office 365 試用版サブスクリプションを構成する](#phase-2-configure-your-office-365-trial-subscription)
- [フェーズ 3: Microsoft 365 E5 の試用版サブスクリプションを追加する](#phase-3-add-a-microsoft-365-e5-trial-subscription)
- [フェーズ 4: Windows 10 Enterprise コンピューターを作成する](#phase-4-create-a-windows-10-enterprise-computer)
- [フェーズ 5: Windows 10 のコンピューターを Azure AD に参加させる](#phase-5-join-your-windows-10-computer-to-azure-ad)

結果の環境を使用して、[エンタープライズ向けのMicrosoft 365](https://www.microsoft.com/microsoft-365/enterprise)の機能と機能をテストします。

![Microsoft クラウドのテスト ラボ ガイド。](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> エンタープライズ テスト ラボ ガイド スタックのMicrosoft 365のすべての記事へのビジュアル マップについては、「エンタープライズ テスト ラボ ガイド スタック[のMicrosoft 365](../downloads/Microsoft365EnterpriseTLGStack.pdf)」を参照してください。

>[!NOTE]
>この記事を印刷しておき、30 日間の Office 365 試用版サブスクリプションの終了後にこの環境で必要になる特定の情報を記録しておくことをお勧めします。 試用版サブスクリプションは、追加で 30 日間まで簡単に延長できます。 永続的なテスト環境の場合は、別個の Azure AD テナントと少数のライセンスを使用して、新しい有料サブスクリプションを作成します。

## <a name="phase-1-create-your-microsoft-365-e5-subscription"></a>フェーズ 1: Microsoft 365 E5 サブスクリプションを作成する

Microsoft 365 E5試用版サブスクリプションから始めてから、Microsoft 365 E5 サブスクリプションを追加します。

>[!NOTE]
>テスト環境に、現在持っている有料サブスクリプションとは別の Azure AD テナントが存在するように、Office 365の試用版サブスクリプションを作成することをお勧めします。 この分離は、運用サブスクリプションに影響を与えることなく、テスト テナント内のユーザーとグループを追加および削除できることを意味します。

Microsoft 365 E5 試用版サブスクリプションを開始するには、最初に、架空の会社名と新しい Microsoft アカウントが必要になります。
  
1. この会社名には、会社名 Contoso のバリエーションを使用するようお勧めします (必須ではありません)。Contoso は、Microsoft のサンプル コンテンツで使用される架空の会社名です。ここに架空の会社名を記録してください: ![直線](../media/Common-Images/TableLine.png)

2. 新しい Microsoft アカウントにサインアップするには、新しい電子メール アカウントとアドレスを使用してアカウントにアクセス [https://outlook.com](https://outlook.com) して作成します。 このアカウントを使用して、Office 365にサインアップします。

    - ここに新しいアカウントの姓名を記録してください: ![直線](../media/Common-Images/TableLine.png)

    - 新しいメール アカウント アドレスをここに記録します。 ![直線](../media/Common-Images/TableLine.png)@outlook.com

### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a>Office 365 E5 試用版サブスクリプションにサインアップする

1. ブラウザーで 、 [https://aka.ms/e5trial](https://aka.ms/e5trial).

2. [Office 365 E5 **選択していただきありがとうございます**] ページの手順 1 で、新しいメール アカウント のアドレスを入力します。
3. 証跡サブスクリプション プロセスの手順 2 で、要求された情報を入力し、検証を実行します。
4. 手順 3 で、組織名と、サブスクリプションのグローバル管理者となるアカウント名を入力します。
5. 手順 4 では、ここにサインイン ページを記録します (選択してコピー): ![直線](../media/Common-Images/TableLine.png)
6. ここでユーザー ID を記録します。 ![Line.](../media/Common-Images/TableLine.png).onmicrosoft.com  
   安全な場所に入力したパスワードを記録します。
   この値を **全体管理者名** と呼ぶことにします。
7. [ **セットアップに移動] を選択します**。
8. Office 365 E5セットアップで、**電子メールとサインインに組織の onmicrosoft.com *を* 使用して続行** を選択し、終了を選択 **して後で続行** します。

Microsoft 365 管理センターが表示されます。

## <a name="phase-2-configure-your-office-365-trial-subscription"></a>フェーズ 2: Office 365 試用版サブスクリプションを構成する

このフェーズでは、他のユーザーとサブスクリプションを構成し、それらをライセンスOffice 365 E5割り当てます。
  
コンピューターから Azure Active Directory PowerShell for Graph モジュールを使用してサブスクリプションに接続するには、Connectの手順[に従って PowerShell をMicrosoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)します。
    
**[Windows PowerShell資格情報要求**] ダイアログ ボックスで、グローバル管理者名 (*jdoe@contosotoycompany.onmicrosoft.com* など) とパスワードを入力します。
  
組織名 ( *contosotoycompany* など)、場所の 2 文字の国コード、共通アカウントのパスワードを入力し、PowerShell プロンプトから次のコマンドを実行します。

```powershell
$orgName="<organization name>"
$loc="<two-character country code, such as US>"
$commonPW="<common user account password>"
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password=$commonPW

$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value "ENTERPRISEPREMIUM" -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License

for($i=2;$i -le 4; $i++) {
    $userUPN= "user$($i)@$($orgName).onmicrosoft.com"
    New-AzureADUser -DisplayName "User $($i)" -GivenName User -SurName $i -UserPrincipalName $userUPN -UsageLocation $loc -AccountEnabled $true -PasswordProfile $PasswordProfile -MailNickName "user$($i)"
    $userObjectID = (Get-AzureADUser -SearchString $userupn).ObjectID
    Set-AzureADUserLicense -ObjectId $userObjectID -AssignedLicenses $LicensesToAssign
}
```

> [!NOTE]
> ここで共通のパスワードを使用するのは、自動化およびテスト環境の構成を容易にするためです。 運用環境のサブスクリプションは避けるように強くお勧めします。 

### <a name="record-key-information-for-future-reference"></a>将来の参照のために重要な情報を記録する

これらの値をまだ記録していない場合は、次のように記録します。
  
- グローバル管理者名: ![直線](../media/Common-Images/TableLine.png).onmicrosoft.com (フェーズ 1 のステップ 6 から)

    このアカウントのパスワードも安全な場所に記録してください。

- 試用版サブスクリプションの組織名: ![直線](../media/Common-Images/TableLine.png) (フェーズ 1 のステップ 4 から)

- ユーザー 2、ユーザー 3、ユーザー 4、およびユーザー 5 のアカウントを一覧表示するには、Azure Active Directory モジュールから次のコマンドを実行してWindows PowerShellプロンプトを表示します。

  ```powershell
  Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName
  ```

    ここにアカウント名を記録してください:

  - ユーザー 2 アカウント名: user2@![直線](../media/Common-Images/TableLine.png).onmicrosoft.com

  - ユーザー 3 アカウント名: user3@![直線](../media/Common-Images/TableLine.png).onmicrosoft.com

  - ユーザー 4 アカウント名: user4@![直線](../media/Common-Images/TableLine.png).onmicrosoft.com

  - ユーザー 5 アカウント名: user5@![直線](../media/Common-Images/TableLine.png).onmicrosoft.com

    これらのアカウントの共通パスワードも安全な場所に記録してください。

### <a name="using-an-office-365-test-environment"></a>Office 365 テスト環境を使用する

Office 365テスト環境のみが必要な場合は、この記事の残りの部分を読む必要はありません。

Office 365とMicrosoft 365の両方に適用されるその他の[テスト ラボ ガイドについては、「エンタープライズ テスト ラボ ガイドのMicrosoft 365](m365-enterprise-test-lab-guides.md)」を参照してください。
  
## <a name="phase-3-add-a-microsoft-365-e5-trial-subscription"></a>フェーズ 3: Microsoft 365 E5 の試用版サブスクリプションを追加する

このフェーズでは、Microsoft 365 E5 試用版サブスクリプションにサインアップして、Office 365 E5 試用版サブスクリプションと同じ組織に追加します。
  
まず、Microsoft 365 E5 試用版サブスクリプションを追加して、新しい Microsoft 365 ライセンスを全体管理者アカウントに割り当てます。
  
1. インターネット ブラウザーのプライベート ウィンドウで、グローバル管理者アカウントの資格情報を使用して、次のMicrosoft 365 管理センターに[https://admin.microsoft.com](https://admin.microsoft.com)サインインします。
    
2. **Microsoft 365 管理センター** ページの左側のナビゲーションで、<a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">**BillingPurchase**</a> >  サービスを選択します。
    
3. [**サービスの購入**] ページ **で、[Microsoft 365 E5**] を選択し、[**無料試用版の入手**] を選択します。

4. **[Microsoft 365 E5試用版**] ページで、テキスト メッセージまたは電話の着信を受け取り、電話番号を入力して、[**テキスト**] または [**通話**] を選択します。 検証を実行します。

5. [ **注文の確認** ] ページで、[ **今すぐ試す**] を選択します。

6. **[注文の受領書]** ページで、[続行] を選択 **します**。

7. Microsoft 365 管理センターで、**[ユーザー]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">**[アクティブなユーザー]**</a> の順に選択します。

8. **アクティブなユーザー** で、管理者アカウントを選択します。

9. **［ライセンスとアプリ］** を選択します。

10. Office 365 Enterprise E5 のライセンスを無効にして、Microsoft 365 E5 のライセンスを有効にします。

11. [ **変更の保存] を** 選択し、ユーザー アカウント情報ウィンドウを閉じます。

次に、その他のすべてのアカウント (User 2、User 3、User 4、および User 5) に前述の手順 8 から 11 を繰り返します。
  
> [!NOTE]
> Microsoft 365 E5試用版サブスクリプションの長さは 30 日間です。 永続的なテスト環境の場合は、少数のライセンスを使用して、この試用版のサブスクリプションを有料サブスクリプションに変換します。
  
テスト環境は、次のようになっています。
  
- Microsoft 365 E5 の試用版サブスクリプション。
- すべての適切なユーザー アカウント (全体管理者のみまたは 5 つすべてのユーザー アカウントのどちらか) が、Microsoft 365 E5 を使用できるようになっている。
    
Microsoft 365 E5を追加する結果の構成は次のようになります。
  
![Microsoft 3656 Enterpriseテスト環境のフェーズ 3。](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase2.png)
  
## <a name="phase-4-create-a-windows-10-enterprise-computer"></a>フェーズ 4: Windows 10 Enterprise コンピューターを作成する

このフェーズでは、物理コンピューター、仮想マシン、Azure 仮想マシンのいずれかとして Windows 10 Enterprise を実行するスタンドアロン コンピューターを作成します。
  
### <a name="physical-computer"></a>物理コンピューター

パーソナル コンピューターで、Windows 10 Enterpriseをインストールします。 Windows 10 Enterpriseの評価版をダウンロードできます。

> [!NOTE]
> Microsoft Evaluation Center は一時的に使用できません。 このダウンロードにアクセスするには、「[Windowsの試用版とキットへのアクセス (Eval Center の回避策)」を](https://techcommunity.microsoft.com/t5/windows-11/accessing-trials-and-kits-for-windows-eval-center-workaround/m-p/3361125)参照してください。<!-- 6049663 -->

### <a name="virtual-machine"></a>仮想マシン

任意のハイパーバイザーを使用して仮想マシンを作成し、その上にWindows 10 Enterpriseをインストールします。 Windows 10 Enterpriseの評価版をダウンロードできます。

> [!NOTE]
> Microsoft Evaluation Center は一時的に使用できません。 このダウンロードにアクセスするには、「[Windowsの試用版とキットへのアクセス (Eval Center の回避策)」を](https://techcommunity.microsoft.com/t5/windows-11/accessing-trials-and-kits-for-windows-eval-center-workaround/m-p/3361125)参照してください。<!-- 6049663 -->

### <a name="virtual-machine-in-azure"></a>Azure での仮想マシン

Microsoft AzureでWindows 10仮想マシンを作成するには、Windows 10 EnterpriseのイメージにアクセスできるVisual Studio ***ベースのサブスクリプションが必要*** です。 試用版サブスクリプションや有料サブスクリプションなど、他の種類の Azure サブスクリプションでは、このイメージにアクセスできません。 最新の情報については、「[開発/テストのシナリオで Azure でクライアントWindows使用する」を](/azure/virtual-machines/windows/client-images)参照してください。
  
> [!NOTE]
> 次のコマンド セットは、Azure PowerShell の最新版を使用します。 「[Azure PowerShell の概要](/powershell/azureps-cmdlets-docs/)」を参照してください。 これらのコマンド セットは、WIN10 という名前のWindows 10 Enterprise仮想マシンとその必要なすべてのインフラストラクチャ (リソース グループ、ストレージ アカウント、仮想ネットワークなど) を構築します。 Azure インフラストラクチャ サービスに既に精通している場合は、現在デプロイされているインフラストラクチャに合わせてこれらの手順を調整します。
  
最初に、Microsoft PowerShell プロンプトを起動します。
  
このコマンドを使用して Azure アカウントにサインインします。
  
```powershell
Connect-AzAccount
```

このコマンドを使用して、サブスクリプション名を取得します。
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

Azure サブスクリプションを設定します。 引用符 (文字を含む \< and > ) 内のすべてを正しい名前に置き換えます。
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

次に、新しいリソース グループを作成します。一意のリソース グループ名を決定するには、このコマンドを使用して既存のリソース グループを一覧表示します。
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

これらのコマンドを使用して、新しいリソース グループを作成します。 引用符 (文字を含む \< and > ) 内のすべてを正しい名前に置き換えます。
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

次に、次のコマンドを使用して、新しい仮想ネットワークと WIN10 仮想マシンを作成します。 メッセージが表示されたら、WIN10 のローカル管理者アカウントの名前とパスワードを入力し、この情報を安全な場所に格納します。
  
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
> Azure の仮想マシンの場合は、  [次の手順に従](/azure/virtual-machines/windows/connect-logon) って接続します。
  
次に、WIN10 コンピューターを Microsoft 365 E5 サブスクリプションの Azure AD テナントに参加させます。
  
1. WIN10 コンピューターのデスクトップで、[職場 **または学校の> Connectにアクセス>アカウント> 設定 >開始]** を選択します。

2. [**職場または学校アカウントのセットアップ**] ダイアログ ボックスで、[**このデバイスをAzure Active Directoryに参加** する] を選択します。

3. **職場または学校アカウント** で、Microsoft 365 E5 サブスクリプションのグローバル管理者アカウント名を入力し、[**次へ**] を選択します。

4. [ **パスワードの入力**] で、グローバル管理者アカウントのパスワードを入力し、[ **サインイン**] を選択します。

5. この組織が自分の組織であることを確認するように求められたら、[ **参加**] を選択し、[ **完了**] を選択します。

6. [設定] ウィンドウを閉じます。

次に、WIN10 コンピューターにMicrosoft 365 Apps for enterpriseをインストールします。
  
1. Microsoft Edge ブラウザーを開き、グローバル管理者アカウントの資格情報を[使用してMicrosoft 365 管理センター](https://admin.microsoft.com)にサインインします。

2. **[Microsoft Office ホーム**] タブで、[**Officeのインストール**] を選択します。

3. 操作を求められたら、[**実行**] を選択し、[**ユーザー アカウント制御**] **で [はい**] を選択します。

4. Office のインストールが完了するまで待ちます。 [ **完了**] が表示されたら、[ **閉じる** ] を 2 回選択します。

結果の環境は次のようになります。

![Microsoft 3656 Enterpriseテスト環境のフェーズ 5。](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

この環境には、次を含む WIN10 コンピューターが含まれます。

- Microsoft 365 E5 サブスクリプションの Azure AD テナントに参加している。
- Microsoft Intune (EMS) で Azure AD デバイスとして登録されている。
- Microsoft 365 Apps for enterpriseインストールされています。
  
[これで、エンタープライズ向けのMicrosoft 365](https://www.microsoft.com/microsoft-365/enterprise)のより多くの機能を試す準備が整いました。
  
## <a name="next-steps"></a>次の手順

テスト ラボ ガイドの他のセットを確認します。
  
- [ID](m365-enterprise-test-lab-guides.md#identity)
- [モバイル デバイス管理](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [情報保護](m365-enterprise-test-lab-guides.md#information-protection)

## <a name="see-also"></a>関連項目

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)

[Microsoft 365 for enterprise の概要](microsoft-365-overview.md)

[Microsoft 365 for enterprise のドキュメント](/microsoft-365-enterprise/)
