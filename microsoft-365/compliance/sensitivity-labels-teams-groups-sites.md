---
title: Microsoft Teams、Office 365 グループ、SharePoint サイトで機密ラベルを使用する (パブリック プレビュー)
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Microsoft Teams、Office 365 グループ、SharePoint サイトにラベルを適用することができます。
ms.openlocfilehash: 1e08df688a62d6c15ef0100b5379e62482ed7b50
ms.sourcegitcommit: 9224a7a5886c0c5fa0bc12bd9f7234a0eba90023
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/02/2020
ms.locfileid: "42372035"
---
# <a name="use-sensitivity-labels-with-microsoft-teams-office-365-groups-and-sharepoint-sites-public-preview"></a>Microsoft Teams、Office 365 グループ、SharePoint サイトで機密ラベルを使用する (パブリック プレビュー)

[Microsoft 365 コンプライアンス センター](https://protection.office.com/)で機密ラベルを作成する場合、次のコンテナーへと適用できるようになりました: Microsoft Teams、Office 365 グループ、SharePoint サイト。 ラベル設定を使用して、これらのコンテナーの次のオプションを制御します。

- Office 365 グループに接続されているチーム サイトのプライバシー(パブリックまたはプライベート)
- 外部ユーザーのアクセス
- 非管理対象デバイスからのアクセス 

サポートされているコンテナーの 1 つにこのラベルを適用すると、構成済みオプションが接続された SharePoint サイトまたはチーム サイトに自動的に適用されます。 

ただし、これらのコンテナーのコンテンツは、ラベル名、視覚的なマーキング、暗号化などの設定のラベルを継承しません。 SharePoint サイトまたはチーム サイトのファイルにラベルを付けるには、[SharePoint および OneDrive で Office ファイルの機密度ラベルを有効にします](sensitivity-labels-sharepoint-onedrive-files.md)。

## <a name="about-the-public-preview-for-microsoft-teams-office-365-groups-and-sharepoint-sites"></a>Microsoft Teams、Office 365 グループ、および SharePoint サイトのパブリック プレビューについて

Microsoft Teams、Office 365 グループ、および SharePoint サイト向けの機密ラベルは徐々にテナントへと展開され、最終リリース前に変更される可能性があります。 このパブリック プレビューは、Office 365 コンテンツ配信ネットワーク (CDN) では機能しません。

このプレビューを有効にして新しい設定の機密ラベルを構成する前に、ユーザーはアプリで機密ラベルを表示および適用できます。 たとえば、Word から: 

![Word デスクトップ アプリに表示される機密ラベル](../media/sensitivity-label-word.png)

このプレビューを有効にして構成すると、ユーザーは追加で機密ラベルを表示し、Microsoft Teams、Office 365 グループ、および SharePoint サイトに適用することができます。 たとえば、SharePoint から新しいチーム サイトを作成する場合:

![SharePoint でチーム サイトを作成するときの機密ラベル](../media/sensitivity-labels-new-team-site.png)

## <a name="enable-this-preview-and-synchronize-labels"></a>このプレビューを有効にしてラベルを同期する

1. この機能は Azure AD 機能を使用するため、Azure AD のドキュメントの指示に従ってプレビューを有効にします: [Assign sensitivity labels to Office 365 groups in Azure Active Directory (preview) (Azure Active Directory の Office 365 グループに機密ラベルを割り当てる (プレビュー))](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels)。

2. PowerShell セッションで、グローバル管理者特権を持つ職場または学校のアカウントを使用して、セキュリティ/コンプライアンス センターに接続します。 例:
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    ```
    
    詳細な手順については、「[Office 365 セキュリティ/コンプライアンス センターの PowerShell への接続](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)」を参照してください。

3. 秘密度ラベルを Office 365 グループで使用できるように、次のコマンドを実行して秘密度ラベルを Azure AD に同期させます。
    
    ```powershell
    Execute-AzureAdLabelSync
    ```

## <a name="how-to-configure-site-and-group-settings-when-you-create-or-edit-sensitivity-labels"></a>機密ラベルを作成または編集する際に、サイトおよびグループの設定を構成する方法

これで、サイトおよびグループで使用する機密ラベルを作成または編集する準備が整いました。 プレビューを有効にすると、秘密度のラベル付けウィザードで新しいページが表示されます: **サイトとグループの設定**

機密ラベルの作成または編集に関するヘルプが必要な場合は、「[機密ラベルを作成して構成する](create-sensitivity-labels.md#create-and-configure-sensitivity-labels)」の手順を参照してください。

この新しい [**サイトとグループの設定**] ページで、設定を構成します。

- **Office 365 グループに接続されたチーム サイトのプライバシー**: デフォルト設定の [**パブリック**] は自動的に選択されます。つまり、組織内のすべてのユーザーがこのラベルが適用されているチーム サイトにアクセスできます。 組織内の承認されたメンバーのみがグループのチーム サイトにアクセスできるようにする場合は、[**プライベート**] を選択します。 
    
    選択した設定は、グループに構成されている可能性がある以前のプライバシー設定を置き換え、プライバシー値をロックします。よって、チーム サイトまたはグループから最初に機密ラベルを削除することによってのみ、変更できるようになります。 機密ラベルを削除しても、ラベルからのプライバシー設定は維持され、必要に応じて変更できるようになりました。

- **外部ユーザー アクセス**: グループの所有者が[ゲストをグループに追加](/office365/admin/create-groups/manage-guest-access-in-groups)できるかどうかを制御します。

- **非管理対象デバイス**: [非管理対象デバイス](/sharepoint/control-access-from-unmanaged-devices)の場合、フル アクセスを許可するか、Web のみのアクセスを許可するか、またはアクセスを完全にブロックします。 

![[サイトとグループの設定] タブ](../media/edit-sensitivity-label-site-group.png)

> [!IMPORTANT]
> チーム、グループ、またはサイトにラベルを適用すると、それらのサイトとグループの設定のみが有効になります。 暗号化やコンテンツ マーキングなどのその他のラベル設定は、チーム、グループ、またはサイト内のコンテンツに適用されません。
> 
> 同様に、ラベルを作成しそれらのサイトとグループの設定をオンにしない場合には、ユーザーがチーム、グループ、およびサイトを作成するときにラベルは引き続き使用できますが、ラベル名のみが適用されます。

秘密度ラベルがまだ公開されていない場合は、[秘密度ラベル ポリシーに追加](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy)して公開します。 このラベルを含む秘密度ラベル ポリシーが割り当てられているユーザーには、サイトとグループ用にそのラベルを選択できます。

## <a name="sensitivity-label-management"></a>機密ラベルの管理

> [!WARNING]
> Microsoft Teams、Office 365 グループ、および SharePoint サイトに使用する機密ラベルを作成、変更、および削除するには、ラベル ポリシーをユーザーに発行する際に慎重な調整が必要です。 

以下のガイダンスを使用して、すべてのユーザーに影響を与える可能性のあるサイトおよびグループの作成エラーを回避します。

**ラベルの作成と発行:**

機密ラベルを作成して公開した後、チーム、グループ、およびサイトでユーザーがラベルを表示できるようになるまでに最大 24 時間かかる場合があります。 以下の手順を使用して、テナント内のすべてのユーザーにラベルを発行します:

1. 機密ラベルを作成し、テナント内の少数のユーザー アカウントに対してのみ発行します。

2. 24 時間待ちます。

3. この 24 時間の待ち時間の後、手順 1 で指定したユーザー アカウントのいずれかを使用して、手順 1 で作成したラベルを持つチーム、Office 365 グループ、または SharePoint サイトを作成します。

4. 手順 3 の作成操作中にエラーが発生しなかった場合、テナント内のすべてのユーザーにラベルを発行します。 エラーがある場合には、[Microsoft サポート](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)へお問い合わせください。

**発行済みラベルの変更および削除:**

1 つ以上のラベル ポリシーに含まれる機密ラベルを変更または削除すると、これらのアクションによりすべてのチーム、グループ、およびサイトの作成が失敗する可能性があります。 この状況を回避するには、以下のガイダンスを使用してください。

1. ラベルを含むすべてのラベル ポリシーから、機密ラベルを削除します。

2. 48 時間待ちます。

3. 48 時間待ってからチーム、グループ、またはサイトを作成し、ラベルが表示されなくなったことを確認してください。

4. 機密ラベルが表示されていない場合は、ラベルを安全に変更または削除できます。 ラベルがまだ表示されている場合には、[Microsoft サポート](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)にお問い合わせください。

## <a name="assign-sensitivity-labels-to-office-365-groups"></a>Office 365 グループに機密ラベルを割り当てる

これで、1 つまたは複数の機密ラベルを Office 365 グループに適用する準備ができました。 手順については、Azure AD のドキュメントに戻ります。

- 「[Assign a label to a new group in Azure portal (Azure ポータルの新しいグループにラベルを割り当てる)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#assign-a-label-to-a-new-group-in-azure-portal)」

-  [Assign a label to an existing group in Azure portal (Azure ポータルの既存のグループにラベルを割り当てる)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#assign-a-label-to-an-existing-group-in-azure-portal)

-  「[Remove a label from an existing group in Azure portal (Azure ポータルの既存のグループからラベルを削除する)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#remove-a-label-from-an-existing-group-in-azure-portal).」

## <a name="apply-a-sensitivity-label-to-a-new-team"></a>新しいチームに機密ラベルを適用する

ユーザーは、Microsoft Teams で新しいチームを作成する際に機密ラベルを選択できます。 ユーザーが機密レベルを選択すると、必要に応じてプライバシー設定が変更されます。 ラベルに対し選択した外部ユーザーのアクセス設定に応じて、ユーザーは組織外のユーザーをチームに追加することができたり、できなかったりします。

[Teams の機密ラベルの詳細について](https://docs.microsoft.com/microsoftteams/sensitivity-labels)

![新しいチームを作成する際のプライバシー設定](../media/privacy-setting-new-team.png)

チームを作成すると、すべてのチャネルの右上隅に機密ラベルが表示されます。

![チームに表示される機密ラベル](../media/privacy-setting-teams.png)

このサービスは、Office 365 グループおよび接続された SharePoint チーム サイトに対して同じ機密ラベルを自動的に適用します。

## <a name="apply-a-sensitivity-label-to-a-new-group-in-outlook-on-the-web"></a>Outlook on the web の新しいグループに機密ラベルを適用する

Outlook on the web では、新しいグループを作成するときに、公開されたラベルの [**機密**] オプションを選択または変更できます。

![グループを作成し、[機密] 下でオプションを選択する](../media/sensitivity-label-new-group.png)

## <a name="apply-a-sensitivity-label-to-a-new-site"></a>新しいサイトに機密ラベルを適用する

管理者およびエンド ユーザーは、[最新のチーム サイトやコミュニケーション サイトを作成する](/sharepoint/create-site-collection)際に機密ラベルを選択できます。

ユーザーが最新のチームおよびコミュニケーション サイトを作成すると、規定で機密ラベルがすでに選択されています。 ユーザーは [ヘルプ] アイコンを選択し、ラベルの詳細を確認できます。

![サイトを作成し、[機密] 下でオプションを選択する](../media/sensitivity-label-new-communication-site.png)

ユーザーがサイトを参照すると、ラベルの名前および適用されているポリシーが表示されます。

![機密ラベルが適用されているサイト](../media/sensitivity-label-site.png)

## <a name="view-sensitivity-labels-in-the-sharepoint-admin-center"></a>SharePoint 管理センターで機密ラベルを表示する

適用された機密ラベルを表示するには、新しい SharePoint 管理センターの [**アクティブなサイト**] ページを使用します。 最初に、[**機密**] 列を追加する必要がある場合があります。

![[アクティブなサイト] ページの [機密] 列](../media/manage-site-sensitivity-labels.png)

[新しい SharePoint 管理センターでのサイト管理の詳細をご覧ください](/sharepoint/manage-sites-in-new-admin-center)。

## <a name="change-site-and-group-settings-for-a-label"></a>ラベル向けのサイトとグループの設定を変更する

ラベルのサイトとグループの設定を変更するたびに、チーム、サイト、グループが新しい設定を使用できるように、次の PowerShell コマンドを実行する必要があります。 ベスト プラクティスとして、ラベルを複数のチーム、グループ、またはサイトに適用した後にラベルのサイトとグループの設定を変更しないようにします。

1. 次のコマンドを実行して、Office 365 セキュリティ/コンプライアンス センターの PowerShell に接続し、機密ラベルとそれらの GUID のリストを取得します。
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Authentication Basic -AllowRedirection -Credential $UserCredential
    Import-PSSession $Session
    Get-Label |ft Name, Guid
    ```

2. 変更を行ったラベルの GUID をメモします。

3. 次に、Exchange Online PowerShell に接続して、Get-UnifiedGroup コマンドレットを実行します。GUID 例の "e48058ea-98e8-4940-8db0-ba1310fd955e" の代わりにラベルの GUID を指定します。 
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session
    $Groups= Get-UnifiedGroup | Where {$_.SensitivityLabel  -eq "e48058ea-98e8-4940-8db0-ba1310fd955e"}
    ```

4. 各グループについて、GUID 例の "e48058ea-98e8-4940-8db0-ba1310fd955e" の代わりにラベルの GUID を指定して機密ラベルを再適用します。
    
    ```powershell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "e48058ea-98e8-4940-8db0-ba1310fd955e"}
    ```

## <a name="support-for-the-sensitivity-labels"></a>機密ラベルのサポート

次のアプリとサービスで、サイトとグループの設定用に構成した機密ラベルを使用できます。

- SharePoint Online
- Teams
- Outlook on the web
- SharePoint 管理センター
- Azure AD 管理センター

サイトおよびグループの設定用に構成した機密ラベルを現在使用できない他のアプリとサービスには、次のものがあります。

- Outlook for the Mac
- Outlook モバイル
- Outlook デスクトップ for Windows
- Forms
- Dynamics 365
- Yammer
- Stream
- Planner
- Project
- PowerBI
- Teams 管理センター
- Microsoft 365 管理センター
- Exchange 管理センター


## <a name="classic-azure-ad-site-classification"></a>従来の Azure AD サイト分類

このプレビューを有効にすると、Office 365 は新しいグループおよび SharePoint サイト向けに古い分類をサポートしなくなります。 ただし、既存のグループおよびサイトには、機密ラベルを使用するように変換しない限り、古い分類が引き続き表示されます。 古い分類には、おそらく Azure AD PowerShell または PnP コア ライブラリを介して設定した、`ClassificationList`設定用の値を定義した "モダンな" サイト分類が含まれています。

たとえば、PowerShell の場合には以下のようになります。

```powershell
   ($setting["ClassificationList"])
