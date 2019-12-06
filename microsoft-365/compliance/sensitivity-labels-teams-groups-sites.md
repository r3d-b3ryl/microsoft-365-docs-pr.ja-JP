---
title: Microsoft Teams、Office 365 グループ、SharePoint サイトで機密ラベルを使用する (パブリック プレビュー)
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/05/2019
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: ラベルは、Microsoft Teams、Office 365 グループ、および SharePoint サイトに適用できます。
ms.openlocfilehash: e69968ad5939069ca8ae1611f3bbdc674f9dd7de
ms.sourcegitcommit: 2468bcb01625f97a322459814d81b9faad717859
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "39871253"
---
# <a name="use-sensitivity-labels-with-microsoft-teams-office-365-groups-and-sharepoint-sites-public-preview"></a>Microsoft Teams、Office 365 グループ、SharePoint サイトで機密ラベルを使用する (パブリック プレビュー)

[Microsoft 365 コンプライアンスセンター](https://protection.office.com/)で機密ラベルを作成すると、それらを microsoft Teams、Office 365 グループ、および SharePoint サイトに適用できるようになります。 ポリシーをラベルに関連付けて、次の操作を制御できます。

- パブリック/プライベート設定
- ゲスト アクセス
- 非管理対象デバイスからのアクセス

チームまたはグループにラベルを適用すると、ラベルは接続された SharePoint チームサイトに自動的に適用され、その他の方法も使用されます。

これで、SharePoint および OneDrive で Office ファイルの機密ラベルを有効にすることもできます。 [詳細については、こちらを参照してください](sensitivity-labels-sharepoint-onedrive-files.md)。

## <a name="about-the-public-preview-for-microsoft-teams-office-365-groups-and-sharepoint-sites"></a>Microsoft Teams、Office 365 グループ、および SharePoint サイトのパブリックプレビューについて

Microsoft Teams、Office 365 グループ、および SharePoint サイトの機密ラベルは、テナントに段階的にロールアウトされるため、最終リリースまでに変更される可能性があります。

パブリックプレビューは、Office 365 コンテンツ配信ネットワーク (CDNs) では機能しません。

## <a name="overview"></a>概要

機密ラベルを発行すると、Office 365 のユーザーは、同じラベルリストにアクセスできるようになります。

次の画像が表示:

- SharePoint から新しいチームサイトを作成するときのリストの表示方法

- Word でリストを表示する場合

![SharePoint からチームサイトを作成するときの機密ラベル](media/sensitivity-label-new-team-site.png)

![Word デスクトップアプリに表示される機密ラベル](media/sensitivity-label-word.png)

## <a name="enable-this-preview-by-using-azure-powershell"></a>Azure PowerShell を使用してこのプレビューを有効にする

1. Azure PowerShell を使用して、グローバル管理者として Azure にサインインします。 手順については、「 [Azure PowerShell を使用](/powershell/azure/authenticate-azureps)してサインインする」を参照してください。

2. 次のコマンドを実行します。

```powershell
  Connect-AzureAD
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

このプレビューを有効にした場合、Office 365 は新しいグループおよび SharePoint サイトに古い分類を使用しなくなりました。 [AZURE AD サイトの分類](/sharepoint/dev/solution-guidance/modern-experience-site-classification)($setting ["ClassificationList"]) を使用した場合は、既存のグループとサイトでも古い分類が表示されます。 新しい分類を表示するには、変換します。 変換方法の詳細については、「[従来の AZURE AD サイトの分類を使用したかどうか](#if-you-used-classic-azure-ad-site-classification)」を参照してください。 

## <a name="set-site-and-group-settings-when-you-create-or-edit-sensitivity-labels"></a>機密ラベルを作成または編集するときにサイトとグループの設定を設定する

プレビューを有効にした後、次の手順に従って、機密ラベルを作成または編集します。 既にラベルが定義されている場合でも、新しい機密ラベルをサイトやグループで使用できるようにするには、次の手順を実行する必要があります。 これらの設定を変更すると、同期が最大24時間かかる場合があります。

1. Microsoft 365 コンプライアンスセンターで、[**分類** > **機密ラベル**] を選択します。

2. [**ラベルの作成**] を選択します。 既にラベルを持っている場合は、次の手順に進みます。

3. 必要なオプションを選択し、[**サイトとグループの設定**] タブで以下を選択します。

    - Privacy (パブリック/プライベート): Private は、組織内の承認されたメンバーのみがグループ内の内容を表示できることを意味します。 組織内の他のすべてのユーザーはグループの内容を表示できません。 [詳細情報](https://support.office.com/article/36236e39-26d3-420b-b0ac-8072d2d2bedc)
    - ゲストアクセス: グループにゲストを追加できるかどうかを制御できます。 [Office 365 グループでのゲストアクセスの管理について](/office365/admin/create-groups/manage-guest-access-in-groups)
    - [管理されていないデバイス]: この設定を使用すると、ハイブリッド AD に参加していない、または Intune で準拠していないデバイスから SharePoint コンテンツへのアクセスをブロックまたは制限できます 管理されていないデバイスを選択する場合は、ポリシーの設定を完了するために Azure AD に移動する必要があります。 詳細については、「[非管理対象デバイスからのアクセスの制御](/sharepoint/control-access-from-unmanaged-devices)」を参照してください。

![[サイトとグループの設定] タブ](media/edit-sensitivity-label-site-group.png)

> [!IMPORTANT]
> チーム、グループ、またはサイトにラベルを適用すると、サイトおよびグループの設定のみが有効になります。 暗号化やコンテンツマーキングなどのその他の設定は、チーム、グループ、またはサイト内のすべてのコンテンツに適用されません。 同様に、ラベルを作成してサイトとグループの設定を有効にしない場合でも、ユーザーがチーム、グループ、およびサイトを作成するときに、ラベルは使用できますが、ユーザーがそれを適用しても何も実行しません。

[機密ラベルを発行する方法について説明します。](/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do)

## <a name="troubleshoot-sensitivity-label-deployment"></a>機密ラベルの展開のトラブルシューティング

これらの設定を有効にした後、または機密ラベルの説明を変更した後に Teams または Office 365 グループを作成したときに問題が発生した場合は、ラベルを保存してから数時間待ってから、チームまたは Office 365 グループをもう一度作成してみてください。 詳細については、「[機密ラベルを作成または変更した後のロールアウトをスケジュールする](sensitivity-labels-sharepoint-onedrive-files.md#schedule-roll-out-after-you-create-or-change-a-sensitivity-label)」を参照してください。

それでも SharePoint Online から新しい機密ラベルを表示できない場合は、直ちに Microsoft サポートにお問い合わせください。

## <a name="apply-a-sensitivity-label-to-a-new-team"></a>新しいチームに機密ラベルを適用する

ユーザーは、Microsoft Teams で新しいチームを作成するときに機密ラベルを選択できます。 機密レベルを選択すると、必要に応じてプライバシー設定が変更されます。 ラベルに対して選択したゲストアクセス設定に応じて、ユーザーは組織外のユーザーをチームに追加できます。

![新しいチームを作成するときのプライバシー設定](media/privacy-setting-new-team.png)

チームを作成すると、すべてのチャネルの右上隅に [機密] ラベルが表示されます。

![機密ラベルがチームに表示されます。](media/privacy-setting-teams.png)

サービスは、Office 365 グループと接続された SharePoint チームサイトに同じ機密ラベルを自動的に適用します。

## <a name="apply-a-sensitivity-label-to-a-new-group"></a>新しいグループに機密ラベルを適用する

Web 上の Outlook の場合、[新しい**秘密度**] ボックスには、発行済みのラベルが表示されます。 ユーザーが詳細情報を必要とする場合は、ヘルプアイコンをクリックすると、使用可能なラベルと関連付けられているポリシーの詳細を確認できます。

![グループを作成し、[感度] の下でオプションを選択する](media/sensitivity-label-new-group.png)

## <a name="apply-a-sensitivity-label-to-a-new-site"></a>新しいサイトに機密ラベルを適用する

管理者とエンドユーザーは、モダンチームサイトとコミュニケーションサイトを作成するときに機密ラベルを選択できます。

[新しい SharePoint 管理センターでサイトを作成する方法について説明します。](/sharepoint/create-site-collection)

ユーザーがモダンチームおよびコミュニケーションサイトを作成する場合、既定では、既に機密ラベルが選択されています。 ユーザーは、[ヘルプ] アイコンを選択して、ラベルの詳細を参照できます。

![サイトを作成し、[秘密度] の下でオプションを選択する](media/sensitivity-label-new-communication-site.png)

ユーザーがサイトを参照すると、ラベルの名前と適用されたポリシーが表示されます。

![機密ラベルが適用されたサイト](media/sensitivity-label-site.png)

## <a name="manage-sensitivity-labels-in-the-sharepoint-admin-center"></a>SharePoint 管理センターで機密ラベルを管理する

ラベルを表示および編集するには、新しい SharePoint 管理センターの [アクティブなサイト] ページを使用します。

![[アクティブなサイト] ページの [秘密度] 列](media/manage-site-sensitivity-labels.png)

[新しい SharePoint 管理センターでのサイト管理の詳細については、「」を参照して](/sharepoint/manage-sites-in-new-admin-center)ください。

## <a name="change-site-and-group-settings-for-a-label"></a>ラベルのサイトとグループの設定を変更する

ベストプラクティスとして、複数のチーム、グループ、またはサイトにラベルを適用した後に設定を変更しないでください。 変更を加える必要がある場合は、Azure AD PowerShell スクリプトを使用して更新プログラムを手動で適用する必要があります。 この方法により、既存のすべてのチーム、サイト、およびグループで新しい設定が適用されます。

## <a name="support-for-the-new-sensitivity-labels"></a>新しい機密ラベルのサポート

このプレビューでは、次のアプリとサービスが機密ラベルをサポートしています。

- Microsoft 365 コンプライアンス センター
- SharePoint
- Outlook on the web
- Teams
- SharePoint 管理センター
- Azure AD 管理センター

次のアプリとサービスを使用して、新しい機密ラベルを使用して Office 365 グループを作成することはできません。

- Mac 用の Outlook
- Outlook mobile  
- Windows 用 Outlook デスクトップ
- フォーム  
- Dynamics 365  
- Yammer  
- Stream  
- Planner  
- Project  
- PowerBI  
- Teams 管理センター  
- Microsoft 365 管理センター  
- Exchange 管理センター

## <a name="if-you-used-classic-azure-ad-site-classification"></a>従来の Azure AD サイトの分類を使用している場合

このプレビューを有効にした場合、Office 365 は新しいグループと SharePoint サイトの古い分類をサポートしなくなりました。 ただし、既存のグループやサイトでは、変換しない限り古い分類が表示されます。 古い分類には、設定に対し`ClassificationList`て定義された "モダン" サイト分類があります。これには、Azure AD PowerShell または PnP コアライブラリを使用して設定します。

たとえば、PowerShell で次のように入力します。

```powershell
   ($setting["ClassificationList"])
```

古い分類法の詳細については、「 [SharePoint "モダン" サイトの分類](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification)」を参照してください。

現在の展開に基づいて、古い分類を新しい分類に変換するための2つのオプションがあります。

### <a name="if-you-never-used-sensitivity-labels-unified-microsoft-information-protection-labels-for-files-and-email"></a>ファイルと電子メールの機密ラベル (統合 Microsoft Information Protection ラベル) を使用していない場合

次のことをお勧めします。

1. Microsoft 365 コンプライアンスセンターで、既存の分類と同じ名前を持つ新しい機密ラベルを作成します。
2. PowerShell を使用して、名前のマッピングを使用して、既存の Office 365 グループおよび SharePoint サイトに新しいラベルを適用します。
3. 古い分類を削除します。

新しい機密ラベルをサポートするアプリとサービスが表示されます。 新しいチーム、グループ、およびサイトを新しいラベルで作成します。 ユーザーは、新しいラベルをサポートしていないアプリやサービスからグループを作成することもできます。 ただし、ユーザーはこれらのグループにラベルを適用することはできません。 PowerShell を使用して、これらのグループに新しい機密ラベルを適用します。

古い分類を維持することができます。ただし、これらのグループに新しい機密ラベルを適用するには、PowerShell を使用することを強くお勧めします。

新しい機密ラベルをサポートするアプリとサービスは、新しいラベルを使用して作成されます。 ユーザーが新しいラベルをサポートしていないアプリやサービスからグループを作成する場合は、分類を選択できます。

### <a name="if-you-use-sensitivity-labels-unified-microsoft-information-protection-labels-for-files-and-email"></a>ファイルと電子メールに機密ラベル (統合 Microsoft Information Protection ラベル) を使用する場合

このプレビューを有効にしたら、Microsoft 365 コンプライアンスセンターの各ラベルに移動し、サイトとグループに必要なポリシーを適用します。 ユーザーは、サイトおよびグループで使用可能な既存のラベルを表示し始めます。

### <a name="prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups"></a>Office 365 グループのラベルを書き換える前に SharePoint Online 管理シェルを準備する

新しいラベルを適用する前に、最新の SharePoint Online 管理シェルを実行していることを確認してください。 すでに最新バージョンをお持ちの場合は、[新しい機密ラベルを使用して Office 365 グループの](#relabel-office-365-groups-with-new-sensitivity-labels)ラベルを書き換えることができます。

プレビュー用の SharePoint Online 管理シェルを準備するには、次のようにします。

1. 以前のバージョンの SharePoint Online Management Shell をインストールした場合は、[**プログラムの追加と削除**] に移動し、"SharePoint Online Management shell" をアンインストールします。

2. Web ブラウザーで、ダウンロードセンターページに移動して、[最新の SharePoint Online 管理シェルをダウンロード](https://go.microsoft.com/fwlink/p/?LinkId=255251)します。

3. 言語を選択し、[**ダウンロード**] をクリックします。

4. X64 ファイルと x86 .msi ファイルのどちらかを選択します。 64ビット版の Windows または x86 ファイル (32 ビット版を実行している場合) を実行する場合は、x64 ファイルをダウンロードしてください。 不明な場合は、[どのバージョンの Windows オペレーティングシステムを実行](https://support.microsoft.com/help/13443/windows-which-operating-system)しているかを確認します。

5. ファイルをダウンロードした後、ファイルを実行し、セットアップウィザードの手順に従います。

### <a name="relabel-office-365-groups-with-new-sensitivity-labels"></a>新しい機密ラベルを使用して Office 365 グループのラベルを変更する

1. SharePoint Online 管理シェルの最新バージョンを使用していることを確認します。 手順については、「 [Office 365 グループのラベルを書き換える前に SharePoint Online 管理シェルを準備](#prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups)する」を参照してください。

2. Office 365 で全体管理者または SharePoint 管理者特権を持つ職場または学校のアカウントを使用して、SharePoint Online 管理シェルに接続します。 方法の詳細については、「[SharePoint のオンライン管理シェルを使うにあたって](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)」を参照してください。

3. 次のコマンドを実行して、機密ラベルとその Guid の一覧を取得します。

    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Authentication Basic -AllowRedirection -Credential $UserCredential
    Import-PSSession $Session
    Get-Label |ft Name, Guid  
    ```

4. 上書きするラベルの GUID をメモしておきます。 たとえば、"General" というラベルがあります。

5. "General" 分類を持つグループの一覧を取得するには、次のコマンドを使用します。 このコマンドを実行すると、Exchange Online PowerShell に接続し、Set-unifiedgroup コマンドレットを実行します。

   ```PowerShell
   Set-ExecutionPolicy RemoteSigned
   $UserCredential = Get-Credential
   $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
   Import-PSSession $Session
   ```

6. 各グループに対して、新しい機密ラベル GUID を追加します。

    ```PowerShell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "457fa763-7c59-461c-b402-ad1ac6b703cc"}
    ```
