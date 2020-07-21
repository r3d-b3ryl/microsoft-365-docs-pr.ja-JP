---
title: Microsoft Teams、Microsoft 365 グループ、SharePoint サイトで秘密度ラベルを使用する
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
description: 秘密度ラベルを使用して、SharePoint サイト、Microsoft Teams サイト、Microsoft 365 グループのコンテンツを保護します。
ms.openlocfilehash: b9168320b5764a3d7ed4e1570c32f0f35ccbc44d
ms.sourcegitcommit: a08103bc120bdec7cfeaf67c1be4e221241e69ad
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2020
ms.locfileid: "45199627"
---
# <a name="use-sensitivity-labels-to-protect-content-in-microsoft-teams-microsoft-365-groups-and-sharepoint-sites"></a>秘密度ラベルを使用して、Microsoft Teams、Microsoft 365 グループ、SharePoint サイトのコンテンツを保護する

>*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*

[秘密度ラベル](sensitivity-labels.md) を使用して、ドキュメントやメールを分類および保護するだけでなく、Microsoft Teams サイト、Microsoft 365 グループ ([以前は Office 365 グループ](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601))、およびSharePoint サイトなどのコンテナーにあるコンテンツを保護するために、秘密度ラベルを使用することもできます。 コンテナー レベルの分類と保護を設定するには、次のラベル設定を使用します。

- Microsoft 365 グループに接続されているチーム サイトのプライバシー (パブリックまたはプライベート)
- 外部ユーザーのアクセス
- 非管理対象デバイスからのアクセス 

サポートされているコンテナーにこの秘密度ラベルを適用すると、分類および保護の設定が、接続されたサイトまたはグループに自動的に適用されます。

ただし、これらのコンテナーのコンテンツは、視覚的なマーキング、または暗号化の分類および設定のラベルを継承しません。 ユーザーが SharePoint サイトまたはチーム サイトでドキュメントにラベルを付けられるようにするには、[SharePoint および OneDrive で Office ファイルの秘密度ラベルを有効にします](sensitivity-labels-sharepoint-onedrive-files.md)。

> [!NOTE]
> コンテナーの秘密度ラベルは、Office 365 のコンテンツ配信ネットワーク (CDNs) ではサポートされていません。

## <a name="using-sensitivity-labels-for-microsoft-teams-microsoft-365-groups-and-sharepoint-sites"></a>Microsoft Teams、Microsoft 365 グループ、およびSharePoint サイトで秘密度ラベルを使用する

コンテナーの秘密度ラベルを有効化し、新しい設定の秘密度ラベルを構成する前に、ユーザーはアプリで秘密度ラベルを表示および適用できます。 たとえば、Word から: 

![Word デスクトップ アプリに表示される機密ラベル](../media/sensitivity-label-word.png)

コンテナーの秘密度ラベルを有効にして構成すると、ユーザーは追加で秘密度ラベルを表示し、Microsoft チーム サイト、Microsoft 365 グループ、および SharePoint サイトに適用することができます。 たとえば、SharePoint から新しいチーム サイトを作成する場合:

![SharePoint でチーム サイトを作成するときの機密ラベル](../media/sensitivity-labels-new-team-site.png)

## <a name="how-to-enable-sensitivity-labels-for-containers-and-synchronize-labels"></a>コンテナーの秘密度ラベルを有効化してラベルを同期する方法

1. この機能は Azure AD 機能を使用するため、Azure AD のドキュメント [「Azure Active Directory で Microsoft 365 グループに秘密度ラベルを割り当てる」](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels) の指示に従い、秘密度ラベルのサポートを有効にします。