```

古い分類方法の詳細については、「[SharePoint の "モダン" サイトの分類](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification)」を参照してください。

古い分類を機密ラベルに変換するには、次のいずれかの操作を行います。

- 既存のラベルを使用: 既に公開されている既存の機密ラベルを編集して、サイトおよびグループに必要なラベル設定を指定します。

- 新しいラベルの作成: 既存の分類と同じ名前を持つ新しい機密ラベルを作成および公開して、サイトおよびグループに必要なラベル設定を指定します。

その後で以下の手順に従います。 

1. PowerShell を使用して、既存の Office 365 グループおよび SharePoint サイトに名前のマッピングを使用して機密ラベルを適用します。 手順については、次のセクションを参照してください。

2. 既存のグループおよびサイトから古い分類を削除します。

機密ラベルをまだサポートしていないアプリやサービスでユーザーが新しいグループを作成できないようにすることはできませんが、定期的な PowerShell スクリプトを実行して、ユーザーが古い分類で作成した新しいグループを探し、機密ラベルを使用するようにそれらを変換することができます。 

#### <a name="use-powershell-to-convert-classifications-for-office-365-groups-to-sensitivity-labels"></a>PowerShell を使用して、Office 365 グループの分類を機密ラベルに変換する

1. SharePoint Online 管理シェルのバージョン 16.0.19418.12000 以降を実行していることを確認してください。 既に最新バージョンを使用している場合は、手順 4 に進みます。

2. PowerShell ギャラリーから以前のバージョンの SharePoint Online 管理シェルをインストールした場合、次のコマンドレットを実行してモジュールを更新できます。
    
    ```PowerShell
    Update-Module -Name Microsoft.Online.SharePoint.PowerShell
    ```

3. Microsoft ダウンロード センターから以前のバージョンの SharePoint Online 管理シェルをインストールした場合は、[**プログラムの追加と削除**] に移動して、SharePoint Online 管理シェルをアンインストールします。  次に、[ダウンロード センター](https://go.microsoft.com/fwlink/p/?LinkId=255251) から最新の SharePoint Online 管理シェルをインストールします。

4. Office 365 のグローバル管理者または SharePoint 管理者権限を持つ職場または学校のアカウントを使用して、SharePoint Online 管理シェルへと接続します。 方法の詳細については、「[SharePoint Online 管理シェルの使用を開始する](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)」を参照してください。

5. 以下のコマンドを実行し、機密ラベルおよびその GUID のリストを取得します。

    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Authentication Basic -AllowRedirection -Credential $UserCredential
    Import-PSSession $Session
    Get-Label |ft Name, Guid  
    ```

