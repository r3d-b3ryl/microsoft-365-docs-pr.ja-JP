---
title: 移行フェーズアクションと Microsoft Cloud Deutschland からの移行に対する影響)
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 03/05/2021
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: '概要: Microsoft Cloud Germany (Microsoft Cloud Deutschland) から新しいドイツデータセンター地域の Office 365 サービスへの移行フェーズのアクションと影響について説明します。'
ms.openlocfilehash: 5764b5cedf17487320fbfd05885120de86da3a84
ms.sourcegitcommit: e02cf5702af178ddd2968877a808874ecb49ed2c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2021
ms.locfileid: "52029064"
---
# <a name="migration-phases-actions-and-impacts-for-the-migration-from-microsoft-cloud-deutschland"></a>移行フェーズアクションと Microsoft Cloud Deutschland からの移行に対する影響

Microsoft Cloud Deutschland (MCD) から Microsoft の Office 365 グローバル サービスの地域 "ドイツ" へのテナント移行は、一連のフェーズと、ワークロードごとに構成されたアクションとして実行されます。 この図は、新しいドイツのデータセンターへの移行の 10 フェーズを示しています。

![新しいドイツのデータセンターへの移行の 10 フェーズ](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

移行プロセスは、組織の全体的な規模と複雑さによって、何週間にも渡って完了します。 移行が進行中の間、ユーザーと管理者は、このドキュメントで詳しく説明されている変更点を使用して、サービスを引き続き利用できます。 グラフィックとテーブルは、移行中のフェーズと手順を定義します。

|手順|Duration|責任ある当事者|説明|
|:--------|:--------|:--------|:--------|
|Opt-In|時間|顧客|組織に移行を選択します。|
|プレワーク|Days|顧客|ユーザー、ワークステーション、およびネットワークを移行用に準備するために必要な作業を完了します。|
|Azure Active Directory (Azure AD)|1~ 2 日|Microsoft|Azure AD組織を世界中に移行します。|
|Azure|週|顧客|新しい世界中の Azure サブスクリプションを作成し、Azure サービスを移行します。|
|サブスクリプション&ライセンス移行|1~ 2 日|Microsoft|世界中のサブスクリプションを購入し、Microsoft Cloud Deutschland サブスクリプションをキャンセルし、ユーザー ライセンスを移行します。|
|SharePoint および OneDrive|15 日以上|Microsoft|SharePoint と OneDrive for Business コンテンツを移行し、URL sharepoint.de 保持します。|
|Exchange Online|15 日以上|Microsoft|Exchange Online コンテンツを移行し、世界中の URL に移行します。|
|セキュリティとコンプライアンス|1~ 2 日|Microsoft|コンプライアンス ポリシー&コンテンツに対するセキュリティの移行。|
|Skype for Business|1~ 2 日|Microsoft|Skype for Business から Microsoft Teams への移行。|
|Power BI & Dynamics 365|15 日以上|Microsoft|Power BI および Dynamics 365 コンテンツを移行します。|
|Azure の最終AD|1~ 2 日|Microsoft|テナントを世界中に切り替えます。|
|Clean-Up|1~ 2 日|顧客|Active Directory フェデレーション サービス (AD FS) 証明書利用者信頼、Azure AD Connect、および Office クライアントの再起動など、Microsoft Cloud Deutschland への従来の接続をクリーンアップします。|
|エンドポイントが無効|30 日間|Microsoft|Azure AD の最終決定から 30 日後、Microsoft Cloud Deutschland Azure AD サービスは移行された組織のエンドポイント アクセスを停止します。 認証などのエンドポイント要求は、Microsoft Cloud Deutschland サービスに対してこの時点から順方向に失敗します。 |


フェーズとそのアクションにより、重要なデータとエクスペリエンスが 365 グローバル Officeに移行されます。 テナントが移行キューに追加されると、各ワークロードは、バックエンド サービスで実行される一連の手順として完了します。 一部のワークロードでは、管理者 (またはユーザー) によるアクションが必要な場合や、移行が実行および説明されているフェーズの使用状況に影響を与える場合があります。「移行の整理方法」を [参照してください。](ms-cloud-germany-transition.md#how-is-the-migration-organized)

次のセクションには、移行のさまざまなフェーズを進むワークロードのアクションと効果が含まれています。 表を確認し、組織に適用できるアクションまたは効果を決定します。 必要に応じて、それぞれのフェーズで手順を実行する準備ができているか確認します。 必要な手順を完了できないと、サービスが停止し、365 サービスへの移行がOffice可能性があります。

## <a name="phase-opt-in"></a>フェーズ: Opt-In

**適用** 対象: Microsoft Cloud Deutschland (MCD) でホストされている Office 365 テナントを持つすべてのお客様は、同意なしに MCD でホストされている Office 365 テナントを移行できません。

| Step(s) | 説明 | 影響 |
|:-------|:-----|:-------|
|**顧客タスク**: 移行に対する同意の付与| お客様は、移行に関する同意を付与し、Microsoft がデータとサービスの移行を Office 365 Global Services インスタンスに移行する権利を取得します。 2 つの方法があります <ol><li>365 Office管理者は、Microsoft が駆動する移行にオプトインします。 </li><li> 2020 年 5 月 1 日以降、MCD Office 365 テナントのサブスクリプションが更新されました。 Microsoft は、毎月移行の権利をこれらのお客様に通知し、30 日待って顧客にキャンセルの機会を与え、その後直接オプトインします。</li></ol> | <ul><li>テナントは移行に同意済みとしてマークされ、管理センターには確認が表示されます。 </li><li>受信確認は、Office 365 テナント メッセージ センターに投稿されます。 サービス構成は、Microsoft Cloud Deutschland エンドポイントから続行されます。 </li><li> </li></ul>
|**テナント管理者**: メッセージの監視|テナント管理者は、365 メッセージ センター Office、この時点からの移行フェーズの状態に関する更新プログラムを監視する必要があります。|顧客は必要なタスクを時間内に実行できます。
||||

## <a name="phase-1-before-the-migration-starts"></a>フェーズ 1: 移行を開始する前に

すべての顧客に適用される移行準備手順をよく理解 [してください](ms-cloud-germany-transition-add-pre-work.md)。

所有する 1 つ以上の DNS 名前空間に _msoid_ という DNS CNAME を設定した場合は、最新のフェーズ 8 の終了まで CNAME を削除する必要があります。 フェーズ 8 の終了前にいつでも CNAME _msoid_ を削除できます。 DNS の [事前作業を参照してください](ms-cloud-germany-transition-add-pre-work.md#dns-entries-for-custom-domains)。

microsoft Cloud Deutschland インスタンスで Office 365 および Azure にシングル サインオンを使用している場合は、Azure サブスクリプションの移行を準備し、スケジュールする必要があります。 Microsoft Azure の事前作業 [を理解してください](ms-cloud-germany-transition-add-pre-work.md#microsoft-azure)。

### <a name="azure-ad-connect-with-ad-fs-federation"></a>Azure AD FS フェデレーションAD接続する
**適用対象**: FS フェデレーションを使用ADユーザー

**適用時**: フェーズ 2 が開始される前

Active Directory フェデレーション サービス (AD FS) を使用している場合は、フェーズ 2 の開始前に、Office 365 グローバル サービスの証明書利用者信頼を追加する前と後に[、ADFS](ms-cloud-germany-transition-azure-ad.md)構成をバックアップしてください。

## <a name="phase-2-azure-ad-migration"></a>フェーズ 2: Azure AD移行
このフェーズでは、Azure Active Directory が新しいデータセンター領域に移行され、アクティブになります。 古い Azure ADエンドポイントは引き続き使用できます。

### <a name="exchange-online-hybrid---modify-authserver-on-premises"></a>Exchange Online ハイブリッド - オンプレミスの AuthServer の変更
**適用対象:** オンプレミスの Exchange サーバーでアクティブな Exchange ハイブリッド構成を使用しているすべてのお客様

**適用時**: フェーズ 2 の終了後

Azure の移行が完了した後、認証のために、オンプレミスの AuthServer がグローバル セキュリティ トークン サービス (STS) をAD必要があります。
これにより、ハイブリッドオンプレミス環境を対象とする移行状態のユーザーからの Exchange 可用性要求に対する認証要求が、オンプレミス サービスにアクセスするために認証されます。 同様に、これにより、オンプレミスから 365 のグローバル サービス エンドポイントへのOffice認証が保証されます。 Azure AD移行 (フェーズ 2) が完了したら、オンプレミス Exchange (ハイブリッド) トポロジの管理者は、Office 365 グローバル サービス用の新しい認証サービス エンドポイントを追加する必要があります。 Exchange PowerShell のこのコマンドを使用して、Azure Active Directory の Azure portal にある組織のテナント `<TenantID>` ID に置き換える。

```powershell
New-AuthServer GlobalMicrosoftSts -AuthMetadataUrl https://accounts.accesscontrol.windows.net/<TenantID>/metadata/json/1
```

このタスクを完了できないと、Microsoft Cloud Deutschland から Office 365 サービスに移行されたメールボックス ユーザーの情報をハイブリッド空き時間要求で提供できない場合があります。

## <a name="phase-3-subscription-transfer"></a>フェーズ 3: サブスクリプションの転送

**適用対象**: Microsoft Cloud Deutschland (MCD) でホストOffice 365 テナントを持つすべてのお客様

パートナーの Microsoft Cloud Deutschland テナントは移行されません。 CSP のお客様は、同Officeの新しいサービス 365 サービス テナントOffice 365 サービスに移行されます。 顧客の移行後、パートナーは 365 サービス テナントOfficeこの顧客を管理できます。

| Step(s) | 説明 | 影響 |
|:-------|:-------|:-------|
| サブスクリプションが転送される| Microsoft Cloud Deutschland サブスクリプションは、対応する 365 Global services サブスクリプションOfficeに移行されます。 <ul><li>このサブスクリプションOffice 365 Global Services オファーは、Microsoft (オファー マッピングとも呼ばれる) _によって定義されます_。</li><li> 対応Office 365 グローバル サービス サブスクリプションは、転送された Microsoft Cloud Deutschland サブスクリプションの Office 365 Global インスタンスで購入されます。</li><li>従来の Microsoft Cloud Deutschland サブスクリプションは、Office 365 サービス テナントから削除されます。</li></ul>| <ul><li>既存のサブスクリプションへの変更は、このフェーズ中にブロックされます (たとえば、新しいサブスクリプション購入やシート 数の変更はありません)。</li><li>ライセンス割り当ての変更はブロックされます。</li><li>サブスクリプションの移行が完了すると、Office 365 サービスと Microsoft Cloud Deutschland サブスクリプションの両方が Office 365 管理ポータルに表示され、Microsoft Cloud Deutschland サブスクリプションの状態がプロビジョニング解除されます。 </li><li>Microsoft Cloud Deutschland サブスクリプションまたは SKU GUID に依存しているすべての顧客プロセスは壊れ、Office 365 サービスを提供して修正する必要があります。 </li><li>Office 365 サービスの新しいサブスクリプションは、新しい用語 (毎月/四半期/年) で購入され、お客様は Microsoft Cloud Deutschland サブスクリプションの未使用残高に対して日割り払い払いを受け取る予定です。 </li></ul> |
|ライセンスが再割り当てされる|割り当てられた Microsoft Cloud Deutschland ライセンスを持つユーザーには、365 Global インスタンスOfficeライセンスが割り当てられます。|<ul><li>ユーザーは、新しい 365 サービス サブスクリプションに関連付Office再割り当てされます。 すべてのユーザーのユーザー ライセンスが新しい機能に自動的に割り当てられます。</li><li>365 サービスによって提供される機能 (サービス プラン) の数は、Office Microsoft Cloud Deutschland オファーよりも大きくなる可能性があります。 365 サービスOfficeユーザー ライセンスは、同様の Microsoft Cloud Deutschland 機能 (サービス プラン) と同等に割り当てられます。 </li></ul> 
|**管理タスク** 機能を無効にする|管理者は、必要に応じて、これらの機能を無効にする明示的なアクションを実行する必要があります。 |<ul><li>ユーザーがポータルに新しい不明なサービスを表示する</li><li>テナント管理者が無効にしない限り、追加の機能 (Microsoft Planner や Microsoft Flow など) を使用できます。ユーザーのライセンスに割り当てられているサービス プランを無効にする方法については、「ユーザー ライセンスの割り当て中に [Microsoft 365](disable-access-to-services-while-assigning-user-licenses.md)サービスへのアクセスを無効にする」を参照してください。</li></ul>
|**管理タスク**|Microsoft Cloud Deutschland サブスクリプションまたは SKU GUID に依存する顧客プロセスを、365 サービスの提供Office変更する|顧客プロセスは引き続き機能します。
||||

**適用対象**: Microsoft パートナー 365 パートナー Office使用している

フェーズ 2 とフェーズ 3 の間、パートナー ポータルにアクセスできない場合があります。 この間、パートナーはパートナー ポータルでテナントの情報にアクセスできない場合があります。 移行ごとに異なるので、アクセシビリティ内の期間は数時間である可能性があります。


## <a name="phase-4-sharepoint-online"></a>フェーズ 4: SharePoint Online

**適用対象**: SharePoint Online を使用しているすべてのお客様

引き続き SharePoint 2013 ワークフローを使用している場合は、SharePoint Online の移行中に SharePoint 2013 ワークフローの使用を制限します。

| Step(s) | 説明 | 影響 |
|:-------|:-----|:-------|
| SharePoint と OneDrive が移行される | SharePoint Online と OneDrive for Business は、このフェーズで Microsoft Cloud Deutschland から Office 365 グローバル サービスに移行されます。<br><ul><li>既存の Microsoft Cloud Deutschland URL は保持されます (たとえば `contoso.sharepoint.de` )。</li><li>既存のサイトは保持されます。</li><li>Microsoft Cloud Deutschland または Office 365 Global services インスタンスのセキュリティ トークン サービス (STS) によって発行されたクライアント側認証トークンは、移行中に有効です。</li></ul>|<ul><li>移行中の 2 つの短い期間、コンテンツは読み取り専用になります。 この間、SharePoint で "コンテンツを編集できない" バナーが表示されます。</li><li>検索インデックスは保持されません。再構築には最大 10 日かかる場合があります。</li><li>SharePoint Online および OneDrive for Business コンテンツは、移行中に 2 つの短い期間の読み取り専用になります。 この間、ユーザーには「コンテンツを編集できない」バナーが簡単に表示されます。</li><li>SharePoint Online の移行が完了すると、インデックスの再構築中に SharePoint Online および OneDrive for Business コンテンツの検索結果が使用できなくなる場合があります。 この期間中、検索クエリで完全な結果が返されない場合があります。 SharePoint Online News などの検索インデックスに依存する機能は、インデックスの再作成が完了する間に影響を受ける可能性があります。</li><li>SharePoint 2013 ワークフローは移行中に壊れ、移行後に再発行する必要があります。</li></ul>
|**SPO 管理者**: SharePoint 2013 ワークフローを再発行する| SharePoint Online 管理者は、移行後に SharePoint 2013 ワークフローを再発行します。|SharePoint 2013 ワークフローを使用できます。
|**PowerShell ユーザー**: 新しいモジュールに更新する| SharePoint Online Powershell モジュールのすべてのユーザーは、SharePoint Online の移行が完了した後、モジュール/Microsoft.SharePointOnline.CSOM をバージョン 16.0.20717.12000 以上に更新する必要があります。 完了はメッセージ センターで伝達されます。| PowerShell またはクライアント側オブジェクト モデル経由の SharePoint Online は失敗しなくなりました。
||||

その他の考慮事項:

- 組織で引き続き SharePoint 2010 ワークフローを使用している場合、2021 年 12 月 31 日以降は機能しなくなりました。 SharePoint 2013 ワークフローは引き続きサポートされます。ただし、2020 年 11 月 1 日から新しいテナントでは既定でオフになっています。 SharePoint Online サービスへの移行が完了したら、Power Automate または他のサポートされているソリューションに移動することをお勧めします。
 - SharePoint Online インスタンスがまだ移行されていない Microsoft Cloud Deutschland のお客様は、SharePoint Online PowerShell モジュール/Microsoft.SharePointOnline.CSOM バージョン 16.0.20616.12000 以下に滞在する必要があります。 それ以外の場合、PowerShell またはクライアント側のオブジェクト モデルを介して SharePoint Online への接続が失敗します。
- このフェーズでは、SharePoint URL の背後にある IP アドレスが変更されます。 Office 365 グローバル サービスに移行すると、保持されているテナント URL (たとえば、および) のアドレスがワールドワイド Microsoft 365 URL および IP アドレス範囲 `contoso.sharepoint.de` `contoso-my.sharepoint.de` [(SharePoint Online および OneDrive for Business)](/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide#sharepoint-online-and-onedrive-for-business)に変更されます。

> [!NOTE]
> 電子情報開示を使用している場合は、電子情報開示の移行エクスペリエンスを [認識してください](ms-cloud-germany-transition-add-scc.md)。

## <a name="phase-5-exchange-online"></a>フェーズ 5: Exchange Online 
フェーズ 5 より、Exchange Online メールボックスは Microsoft Cloud Deutschland から 365 Global services Officeに移動されます。

365 Officeグローバル サービス領域は既定として設定され、内部負荷分散サービスはメールボックスを 365 サービス内の適切な既定の領域に再配布Officeできます。 この移行では、どちらの側 (MCD またはグローバル サービス) のユーザーも同じ組織内にいて、いずれかの URL エンドポイントを使用できます。

新しい地域 "ドイツ" が組織のセットアップに追加されます。 Exchange Online の構成では、移行中の組織に新しい移動先のドイツ語地域が追加されます。

- ユーザーとサービスを従来の MCD URL ( ) から新しいサービス `https://outlook.office.de` 365 Office URL ( ) に移行します `https://outlook.office365.com` 。
-  新しいドイツのデータセンター地域の Exchange Online サービス (Outlook Web Access および Exchange 管理センター) は、このフェーズから利用できます。以前は利用できません。
- ユーザーは移行中に従来の MCD URL を通じてサービスに引き続きアクセスすることができますが、移行が完了すると、従来の URL の使用を停止する必要があります。
- ユーザーは、オンライン機能 (予定表、メールOfficeユーザー) Office のOfficeポータルを使用するに移行する必要があります。 365 サービスにまだ移行されていないサービスOffice移行するまでは機能しません。 
- この制限は、"My Account" などのバックグラウンド サービスにも適用されます。 グローバル サービスのアカウントは、フェーズ 9 の完了後に利用できます。 この場合、ユーザーは MCD ポータルを使用してアカウント設定を管理する必要があります。
- 移行Outlook Web Appパブリック フォルダーエクスペリエンスは提供しない場合があります。

フェーズ 5 の間にユーザーの写真を変更する場合は [、「Exchange Online PowerShell -](#exchange-online-powershell)フェーズ 5 のSet-UserPhotoを参照してください。

### <a name="dns-record-for-autodiscover-in-exchange-online"></a>Exchange Online での自動検出の DNS レコード
**適用対象:** カスタム ドメインで Exchange Online を使用しているお客様

現在 Microsoft Cloud Deutschland を指している自動検出の顧客管理 DNS 設定は、Exchange Online フェーズ (フェーズ 5) の完了時に Office 365 グローバル エンドポイントを参照するために更新する必要があります。 <br> CNAME を指す既存の DNS エントリは、autodiscover-outlook.office.de をポイントするために更新する **autodiscover.outlook.com。**

移行フェーズ **9** の完了時にこれらの DNS 更新プログラムを実行しないお客様は、移行が完了するとサービスの問題が発生する可能性があります。

> [!NOTE]
> 自動検出エントリのカスタム ドメインの管理センターの検証エラーは無視できます。 サービスは、CNAME レコードが新しいレコードに変更された場合にのみ autodiscover.outlook.com。

### <a name="exchange-online-powershell"></a>Exchange Online PowerShell
**適用対象:** Exchange Online PowerShell を使用する Exchange Online 管理者

移行フェーズ中に、PowerShell コマンドレット **New-MigrationEndpoint、Set-MigrationEndpoint、** および **Test-MigrationsServerAvailability** を使用すると、エラー (プロキシでエラー) が発生する可能性があります。  これは、調停メールボックスが世界中に移行されたが、管理者メールボックスが移行または逆の場合に発生します。 これを解決するには、テナント PowerShell セッションの作成中に **、ConnectionUri** のルーティング ヒントとして調停メールボックスを使用します。 例:

```powershell
New-PSSession 
    -ConfigurationName Microsoft.Exchange 
    -ConnectionUri "https://outlook.office365.com/powershell-liveid?email=Migration.8f3e7716-2011-43e4-96b1-aba62d229136@<tenant>.onmicrosoft.de"
    -Credential $UserCredential
    -Authentication Basic
    -AllowRedirection
```
PowerShell コマンドレット **Set-UserPhoto** を使用すると、ユーザー メールボックスが移行されたが管理者メールボックスが移行されていない場合、またはその逆の場合はエラーが発生します。 このような場合、管理者は、テナント PowerShell セッションの作成中に写真を変更する必要があるユーザーの電子メール ID を `ConnectionUri` 渡す必要があります。 
```powershell
-ConnectionUri "https://outlook.office.de/powershell-liveid?email=<user_email>" 
```
 ここで `<user_email>` 、ユーザー メールボックスの電子メール ID のプレースホルダーを指定します。 

その他の考慮事項:
- 他のOutlook Web Appの共有メールボックスにアクセスするユーザー (たとえば、MCD 環境のユーザーがグローバル環境の共有メールボックスにアクセスする場合など) は、2 回目の認証を求めるメッセージが表示されます。 ユーザーは、最初に自分のメールボックスを認証してアクセスし、次に共有メールボックスを `outlook.office.de` 開く必要があります `outlook.office365.com` 。 他のサービスでホストされている共有リソースにアクセスする場合は、2 回目の認証が必要です。
- 既存の Microsoft Cloud Deutschland のお客様または移行中のユーザーの場合、ファイル > **Info >** Add Account を使用して共有メールボックスを Outlook に追加すると、予定表のアクセス許可の表示が失敗する場合があります (Outlook クライアントは Rest API の使用を試みる)。 `https://outlook.office.de/api/v2.0/Me/Calendars` 予定表のアクセス許可を表示するアカウントを追加する場合は [、「Outlook](https://support.microsoft.com/office/user-experience-changes-for-sharing-a-calendar-in-outlook-5978620a-fe6c-422a-93b2-8f80e488fdec) で予定表を共有するためのユーザー エクスペリエンスの変更」の説明に従ってレジストリ キーを追加して、このアクションが成功するようにすることができます。 このレジストリ キーは、グループ ポリシーを使用して組織全体に展開できます。
- アクティブな Exchange ハイブリッド構成を使用しているすべてのお客様は、メールボックスをオンプレミス Exchange Server から Exchange Online に移動することはできません。Microsoft Cloud Deutschland にも、ドイツの新しいデータセンター地域にも移動できません。 お客様は、フェーズ 5 より前に継続的なメールボックスの移動が完了し、このフェーズが完了した後に再開される必要があります。
- Exchange Online の移行前の手順で説明したように、デバイスにレガシ プロトコル (POP3/IMAP4/SMTP) を使用しているすべてのユーザーが [、Exchange](ms-cloud-germany-transition-add-pre-work.md#exchange-online)メールボックスが新しいドイツのデータセンター地域に移動された後にクライアントのエンドポイントを変更する準備ができているか確認します。
- メールボックスの移行後、Outlook Web App Skype for Business 会議をスケジュールすることはできません。 必要に応じて、ユーザーは代わりに Outlook を使用する必要があります。

移行および Exchange Online リソースの移行後の組織の違いの詳細については、「新しいドイツのデータセンター地域の [Office 365](ms-cloud-germany-transition-experience.md)サービスへの移行中のカスタマー エクスペリエンス」の情報を確認してください。

## <a name="phase-6-exchange-online-protection--security-and-compliance"></a>フェーズ 6: Exchange Online Protection / Security and Compliance

**適用対象:** Exchange Online を使用しているすべてのお客様<br>

Exchange Online Protection (EOP) のバック エンド機能は、新しい地域 "ドイツ" にコピーされます。 Exchange Online を使用すると、外部ホストから Office 365 へのルーティングが可能で、テナントの履歴の詳細が移行されています。これには、セキュリティおよびコンプライアンス機能のバック エンド サービスも含まれます。

Exchange Online 機能のみを使用しているお客様 (ハイブリッド以外) は、この段階で注意を払う必要があります。

### <a name="exchange-online-hybrid-deployments"></a>Exchange Online ハイブリッド展開
**適用対象:** オンプレミスの Exchange サーバーでアクティブな Exchange ハイブリッド構成を使用しているすべてのお客様

移行手順 [5 が](ms-cloud-germany-transition-add-pre-work.md#exchange-online-hybrid-customers) 開始する前に Exchange の事前作業 **が適用済みである必要があります**。 Exchange Online ハイブリッドのお客様は、「Office 365 Germany」モードで Exchange ハイブリッド構成ウィザード (HCW) の最新バージョンを実行して、Office 365 グローバル サービスへの移行用のオンプレミス構成を準備する必要があります。

**管理アクション:**
- 移行フェーズ 6 の開始と移行フェーズ 9 の完了 (メッセージ センター通知が公開されている場合) の間に、Office 365 Worldwide 設定を使用して HCW を再度実行して、オンプレミス システムを Office 365 グローバル サービスに接続する必要があります。 フェーズ 9 [移行の完了] の前にこのタスクを完了できなかった場合、オンプレミスの Exchange 展開と 365 の間でルーティングされるメールの NDRs Officeがあります。
- オンボーディングメールボックスまたはオフボードメールボックスの移動を停止または削除します。Exchange オンプレミスと Exchange Online の間でメールボックスを移動しない。  これにより、メールボックスの移動要求がエラーと一緒に失敗しない。 そうしない場合は、サービスまたはクライアントのOfficeがあります。
- HCW Send-Connectors作成され、Exchange Online を対象とするコネクタ以外に作成された追加のサーバーは、HCW の実行が実行された直後にこのフェーズで更新する必要があります。それ以外の場合は動作を停止します。 これらの送信コネクタの TLS ドメインを更新する必要があります。 <br> TLS ドメインを更新するには、次の PowerShell コマンドを使用して、Exchange Serverします。
```powershell
Set-SendConnector -Identity <SendConnectorName> -TlsDomain "mail.protection.outlook.com"
```

## <a name="phase-7-skype-for-business-online"></a>フェーズ 7: Skype for Business Online

**適用対象:** Skype for Business Online を使用しているすべてのお客様

Skype [for Business Online 移行の移行前の手順を確認](ms-cloud-germany-transition-add-pre-work.md#skype-for-business-online) し、すべての手順を完了してください。
このフェーズでは、Skype for Business が Microsoft Teams に移行されます。 既存の Skype for Business のお客様は、ヨーロッパの Office 365 グローバル サービスに移行され、Office 365 サービスの地域 "ドイツ" の Microsoft Teams に移行されます。

- ユーザーは移行日に Skype for Business にサインインできない。 移行の 10 日前に、移行がいつ行われますか、また移行が開始されたときに再び通知するメッセージが管理センターに表示されます。
- ポリシー構成が移行されます。
- ユーザーは Teams に移行され、移行後に Skype for Business にアクセスできなくなりました。
- ユーザーには、Microsoft Teams デスクトップ クライアントがインストールされている必要があります。 インストールは、Skype for Business インフラストラクチャのポリシーを介して 10 日間に行われますが、失敗した場合でも、ユーザーはクライアントをダウンロードするか、サポートされているブラウザーに接続する必要があります。
- 連絡先と会議は Microsoft Teams に移行されます。
- タイム サービスが Office 365 サービスに移行するまで、顧客の DNS エントリが完了するまで、ユーザーは Skype for Business にサインインできない。
- 連絡先と既存の会議は、引き続き Skype for Business 会議として機能します。
- Microsoft Teams の Web ブラウザー バージョンは、フェーズ 9 が完了するまで機能しません。

移行フェーズ 9 の完了後に PowerShell を使用して Skype for Business Online に接続する必要がある場合は、次の PowerShell コードを使用して接続します。

```powershell
Import-Module MicrosoftTeams
$userCredential = Get-Credential
Connect-MicrosoftTeams -Credential $userCredential -OverridePowershellUri "https://admin4E.online.lync.com/OcsPowershellOAuth"
```

## <a name="phase-8-dynamics-365"></a>フェーズ 8: Dynamics 365

**適用対象:** Microsoft Dynamics 365 を使用しているすべてのお客様

[Microsoft Dynamics 365](ms-cloud-germany-transition-add-pre-work.md#dynamics365)のインストール手順の事前作業について理解している必要があります。

Dynamics 365 をお持ちのお客様は、組織の Dynamics 組織を個別に移行するために追加の契約が必要です。

| Step(s) | 説明 | 影響 |
|:-------|:-------|:-------|
| Microsoft Dynamics リソース | Microsoft Dynamics をお持ちのお客様は、Microsoft Engineering または Microsoft FastTrack が Microsoft Dynamics 365 を Office 365 Global services インスタンスに移行します。* |<ul><li>移行後、管理者は組織を検証します。 <</li><li>管理者は、必要に応じてワークフローを変更します。 </li><li>管理者は、必要に応じて AdminOnly モードをクリアします。</li><li>管理者は、必要に応じて _サンドボックスから組織_ の種類を変更します。</li><li>インスタンス (org) にアクセスする新しい URL をエンド ユーザーに通知します。</li><li>新しいエンドポイント URL への受信接続を更新します。 </li><li>移行中は、ユーザーが Dynamics サービスを利用できません。 </li><li>ユーザーは、各組織の移行後に組織の正常性と機能を検証する必要があります。</li></ul>|
||||

\* (i) Microsoft Dynamics 365 をお持ちのお客様は、提供される移行プロセスで定義されているこの移行シナリオでアクションを実行する必要があります。 (ii) お客様がアクションを実行できなかった場合、Microsoft は移行を完了できません。 (iii) お客様の不作為により Microsoft が移行を完了できない場合、お客様のサブスクリプションは 2021 年 10 月 29 日に期限切れになります。

## <a name="phase-8-power-bi"></a>フェーズ 8: Power BI

**適用対象:** Microsoft Power BI (PBI) を使用しているすべてのお客様

| Step(s) | 説明 | 影響 |
|:-------|:-------|:-------|
| Power BI リソースの移行 | Microsoft Power BI (PBI) をお持ちのお客様は、既存の PBI 移行ツールを手動でトリガーして Power BI を Office 365 グローバル サービス インスタンスに移行した後、Microsoft Engineering または Microsoft FastTrack に参加します。\*\* |<ul><li>次の Power BIアイテムは移行されないので、次のアイテムを再作成する必要<</li><li>リアルタイム データセット (ストリーミング データセットやプッシュ データセットなど)。 </li><li>Power BI オンプレミス データ ゲートウェイの構成とデータ ソース。 </li><li>リアルタイム データセットの上に構築されたレポートは、移行後に使用できないので、再作成する必要があります。 </li><li>Power BI サービスは、移行中にユーザーが利用できません。 サービスが利用できない時間は 24 時間を超えてはならない。</li><li>移行後、ユーザーは Power BI サービスを使用してデータ ソースとオンプレミス のデータ ゲートウェイを再構成する必要があります。  そうするまで、ユーザーは、これらのデータ ソースを使用して、スケジュールされた更新を実行したり、これらのデータ ソースに対して直接クエリを実行したりすることはできません。 </li><li>容量とプレミアム ワークスペースは移行できません。 移行前にすべての容量を削除し、移行後に再作成する必要があります。 ワークスペースを必要に応じて容量に戻します。</li></ul>  |
||||

\*\* (i) Microsoft Power BI をお持ちのお客様は、提供される移行プロセスで定義されているこの移行シナリオでアクションを実行する必要があります。 (ii) お客様がアクションを実行できなかった場合、Microsoft は移行を完了できません。 (iii) お客様の不作為により Microsoft が移行を完了できない場合、お客様のサブスクリプションは 2021 年 10 月 29 日に期限切れになります。

## <a name="phase-9-office-apps"></a>フェーズ 9: Office アプリ

**適用対象:** デスクトップ アプリケーションをOfficeしているすべてのお客様 (Word、Excel、PowerPoint、Outlook、...)

Office "ドイツ" に移行する 365 テナントでは、テナント移行がフェーズ 9 に達した後、すべてのユーザーが Office 365 からサインアウトし、すべての Office デスクトップ アプリケーション (Word、Excel、PowerPoint、Outlook など) および OneDrive for Business クライアントに戻る必要があります。 サインアウトしてサインインすると、Officeサービスは、グローバル Azure AD サービスから新しい認証トークンを取得できます。

最新のアプリケーションを使用して、最適なユーザー エクスペリエンスOfficeできます。 企業は、月次エンタープライズ チャネルの使用を検討する必要があります。

モバイル デバイスの手順の事前 [作業が完了済みである必要](ms-cloud-germany-transition-add-pre-work.md#mobile-device-management) があります。

| Step(s) | 説明 | 影響 |
|:-------|:-------|:-------|
| クライアントはOffice切りOffice、Azure ADは、365 サービスを指すテナント スコープをOfficeします。 | この構成変更により、Office 365 サービス エンドポイントを更新し、Officeポイントできます。 | <ul><li>すべての Office _アプリを_ 閉じてからサインイン (またはクライアントの再起動とユーザーのサインインを強制する) をユーザーに通知して、Office クライアントが変更を受け取るのを有効にします。 </li><li>カットオーバーから 72時間以内に、Office アプリの再アクティブ化を求める Office バナーが表示される可能性があるユーザーとヘルプ デスク スタッフに通知します。 </li><li>個人用Office上のすべてのアプリケーションを閉じ、ユーザーはサインアウトしてからもう一度サインインする必要があります。 [黄色のライセンス認証] バーでサインインし、365 サービスOffice再アクティブ化します。</li><li>共有コンピューターでは、個人用のコンピューターに似たアクションが必要であり、特別な手順は必要とします。 </li><li>モバイル デバイスでは、ユーザーはアプリからサインアウトして閉じてから、もう一度サインインする必要があります。</li></ul>|
||||

## <a name="phase-9-line-of-business-apps"></a>フェーズ 9: Line-of-business アプリ

**適用対象:** 365 から 365 に接続されている一Office

Line-of-business アプリがある場合は、業務行アプリの手順の事前作業 [が完了済みである必要](ms-cloud-germany-transition-add-pre-work.md#line-of-business-apps) があります。

## <a name="phase-9--10-azure-ad-finalization"></a>フェーズ 9 & 10: Azure ADファイナライゼーション

**適用対象:** すべてのお客様

移行のOffice 365 テナントが移行の最終ステップ (Azure AD Finalization (Phase 9)) を完了すると、すべてのサービスが世界中に移行されます。 Microsoft Cloud Deutschland エンドポイントに対して、アプリケーションまたはユーザーがテナントのリソースにアクセスする必要はありません。 最終処理が完了した 30 日後に自動的に、Microsoft Cloud Deutschland Azure AD サービスは移行されたテナントのエンドポイント アクセスを停止します。 認証などのエンドポイント要求は、Microsoft Cloud Deutschland サービスに対してこの時点から順方向に失敗します。 

| Step(s) | 説明 | 影響 |
|:-------|:-------|:-------|
| ユーザー エンドポイントの更新 | すべてのユーザーが適切な Microsoft ワールドワイド エンドポイントを使用してサービスにアクセスする |移行が完了した 30 日後、Microsoft Cloud Deutschland エンドポイントは要求の尊重を停止します。クライアントまたはアプリケーション のトラフィックは失敗します。  |
| Azure ADアプリケーション エンドポイントを更新する | アプリケーションの認証、Azure Active Directory (Azure AD) Graph、MS Graph エンドポイントを Microsoft Worldwide サービスのエンドポイントに更新する必要があります。 | 移行が完了した 30 日後、Microsoft Cloud Deutschland エンドポイントは要求の尊重を停止します。クライアントまたはアプリケーション のトラフィックは失敗します。 |
||||

### <a name="azure-ad-connect"></a>Azure AD Connect
**適用対象:** すべてのお客様が Azure AD接続と ID を同期する

| Step(s) | 説明 | 影響 |
|:-------|:-------|:-------|
| Azure AD接続を更新します。 | Azure AD への切り上げが完了すると、組織は Office 365 サービスを完全に使用し、Microsoft Cloud Deutschland に接続されなくなりました。 この時点で、お客様はデルタ同期プロセスが完了した後、レジストリ パスの文字列値を `AzureInstance` 3 (Microsoft Cloud Deutschland) から 0 に変更する必要があります `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Azure AD Connect` 。 | レジストリ キーの `AzureInstance` 値を変更します。 そうしない場合、Microsoft Cloud Deutschland エンドポイントが使用できなくなった後、オブジェクトが同期されません。 |
|||||

## <a name="post-migration"></a>移行後

移行後のアクティビティの記事を [必ず読んで](ms-cloud-germany-transition-add-experience.md) 、それを実行してください。
