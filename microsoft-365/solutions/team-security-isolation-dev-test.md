---
title: 開発/テスト環境でセキュリティの分離を使用してチームを構成する
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 08/14/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
ms.custom: ''
description: 従業員がいつでもどこからでもリモートで作業できるようにするセキュリティとインフラストラクチャを構成します。
ms.openlocfilehash: 5b2c47dff19b07a5ca2a207785891ebfb6777459ea9c5254680079f4458e8f84
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53804653"
---
# <a name="configure-a-team-with-security-isolation-in-a-devtest-environment"></a>開発/テスト環境でセキュリティの分離を使用してチームを構成する

この記事では、開発/テスト環境で[セキュリティを分離したチーム](secure-teams-security-isolation.md)を作るための詳細な手順について説明します。

![会社戦略の分離チームの構成](../media/team-security-isolation-dev-test/team-security-isolation-dev-test-config.png)

こうしたチームを運用環境に展開する前に、この開発/テスト環境を使用して、特定のニーズに合わせて設定を検証し、微調整します。

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>フェーズ 1: Microsoft 365 Enterprise のテスト環境を構築する

最小要件で機密チームと高機密チームを簡易な方法でテストする場合は、「[軽量な基本構成](../enterprise/lightweight-base-configuration-microsoft-365-enterprise.md)」の手順に従ってください。

シミュレーションのエンタープライズで機密チームと高機密チームをテストするには、「[パスワード ハッシュの同期](../enterprise/password-hash-sync-m365-ent-test-environment.md)」の手順に従ってください。

> [!NOTE]
> セキュリティ分離を使用してチームをテストする場合、シミュレーションのエンタープライズ テスト環境は必要ありません。シミュレーションのエンタープライズ テスト環境には、インターネットに接続されたシミュレーションのイントラネット、Active Directory Domain Services (AD DS) フォレスト用のディレクトリ同期が含まれています。 この機能は、セキュリティ分離を使用してチームをテストし、一般的な組織と類似した環境で試していただけるようオプションとしてここで提供されています。

## <a name="phase-2-create-and-configure-your-azure-active-directory-azure-ad-group-and-users"></a>フェーズ 2: Azure Active Directory (Azure AD) のグループとユーザーを作成して構成する

このフェーズでは、架空の組織用の Azure AD のグループとユーザーを作成して構成します。

まず、Azure ポータルでセキュリティ グループを作成します。