6. Office 365 グループに適用する機密ラベルの GUID をメモします。

7. 次のコマンドを例として使用して、現在 "一般" の分類を持つグループのリストを取得します。

   ```PowerShell
   $Groups= Get-UnifiedGroup | Where {$_.classification -eq "General"}
   ```

6. グループごとに、新しい機密ラベル GUID を追加します。 例:

    ```PowerShell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "457fa763-7c59-461c-b402-ad1ac6b703cc"}
    ```

## <a name="auditing-sensitivity-label-activities"></a>機密ラベル アクティビティの監査

誰かが機密ラベルで保護されているサイトにドキュメントをアップロードし、そのドキュメントの機密ラベルが、サイトに適用されている機密ラベルよりも[優先度が高く](sensitivity-labels.md#label-priority-order-matters)なっている場合、このアクションはブロックされません。 たとえば、「**一般**」ラベルを SharePoint サイトに適用し、誰かがこのサイトに「**社外秘**」というラベルの付けられたドキュメントをアップロードしたとします。 優先度の高い機密ラベルは、優先順位の低いコンテンツよりも機密性の高いコンテンツを識別するため、この状況はセキュリティ上の懸念になる可能性があります。

アクションはブロックされませんが、監査されるため、ラベルの優先度にこのようなずれが見られるドキュメントを特定し、必要に応じてアクションを実行できます。 たとえば、アップロードされたドキュメントをサイトから削除または移動します。 

ドキュメントの機密ラベルが、サイトに適用されている機密ラベルよりも優先度が低い場合、セキュリティ上の懸念にはなりません。 たとえば、「**一般**」というラベルの付いたドキュメントが、「**社外秘**」というラベルの付いたサイトにアップロードされている場合です。 このシナリオでは、監査イベントは生成されません。

このイベントの監査ログを検索するには、[**ファイルとページのアクティビティ**] カテゴリから [**検出されたドキュメントの機密度の不一致**] を探します。 

誰かがサイトまたはグループに対して機密ラベルの追加または削除を行うと、これらのアクティビティも監査されます。 これらのイベントは、[[機密ラベル アクティビティ](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities)] カテゴリにあります。 

監査ログを検索する手順については、「[セキュリティ/コンプライアンス センターで監査ログを検索する](search-the-audit-log-in-security-and-compliance.md)」を参照してください。

## <a name="troubleshoot-sensitivity-label-deployment"></a>機密ラベルの展開のトラブルシューティング

Microsoft Teams、Office 365 グループ、および SharePoint サイトの機密ラベルに問題がありますか ? 以下を確認してください。

### <a name="labels-not-visible-after-publishing"></a>発行後にラベルが表示されない
これらの設定を有効にした後、または機密ラベルの説明を変更した後でチームまたは Office 365 グループを作成する際に問題が発生した場合には、ラベルの変更を保存してから数時間待ち、その後チームまたはグループの作成を再試行してみてください。 詳細については、「[Schedule roll-out after you create or change a sensitivity label (機密ラベルを作成または変更した後にロールアウトをスケジュールする)](sensitivity-labels-sharepoint-onedrive-files.md#schedule-roll-out-after-you-create-or-change-a-sensitivity-label)」を参照してください。

それでも SharePoint Online から新しい機密ラベルを表示できない場合には、[Microsoft サポート](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)へお問い合わせください。

### <a name="team-group-or-sharepoint-site-creation-errors"></a>チーム、グループ、または SharePoint サイトの作成エラー
パブリック プレビュー中に作成エラーが発生した場合、2 つのオプションがあります。

- どのユーザーに対しても機密ラベルが必須ではないことを確認してください。

- [[Enable sensitivity label support in PowerShell (PowerShell で機密ラベルのサポートを有効にする)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#enable-sensitivity-label-support-in-powershell)] と同じ手順を使用することで、Microsoft Teams、Office 365 グループ、および SharePoint サイトの機密ラベルをオフにできます。 ただし、プレビューを無効にするには、手順 5 で `$setting["EnableMIPLabels"] = "False"` を使用して機能を無効にします。

