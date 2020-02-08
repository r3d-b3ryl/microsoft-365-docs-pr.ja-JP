---
title: Microsoft Teams、Office 365 グループ、SharePoint サイトで機密ラベルを使用する (パブリック プレビュー)
f1.keywords:
- NOCSH
ms.author: krowley
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
ms.openlocfilehash: 7fd19d9d8f84bd6463d61aec68dbd86c4fc627c0
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601564"
---
# <a name="use-sensitivity-labels-with-microsoft-teams-office-365-groups-and-sharepoint-sites-public-preview"></a>Microsoft Teams、Office 365 グループ、SharePoint サイトで機密ラベルを使用する (パブリック プレビュー)

[Microsoft 365 コンプライアンス センター](https://protection.office.com/)で機密ラベルを作成する場合、Microsoft Teams、Office 365 グループ、SharePoint サイトへと適用できるようになりました。 ポリシーをラベルに関連付けることで、以下を制御できます。

- パブリック/プライベート設定
- ゲスト アクセス
- 非管理対象デバイスからのアクセス

ラベルをチームまたはグループに適用すると、ラベルは接続された SharePoint チーム サイトに自動的に適用され、その逆の場合にも同様に適用されます。

また、SharePoint および OneDrive で Office ファイルの機密ラベルを有効にできるようになりました。 詳細については、「[SharePoint および OneDrive で Office ファイルの機密度ラベルを有効にする (パブリック プレビュー)](sensitivity-labels-sharepoint-onedrive-files.md)」を参照してください。

## <a name="about-the-public-preview-for-microsoft-teams-office-365-groups-and-sharepoint-sites"></a>Microsoft Teams、Office 365 グループ、および SharePoint サイトのパブリック プレビューについて

Microsoft Teams、Office 365 グループ、および SharePoint サイト向けの機密ラベルは徐々にテナントへと展開され、最終リリース前に変更される可能性があります。

このパブリック プレビューは、Office 365 コンテンツ配信ネットワーク (CDN) では機能しません。

## <a name="overview"></a>概要

機密ラベルを発行すると、Office 365 全体のユーザーが同じラベルのリストにアクセスできます。

これらの画像は以下について示しています。

- SharePoint から新しいチーム サイトを作成する際のリストの表示内容

- Word でリストを表示する場合

以下に例を示します。

![SharePoint でチーム サイトを作成するときの機密ラベル](media/sensitivity-label-new-team-site.png)

![Word デスクトップ アプリに表示される機密ラベル](media/sensitivity-label-word.png)

## <a name="enable-this-preview"></a>このプレビューを有効にする

Microsoft Teams、Office 365 グループ、および SharePoint サイトで機密ラベルのこのプレビューを有効にするには、[Azure Active Directory PowerShell for Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) (モジュール名 **AzureADPreview**) を使用する必要があります。

- 以前に Azure AD PowerShell モジュールのいかなるバージョンもインストールしたことがない場合には、「[Installing the Azure AD Module (Azure AD モジュールのインストール)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module)」を参照し、指示に従ってパブリック プレビュー リリースをインストールしてください。

- Azure AD PowerShell モジュール (AzureAD) の 2.0 一般提供バージョンをインストールしている場合には、PowerShell セッションで `Uninstall-Module AzureAD` を実行してアンインストールし、`Install-Module AzureADPreview` を実行してプレビュー バージョンをインストールする必要があります。

- プレビュー バージョンを既にインストールしている場合には、`Install-Module AzureADPreview`を実行しそれがこのモジュールの最新バージョンであることを確認します。

これで Microsoft Teams、Office 365 グループ、および SharePoint サイトで機密ラベルのプレビューを有効にする準備ができました。

1. PowerShell セッションで、グローバル管理者特権を持つ職場または学校のアカウントを使用して Azure Active Directory に接続します。 たとえば、以下を実行します。
    
    ```powershell
    Connect-AzureAD
    ````
    
    詳しい手順については、「[Azure AD への接続](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#connect-to-azure-ad)」を参照してください。

2. 以下のコマンドを実行します。
    
    ```powershell
    $setting=(Get-AzureADDirectorySetting | where -Property DisplayName -Value "Group.Unified" -EQ)
    if ($setting -eq $null)
    {
    $template = Get-AzureADDirectorySettingTemplate -Id 62375ab9-6b52-47ed-826b-58e47e0e304b
    $setting = $template.CreateDirectorySetting()
    $setting["EnableMIPLabels"] = "True"
    New-AzureADDirectorySetting -DirectorySetting $setting
    }
    else
    {
    $setting["EnableMIPLabels"] = "True"
    Set-AzureADDirectorySetting -Id $setting.Id -DirectorySetting $setting
    }
    ```
    
    > [!NOTE]
    > このプレビューを有効にすると、Office 365 は新しいグループおよび SharePoint サイトに古い分類を使用しなくなります。 [Azure AD サイト分類](/sharepoint/dev/solution-guidance/modern-experience-site-classification) ($setting["ClassificationList"]) を使用した場合には、既存のグループおよびサイトには古い分類が引き続き表示されます。 新しい分類を表示するには、それらを変換します。 変換する方法については、「[If you used classic Azure AD site classification (従来の Azure AD サイト分類を使用した場合)](#if-you-used-classic-azure-ad-site-classification)」を参照してください。 

3. 同じ PowerShell セッションで、グローバル管理者特権を持つ職場または学校のアカウントを使用して、セキュリティ/コンプライアンス センターに接続します。 手順については、「[Office 365 セキュリティ/コンプライアンス センターの PowerShell への接続](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)」を参照してください。

4. ラベルを Office 365 グループで使用できるように、次のコマンドを実行してラベルを Azure AD に同期させます。
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    Execute-AzureAdLabelSync
    ```
## <a name="set-site-and-group-settings-when-you-create-or-edit-sensitivity-labels"></a>機密ラベルを作成または編集する際に、サイトおよびグループの設定を行う

プレビューを有効にしたら、以下の手順を使用して機密ラベルを作成または編集します。 すでに定義されたラベルがある場合でも、新しい機密ラベルをサイトおよびグループで機能させるにはこれらの手順を完了させる必要があります。 これらの設定変更は、同期に最大 24 時間かかる場合があります。

1. Microsoft 365 コンプライアンス センターで [**分類**] >  [**機密ラベル**] の順に選択します。

2. [**ラベルを作成**] を選択します。 ラベルが既にある場合には、次の手順へと進みます。

3. 必要なオプションを選択し、[**サイトとグループの設定**] タブで以下を選択します。
    
    - プライバシー (パブリック/プライベート): プライベートとは、組織内の承認されたメンバーのみがグループ内のコンテンツを閲覧できることを意味します。 組織内の他のユーザーは、グループの内容を見ることができません。 [詳細情報](https://support.office.com/article/36236e39-26d3-420b-b0ac-8072d2d2bedc)
    - ゲストアクセス: ゲストをグループに追加できるかどうかを制御できます。 [Office 365 グループでのゲスト アクセスの管理について](/office365/admin/create-groups/manage-guest-access-in-groups)
    - 管理されていないデバイス: この設定により、ハイブリッド AD に参加していないデバイスまたは Intune に準拠していないデバイスからの SharePoint コンテンツへのアクセスをブロックまたは制限することができます。 非管理対象デバイスを選択した場合、Azure AD にアクセスしてポリシーのセットアップを完了させる必要があります。 詳細については、「[非管理対象デバイスからのアクセスを制御する](/sharepoint/control-access-from-unmanaged-devices)」を参照してください。
    
    ![[サイトとグループの設定] タブ](media/edit-sensitivity-label-site-group.png)

> [!IMPORTANT]
> チーム、グループ、またはサイトにラベルを適用すると、サイトとグループの設定のみが有効になります。 暗号化やコンテンツ マーキングなどのその他の設定は、チーム、グループ、またはサイト内のすべてのコンテンツに適用されるわけではありません。
> 
> 同様に、ラベルを作成しサイトとグループの設定をオンにしない場合には、ユーザーがチーム、グループ、およびサイトを作成するときにラベルは引き続き使用できますが、いかなる設定も適用せずに分類します。

[機密ラベルの発行の詳細について](/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do)

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

## <a name="troubleshoot-sensitivity-label-deployment"></a>機密ラベルの展開のトラブルシューティング

### <a name="labels-not-visible-after-publishing"></a>発行後にラベルが表示されない
これらの設定を有効にした後、または機密ラベルの説明を変更した後でチームまたは Office 365 グループを作成する際に問題が発生した場合には、ラベルを保存し、数時間待ってからチームまたはグループの作成を再試行してみてください。 詳細については、「[Schedule roll-out after you create or change a sensitivity label (機密ラベルを作成または変更した後にロールアウトをスケジュールする)](sensitivity-labels-sharepoint-onedrive-files.md#schedule-roll-out-after-you-create-or-change-a-sensitivity-label)」を参照してください。

それでも SharePoint Online から新しい機密ラベルを表示できない場合には、[Microsoft サポート](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)へお問い合わせください。

### <a name="team-group-or-sharepoint-site-creation-errors"></a>チーム、グループ、または SharePoint サイトの作成エラー
パブリック プレビュー中に作成エラーが発生した場合、2 つのオプションがあります。

- どのユーザーに対しても機密ラベルが必須ではないことを確認してください。

- このページの [[このプレビューを有効にする](#enable-this-preview)] セクションと同じ手順を使用することで、Microsoft Teams、Office 365 グループ、および SharePoint サイトの機密ラベルをオフにできます。 ただし、プレビューを無効にするには、`$setting["EnableMIPLabels"] = "True"`行を検索し、**True** 値を **False** に変更します。

## <a name="apply-a-sensitivity-label-to-a-new-team"></a>新しいチームに機密ラベルを適用する

ユーザーは、Microsoft Teams で新しいチームを作成する際に機密ラベルを選択できます。 ユーザーが機密レベルを選択すると、必要に応じてプライバシー設定が変更されます。 ラベルに対し選択したゲスト アクセス設定に応じて、ユーザーは組織外のユーザーをチームに追加することができたり、できなかったりします。

[Teams の機密ラベルの詳細について](https://docs.microsoft.com/microsoftteams/sensitivity-labels)

![新しいチームを作成する際のプライバシー設定](media/privacy-setting-new-team.png)

チームを作成すると、すべてのチャネルの右上隅に機密ラベルが表示されます。

![チームに表示される機密ラベル](media/privacy-setting-teams.png)

このサービスは、Office 365 グループおよび接続された SharePoint チーム サイトに対して同じ機密ラベルを自動的に適用します。

## <a name="apply-a-sensitivity-label-to-a-new-group"></a>新しいグループに機密ラベルを適用する

Outlook on the web では、新しい [**機密**] ボックスに発行されたラベルが含まれています。 ユーザーが詳細を知りたい場合には、[ヘルプ] アイコンをクリックすると使用できるラベルおよび関連ポリシーに関する詳細情報が表示されます。

![グループを作成し、[機密] 下でオプションを選択する](media/sensitivity-label-new-group.png)

## <a name="apply-a-sensitivity-label-to-a-new-site"></a>新しいサイトに機密ラベルを適用する

管理者およびエンド ユーザーは、最新のチーム サイトやコミュニケーション サイトを作成する際に機密ラベルを選択できます。

[新しい SharePoint 管理センターでサイトを作成する方法について](/sharepoint/create-site-collection)

ユーザーが最新のチームおよびコミュニケーション サイトを作成すると、規定で機密ラベルがすでに選択されています。 ユーザーは [ヘルプ] アイコンを選択し、ラベルの詳細を確認できます。

![サイトを作成し、[機密] 下でオプションを選択する](media/sensitivity-label-new-communication-site.png)

ユーザーがサイトを参照すると、ラベルの名前および適用されているポリシーが表示されます。

![機密ラベルが適用されているサイト](media/sensitivity-label-site.png)

## <a name="manage-sensitivity-labels-in-the-sharepoint-admin-center"></a>SharePoint 管理センターで機密ラベルを管理する

ラベルを表示および編集するには、新しい SharePoint 管理センターの [アクティブなサイト] ページを使用します。

![[アクティブなサイト] ページの [機密] 列](media/manage-site-sensitivity-labels.png)

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

## <a name="support-for-the-new-sensitivity-labels"></a>新しい機密ラベルのサポート

以下のアプリおよびサービスは、このプレビューの機密ラベルをサポートしています:

- Microsoft 365 コンプライアンス センター
- SharePoint
- Outlook on the web
- Teams
- SharePoint 管理センター
- Azure AD 管理センター

以下のアプリおよびサービスを使用して、新しい機密ラベルを用いた Office 365 グループを作成することはできません。

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

## <a name="if-you-used-classic-azure-ad-site-classification"></a>従来の Azure AD サイト分類を使用した場合

このプレビューを有効にすると、Office 365 は新しいグループおよび SharePoint サイト向けに古い分類をサポートしなくなります。 ただし、既存のグループおよびサイトには変換しない限り古い分類が引き続き表示されます。 古い分類には、おそらく Azure AD PowerShell または PnP コア ライブラリを介して設定した、`ClassificationList`設定用の値を定義した "モダンな" サイト分類が含まれています。

たとえば、PowerShell の場合には以下のようになります。

```powershell
   ($setting["ClassificationList"])
```

古い分類方法の詳細については、「[SharePoint の "モダン" サイトの分類](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification)」を参照してください。

現在の展開に基づき、古い分類を新しい分類に変換するための 2 つのオプションがあります。

### <a name="if-you-never-used-sensitivity-labels-unified-microsoft-information-protection-labels-for-files-and-email"></a>ファイルおよびメールに機密ラベル (統合 Microsoft Information Protection ラベル) を使用したことがない場合

以下のことをお勧めします。

1. Microsoft 365 コンプライアンス センターで、既存の分類と同じ名前の新しい機密ラベルを作成します。
2. PowerShell を使用して、既存の Office 365 グループおよび名前のマッピングを使用する SharePoint サイトに新しいラベルを適用します。
3. 古い分類を削除します。

新しい機密ラベルをサポートするアプリおよびサービスは、それらを表示します。 新しいラベルを使用して新しいチーム、グループ、およびサイトを作成します。 ユーザーは引き続き、新しいラベルをサポートしていないアプリおよびサービスからグループを作成できます。 ただし、ユーザーはこれらのグループにラベルを適用できません。 PowerShell を使用して、これらのグループに新しい機密ラベルを適用します。

古い分類は保持可能です。ただし、PowerShell を使用してこれらのグループに新しい機密ラベルを適用することを強くお勧めします。

新しい機密ラベルをサポートするアプリおよびサービスは、新しいラベルで作成されます。 ユーザーが新しいラベルをサポートしないアプリおよびサービスからグループを作成する場合、ユーザーは分類を選択できます。

### <a name="if-you-use-sensitivity-labels-unified-microsoft-information-protection-labels-for-files-and-email"></a>ファイルおよびメールに機密ラベル (統合 Microsoft Information Protection ラベル) を使用する場合

このプレビューを有効にしたら Microsoft 365 コンプライアンス センター内の各ラベルに移動し、サイトおよびグループに必要なポリシーを適用します。 ユーザーは、サイトおよびグループで利用可能な既存のラベルの表示を開始します。

### <a name="prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups"></a>Office 365 グループのラベルを付け直す前に、SharePoint Online 管理シェルを準備する

新しいラベルを適用する前に、最新の SharePoint Online 管理シェルを実行していることを確認してください。 既に最新バージョンをお持ちの場合には、先に進み [Office 365 グループに新しい機密ラベルを付け直してください](#relabel-office-365-groups-with-new-sensitivity-labels)。

プレビューのために SharePoint Online 管理シェルを準備するには:

1. SharePoint Online 管理シェルの以前のバージョンがインストールされている場合には、[**プログラムの追加と削除**] に移動して “SharePoint Online 管理シェル“ をアンインストールします。

2. Web ブラウザーで [ダウンロード センター] ページへと移動し、[最新の SharePoint Online 管理シェルをダウンロードします](https://go.microsoft.com/fwlink/p/?LinkId=255251)。

3. 言語を選択し、[**ダウンロード**] をクリックします。

4. x64 および x86 の .msi ファイルのいずれかを選択します。 Windows の 64 ビット版を実行している場合には x64 ファイルを、32 ビット版を実行している場合には x86 ファイルをダウンロードします。 不明な場合には、「[実行している Windows オペレーティング システムの確認方法](https://support.microsoft.com/help/13443/windows-which-operating-system)」を参照してください。

5. ファイルをダウンロードしたら、そのファイルを実行し、セットアップ ウィザードの手順に従います。

### <a name="relabel-office-365-groups-with-new-sensitivity-labels"></a>新しい機密ラベルで Office 365 グループにラベルを付け直します

1. SharePoint Online 管理シェルの最新バージョンを使用していることを確認してください。 手順については、「[Office 365 グループのラベルを付け直す前に、SharePoint Online 管理シェルを準備する](#prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups)」を参照してください。

2. Office 365 のグローバル管理者または SharePoint 管理者権限を持つ職場または学校のアカウントを使用して、SharePoint Online 管理シェルへと接続します。 方法の詳細については、「[SharePoint Online 管理シェルの使用を開始する](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)」を参照してください。

3. 以下のコマンドを実行し、機密ラベルおよびその GUID のリストを取得します。

    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Authentication Basic -AllowRedirection -Credential $UserCredential
    Import-PSSession $Session
    Get-Label |ft Name, Guid  
    ```

4. 上書きするラベルの GUID をメモします。 たとえば、"一般" ラベル。

5. 以下のコマンドを使用して、"一般" 分類を持つグループのリストを取得します。 このコマンドを実行すると Exchange Online PowerShell へと接続し、Get-UnifiedGroup コマンドレットを実行します。

   ```PowerShell
   Set-ExecutionPolicy RemoteSigned
   $UserCredential = Get-Credential
   $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
   Import-PSSession $Session
   $Groups= Get-UnifiedGroup | Where {$_.classification -eq "General"}
   ```

6. グループごとに、新しい機密ラベル GUID を追加します。

    ```PowerShell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "457fa763-7c59-461c-b402-ad1ac6b703cc"}
    ```