1. ブラウザーで新しいタブを開き、Azure portal ([https://portal.azure.com](https://portal.azure.com)) に移動します。 必要に応じて、Microsoft 365 E5 の試用版または有料サブスクリプション用の全体管理者アカウントの資格情報でサインインします。

2. Azure Portal で **[Azure Active Directory] > [グループ]** の順にクリックします。

3. **[グループ] - [すべてのグループ]** ブレードで、**[+ 新しいグループ]** をクリックします。

4. **[グループ]** ブレードでの手順:

  - **[グループの種類]** で **[セキュリティ]** を選択します。

  - **[名前]** に「**C スイート**」と入力します。

  - **[メンバーシップの種類]** で **[割り当て済み]** を選択します。

5. **[作成]** をクリックして、 **[グループ]** ブレードを閉じます。

次に、新しい **C スイート** グループのメンバーに Microsoft 365 E5 ライセンスが自動的に割り当てられるように、自動ライセンスを設定します。

1. Azure portal で **[Azure Active Directory] > [ライセンス] > [すべての製品]** の順にクリックします。

2. 一覧で、「**Microsoft 365 Enterprise E5**」を選択し、**[割り当て]** をクリックします。

3. **[ライセンスの割り当て]** ブレードで、 **[ユーザーとグループ]** をクリックします。

4. グループの一覧で、[**C スイト**] を選択します。

5. **[選択]** をクリックし、 **[割り当て]** をクリックします。

6. ブラウザーの [Azure Portal] タブを閉じます。

次に、[Graph 用 Azure Active Directory PowerShell モジュールに接続します](../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。

組織名、場所、および共通のパスワードを入力し、PowerShell コマンド プロンプトまたは Integrated Script Environment (ISE) からこれらのコマンドを実行し、新しいユーザー アカウントを作成し、それぞれの C スイト グループに追加します。

```powershell
$orgName="<organization name, such as contoso-test for the contoso-test.onmicrosoft.com trial subscription domain name>"
$location="<the ISO ALPHA2 country code, such as US for the United States>"
$commonPassword="<common password for all the new accounts>"

$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password=$commonPassword

$groupName="C-Suite"
$userNames=@("CEO","CFO","CIO")
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
```

> [!NOTE]
> ここで共通のパスワードを使用するのは、自動化と開発/テスト環境の構成を用意にするためです。当然ながら、これは運用サブスクリプションではお勧めできません。

次の手順を使用して、グループ ベースのライセンスが正しく機能していることを確認します。

1. [Microsoft 365 管理センター](https://admin.microsoft.com)にサインインします。

2. ブラウザーの新しい **[Microsoft 365 管理センター]** タブで、**[ユーザー]** をクリックします。

3. ユーザーの一覧で、**[CEO]** をクリックします。

4. **CEO** ユーザー アカウントのプロパティが一覧表示されているウィンドウで、**製品ライセンス** 内に **Microsoft 365 Enterprise E5** のライセンスが割り当てられている ことを確認します。

## <a name="phase-3-create-your-team"></a>フェーズ 3: チームを作成する

このフェーズでは、シニア リーダーシップ チームのメンバーが会社の戦略に協力できるように、セキュリティを分離したチームを作成して構成します。

まず、[この記事](../compliance/sensitivity-labels-teams-groups-sites.md)の手順に進む前に、Microsoft Teams、Office 365 グループ、SharePoint サイトのコンテンツを保護するために秘密度ラベルを有効にします。

次に、チームを作ります。

1. Teams で、アプリの左側にある **[Teams]** をクリックして、チーム リストの下部にある **[チームに参加またはチームの作成]** をクリックします。
2. **[チームの作成]** (最初のカード、左上隅) をクリックします。
3. **[初めからチームを作成する]** を選びます。
4. **[秘密度]**] リストで、既定のままにします。
5. **[プライバシー]** で、**[プライベート]** をクリックします。
6. **会社戦略** と入力し、[**作成**]  >  [**閉じる**] の順にクリックします。

次に、プライベート チャネルの作成を会社戦略グループの所有者に制限します。

1. チームで、**[その他のオプション]** をクリックしてから、**[チームの管理]** をクリックします。
2. **[設定]** タブで、**[メンバーのアクセス許可]** を展開します。
3. **[プライベート チャネルを作成する]** チェック ボックスをオフにします。

次に、秘密度ラベルを次の設定で構成します。

- 名前は "会社戦略" です。
- 暗号化が有効になっています
- 会社戦略グループには、共同編集のアクセス許可があります

次の手順を実行します。

1. [Microsoft 365 コンプライアンス センター](https://compliance.microsoft.com)を開きます。
2. **[ソリューション]** で、**[情報保護]** をクリックします。
3. **[ラベルの作成]** をクリックします。
4. ラベル名に **会社戦略** と入力します。
5. ツール ヒントに **シニア リーダーシップの会社戦略文書** と入力し、[**次へ**] をクリックします。
6. **[暗号化]** ページの **[暗号化]** ドロップダウンで、**[適用]** を選びます。
7. チームのアクセス許可を追加するには:<br>
  a. **[アクセス許可の割り当て]** をクリックします。<br>
  b. **[ユーザーまたはグループの追加]** をクリックして、**会社戦略** を選択してから [**追加**] をクリックします。<br>
  c.  **[アクセス許可の選択]** をクリックします。<br>
  d.  ドロップダウン リストから **[共同編集者]** を選択し、**[保存]** をクリックします。<br>
8. [**次へ**] をクリックします。
9. **[コンテンツのマーキング]** ページで、**[次へ]** をクリックします。
10. **[サイトとグループの設定]** ページで、**[サイトとグループの設定]** を **[オン]** に設定します。
11. **[Office 365 グループに接続されているチーム サイトのプライバシー]** ドロップダウンで、**[非公開 - メンバーのみがサイトにアクセス可能]** を選びます。
12. **[非管理対象デバイス]** で、**[アクセスをブロックする]** を選びます。
13. **[次へ]** をクリックします。
14. **[Office アプリの自動ラベル付け]** ページで、**[次へ]** をクリックします。
15. **[送信]** をクリックしてから、**[完了]** をクリックします。

次に、新しいラベルを次の手順で発行します。

1. Microsoft 365 コンプライアンス センターまたは **[情報保護]** ページで、**[ラベル ポリシー]** タブを選びます。
2. **[ラベルの発行]** をクリックします。
3. **[発行する秘密度ラベルの選択]** ページで、**[発行する秘密度ラベルの選択]** をクリックします。
4. **会社戦略** を選択し、[**追加**] をクリックします。
5. [**次へ**] をクリックします。
6. [**ユーザーとグループに発行**] ページで、[**ユーザーとグループの選択**] をクリックします。
7. [**追加**] をクリックし、**会社戦略** を選択します。
8. **[追加]** をクリックし、**[完了]** をクリックします。
9. **[次へ]** をクリックします。
10. [ポリシーの設定] ページで、**[ユーザーはラベルを削除するか、分類ラベルを下げるために正当な理由を提供する必要がある]** チェック ボックスをオンにし、**[次へ]** をクリックします。
11. ポリシー名として **会社戦略** と入力し、[**次へ**] をクリックします。
12. **[送信]** をクリックしてから、**[完了]** をクリックします。

発行後に **会社戦略** ラベルが使用可能になるまでに、しばらく時間がかかる場合があります。

次に、新しいラベルを **会社戦略** チームに適用し、既定の共有リンクの種類を更新して、意図したよりも広い対象ユーザーにファイルやフォルダーが不用意に共有されるリスクを軽減します。

1. [SharePoint 管理センター](https://admin.microsoft.com/sharepoint)を開きます。
2. **[サイト]** で、**[アクティブなサイト]** をクリックします。
3. **会社戦略** サイトをクリックします。
4. **[ポリシー]** タブで、**[秘密度]** の下側にある **[編集]** をクリックします。
5. **会社戦略** ラベルを選択し、[**保存**] をクリックします。
6. **[ポリシー]** タブで、**[外部共有]** の下側にある **[編集]** をクリックします。
5. [**組織内のユーザーのみ**] を選択します。
6. [**既定の共有リンクの種類**] で、[**組織レベルの設定と同じ**] チェック ボックスをオフにして、[**既存のアクセス権を持つユーザー**] を選びます。
7. [**保存**] をクリックします。

次に、**会社戦略** チームの所有者のみのサイト共有を構成します。

1. Teams で、**会社戦略** チームの **[全般]** タブに移動します。
2. チームのツール バーで、**[ファイル]** をクリックします。
3. 省略記号をクリックし、**[SharePoint で開く]** をクリックします。
4. 基となる SharePoint サイトのツール バーで、設定アイコンをクリックしてから、**[サイトの権限]** をクリックします。
5. [サイトの権限] ウィンドウで、**[サイトの共有]** の **[メンバーが共有する方法を変更]** をクリックします。
6. **[共有アクセス許可]** で、**[サイト所有者のみが、ファイル、フォルダー、およびサイトを共有できます]** を選択して、**[保存]** をクリックします。
7. [**アクセス許可**] および [**設定**] ウィンドウを閉じます。

会社戦略グループのメンバーとしてサインインすると、Word、Excel、PowerPoint のホーム ツール バーの [**秘密度**] オプションに **会社戦略** が表示されています。 ラベルをファイルに割り当てるには、[**秘密度**] オプションから **会社戦略** ラベルを選択します。

会社戦略チームの最終的な構成をここに示します。

![会社戦略の分離チームの構成](../media/team-security-isolation-dev-test/team-security-isolation-dev-test-config.png)

## <a name="next-step"></a>次のステップ

実稼働環境の展開の準備ができたら、「[構成手順](secure-teams-security-isolation.md)」を参照してください。
