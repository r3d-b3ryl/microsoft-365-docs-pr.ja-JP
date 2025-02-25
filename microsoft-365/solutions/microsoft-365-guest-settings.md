---
title: Microsoft 365 ゲストの共有設定のリファレンス
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
- m365initiative-externalcollab
f1.keywords: NOCSH
ms.custom:
- seo-marvel-apr2020
- admindeeplinkTEAMS
- admindeeplinkSPO
ms.localizationpriority: high
recommendations: false
description: 組織外のユーザーとの共有に影響を与える可能性がある、Microsoft 365 で使用できるゲスト共有設定について説明します。
ms.openlocfilehash: 574e2ab6b3ca01de31d4489b80c5b6aefddd6a9f
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66949461"
---
# <a name="microsoft-365-guest-sharing-settings-reference"></a>Microsoft 365 ゲストの共有設定のリファレンス

この記事では、Microsoft 365 のワークロードについて、Teams、Microsoft 365 グループ、SharePoint、OneDrive の組織外のユーザーとの共有に影響を与える可能性のあるさまざまな設定について説明します。 これらの設定は、Azure Active Directory、Microsoft 365、Teams、および SharePoint 管理センターにあります。

## <a name="azure-active-directory"></a>Azure Active Directory

**管理者ロール:** グローバル管理者

Azure Active Directory は、Microsoft 365 により使用されるディレクトリ サービスです。 Azure Active Directory の組織の関係設定は、Teams、Microsoft 365 グループ、SharePoint、OneDrive での共有に直接影響します。

> [!NOTE]
> これらの設定は、[SharePoint および OneDrive の Azure AD B2B との統合](/sharepoint/sharepoint-azureb2b-integration-preview)が構成された場合にのみ、SharePoint に反映されます。 次の表では、この設定が構成されていることを前提としています。

### <a name="external-collaboration-settings"></a>外部コラボレーションの設定