2. 秘密度ラベルを Azure AD に同期することが必要になります。 まず、[Office 365 セキュリティ/コンプライアンス センター PowerShell へ接続します](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。 
    
    たとえば、管理者として実行している PowerShell セッションで、グローバル管理者アカウントでサインインします。
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    ```

3. 秘密度ラベルを Microsoft 365 グループで使用できるように、次のコマンドを実行します。
    
    ```powershell
    Execute-AzureAdLabelSync
    ```

## <a name="how-to-configure-site-and-group-settings"></a>サイトおよびグループの設定を構成する方法

これで、サイトおよびグループで使用する機密ラベルを作成または編集する準備が整いました。 コンテナーの秘密度ラベルを有効にすると、秘密度のラベル付けウィザードで新しいページが表示されます: **サイトとグループの設定**

機密ラベルの作成または編集に関するヘルプが必要な場合は、「[機密ラベルを作成して構成する](create-sensitivity-labels.md#create-and-configure-sensitivity-labels)」の手順を参照してください。

この新しい [**サイトとグループの設定**] ページで、設定を構成します。

- **Office 365 グループに接続されたチーム サイトのプライバシー**: このラベルが適用されているチーム サイトまたはグループに組織内の誰もがアクセスできるようにする場合は、既定の [**公開 - 組織内のすべてのユーザーがサイトにアクセスできます**] に設定します。
    
    組織内の承認されたメンバーのみにアクセスを制限する場合は、[**プライベート**] を選択します。
    
    秘密度ラベルを使用してコンテナー内のコンテンツを保護し、ユーザーが自分でプライバシー設定を構成できるようにする場合は、[**なし - ユーザーがサイトにアクセスできるユーザーを選択できるようにします**] を選択します。
    
    このラベルをコンテナーに適用すると、[**パブリック**] または [**プライベート**] の設定によってプライバシー設定が設定およびロックされます。 選択した設定は、チームまたはグループに構成されている可能性がある以前のプライバシー設定を置き換え、プライバシー値をロックします。これにより、コンテナーから最初に秘密度ラベルを削除することによってのみ、変更できるようになります。 秘密度ラベルを削除しても、ラベルからのプライバシー設定は維持され、ユーザーは再びラベルを変更することができます。

- **外部ユーザー アクセス**: グループの所有者が[ゲストをグループに追加](/office365/admin/create-groups/manage-guest-access-in-groups)できるかどうかを制御します。

- **非管理対象デバイス**: [非管理対象デバイス](/sharepoint/control-access-from-unmanaged-devices)の場合、フル アクセスを許可するか、Web のみのアクセスを許可するか、またはアクセスを完全にブロックします。 この設定をテナント レベルまたは特定のサイトで構成した場合、ここで指定した設定は、より制限の厳しい場合にのみ適用されます。

![[サイトとグループの設定] タブ](../media/edit-sensitivity-label-site-group2.png)

> [!IMPORTANT]
> チーム、グループ、またはサイトにラベルを適用すると、それらのサイトとグループの設定のみが有効になります。 暗号化やコンテンツ マーキングなどのその他のラベル設定は、チーム、グループ、またはサイト内のコンテンツに適用されません。
> 
> テナントへの段階的なロールアウト: ユーザーがチーム、グループ、サイトを作成するときに選択できるのは、サイトの設定およびグループの設定のラベルのみです。 ラベルにサイトとグループの設定が有効になっていないときに、ラベルをコンテナーに適用する場合は、ラベル名のみがコンテナーに適用されます。

秘密度ラベルがまだ公開されていない場合は、[秘密度ラベル ポリシーに追加](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy)して公開します。 このラベルを含む秘密度ラベル ポリシーが割り当てられているユーザーには、サイトとグループ用にそのラベルを選択できます。

このラベルをコンテナーに適用する場合、ラベル ポリシーからは、ポリシー設定 **[既定でドキュメントとメールにこのラベルを適用する]** のみが適用されます。 必須のラベル付け、ユーザーの妥当性の要求、カスタム ヘルプ ページへのリンクなど、他のポリシー設定は適用されません。

## <a name="sensitivity-label-management"></a>機密ラベルの管理

サイトとグループに対して構成されている秘密度ラベルを作成、変更、または削除する場合は、次のガイダンスを使用します。

### <a name="creating-and-publishing-labels-that-are-configured-for-sites-and-groups"></a>サイトとグループに対して構成されているラベルを作成して発行する

新しい機密ラベルを作成して公開すると、チーム、グループ、およびサイトでユーザーには、1 時間以内に表示されます。 ただし、既存のラベルを変更する場合は、最大で 24 時間かかります。 このラベルがサイトおよびグループの設定に対して構成されている場合、次のガイダンスを使用して、ユーザーのラベルを発行します。

1. 秘密度ラベルを作成し構成したら、少数のテスト ユーザーにのみ適用されるラベル ポリシーにこのラベルを追加します。

2. 変更がレプリケートされるまで待機します。
    - 新規ラベル: 1 時間待機します。
    - 既存のラベル: 24 時間待機します。

3. この待ち時間の後、テスト ユーザー アカウントのいずれかを使用して、手順 1 で作成したラベルを持つチーム、Microsoft 365 グループ、または SharePoint サイトを作成します。

4. この作成操作中にエラーが発生しなかった場合、テナント内のすべてのユーザーに安全にラベルを発行できます。

### <a name="modifying-published-labels-that-are-configured-for-sites-and-groups"></a>サイトとグループに対して構成されている発行済みのラベルを変更する

ベスト プラクティスとして、秘密度ラベルを複数のチーム、グループ、またはサイトに適用した後に、ラベルのサイトとグループの設定を変更しないようにします。 この場合、ラベルが適用されているすべてのコンテナーに変更を複製されるまで 24 時間待機することを忘れないでください。 

また、**外部ユーザーのアクセス** 設定を含む変更は、次のようになります。

- 新しい設定は新しいユーザーに適用されますが、既存のユーザーには適用されません。 たとえば、この設定は以前に選択されていて、その結果、ゲスト ユーザーがサイトにアクセスした場合、この設定をラベル構成で解除した後も、これらのゲスト ユーザーはサイトにアクセスできます。

- HiddenMembership および roleEnabled グループ プロパティのプライバシー設定は更新されません。


### <a name="deleting-published-labels-that-are-configured-for-sites-and-groups"></a>サイトとグループに対して構成されている発行済みラベルを削除する

サイトとグループの設定を有効にして秘密度ラベルの削除を行い、そのラベルが 1 つ以上のラベル ポリシーに含まれている場合、新しいチーム、グループ、サイトの作成に失敗してしまう可能性があります。 この状況を回避するには、以下のガイダンスを使用してください。

1. ラベルを含むすべてのラベル ポリシーから、機密ラベルを削除します。

2. 1 時間待機します。

3. この待ち時間の後、チーム、グループ、またはサイトを作成し、ラベルが表示されなくなったことを確認してください。

4. 秘密度ラベルが表示されていない場合は、ラベルを安全に削除できます。

## <a name="how-to-apply-sensitivity-labels-to-containers"></a>コンテナーに秘密度ラベルを適用する

これで、１つまたは複数の秘密度ラベルを次のようなコンテナーに適用する準備ができました。

- [Azure AD の Microsoft 365 グループ](#apply-sensitivity-labels-to-microsoft-365-groups)
- [Microsoft Teams のチーム サイト](#apply-a-sensitivity-label-to-a-new-team)
- [Outlook on the web の Microsoft 365 グループ](#apply-a-sensitivity-label-to-a-new-group-in-outlook-on-the-web)
- [SharePoint サイト](#apply-a-sensitivity-label-to-a-new-site)

[複数のサイトに秘密度ラベルを適用する](#use-powershell-to-apply-a-sensitivity-label-to-multiple-sites) 必要がある場合、PowerShell を使用できます。

### <a name="apply-sensitivity-labels-to-microsoft-365-groups"></a>Microsoft 365 グループに秘密度ラベルを適用する

これで、1 つまたは複数の秘密度ラベルを Microsoft 365 グループに適用する準備ができました。 手順については、Azure AD のドキュメントに戻ります。

- 「[Assign a label to a new group in Azure portal (Azure ポータルの新しいグループにラベルを割り当てる)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#assign-a-label-to-a-new-group-in-azure-portal)」

-  [Assign a label to an existing group in Azure portal (Azure ポータルの既存のグループにラベルを割り当てる)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#assign-a-label-to-an-existing-group-in-azure-portal)

-  「[Remove a label from an existing group in Azure portal (Azure ポータルの既存のグループからラベルを削除する)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#remove-a-label-from-an-existing-group-in-azure-portal).」

### <a name="apply-a-sensitivity-label-to-a-new-team"></a>新しいチームに機密ラベルを適用する

ユーザーは、Microsoft Teams で新しいチームを作成する際に機密ラベルを選択できます。 **[秘密度]** ドロップダウンからラベルを選択すると、プライバシー設定によってラベル構成が変更される場合があります。 ラベルに対し選択した外部ユーザーのアクセス設定に応じて、ユーザーは組織外のユーザーをチームに追加することができたり、できなかったりします。

[Teams の機密ラベルの詳細について](https://docs.microsoft.com/microsoftteams/sensitivity-labels)

![新しいチームを作成する際のプライバシー設定](../media/privacy-setting-new-team.png)

チームを作成すると、すべてのチャネルの右上隅に機密ラベルが表示されます。

![チームに表示される機密ラベル](../media/privacy-setting-teams.png)

このサービスは、Microsoft 365 グループおよび接続された SharePoint チーム サイトに対して同じ秘密度ラベルを自動的に適用します。

### <a name="apply-a-sensitivity-label-to-a-new-group-in-outlook-on-the-web"></a>Outlook on the web の新しいグループに機密ラベルを適用する

Outlook on the web では、新しいグループを作成するときに、公開されたラベルの [**機密**] オプションを選択または変更できます。

![グループを作成し、[機密] 下でオプションを選択する](../media/sensitivity-label-new-group.png)

### <a name="apply-a-sensitivity-label-to-a-new-site"></a>新しいサイトに機密ラベルを適用する

管理者およびエンド ユーザーは、[最新のチーム サイトやコミュニケーション サイトを作成する](/sharepoint/create-site-collection)際に秘密度ラベルを選択し、以下のような**詳細設定**を行うことができます。

![サイトを作成し、[秘密度] 下でオプションを選択する](../media/sensitivity-label-new-communication-site.png)

ドロップダウン ボックスには選択したラベル名が表示され、ヘルプ アイコンにはすべてのラベル名とヒントが表示されます。これにより、ユーザーは適用するラベルを正しく選ぶことができます。

ラベルが適用され、ユーザーがサイトを参照すると、ラベルの名前および適用されているポリシーが表示されます。 たとえば、以下のサイトでは、**秘密**のラベル付けがされており、プライバシー設定は**プライベート**になっています。

![機密ラベルが適用されているサイト](../media/sensitivity-label-site.png)

### <a name="use-powershell-to-apply-a-sensitivity-label-to-multiple-sites"></a>PowerShell を使用して、複数のサイトに秘密度ラベルを適用する

[Set-SPOSite](/powershell/module/sharepoint-online/set-sposite?view=sharepoint-ps) と [Set-SPOTenant](/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps) コマンドレットを使用して、現在の SharePoint Online 管理シェルの *秘密度ラベル* のパラメーターによって、多くのサイトに秘密度ラベルを適用できます。 サイトには、任意の SharePoint サイトコレクション、または OneDrive サイトを使用できます。

SharePoint Online 管理シェルのバージョン16.0.19418.12000 以降があることを確認します。

1. **[管理者として実行]** オプションを使用して PowerShell セッションを開きます。

2. ラベルの GUID がわからない場合、[Office 365 セキュリティ/コンプライアンス センターの PowerShellに接続し](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)、秘密度ラベルとそれらの GUID のリストを取得します。
    
    ```powershell
    Get-Label |ft Name, Guid
    ```

3. ここでは、[Exchange Online PowerShellに接続して](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)、ラベルの GUID を変数として保存します。 例: 
    
    ```powershell
    $Id = [GUID]("e48058ea-98e8-4940-8db0-ba1310fd955e")
    ```

4. URL に共通の識別文字列が含まれる複数のサイトを特定する新しい変数を作成します。 例:
    
    ```powershell
    $sites = Get-SPOSite -IncludePersonalSite $true -Limit all -Filter "Url -like 'documents" 
    ```

5. これらのサイトにラベルを適用するには、次のコマンドを実行します。 サンプルを使用します。
    
    ```powershell
    $sites | ForEach-Object {Set-SpoTenant $_.url -SensitivityLabel $Id}
    ```

異なるサイトに異なるラベルを適用するには、各サイトで次のコマンドを繰り返します。 `Set-SPOSite -Identity <URL> -SensitivityLabel "<labelguid>"`

## <a name="view-and-manage-sensitivity-labels-in-the-sharepoint-admin-center"></a>SharePoint 管理センターで秘密度ラベルを表示し管理する

適用された秘密度ラベルを表示、並べ替え、および検索するには、新しい SharePoint 管理センターの [**アクティブなサイト**] ページを使用します。 最初に、[**機密**] 列を追加する必要がある場合があります。

![[アクティブなサイト] ページの [機密] 列](../media/manage-site-sensitivity-labels.png)

列を追加する方法など、[アクティブなサイト] ページからサイトを管理する方法の詳細については、「[新しい SharePoint 管理センターでサイトを管理する](/sharepoint/manage-sites-in-new-admin-center)」 を参照してください。

このページからラベルを変更して適用することもできます。

1. [詳細] ウィンドウを開くには、サイト名を選択します。

2. [**ポリシー**] タブを選択し、**秘密度** の設定で [**編集**] を選択します。

3. [**秘密度の設定の編集**] ウィンドウで、サイトに適用する秘密度ラベルを選び、[**保存**] を選択します。

## <a name="support-for-sensitivity-labels"></a>秘密度ラベルのサポート

次のアプリとサービスで、サイトとグループの設定用に構成した秘密度ラベルをサポートしています。

- 管理センター:
    - SharePoint 管理センター
    - Azure Active Directory ポータル
    - Microsoft 365 コンプライアンス センター、Microsoft 365 セキュリティ センター、Office 365 セキュリティ/コンプライアンス センター

- ユーザーのアプリとサービス:
    - SharePoint
    - Teams
    - Outlook on the web and for Windows、MacOS、iOS、および Android
    - フォーム
    - Stream

次のアプリとサービスで、サイトとグループの設定用に構成した秘密度ラベルをサポートしています。

- 管理センター:
    - Microsoft 365 管理センター
    - Teams 管理センター
    - Exchange 管理センター

- ユーザーのアプリとサービス:
    - Dynamics 365
    - Yammer
    - Planner
    - Project
    - PowerBI

## <a name="classic-azure-ad-group-classification"></a>従来の Azure AD グループの分類

コンテナーの秘密度ラベルを有効にすると、Microsoft 365 は新しい Microsoft 365 のグループおよび SharePoint サイト向けに古い分類をサポートしなくなります。 ただし、秘密度ラベルをサポートしている既存のグループおよびサイトには、秘密度ラベルを使用するように変換しない限り、古い分類値が引き続き表示されます。

SharePoint の古いグループ分類を使用した場合の例として、「[SharePoint の "モダン" サイトの分類」](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification)を参照してください。

これらの分類は、Azure AD PowerShell または PnP コア ライブラリを使用し、`ClassificationList` 設定に値を定義することによって構成されています。 テナントに分類値が定義されている場合は、[AzureADPreview PowerShell モジュール](https://www.powershellgallery.com/packages/AzureADPreview)から次のコマンドを実行すると、それらが表示されます。

```powershell
   ($setting["ClassificationList"])
```

古い分類を機密ラベルに変換するには、次のいずれかの操作を行います。

- 既存のラベルを使用: 既に公開されている既存の機密ラベルを編集して、サイトおよびグループに必要なラベル設定を指定します。

- 新しいラベルの作成: 既存の分類と同じ名前を持つ新しい機密ラベルを作成および公開して、サイトおよびグループに必要なラベル設定を指定します。

その後で以下の手順に従います。 

1. PowerShell を使用し、既存の Microsoft 365 グループおよび SharePoint サイトに名前のマッピングを使用して秘密度ラベルを適用します。 手順については、次のセクションを参照してください。

2. 既存のグループおよびサイトから古い分類を削除します。

機密ラベルをまだサポートしていないアプリやサービスでユーザーが新しいグループを作成できないようにすることはできませんが、定期的な PowerShell スクリプトを実行して、ユーザーが古い分類で作成した新しいグループを探し、機密ラベルを使用するようにそれらを変換することができます。 

サイトとグループの秘密度ラベルと Azure AD の分類の共存を管理する方法については、「[Microsoft 365 グループの Azure Active Directory の分類と秘密度ラベル](migrate-aad-classification-sensitivity-labels.md)」 を参照してください。

#### <a name="use-powershell-to-convert-classifications-for-microsoft-365-groups-to-sensitivity-labels"></a>PowerShell を使用して Microsoft 365 グループの分類を秘密度ラベルに変換する

1. まず、[Office 365 セキュリティ/コンプライアンス センター PowerShell へ接続します](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。 
    
    たとえば、管理者として実行している PowerShell セッションで、グローバル管理者アカウントでサインインします。
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    ```

2. [Get-Label](https://docs.microsoft.com/powershell/module/exchange/get-label?view=exchange-ps) コマンドレットを使用して、機密ラベルおよびその GUID のリストを取得します。
    
    ```powershell
    Get-Label |ft Name, Guid
    ```

3. Microsoft 365 グループに適用する秘密度ラベルの GUID をメモします。

4. 次に、[Exchange Online PowerShell に接続](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)します。
    
    例:
    
    ```powershell
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session
    ```

5. 次のコマンドを例として使用して、現在 "一般" の分類を持つグループのリストを取得します。

   ```PowerShell
   $Groups= Get-UnifiedGroup | Where {$_.classification -eq "General"}
   ```

6. グループごとに、新しい機密ラベル GUID を追加します。 以下に例を示します。

    ```PowerShell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "457fa763-7c59-461c-b402-ad1ac6b703cc"}
    ```

7. 残りのグループ分類について、手順 5 と 6 を繰り返します。

## <a name="auditing-sensitivity-label-activities"></a>機密ラベル アクティビティの監査

誰かが機密ラベルで保護されているサイトにドキュメントをアップロードし、そのドキュメントの機密ラベルが、サイトに適用されている機密ラベルよりも[優先度が高く](sensitivity-labels.md#label-priority-order-matters)なっている場合、このアクションはブロックされません。 たとえば、「**一般**」ラベルを SharePoint サイトに適用し、誰かがこのサイトに「**社外秘**」というラベルの付けられたドキュメントをアップロードしたとします。 優先度の高い機密ラベルは、優先順位の低いコンテンツよりも機密性の高いコンテンツを識別するため、この状況はセキュリティ上の懸念になる可能性があります。

アクションはブロックされていませんが、監査され、ドキュメントをアップロードした人とサイト管理者にメールが自動的に生成されます。 結果として、ユーザーと管理者の両方が、この不適切なラベルの優先順位を設定し、必要に書類を特定することができます。 たとえば、アップロードされたドキュメントをサイトから削除または移動します。 

ドキュメントの機密ラベルが、サイトに適用されている機密ラベルよりも優先度が低い場合、セキュリティ上の懸念にはなりません。 たとえば、「**一般**」というラベルの付いたドキュメントが、「**社外秘**」というラベルの付いたサイトにアップロードされている場合です。 このシナリオでは、監査イベントとメールが生成されません。

このイベントの監査ログを検索するには、[**ファイルとページのアクティビティ**] カテゴリから [**検出されたドキュメントの機密度の不一致**] を探します。 

自動生成されたメールには、サブジェクト **の互換性がない秘密度ラベルが検出されました**とメールメッセージは、アップロードされたドキュメントとサイトへのリンクとのラベルの不一致を説明します。 ユーザーが感度ラベルを変更できるようにするドキュメントリンクも含まれています。 現在、これらの自動メールは無効にすることも、カスタマイズすることができません。

サイトまたはグループに対して、または、ある人が機密ラベルを追加または削除する場合、これらのアクティビティも監査されますが、メールは自動的に生成されません。 

これらの監査イベントはすべて、[秘密ラベルのアクティビティ](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) カテゴリに記載されています。 監査ログを検索する手順については、「[セキュリティ/コンプライアンス センターで監査ログを検索する](search-the-audit-log-in-security-and-compliance.md)」を参照してください。

## <a name="how-to-disable-sensitivity-labels-for-containers"></a>コンテナーの秘密度ラベルを無効にする方法

「[PowerShell で秘密度ラベルのサポートを有効にする](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#enable-sensitivity-label-support-in-powershell)」と同じ手順で、Microsoft Teams、Microsoft 365 グループ、SharePoint サイトの秘密度ラベルをオフにすることができます。 ただし、この機能を無効にするには、手順5で `$setting["EnableMIPLabels"] = "False"`を指定します。

秘密度ラベルを作成または編集しているときに、**サイトとグループの設定** ページが非表示になるだけでなく、この操作では、コンテナーが構成に使用するプロパティは元に戻ります。 Microsoft Teams、Microsoft 365 グループ、SharePoint サイトで秘密度ラベルを有効にすると、**分類** ([Azure AD グループの分類](#classic-azure-ad-group-classification) に使用) に使用されているプロパティが **秘密度** に切り替わります。 コンテナーの秘密度ラベルを無効にすると、コンテナーは秘密度プロパティを無視して、もう一度分類プロパティを使用します。

つまり、以前コンテナーに適用されたサイトとグループのラベル設定が適用されなくなり、コンテナーにはラベルが表示されなくなります。

これらのコンテナーに Azure AD 分類値が適用されている場合、コンテナーは再び分類を使用します。 この機能を有効にした後に作成された新しいサイトやグループにはラベルが表示されず、分類もされないので注意してください。 これらのコンテナー、および新しいコンテナーの場合、分類値を適用できるようになりました。 詳細については、「[SharePoint の 「最新の」 サイト分類](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification)」 および 「[組織の Office グループの分類を作成する](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell)」 を参照してください。。

## <a name="additional-resources"></a>その他のリソース

[Microsoft Teams、O365 グループおよび SharePoint Online サイトでの秘密度ラベルの使用](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/using-sensitivity-labels-with-microsoft-teams-o365-groups-and/ba-p/1221885#M1380)については、ウェビナーのレコーディングと回答をご覧ください。

このウェビナーは、当該機能がまだプレビューに含まれているときに記録されているので、UI にいくつかの矛盾が見つかる可能性があります。 ただし、このページに記載されている新しい機能があれば、この機能の情報は正確です。
