---
title: 移行フェーズアクションと Microsoft Cloud Deutschland からの移行への影響 (上級)
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/11/2020
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
description: '概要: Microsoft Cloud Germany (Microsoft Cloud Deutschland) から新しいドイツデータセンター地域の Office 365 サービスに移行する際のカスタマー エクスペリエンスに関するその他の情報。'
ms.openlocfilehash: 84705eaf78da4d1e8d35f743599f6a4e9e46208f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924424"
---
# <a name="migration-phases-actions-and-impacts-for-the-migration-from-microsoft-cloud-deutschland-advanced"></a>移行フェーズアクションと Microsoft Cloud Deutschland からの移行への影響 (上級) 

Microsoft Cloud Deutschland から Microsoft の Office 365 サービスのドイツ地域へのテナント移行は、一連のフェーズと、ワークロードごとに構成されたアクションとして実行されます。 次の図は、新しいドイツのデータセンターへの移行の 9 つのフェーズを示しています。

![新しいドイツのデータセンターへの移行の 9 つのフェーズ](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

以下のセクションでは、Microsoft Cloud Germany (Microsoft Cloud Deutschland) から新しいドイツデータセンター地域の Office 365 サービスに移行する際のカスタマー エクスペリエンスに関する追加情報を提供します。

## <a name="office-365-portal-services"></a>Office 365 ポータル サービス

フェーズ 2 / 9 からフェーズ 3 / 9 の間、パートナー ポータルにアクセスできない場合があります。 この間、パートナーはパートナー ポータルのテナント情報にアクセスできない場合があります。 移行ごとに異なるので、アクセシビリティ内の期間は数時間である可能性があります。

### <a name="prework-for-azure-ad-phase-2"></a>Azure ADの事前作業 (フェーズ 2)

| Step(s) | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| Azure AD Microsoft Cloud Deutschland のテナントを 365 Services Officeコピーしました。 | Azure ADは、テナントを 365 Officeにコピーします。 テナントとユーザー識別子は保持されます。 Azure ADサービス呼び出しは、Microsoft Cloud Deutschland から 365 サービスOfficeにリダイレクトされ、サービスに対して透過的です。 | すべてのOffice顧客 | - 一般的なデータ保護規則 (GDPR) データ主体要求 (DSR) は、将来の要求のために Azure Admin ポータルから実行されます。 Microsoft Cloud Deutschland に常駐している従来の診断データまたは顧客以外の診断データは、30 日以上経過した時点で削除されます。 <br><br> - Active Directory フェデレーション サービス (AD FS) でフェデレーション認証を使用しているお客様は、移行中にオンプレミスの Active Directory を使用するすべての認証に使用される発行者 URI を変更する必要があります。 発行者 URI を変更すると、ドメイン内のユーザーの認証エラーが発生します。 発行者 URI は、FS またはドメインAD管理からフェデレーションに変換される場合、またはその逆に直接変更できます。 移行された Azure ドメインテナントでフェデレーション ドメインを追加、削除、またはADすることをお勧めします。 発行者 URI は、移行が完全に完了した後で変更できます。 <br><br> - Microsoft Authenticator を使用する多要素認証 (MFA) 要求は、テナントが 365 サービスにコピーされている間にユーザー ObjectID (GUID) として表示Officeします。 MFA 要求は、この表示動作にもかかわらず期待通り実行されます。  365 サービス エンドポイントを使用してOfficeされた Microsoft Authenticator アカウントには、ユーザー プリンシパル名 (UPN) が表示されます。  Microsoft Cloud Deutschland エンドポイントを使用して追加されたアカウントは、ユーザー ObjectID を表示しますが、Microsoft Cloud Deutschland と Office 365 サービス エンドポイントの両方で動作します。  |
| Azure リソースの移行。 | Office 365 および Azure リソース (ネットワーク、コンピューティング、ストレージなど) を使用しているお客様は、Office 365 サービス インスタンスへのリソースの移行を実行します。 この移行は、お客様の責任です。 メッセージ センターの投稿は開始を示します。 365 サービス環境で Azure AD組織をOfficeする必要があります。 | Azure のお客様 | Azure 移行については、「Azure 移行プレイブック」、「Azure Germany の移行 [ガイダンスの概要」を参照してください](/azure/germany/germany-migration-main)。 |
|||||

### <a name="exchange-online-before-phase-5"></a>Exchange Online before phase 5

**適用対象:** オンプレミスの Exchange サーバーで Exchange ハイブリッド構成を使用しているすべてのお客様

| Step(s) | 説明 | 影響 |
|:-------|:-------|:-------|
| グローバル STS サービスを指す AuthServer オンプレミスを確立します。 | これにより、ハイブリッドオンプレミス環境を対象とする Exchange 可用性要求用に Microsoft Cloud Deutschland に移行するユーザーからの要求が、オンプレミス サービスにアクセスするために認証されます。 同様に、これにより、オンプレミスから 365 サービス エンドポイントへのOffice認証が保証されます。 | Azure AD移行が完了したら、オンプレミスの Exchange (ハイブリッド) トポロジの管理者は、365 サービスの新しい認証サービス エンドポイントOfficeする必要があります。 Exchange PowerShell のこのコマンドを使用して、組織のテナント ID に置き換 `<TenantID>` えてください **(Azure Active Directory** の Azure portal にあります)。<br><br>`New-AuthServer GlobalMicrosoftSts -AuthMetadataUrl https://accounts.accesscontrol.windows.net/<TenantId>/metadata/json/1` <br> <br> このタスクを完了できないと、Microsoft Cloud Deutschland から Office 365 サービスに移行されたメールボックス ユーザーの情報をハイブリッド空き時間要求で提供できない場合があります。  |
|オンプレミスの Exchange と Exchange Online の間でメールボックスを移動しない、オンボーディングメールボックスまたはオフボード メールボックスの移動を停止または削除する  | これにより、メールボックスの移動要求がエラーと一緒に失敗しない。 | サービスまたはソフトウェア クライアントの障害が発生する可能性があります。 |
||||

<!--
    Question from ckinder
    Not clear if this has to be done before, during or after phase 5
-->

**適用対象:** ユーザーの写真を Exchange Online に保存し **、Set-UserPhoto** を使用しているすべてのお客様:

| Step(s) | 説明 | 影響 |
|:-------|:-------|:-------|
| 新しい地域 "ドイツ" は既存の Exchange Online 組織のセットアップに追加され、メールボックスは 365 サービスOffice移動されます。 | Exchange Online の構成では、移行中の組織に新しい移動先のドイツ語地域が追加されます。 このOffice 365 サービス領域は既定として設定されています。これにより、内部負荷分散サービスは、メールボックスを 365 サービス内の適切な既定の領域に再配布Officeできます。 この移行では、いずれかの側 (ドイツまたは Office 365 サービス) のユーザーが同じ組織内にいて、いずれかの URL エンドポイントを使用できます。 | ユーザー メールボックスが移行されたが、管理者メールボックスが移行されていない場合、またはその逆の場合、管理者は **PowerShell コマンドレットである Set-UserPhoto** を実行できません。 このような場合、管理者は、次の構文を使用して接続セットアップ中に追加 `ConnectionUri` の文字列を渡す必要があります。 <br> `https://outlook.office.de/PowerShell-LiveID?email=<user_email>` <br> ここで `<user_email>` **、Set-UserPhoto** を使用して写真を変更する必要があるユーザーの電子メール ID のプレースホルダーです。 |
||||

## <a name="during-migration"></a>移行中

### <a name="sharepoint-online-phase-4"></a>SharePoint Online フェーズ 4

**適用対象:** 電子情報開示を使用しているすべてのユーザー

| Step(s) | 説明 | 影響 |
|:-------|:-------|:-------|
| SharePoint と OneDrive が移行されます。 | SharePoint と OneDrive は、フェーズ 4 で Microsoft Cloud Deutschland Office 365 グローバル サービスに移行されます。 既存の Microsoft Cloud Deutschland URL は保持されます `contoso.sharepoint.de` ()。 Microsoft Cloud Deutschland または 365 サービスOffice発行されたトークンは、移行中に有効です。 | Inflight SharePoint 2013 ワークフローは移行中に破損し、移行後に再発行する必要があります。 |
||||

### <a name="ediscovery-phase-4-to-the-end-of-phase-9"></a>電子情報開示フェーズ 4 ~ フェーズ 9 の終了

**適用対象:** 電子情報開示を使用しているすべてのユーザー

| Step(s) | 説明 | 影響 |
|:-------|:-------|:-------|
| フェーズ 4 の初めからフェーズ 9 が完了するまで、電子情報開示検索は失敗するか、移行された SharePoint Online、OneDrive for Business、Exchange Online の場所に対して 0 の結果を返します。 | 移行中、お客様は、コンテンツ検索を含むセキュリティ & コンプライアンス センターでケース、保留、[検索、およびエクスポートを](../compliance/manage-legal-investigations.md)[作成し続けます](../compliance/search-for-content.md)。  ただし、移行された SharePoint Online、OneDrive for Business、Exchange Online の場所に対して検索すると、0 の結果が返されるか、エラーが発生します。 修復については、「Impact」列 _を参照_ してください。 | 移行中に検索で結果がゼロまたはエラーが返された場合は、SharePoint Online で次のアクションを実行してください。 <ul><li>「OneDrive または SharePoint からファイルとフォルダーをダウンロードする」の手順に従って [、SharePoint Online/OneDrive](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)for Business サイトからサイトを直接ダウンロードします。 このメソッドには、サイトに対する SharePoint Online 管理者のアクセス許可または読み取り専用のアクセス許可が必要です。</li><li>制限を超えた場合は [、「OneDrive](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)または SharePoint からファイルとフォルダーをダウンロードする」で説明したように、お客様は、SharePoint ファイルと [Teams](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88)ファイルをコンピューターと同期するのガイダンスに従って OneDrive for Business 同期クライアントを使用できます。</li><li>詳細については  [、「In-Place eDiscovery in Exchange Server](/Exchange/policy-and-compliance/ediscovery/ediscovery) |
||||

## <a name="post-migration"></a>移行後

### <a name="azure-ad-phase-9"></a>Azure ADフェーズ 9

**適用対象:** すべてのお客様が Azure AD接続と ID を同期する

| Step(s) | 説明 | 影響 |
|:-------|:-------|:-------|
| Azure AD接続を更新します。 | Azure AD への切り上げが完了すると、組織は Office 365 サービスを完全に使用し、Microsoft Cloud Deutschland に接続されなくなりました。 この時点で、お客様はデルタ同期プロセスが完了した後、レジストリ パスの文字列値を `AzureInstance` 3 (Microsoft Cloud Deutschland) から 0 に変更する必要があります `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Azure AD Connect` 。 | レジストリ キーの `AzureInstance` 値を変更します。 そうしない場合、Microsoft Cloud Deutschland エンドポイントが使用できなくなった後、オブジェクトが同期されません。 |
|||||

**適用対象:** ADFS でフェデレーション認証を使用しているすべてのお客様

| Step(s) | 説明 | 影響 |
|:-------|:-------|:-------|
| Microsoft Cloud Deutschland および FS から証明書利用者の信頼AD削除します。 | Azure AD への切り上げが完了すると、組織は Office 365 サービスを完全に使用し、Microsoft Cloud Deutschland に接続されなくなりました。 この時点で、顧客は Microsoft Cloud Deutschland エンドポイントに対する証明書利用者の信頼を削除する必要があります。 これは、Azure AD が ID プロバイダー (IdP) として活用されている場合にのみ、顧客のアプリケーションが Microsoft Cloud Deutschland エンドポイントを指し示さない場合にのみ実行できます。 | フェデレーション認証組織 | なし。 |
|||||

<!--
    Question from ckinder
    The following paragraph is not clear
-->
Azure の場合AD:

| Step(s) | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| 移行前の過去 30 日間に Azure AD グループに参加する要求は、元の要求が承認されなかった場合は、再度要求する必要があります。 | 移行前の過去 30 日間にこれらの要求が承認されなかった場合、エンドユーザーのお客様は Access パネルを使用して Azure AD グループに再度参加する要求を送信する必要があります。 | 移行前の過去 30 日間に Azure AD承認要求が承認されなかったエンド ユーザー |  エンド ユーザーとして: <ol><li>[アクセス] [パネルに移動します](https://account.activedirectory.windowsazure.com/r#/joinGroups)。</li><li>移行の 30 日前にAD承認が保留された Azure グループを検索します。</li><li>Azure ADへの参加を要求します。</li></ol> 移行後に再要求しない限り、移行が承認される 30 日未満前にアクティブなグループに参加する要求。 |
|||||

<!--
    Question from ckinder
    The following paragraph is not clear
-->
**適用対象:**  自分の DNS ゾーンを管理しているすべての顧客

| Step(s) | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| 365 サービス エンドポイントのOffice DNS サービスを更新します。 | Microsoft Cloud Deutschland を指す顧客管理 DNS エントリを更新して、Office 365 グローバル サービス エンドポイントをポイントする必要があります。 | サービスまたはソフトウェア クライアントの障害が発生する可能性があります。 |
||||

365 サービス エンドポイントOfficeサード パーティ サービスの場合:

| Step(s) | 説明 | 影響 |
|:-------|:-------|:-------|
| 365 サービス エンドポイントのパートナーとOfficeサービスを更新します。 | <ul><li>Office 365 ドイツを指すサード パーティのサービスとパートナーは、Office 365 サービス エンドポイントをポイントするために更新する必要があります。 例: 利用可能な場合は、ベンダーやパートナーと連携して、ギャラリー アプリのバージョンのアプリケーションを再登録します。 </li><li>Graph API を利用するカスタム アプリケーションのポイントを指定 `graph.microsoft.de` します `graph.microsoft.com` 。 エンドポイントが変更された他の API も、活用する場合は更新する必要があります。 </li><li>すべてのファースト パーティ以外のエンタープライズ アプリケーションを変更して、世界中のエンドポイントにリダイレクトします。 </li></ul>| 必須のアクション。 サービスまたはソフトウェア クライアントの障害が発生する可能性があります。 |
||||

### <a name="sharepoint-online-post-migration"></a>SharePoint Online の移行後

| Step(s) | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| SharePoint 2013 ワークフローを再発行します。 | 移行前の作業では、SharePoint 2013 ワークフローの数を減らしました。 移行が完了すると、顧客はワークフローを再発行できます。 | これは必須のアクションです。 そうしない場合は、ユーザーの混乱やヘルプ デスクの呼び出しが発生する可能性があります。 |
| Outlook 経由でアイテムを共有する | SharePoint Online と OneDrive for Business のアイテムを Outlook 経由で共有すると、テナントの切り替え後に機能しなくなりました。 |<ul><li>SharePoint Online および OneDrive for Business では、Outlook 経由でアイテムを共有できます。 Outlook ボタンを押すと、共有可能なリンクが作成され、新しいメッセージにプッシュOutlook Web App。</li><li>テナントの切り替え後、この共有方法は機能しません。 これは既知の問題だと認識しています。 ただし、この Outlook 機能は廃止の道にあるので、廃止が展開されるまで問題の修正は計画されていません。 </li></ul>|
||||

### <a name="exchange-online-post-migration"></a>Exchange Online の移行後

ハイブリッド Exchange 構成を使用している場合:

| Step(s) | 説明 | 影響 |
|:-------|:-------|:-------|
| ハイブリッド構成ウィザード (HCW) を 365 サービスOffice再実行します。 | 既存の HCW 構成は、Microsoft Cloud Deutschland をサポートすることを意図しています。 Exchange サービスの移行が完了すると、Microsoft Cloud Deutschland からオンプレミス構成を切り離します。 |<ul><li>必須のアクション。 サービスまたはソフトウェア クライアントの障害が発生する可能性があります。 Exchange メールボックスの移行が開始する前に (5 日以上の通知を含む)、メールボックスのオンボーディングまたはオフボードの移動を停止して削除する必要があるクライアントに通知します。  表示しない場合は、移動要求にエラーが表示されます。 </li><li>Exchange メールボックスの移行が完了したら、オンボーディングとオフボードの移動を再開できるクライアントに通知します。 <br> Microsoft Cloud Deutschland から 365 サービスへの Exchange の移行中に、PowerShell コマンドレットである **Test-MigrationServerAvailabiilty** を実行すると、Office 365 サービスが動作しない可能性があります。 ただし、移行が完了すると正しく動作します。 </li><li>メールボックスの移行後にクライアントが資格情報または承認に関する問題にぶつかった場合、ユーザーは Exchange コントロール パネル (ECP) を使用して、移行エンドポイントでオンプレミスの管理者資格情報を再入力できます。 `Set-MigrationEndpoint endpointName -Credential $(Get-Credential)` </li></ul>|

### <a name="ediscovery-post-migration"></a>電子情報開示の移行後

| Step(s) | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
|  すべての SharePoint Online、OneDrive for Business、Exchange Online の場所は、セキュリティおよびコンプライアンス センター (SCC) と共に移行されています。 | すべての電子情報開示アクティビティは、世界中のテナントから実行する必要があります。 これで、検索は 100% 成功します。  エラーやエラーは、通常のサポート チャネルに従う必要があります。 | 電子情報開示を使用しているすべての顧客 | なし。 |
| 移行前の手順で作成された組織全体の保持ポリシーを削除する | 顧客は、移行前の作業中に作成された組織全体の保持ポリシーを削除できます。 | 移行前の手順の一部としてアイテム保持ポリシーを適用したすべてのお客様。 | なし。 |
|||||

## <a name="next-step"></a>次の手順

[移行フェーズのアクションと影響について理解する](ms-cloud-germany-transition-phases.md)

## <a name="more-information"></a>詳細

はじめに:

- [新しいドイツのデータセンター地域Office 365 サービスへの Microsoft Cloud Deutschland からの移行](ms-cloud-germany-transition.md)
- [Microsoft Cloud Deutschland 移行アシスタント](https://aka.ms/germanymigrateassist)
- [移行のオプトイン方法](ms-cloud-germany-migration-opt-in.md)
- [移行中のカスタマー エクスペリエンス](ms-cloud-germany-transition-experience.md)

切り替えの移動:

- [移行フェーズのアクションと影響](ms-cloud-germany-transition-phases.md)
- [その他の作業前](ms-cloud-germany-transition-add-pre-work.md)
- Azure [AD、デバイス](ms-cloud-germany-transition-add-devices.md)[、](ms-cloud-germany-transition-azure-ad.md)[エクスペリエンス](ms-cloud-germany-transition-add-experience.md)、および FS のAD[情報](ms-cloud-germany-transition-add-adfs.md)です。

クラウド アプリ:

- [Dynamics 365 移行プログラム情報](/dynamics365/get-started/migrate-data-german-region)
- [Power BI 移行プログラム情報](/power-bi/admin/service-admin-migrate-data-germany)
- [Microsoft Teams へのアップグレードを開始する](/microsoftteams/upgrade-start-here)