**ナビゲーション:** [[Azure Active Directory 管理センター]](https://aad.portal.azure.com) > [Azure Active Directory] > [外部 ID] > [外部コラボレーションの設定]

![Azure Active Directory の [組織関係設定] ページのスクリーンショット](../media/azure-ad-organizational-relationships-settings.png)

| 設定 | 既定値 | 説明 |
|:-----|:-----|:-----|
|ゲスト ユーザー アクセス|ゲスト ユーザーは、ディレクトリ オブジェクトのプロパティとメンバーシップへのアクセスが制限されています|[ゲストが Azure Active Directory で持つアクセス許可](/azure/active-directory/fundamentals/users-default-permissions)を決定します。|
|ゲスト招待設定|組織内のあらゆるユーザーが、ゲストや管理者以外のユーザーを含むゲスト ユーザーを招待できます|ゲスト、メンバー、および管理者がゲストを組織に招待できるかどうかを決定します。 <p> この設定は、Teams や SharePoint などの Microsoft 365 共有エクスペリエンスに影響します。|
|ユーザー フロー経由でゲストのセルフ サービスのサインアップを有効にする|いいえ|作成したアプリに誰かがサインアップして新しいゲスト アカウントを作成できるようにするユーザー フローを作成できるかどうかを決定します。|
|共同作業における制限事項|招待を任意のドメインに送信することを許可する|この設定では、共有するドメインの許可またはブロックのリストを指定できます。 許可されたドメインを指定すると、共有の招待をそのドメインにのみ送信できます。 拒否されたドメインを指定すると、共有の招待はそのドメインに送信できません。 <p> この設定は、Teams や SharePoint などの Microsoft 365 共有エクスペリエンスに影響します。 SharePoint と Teams でドメインのフィルタリングを使用して、より詳細にドメインを許可したりブロックしたりできます。|

これらの設定は、ユーザーがディレクトリに招待される方法に影響します。 ディレクトリにすでに存在しているゲストとの共有には影響しません。

### <a name="cross-tenant-access-settings"></a>テナント間アクセス設定を構成する

**ナビゲーション:** [[Azure Active Directory 管理センター]](https://aad.portal.azure.com) > [Azure Active Directory] > [外部 ID] > [テナント間アクセス設定] > [既定の設定] タブ

既定の設定は、組織固有の設定を除くすべての外部 Azure AD 組織に適用されます。 特定の組織の設定は、**[組織の設定]** タブで構成できます。ゲスト (B2B コラボレーション) と [Azure AD B2B 直接接続](/azure/active-directory/external-identities/b2b-direct-connect-overview) ユーザーには別の設定があります。

![Azure Active Directory テナント間アクセス設定ページのスクリーンショット。](../media/azure-ad-cross-tenant-default-settings.png)

**受信アクセス設定**

[受信アクセス設定] は、外部の Azure AD 組織のユーザーが組織内のリソースにアクセスできるかどうかを制御します。

| 設定 | 既定値 | 説明 |
|:-----|:-----|:-----|
|B2B コラボレーション - 外部ユーザーとグループ|すべて許可|他の Azure AD 組織のユーザーにゲストとして組織内のリソースへのアクセスを許可できるユーザーを決定します。|
|B2B コラボレーション - アプリケーション|すべて許可|組織のゲストにアクセス権を付与できるアプリを決定します。|
|B2B 直接接続 - 外部ユーザーとグループ|すべてブロック済み|B2B 直接接続を使用して、他の Azure AD 組織のユーザーに組織内のリソースへのアクセスを許可できるかどうかを決定します。|
|B2B 直接接続 - アプリケーション|すべてブロック済み|組織内の B2B 直接接続ユーザーにアクセスを許可できるアプリを決定します。|
|信頼設定|無効|条件付きアクセス ポリシーが、他の Azure AD 組織のユーザーがリソースにアクセスするときに、それらの組織からの要求を受け入れるかどうかを決定します。 |

**送信アクセス設定**

[送信アクセス設定] は、ユーザーが外部組織のリソースにアクセスできるかどうかを制御します。

| 設定 | 既定値 | 説明 |
|:-----|:-----|:-----|
|B2B コラボレーション - 外部ユーザーとグループ|すべて許可|組織内のどのユーザーに、ゲストとして他の Azure AD 組織のリソースへのアクセスを許可できるかを決定します。|
|B2B コラボレーション - アプリケーション|すべて許可|ユーザーにゲストとしてのアクセスを許可できる他の Azure AD 組織のアプリを決定します。|
|B2B 直接接続 - 外部ユーザーとグループ|すべてブロック済み|B2B 直接接続を使用して、組織内のどのユーザーに他の Azure AD 組織のリソースへのアクセスを許可できるかを決定します。|
|B2B 直接接続 - アプリケーション|すべてブロック済み|B2B 直接接続を介してユーザーにアクセスを許可できる他の Azure AD 組織のアプリを決定します。|

## <a name="microsoft-365"></a>Microsoft 365

**管理者ロール:** グローバル管理者

Microsoft 365 管理センターには、共有および Microsoft 365 グループ用の組織レベル設定があります。

### <a name="sharing"></a>共有

**ナビゲーション:** [[Microsoft 365 管理センター]](https://admin.microsoft.com) > **[設定]** > **[組織の設定]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">**[セキュリティとプライバシー]** タブ</a> > **[共有]**。

![Microsoft 365 管理センターにおけるセキュリティとプライバシーのゲスト共有設定のスクリーンショット](../media/sharepoint-security-privacy-sharing-setting.png)

| 設定 | 既定値 | 説明 |
|:-----|:-----|:-----|
|ユーザーが組織に新しいゲストを追加できるようにする|オン|**[はい]** に設定すると、Azure AD メンバーは Azure AD を使用してゲストを招待できます。**[いいえ]** に設定すると招待できません。 **[はい]** に設定すると、Microsoft 365 グループのメンバーは所有者の承認を受けているゲストを招待できます。**[いいえ]** に設定すると、Microsoft 365 グループのメンバーは所有者の承認を受けているゲストを招待できますが、所有者が承認するにはグローバル管理者でなければなりません。 <p> **[メンバーが招待できる]** は、(ゲストではなく) Azure AD のメンバーを参照し、Microsoft 365 のサイトまたはグループ メンバーを参照しない点に注意してください。 <p> これは、Azure Active Directory の組織の関係設定で **[メンバーが招待できる]** 設定と同じです。|

### <a name="microsoft-365-groups"></a>Microsoft 365 グループ

**ナビゲーション:**[[Microsoft 365 管理センター]](https://admin.microsoft.com) > **[設定]** > **[組織の設定]** > [Microsoft 365 グループ]

![Microsoft 365 管理センターにおける Microsoft 365 グループのゲスト設定のスクリーンショット](../media/office-365-groups-guest-settings.png)

| 設定 | 既定値 | 説明 |
|:-----|:-----|:-----|
|組織の外部のグループ メンバーがグループのコンテンツにアクセスできるようにする|オン|**[オン]** に設定すると、ゲストはグループのコンテンツにアクセスできます。**[オフ]** に設定するとアクセスできません。 この設定は、ゲストが Microsoft 365 グループまたは Teams と連携している場合に **[オン]** にしてください。|
|グループ所有者が組織外のユーザーをグループに追加できるようにする|オン|**[オン]** の場合、Microsoft 365 グループまたは Teams の所有者は新しいゲストをグループに招待できます。 **[オフ]** の場合は、できません。 この設定は、ゲストをグループに追加するシナリオでは、**[オン]** にする必要があります。|

これらを、組織レベルで設定できます。PowerShell を使用し、グループ レベルでこれらの設定を変更する方法の詳細については、「[特定のグループに対する設定を作成する](/azure/active-directory/users-groups-roles/groups-settings-cmdlets#create-settings-for-a-specific-group)」を参照してください。

## <a name="teams"></a>Teams

Teams のゲスト アクセスのスイッチである **[Teams でのゲスト アクセスを許可する]** を **[オン]** にして、他のゲスト設定を選択できるようにする必要があります。

**管理者ロール:** Teams サービス管理者

### <a name="guest-access"></a>ゲスト アクセス

**ナビゲーション:** [[Teams 管理センター]](https://admin.teams.microsoft.com) > **[組織全体の設定]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2173122" target="_blank">**[ゲスト アクセス]**</a>

![Teams ゲスト アクセスのトグルのスクリーンショット](../media/teams-guest-access-toggle.png)

| 設定 | 既定値 | 説明 |
|:-----|:-----|:-----|
|Teams でのゲスト アクセスを許可する|オン|Teams 全体でゲスト アクセスをオンまたはオフにします。 この設定は、一度変更し反映されるのに 24 時間かかることがあります。|

### <a name="guest-calling"></a>ゲスト通話

**ナビゲーション:** [[Teams 管理センター]](https://admin.teams.microsoft.com) > **[組織全体の設定]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2173122" target="_blank">**[ゲスト アクセス]**</a>

![Teams ゲスト通話オプションのスクリーンショット](../media/teams-guest-calling-setting.png)

| 設定 | 既定値 | 説明 |
|:-----|:-----|:-----|
|プライベート通話をする|オン|**[オン]** の場合、ゲストは Teams でピアツーピアの通話を行うことができます。**[オフ]** の場合は通話できません。|

### <a name="guest-meeting"></a>ゲスト会議

**ナビゲーション:** [[Teams 管理センター]](https://admin.teams.microsoft.com) > **[組織全体の設定]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2173122" target="_blank">**[ゲスト アクセス]**</a>

![Teams ゲスト会議設定のスクリーンショット](../media/teams-guest-meeting-settings.png)

| 設定 | 既定値 | 説明 |
|:-----|:-----|:-----|
|IP のビデオを許可する|オン|**[オン]** の場合、ゲストは通話と会議でビデオを使用できます。**[オフ]** の場合は使用できません。|
|画面共有モード|画面全体|**[無効]** にすると、ゲストは Teams で画面を共有できません。 **[1 つのアプリケーション]** に設定すると、ゲストは画面上でアプリケーションを 1 つのみ共有できます。 **[画面全体]** に設定すると、ゲストはアプリケーションまたは画面全体を共有するよう選択できます。|
|[会議の開始] を許可する|オン|**[オン]** の場合、ゲストは Teams で [会議の開始] 機能を使用できます。**[オフ]** の場合は使用できません。|

### <a name="guest-messaging"></a>ゲスト メッセージング

**ナビゲーション:** [[Teams 管理センター]](https://admin.teams.microsoft.com) > **[組織全体の設定]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2173122" target="_blank">**[ゲスト アクセス]**</a>

![Teams ゲスト メッセージング設定のスクリーンショット](../media/teams-guest-messaging-settings.png)

| 設定 | 既定値 | 説明 |
|:-----|:-----|:-----|
|送信済みメッセージを編集する|オン|**[オン]** の場合、ゲストは以前に送信したメッセージを編集できます。**[オフ]** の場合は編集できません。|
|送信済みメッセージを削除する|オン|**[オン]** の場合、ゲストは以前に送信したメッセージを削除できます。**[オフ]** の場合は削除できません。|
|チャット|オン|**[オン]** の場合、ゲストは Teams でチャット機能を使用できます。**[オフ]** の場合は使用できません。|
|会話で Giphy を使用する|オン|**[オン]** の場合、ゲストは会話で Giphy を使用できます。**[オフ]** の場合は使用できません。|
|Giphy コンテンツの評価|中|**[すべてのコンテンツを許可]** に設定すると、ゲストはコンテンツ評価に関係なく、すべての Giphy をチャットに挿入できるようになります。 **[中]** に設定すると、ゲストは Giphy をチャットに挿入できますが、成人向けコンテンツの挿入についてはある程度制限されます。 **[高]** に設定すると、ゲストは Giphy をチャットに挿入できますが、成人向けコンテンツの挿入については制限されます。|
|会話でミームを使用する|オン|**[オン]** の場合、ゲストは会話でミームを使用できます。**[オフ]** の場合は使用できません。|
|会話でステッカーを使用する|オン|**[オン]** の場合、ゲストは会話でステッカーを使用できます。**[オフ]** の場合は使用できません。|
|イマーシブ リーダーがメッセージを表示するのを許可する|オン|**[オン]** の場合、ゲストはイマーシブ リーダーでメッセージを表示できます。**[オフ]** の場合は表示できません。|

## <a name="sharepoint-and-onedrive-organization-level"></a>SharePoint と OneDrive (組織レベル)

**管理者ロール:** SharePoint 管理者

これらの設定は組織のすべてのサイトに影響します。 Microsoft 365 グループや Teams には直接影響しませんが、これらの設定を Microsoft 365 グループ と Teams の設定に合わせて、ユーザー エクスペリエンスの問題を回避することをお勧めします。 (たとえば、ゲスト共有が SharePoint ではなく Teams で許可されている場合、Teams ファイルは SharePoint に保存されているため、Teams のゲストは [ファイル] タブにアクセスできません)。

### <a name="sharepoint-and-onedrive-sharing-settings"></a>SharePoint と OneDrive の共有設定

OneDrive はSharePoint のサイトの階層であるため、組織レベルの共有設定は、他の SharePoint サイトに影響するように OneDrive に直接影響します。

**ナビゲーション:** [SharePoint 管理センター] > **[ポリシー]**  > ><a href="https://go.microsoft.com/fwlink/?linkid=2185222" target="_blank"> **[共有]**</a>

![SharePoint 組織レベルの共有設定のスクリーンショット](../media/sharepoint-organization-external-sharing-controls.png)

| 設定 | 既定値 | 説明 |
|:-----|:-----|:-----|
|SharePoint|すべてのユーザー|SharePoint サイトで許可されている制限が最も少ない共有アクセス許可を指定します。|
|OneDrive|すべてのユーザー|OneDrive サイトで許可されている制限が最も少ない共有アクセス許可を指定します。 この設定は SharePoint の設定よりも制限を少なくすることはできません。|

### <a name="sharepoint-and-onedrive-advanced-sharing-settings"></a>SharePoint と OneDrive の詳細な共有設定

**ナビゲーション:** [SharePoint 管理センター] > **[ポリシー]**  > ><a href="https://go.microsoft.com/fwlink/?linkid=2185222" target="_blank"> **[共有]**</a>

![SharePoint における組織レベルの追加共有設定のスクリーンショット](../media/external-sharing.png)

| 設定 | 既定値 | 説明 |
|:-----|:-----|:-----|
|ドメインごとに外部共有を制限する|オフ|この設定では、共有するドメインの許可またはブロックのリストを指定できます。 許可されたドメインを指定すると、共有の招待をそのドメインにのみ送信できます。 拒否されたドメインを指定すると、共有の招待はそのドメインに送信できません。 <p> この設定は、組織内のすべての SharePoint サイトと OneDrive サイトに影響します。|
|特定のセキュリティ グループ内のユーザーにのみ、外部との共有を許可する|オフ|SharePoint と OneDrive のゲストと共有できるユーザーを制限する場合は、指定したセキュリティ グループ内のユーザーへの共有を制限することで行うことができます。 これらの設定は、Microsoft 365 グループまたは Teams による共有には影響しません。 グループまたはチーム経由で招待されたゲストも、関連サイトにアクセスできます。ただし、ドキュメントとフォルダーの共有は、指定したセキュリティ グループのユーザーのみが行うことができます。 <p> 指定したグループごとに、[すべてのユーザー] リンクと共有できるユーザーを選択できます。|
|ゲストは共有への招待が送信されたアカウントと同じアカウントを使用してサインインする必要がある|オフ|招待の送信先とは別のメールアドレスを使用して、ゲストがサイト共有の招待を交換しないようにします。 <p> [SharePoint および OneDrive の Azure AD B2B (プレビュー) との統合](/sharepoint/sharepoint-azureb2b-integration-preview)では、招待の送信先のメールアドレスに基づいてすべてのゲストがディレクトリに追加されるため、この設定は使用されません。代わりのメールアドレスは、サイトにアクセスする際に使用できません。|
|ゲストに所有していないアイテムの共有を許可する|オン|**[オン]** の場合、ゲストは他のユーザーやゲストと自分が所有していないアイテムを共有できます。**[オフ]** の場合は共有できません。 ゲストは常にフル コントロールのあるアイテムを共有できます。|
|認証コードを使用するユーザーに、再認証を要求するまでの日数|オフ|この設定により、ワンタイム パスコードで認証するユーザーが特定の日数後に再認証する必要があることを要求できます。|
|サイトまたは OneDrive へのゲスト アクセスは、この数日後に自動的に期限切れになります|オン|管理者がゲスト アクセスの有効期限を設定している場合、サイトに招待したゲスト、または個別のファイルとフォルダーを共有している各ゲストには、特定の日数のアクセスが許可されます。詳細については、「[サイトのゲストの有効期限を管理する](https://support.microsoft.com/en-us/office/manage-guest-expiration-for-a-site-25bee24f-42ad-4ee8-8402-4186eed74dea)」 をご覧ください。

### <a name="sharepoint-and-onedrive-file-and-folder-link-settings"></a>SharePoint と OneDrive のファイルとフォルダーのリンク設定

SharePoint と OneDrive でファイルとフォルダーを共有すると、共有の受信者はファイルまたはフォルダーに直接アクセスできるようになるのではなく、ファイルまたはフォルダーへのアクセス許可のリンクが送信されます。 リンクにはいくつかの種類があり、ユーザーがファイルまたはフォルダーを共有するときに表示される既定のリンクの種類を選択できます。 また、*すべてのユーザー* のリンクのアクセス許可と有効期限のオプションを設定することもできます。

**ナビゲーション:** [SharePoint 管理センター] > **[ポリシー]**  > ><a href="https://go.microsoft.com/fwlink/?linkid=2185222" target="_blank"> **[共有]**</a>

![SharePoint における組織レベルのファイルとフォルダー共有設定のスクリーンショット](../media/sharepoint-organization-files-folders-sharing-settings.png)

| 設定 | 既定値 | 説明 |
|:-----|:-----|:-----|
|ファイルとフォルダーのリンク|リンクを知っているすべてのユーザー|ユーザーがファイルまたはフォルダーを共有するときに、既定で表示される共有リンクを指定します。 ユーザーは必要に応じて、共有する前にオプションを変更できます。 既定値が **[リンクを知っているすべてのユーザー]** に設定されており、*[すべてのユーザー]* の共有が特定のサイトで許可されていない場合は、**組織内のユーザーのみ** がそのサイトの既定値として表示されます。|
|これらのリンクは指定された日数以内に有効期限が切れる|オフ (有効期限なし)|*[すべてのユーザー]* のリンクが作成されてから期限切れになるまでの日数を指定します。 期限切れのリンクは更新できません。 期限が切れた後も共有を続ける必要がある場合は、新しいリンクを作成します。|
|ファイルのアクセス許可|表示と編集|ユーザーが *[すべてのユーザー]* のリンクを作成するときに使用できるファイルのアクセス許可のレベルを指定します。 **[表示]** が選択されている場合、ユーザーは、表示のアクセス許可のある *[すべてのユーザー]* ファイルのリンクのみを作成できます。 **[表示と編集]** が選択されている場合、ユーザーはリンクを作成するときに、[表示] と [表示と編集] のアクセス許可の中から選択できます。|
|フォルダーのアクセス許可|表示、編集、およびアップロード|ユーザーが *[すべてのユーザー]* のリンクを作成するときに使用できるフォルダーのアクセス許可のレベルを指定します。 **[表示]** が選択されている場合、ユーザーは、表示のアクセス許可のある *[すべてのユーザー]* フォルダーのリンクのみを作成できます。 **[表示、編集、およびアップロード]** が選択されている場合、ユーザーはリンクを作成するときに、[表示] と [表示、編集、およびアップロード] のアクセス許可の中から選択できます。|

## <a name="sharepoint-site-level"></a>SharePoint (サイト レベル)

**管理者ロール:** SharePoint 管理者

これらの設定は SharePoint における組織全体の設定の対象になるため、組織レベルの設定が変更された場合は、サイトで有効な共有設定が変更される可能性があります。 ここで設定を選択し、組織レベルがより制限の多い値に設定された場合、このサイトはその制限の多い値で動作します。 たとえば、**[すべてのユーザー]** を選択した後に、組織レベルの設定を **[新規および既存のゲスト]** に設定した場合、このサイトでは新規および既存のゲストのみが許可されます。 組織レベルの設定を **[すべてのユーザー]** に戻すと、このサイトでは *[すべてのユーザー]* のリンクが再度許可されます。

### <a name="site-sharing"></a>サイトの共有

SharePoint の各サイトにゲストの共有のアクセス許可を設定できます。 この設定は、サイトの共有と、ファイルとフォルダーの共有の両方に適用されます (*[すべてのユーザー]* の共有はサイトの共有には利用できません)。 **[すべてのユーザー]** を選択した場合、ユーザーは *[すべてのユーザー]* のリンクを使用してファイルとフォルダーを、新規および既存のゲストとはサイト自体を共有できます)。

サイトに機密ラベルが適用されている場合、そのラベルが外部共有設定を制御する場合があります。 詳細については、「[機密ラベルを使用して、Microsoft Teams、Office 365 グループ、SharePoint サイトのコンテンツを保護する](../compliance/sensitivity-labels-teams-groups-sites.md)」 をご覧ください。

> [!NOTE]
> チャネル サイトの共有設定は、[Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) PowerShell コマンドレットを使用してのみ変更できます。

**ナビゲーション:** SharePoint 管理センター > <a href="https://go.microsoft.com/fwlink/?linkid=2185220" target="_blank">**[アクティブなサイト]**</a> > サイトを選択 > **[ポリシー]** タブ > **[外部共有の編集]**

![SharePoint サイトの外部共有設定のスクリーンショット](../media/sharepoint-site-external-sharing-settings.png)

| 設定 | 既定値 | 説明 |
|:-----|:-----|:-----|
|サイトのコンテンツの共有先|サイトの種類によって異なります (次の表を参照してください)|このサイトに許可されている外部共有の種類を示します。 ここで使用できるオプションは、SharePoint における組織レベルの共有設定の対象です。|

### <a name="site-file-and-folder-link-settings"></a>サイトのファイルとフォルダーのリンク設定

リンクの種類とアクセス許可の既定値と、各サイトの [*すべてのユーザー*] リンクの有効期限を設定できます。 サイト レベルで設定した場合、これらの設定は組織レベルの設定に優先します。 [*すべてのユーザー*] リンクが組織レベルで無効に設定されている場合、[*すべてのユーザー*] はサイト レベルで使用可能なリンクの種類として含まれません。

**ナビゲーション:** SharePoint 管理センター > <a href="https://go.microsoft.com/fwlink/?linkid=2185220" target="_blank">**[アクティブなサイト]**</a> > サイトを選択 > **[ポリシー]** タブ > **[外部共有の編集]**

![SharePoint のサイト レベルのリンク共有設定のスクリーンショット](../media/sharepoint-site-link-sharing-settings.png)

| 設定 | 既定値 | 説明 |
|:-----|:-----|:-----|
|ドメイン共有を制限する|オフ|この設定では、共有するドメインの許可またはブロックのリストを指定できます。 許可されたドメインを指定すると、共有の招待をそのドメインにのみ送信できます。 拒否されたドメインを指定すると、共有の招待はそのドメインに送信できません。 <p> この設定は、組織レベルまたは Azure AD レベルで設定されているドメインの制限を上書きするためには使用できません。|
|既定の共有リンクの種類|組織レベルの設定と同じ|この設定は、このサイトでユーザーに表示される既定の共有リンクを指定するために使用できます。 [*組織レベルの設定と同じ*] オプションは、組織とサイトの共有設定の組み合わせによって定義されます。|
|[すべてのユーザー] リンクの詳細設定|組織レベルの設定と同じ|このサイトのファイル用に [*すべてのユーザー*] のリンクが作成されてから期限切れになるまでの日数を指定します。 期限切れのリンクは更新できません。 期限が切れた後も共有を続ける必要がある場合は、新しいリンクを作成します。|
|既定のリンクのアクセス許可|組織レベルの設定と同じ|この設定は、このサイトのファイル用に作成された共有リンクの既定のアクセス許可 ([閲覧] または [編集]) を指定するために使用できます。|

### <a name="default-site-sharing-settings"></a>既定のサイト共有設定

次の表は、各サイトの種類の既定の共有設定を示しています。

| サイトの種類 | 既定の共有設定 |
|:-----|:-----|
|クラシック|**組織内のユーザーのみ**|
|OneDrive|**すべてのユーザー**|
|グループに接続されたサイト (チームを含む)|Microsoft 365 グループの設定の、**[グループ所有者が組織外のユーザーをグループに追加できるようにする]** が **[オン]** の場合、**[新規および既存のゲスト]** になり、オフの場合は **[既存のゲストのみ]** になります。|
|コミュニケーション|**組織内のユーザーのみ**|
|グループのないモダン サイト (#STS3 TeamSite)|**組織内のユーザーのみ**|

> [!NOTE]
> ルート通信サイト (tenant-name.sharepoint.com) には、**すべてのユーザー** の既定の共有設定があります。

## <a name="see-also"></a>関連項目

[SharePoint と OneDrive の外部共有の概要](/sharepoint/external-sharing-overview)

[Microsoft Teams でのゲスト アクセス](/MicrosoftTeams/guest-access)

[Microsoft 365 グループへのゲストの追加](https://support.office.com/article/bfc7a840-868f-4fd6-a390-f347bf51aff6)
