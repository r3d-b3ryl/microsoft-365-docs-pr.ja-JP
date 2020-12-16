---
title: 移行フェーズのアクションと Microsoft Cloud Deutschland からの移行に対する影響 (高度)
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
description: '概要: Microsoft Cloud Germany (Microsoft Cloud Deutschland) から新しいドイツデータセンター リージョンの Office 365 サービスに移行する際の追加のカスタマー エクスペリエンス情報。'
ms.openlocfilehash: 3f22ca9c380b3271d0c186be1f50fae4a0ea5bb9
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688195"
---
# <a name="migration-phases-actions-and-impacts-for-the-migration-from-microsoft-cloud-deutschland-advanced"></a>移行フェーズのアクションと Microsoft Cloud Deutschland からの移行に対する影響 (高度) 

以下のセクションでは、Microsoft Cloud Germany (Microsoft Cloud Deutschland) から新しいドイツデータセンター リージョンの Office 365 サービスに移行する際のカスタマー エクスペリエンスに関する追加情報を提供します。

## <a name="services"></a>サービス

### <a name="azure-ad"></a>Azure AD

| 手順 | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| Azure AD Microsoft Cloud Deutschland のテナントは、Office 365 サービスにコピーされました。 | Azure ADは、テナントを 365 Officeにコピーします。 テナントとユーザー識別子は保持されます。 Azure ADサービス呼び出しは、Microsoft Cloud Deutschland から 365 Officeにリダイレクトされ、サービスに対して透過的です。 | すべてのOffice顧客 | - 一般データ保護規則 (GDPR) データ主体要求 (DSR) は、Azure 管理ポータルから今後の要求のために実行されます。 Microsoft Cloud Deutschland に常駐している従来の診断データまたは顧客以外の診断データは、30 日以内に削除されます。 <br><br> - Active Directory フェデレーション サービス (AD FS) でフェデレーション認証を使用しているお客様は、移行中にオンプレミスの Active Directory のすべての認証に使用される発行者 URI に変更を加えてはならない。 発行者 URI を変更すると、ドメイン内のユーザーの認証エラーが発生します。 発行者 URI は、AD FS で直接変更したり、ドメインを管理からフェデレーションに変換したり、その逆に変更したりできます。 移行された Azure AD テナントのフェデレーション ドメインを追加、削除、または変換しなことをお勧めします。 発行者 URI は、移行が完全に完了した後で変更できます。 <br><br> - Microsoft Authenticator を使用する多要素認証 (MFA) 要求は、テナントが Office 365 サービスにコピーされている間、ユーザー ObjectID (GUID) として表示されます。 MFA 要求は、この表示動作にもかかわらず期待通り実行されます。  365 サービス エンドポイントを使用してOfficeされた Microsoft Authenticator アカウントには、ユーザー プリンシパル名 (UPN) が表示されます。  Microsoft Cloud Deutschland エンドポイントを使用して追加されたアカウントは、ユーザー ObjectID を表示しますが、Microsoft Cloud Deutschland と Office 365 サービス エンドポイントの両方で動作します。  |
| グローバル STS サービスを指すオンプレミスの AuthServer を確立します。 | これにより、ハイブリッドオンプレミス環境を対象とする Exchange 可用性要求に対して Microsoft Cloud Deutschland に移行するユーザーからの要求が、オンプレミス サービスにアクセスする認証を受け取る必要があります。 同様に、これにより、オンプレミスから 365 サービス エンドポイントへのOffice認証が保証されます。 | ハイブリッド (オンプレミス) 展開を使用している Exchange Online のお客様 | Azure AD移行が完了したら、オンプレミスの Exchange (ハイブリッド) トポロジの管理者は、Office 365 サービスの新しい認証サービス エンドポイントを追加する必要があります。 Exchange PowerShell からこのコマンドを使用して、組織のテナント ID (Azure Active Directory の Azure portal にあります) に置き `<TenantID>` **換えてください**。 <br><br> - `New-AuthServer GlobalMicrosoftSts -AuthMetadataUrl https://accounts.accesscontrol.windows.net/<TenantId>/metadata/json/1` <br> <br> このタスクを完了できないと、ハイブリッドの空き時間情報要求が、Microsoft Cloud Deutschland から Office 365 サービスに移行されたメールボックス ユーザーに関する情報を提供できない可能性があります。  |
| Azure リソースの移行。 | Office 365 と Azure のリソース (ネットワーク、コンピューティング、ストレージなど) を使用しているお客様は、Office 365 サービス インスタンスへのリソースの移行を実行します。 この移行は、お客様の責任です。 メッセージ センターの投稿は、開始を示します。 Office 365 サービス環境で Azure AD組織の最終処理を行う前に、移行を完了する必要があります。 | Azure Customers | Azure の移行については、Azure 移行プレイブック、Azure Germany の移行 [ガイダンスの概要をご覧ください](https://docs.microsoft.com/azure/germany/germany-migration-main)。 |
|||||

### <a name="exchange-online"></a>Exchange Online

**Set-UserPhoto を使用している場合**:

| 手順 | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| 新しいドイツ地域が既存の組織のセットアップに追加され、メールボックスは Office 365 サービスに移動されます。 | Exchange Online 構成は、移行中の組織に新しいドイツ語の新しい地域を追加します。 このOffice 365 サービス地域が既定として設定され、内部負荷分散サービスが Office 365 サービスの適切な既定の地域にメールボックスを再配布できます。 この移行では、どちらの側 (ドイツまたは Office 365 サービス) のユーザーも同じ組織内にいて、どちらの URL エンドポイントも使用できます。 |  Exchange Online | ユーザー メールボックスが移行されているが、管理者メールボックスが移行されていない場合、またはその逆の場合、管理者は **PowerShell コマンドレットである Set-UserPhoto** を実行できません。 この場合、管理者は、次の構文を使用して接続のセットアップ中に追加 `ConnectionUri` の文字列を渡す必要があります。 <br><br> `https://outlook.office.de/PowerShell-LiveID?email=<user_email>` <br><br> `<user_email>`**ここで、Set-UserPhoto** を使用して写真を変更する必要があるユーザーの電子メール ID のプレースホルダーです。 |
|||||

ハイブリッドのオンプレミス展開を使用している場合:

| 手順 | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
|メールボックスのオンボードまたはオフボードの移動を停止または削除します。  | これにより、移動要求がエラーで失敗する心配がなされます。 | ハイブリッド (オンプレミス) 展開を使用している Exchange Online のお客様 | 必要なアクション。 サービスまたはソフトウェア クライアントの障害が発生する可能性があります。 |
|||||

### <a name="dynamics"></a>Dynamics

| 手順 | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| Microsoft Dynamics のリソース | Microsoft Dynamics を使用しているお客様は、エンジニアリングまたは FastTrack の関与を受け、Dynamics を Office 365 サービス インスタンスに移行します。* | Microsoft Dynamics 365 のお客様 | - 移行後、管理者は組織を検証します。 <br><br> - 管理者は必要に応じてワークフローを変更します。 <br><br> - 管理者は、必要に応じて AdminOnly モードをクリアします。 <br><br> - 管理者が組織の種類を _サンドボックスから必要_ に応じて変更する <br><br> - インスタンス (組織) にアクセスする新しい URL をエンド ユーザーに通知します。 <br><br> - 新しいエンドポイント URL への受信接続を更新します。 <br><br> - 移行中、ユーザーは Dynamics サービスを利用できません。 <br><br> - ユーザーは、各組織の移行後に、組織の正常性と機能を検証する必要があります。  |
|||||

\* (i) Microsoft Dynamics 365 をお持ちのお客様は、提供される移行プロセスで定義されているこの移行シナリオでアクションを実行する必要があります。 (ii) お客様がアクションを実行できなかった場合、Microsoft は移行を完了できません。 (iii) お客様の不作為により Microsoft が移行を完了できない場合、お客様のサブスクリプションは 2021 年 10 月 29 日に期限切れになります。 


### <a name="power-bi"></a>Power BI

| 手順 | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| Power BI リソースの移行 | 既存の PBI 移行ツールを手動でトリガーして Power BI を Office 365 サービス インスタンスに移行した後、Microsoft Power BI のお客様はエンジニアリングまたは FastTrack に関与します。\*\* | Microsoft Power BI のお客様 | - 次の Power  BI アイテムは移行されないので、再作成する必要があります。 <br><br> - リアルタイム データセット (ストリーミング データセットやプッシュ データセットなど)。 <br> - Power BI オンプレミス のデータ ゲートウェイ構成とデータ ソース。 <br> - リアルタイム データセットの上に構築されたレポートは、移行後には使用できないので、再作成する必要があります。 <br><br> - 移行中、ユーザーは Power BI サービスを利用できません。 サービスを利用できない時間は 24 時間を超えてはならない。 <br><br> - 移行後、ユーザーはデータ ソースとオンプレミスのデータ ゲートウェイを Power BI サービスで再構成する必要があります。  これを行うまで、ユーザーは、これらのデータ ソースを使用して、スケジュールされた更新を実行したり、これらのデータ ソースに対してクエリを直接実行したりすることはできません。 <br><br> - 容量とプレミアム ワークスペースは移行できません。 お客様は、移行前に容量を削除し、移行後に再作成する必要があります。 ワークスペースを必要に応じて容量に戻します。  |
|||||

\*\* (i) Microsoft Power BI を使用しているお客様は、提供される移行プロセスで定義されているこの移行シナリオでアクションを実行する必要があります。 (ii) お客様がアクションを実行できなかった場合、Microsoft は移行を完了できません。 (iii) お客様の不作為により Microsoft が移行を完了できない場合、お客様のサブスクリプションは 2021 年 10 月 29 日に期限切れになります。 


### <a name="office-apps"></a>Office アプリ

| 手順 | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| クライアントはOffice切りOffice、Azure AD 365 サービスをポイントするようにテナント スコープをOfficeします。 | この構成の変更によりOffice 365 サービス エンドポイントを更新し、Officeポイントできます。 | すべてのOffice顧客 | - 顧客が所有する DNS から MSOID CName が存在する場合は削除します。 <br><br> - すべての Officeアプリを閉じてから再びサインイン (またはクライアントを再起動し、ユーザーにサインインを強制する) をユーザーに通知して、Office クライアントが変更を受け取るのを有効にします。 <br><br> - カットオーバーから 72時間以内に Office アプリを再アクティブ化するように求める Office バナーがユーザーに表示される可能性がある場合は、ユーザーとヘルプ デスクのスタッフに通知します。 <br><br> - 個人用Officeのすべてのアプリケーションを閉じ、ユーザーはサインアウトしてから再度サインインする必要があります。 黄色のアクティブ化バーでサインインし、365 サービスOffice再アクティブ化します。 <br><br> - 共有コンピューターでは、個人用のコンピューターに似た操作が必要であり、特別な手順は必要とされます。 <br><br> - モバイル デバイスでは、ユーザーはアプリからサインアウトし、アプリを閉じてから、もう一度サインインする必要があります。 |
|||||

## <a name="during-migration"></a>移行中


### <a name="exchange-online"></a>Exchange Online

電子情報開示の場合:

| 手順 | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| 移行中に、電子情報開示検索が失敗するか、移行された SharePoint Online、OneDrive for Business、Exchange Online の場所に対して 0 件の結果が返されます。 | 移行中、お客様は、コンテンツ検索を含むセキュリティ & コンプライアンス センターで引 [き続き](https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations)ケース、保留、検索、エクスポート [を作成できます](https://docs.microsoft.com/microsoft-365/compliance/search-for-content)。  ただし、移行された SharePoint Online、OneDrive for Business、Exchange Online の場所に対する検索では、0 件の結果が返されるか、エラーが発生します。 修復については、「影響」列 _を参照_ してください。 | 電子情報開示を使用しているすべてのお客様 |  移行中に検索で 0 件の結果またはエラーが返された場合は、SharePoint Online に対して次のアクションを実行してください。 <br><br>  「OneDrive または SharePoint からファイルとフォルダーをダウンロードする」の手順に従って、SharePoint Online/OneDrive for Business サイトから直接サイト [をダウンロードします](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)。 この方法では、サイトに対する SharePoint Online 管理者のアクセス許可または読み取り専用アクセス許可が必要です。 <br><br> [「OneDrive](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)または SharePoint からファイルとフォルダーをダウンロードする」で説明したように、制限を超えた場合、お客様は OneDrive for Business 同期クライアントを使用できます。その場合は[、「SharePoint](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88)ファイルと Teams ファイルをコンピューターと同期する」のガイダンスに従います。 <br><br> - Exchange Online <br><br> - [In-Place eDiscovery in Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/ediscovery/ediscovery) |
|||||


### <a name="sharepoint-online"></a>SharePoint Online

| 手順 | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| SharePoint と OneDrive が移行されます。 | SharePoint と OneDrive は、このフェーズで Microsoft Cloud Deutschland Office 365 サービスに移行されます。 既存の Microsoft Cloud Deutschland URL は保持されます ( `contoso.sharepoint.de` )。 Microsoft Cloud Deutschland または Office 365 サービスによって発行されたトークンは、移行中に有効です。 | SharePoint のお客様 | Inflight SharePoint 2013 ワークフローは移行中に破損し、移行後に再発行する必要があります。 |
|||||

### <a name="skype-for-business-online"></a>Skype for Business Online

| 手順 | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| Skype for Business から Teams への移行。 | 既存の Skype for Business のお客様は、ヨーロッパの Office 365 サービスに移行された後、Office 365 サービスのドイツリージョンの Microsoft Teams に移行されます。 | Skype for Business のお客様 |  PowerShell は、テナントとユーザーの設定とポリシーを管理するために使用します。 PowerShell セッションに接続する場合は、次を追加します。 <br><br> `-OverridePowershellUri "https://admin4E.online.lync.com/OcsPowershellOAuth"` |
|||||


## <a name="post-migration"></a>移行後

### <a name="azure-ad"></a>Azure AD

ハイブリッドの場合:

| 手順 | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| Azure AD Connect を更新します。 | Azure AD への移行が完了すると、組織は Office 365 サービスを完全に使用し、Microsoft Cloud Deutschland に接続されなくなりました。 この時点で、お客様はデルタ同期プロセスが完了し、その後、レジストリ パスの文字列値を `AzureInstance` 3 (Microsoft Cloud Deutschland) から 0 に変更する必要があります `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Azure AD Connect` 。 | ハイブリッド Azure AD接続された組織 | レジストリ キーの `AzureInstance` 値を変更します。 そうしない場合、Microsoft Cloud Deutschland エンドポイントが使用できなくなった後にオブジェクトが同期されません。 |
|||||

フェデレーション認証の場合:

| 手順 | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| MICROSOFT Cloud Deutschland および FS から証明書利用者信頼ADします。 | Azure AD への移行が完了すると、組織は Office 365 サービスを完全に使用し、Microsoft Cloud Deutschland に接続されなくなりました。 この時点で、お客様は Microsoft Cloud Deutschland エンドポイントに対する証明書利用者信頼を削除する必要があります。 これは、Azure AD が ID プロバイダー (IdP) として利用されている場合に、顧客のアプリケーションが Microsoft Cloud Deutschland エンドポイントをポイントしがない場合にのみ実行できます。 | フェデレーション認証組織 | なし。 |
|||||

Azure AD の場合:

| 手順 | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| 移行前の過去 30 日間に Azure AD グループに参加する要求は、元の要求が承認されなかった場合にもう一度要求する必要があります。 | エンド ユーザーのお客様は、移行前の過去 30 日以内にそれらの要求が承認されなかった場合に、アクセス パネルを使用して Azure AD グループに再度参加する要求を送信する必要があります。 | 移行前の過去 30 日間ADの承認要求が承認されなかった Azure ユーザーのエンド ユーザー |  エンド ユーザー: <ol><li>Access パネル [に移動します](https://account.activedirectory.windowsazure.com/r#/joinGroups)。</li><li>移行の 30 日前ADメンバーシップの承認が保留された Azure グループを検索します。</li><li>Azure グループに再度参加AD要求します。</li></ol> 移行の 30 日以内にアクティブなグループに参加する要求は、移行後に再要求されていない限り、承認できません。 |
|||||

DNS の場合:

| 手順 | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| 365 サービス エンドポイント用のOffice DNS サービスを更新します。 | Office 365 Germany をポイントする顧客管理の DNS エントリは、Office 365 サービス エンドポイントをポイントするために更新する必要があります。 | すべてのOffice顧客 | 必要なアクション。 サービスまたはソフトウェア クライアントの障害が発生する可能性があります。 |
|||||

365 サービス エンドポイント用のサード Officeの場合:

| 手順 | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| 365 サービス エンドポイント用にパートナー Officeサービスを更新します。 | - Office 365 Germany をポイントするサード パーティのサービスとパートナーは、Office 365 サービス エンドポイントをポイントするために更新する必要があります。 例: ベンダーやパートナーに合わせ、ギャラリー アプリバージョンのアプリケーションを再登録します (可能な場合)。 <br><br> - Graph API を利用するカスタム アプリケーションの参照をポイント `graph.microsoft.de` します `graph.microsoft.com` 。 エンドポイントが変更された他の API も、利用する場合は更新する必要があります。 <br><br> - 世界規模のエンドポイントにリダイレクトするために、ファースト パーティ以外のすべてのエンタープライズ アプリケーションを変更します。  | すべてのOffice顧客 | 必要なアクション。 サービスまたはソフトウェア クライアントの障害が発生する可能性があります。 |
|||||

### <a name="exchange-online"></a>Exchange Online

ハイブリッド Exchange 構成を使用している場合:

| 手順 | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| ハイブリッド構成ウィザード (HCW) を 365 サービスOffice再実行します。 | 既存の HCW 構成は、Microsoft Cloud Deutschland をサポートすることを意図しています。 Exchange サービスの移行が完了すると、Microsoft Cloud Deutschland からオンプレミス構成が切り離されます。 | ハイブリッド展開を実行している Exchange Online のお客様 | - 必要なアクション。 サービスまたはソフトウェア クライアントの障害が発生する可能性があります。 Exchange メールボックスの移行が開始する前 (5 日以上の通知がある場合) に、メールボックスのオンボードまたはオフボードの移動を停止して削除する必要があるクライアントに通知します。  そうしない場合、移動要求にエラーが表示されます。 <br><br> - Exchange メールボックスの移行が完了したら、オンボードとオフボードの移動を再開できるクライアントに通知します。 <br> Microsoft Cloud Deutschland から Office 365 サービスへの Exchange の移行中に、PowerShell コマンドレットである **Test-MigrationServerAvailabiilty** を実行できない可能性があります。 ただし、移行が完了すると正常に動作します。 <br><br> メールボックスの移行後にクライアントに資格情報または承認の問題が発生した場合、ユーザーは、Exchange コントロール パネル (ECP) を使用して、移行エンドポイントでオンプレミス管理者の資格情報を再入力できます。 `Set-MigrationEndpoint endpointName -Credential $(Get-Credential)`  |

電子情報開示の場合:

| 手順 | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
|  SharePoint Online、OneDrive for Business、および Exchange Online のすべての場所が、セキュリティ/コンプライアンス センター (SCC) と共に移行されました。 | すべての電子情報開示アクティビティは、世界中のテナントから実行する必要があります。 これで、検索は 100% 成功します。  エラーやエラーは、通常のサポート チャネルに従う必要があります。 | 電子情報開示を使用しているすべての顧客 | なし。 |
| 移行前の手順で作成された組織全体のアイテム保持ポリシーを削除する | お客様は、移行前の作業中に作成された組織全体のアイテム保持ポリシーを削除できます。 | 移行前の手順の一部としてアイテム保持ポリシーを適用したユーザーすべて。 | なし。 |
|||||

### <a name="sharepoint-online"></a>SharePoint Online

| 手順 | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| SharePoint 2013 ワークフローを再発行します。 | 移行前作業では、SharePoint 2013 ワークフローの数を削減しました。 移行が完了したら、お客様はワークフローを再発行できます。 | すべてのOffice顧客 | これは必須のアクションです。 そうしない場合は、ユーザーが混乱し、ヘルプ デスクへの電話が必要な場合があります。 |
| Outlook 経由でアイテムを共有する | Outlook を介したアイテムの共有は、テナントのカットオーバー後に機能しなくなりました。 | SharePoint Online と OneDrive for Business | - SharePoint Online と OneDrive for Business では、Outlook 経由でアイテムを共有できます。 Outlook ボタンを押すと、共有可能なリンクが作成され、新しいメッセージにプッシュOutlook Web App。 <br><br> - テナントのカットオーバー後、この共有方法は機能しません。 これは既知の問題です。 ただし、この Outlook 機能は廃止の道のりにあるので、廃止が展開されるまで問題の修正は計画されていません。 |

## <a name="next-step"></a>次の手順

[移行フェーズのアクションと影響について理解する](ms-cloud-germany-transition-phases.md)

## <a name="more-information"></a>詳細

はじめに:

- [Microsoft Cloud Deutschland から新しいドイツのデータセンター リージョンOffice 365 サービスへの移行](ms-cloud-germany-transition.md)
- [Microsoft Cloud Deutschland 移行アシスタント](https://aka.ms/germanymigrateassist)
- [移行のオプトイン方法](ms-cloud-germany-migration-opt-in.md)
- [移行中のカスタマー エクスペリエンス](ms-cloud-germany-transition-experience.md)

移行を進む:

- [移行フェーズのアクションと影響](ms-cloud-germany-transition-phases.md)
- [追加の作業前作業](ms-cloud-germany-transition-add-pre-work.md)
- Azure [AD、](ms-cloud-germany-transition-add-devices.md)[デバイス](ms-cloud-germany-transition-azure-ad.md)、[エクスペリエンス、および](ms-cloud-germany-transition-add-experience.md)AD FS[に関する追加情報](ms-cloud-germany-transition-add-adfs.md)。

クラウド アプリ:

- [Dynamics 365 移行プログラム情報](https://aka.ms/d365ceoptin)
- [Power BI 移行プログラム情報](https://aka.ms/pbioptin)
- [Microsoft Teams へのアップグレードを開始する](https://aka.ms/SkypeToTeams-Home)
