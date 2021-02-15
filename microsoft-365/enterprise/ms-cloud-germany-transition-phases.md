---
title: 移行フェーズのアクションと、Microsoft Cloud Deutschland からの移行に対する影響 (全般)
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 01/26/2021
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
description: '概要: 移行フェーズのアクションと、Microsoft Cloud Germany (Microsoft Cloud Deutschland) から新しいドイツデータセンター リージョンの Office 365 サービスへの移行による影響について説明します。'
ms.openlocfilehash: 9dc2f4c0923f52bfc83a9177b595a6955a3afa8f
ms.sourcegitcommit: 78f48304f990e969a052fe6536b2e8d6856e1086
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2021
ms.locfileid: "50242736"
---
# <a name="migration-phases-actions-and-impacts-for-the-migration-from-microsoft-cloud-deutschland-general"></a>移行フェーズのアクションと、Microsoft Cloud Deutschland からの移行に対する影響 (全般)

Microsoft Cloud Deutschland から Microsoft の Office 365 サービスのドイツリージョンへのテナント移行は、一連のフェーズと、ワークロードごとに構成されたアクションとして実行されます。 この図は、新しいドイツのデータセンターへの移行の 9 つのフェーズを示しています。

![新しいドイツデータセンターへの移行の 9 つのフェーズ](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

フェーズとそのアクションにより、重要なデータとエクスペリエンスが Office 365 サービスに移行されます。 テナントが移行キューに追加されると、各ワークロードはバックエンド サービスで実行される一連の手順として完了します。 ワークロードによっては、管理者 (またはユーザー) による操作が必要な場合や、移行が実行され、「移行の編成方法」で説明されているフェーズの使用に影響を与える [場合があります。](ms-cloud-germany-transition.md#how-is-the-migration-organized)

以下のセクションでは、移行のさまざまなフェーズを進むワークロードに対するアクションと影響について説明します。 表を確認し、組織に適用可能なアクションまたは効果を決定します。 必要に応じて、それぞれのフェーズで手順を実行する準備ができているか確認します。 必要な手順を完了できないと、サービスが停止し、Office 365 サービスへの移行が遅れる可能性があります。

## <a name="sharepoint-online-phase-4-of-9"></a>SharePoint Online (フェーズ 4/9)

| 手順 | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| SharePoint と OneDrive が移行されます。 | SharePoint と OneDrive は、このフェーズで Microsoft Cloud Deutschland Office 365 サービスに移行されます。 既存の Microsoft Cloud Deutschland URL は保持されます (例 `contoso.sharepoint.de` : )。 Microsoft Cloud Deutschland または Office 365 サービスによって発行されたトークンは、移行中に有効です。 | SharePoint のお客様 | - 移行中に 2 つの短い期間、コンテンツは読み取り専用になります。 この間、SharePoint で「コンテンツを編集できない」バナーが表示されます。 <br><br> - 検索インデックスは保持されません。再構築には最大 10 日かかる場合があります。 <br><br> - SharePoint/OneDrive のコンテンツは、移行中に 2 つの短い期間、読み取り専用になります。 この間、ユーザーに "コンテンツを編集できない" バナーが短時間表示されます。 <br><br> - インデックスが再構築されている間、検索インデックスが使用できない可能性があります。 この期間中、検索クエリは完全な結果を返していない可能性があります。 <br><br> - 既存のサイトは保持されます。 |
|||||

その他の考慮事項:

- ドイツ リージョンへの SharePoint Online の移行が完了すると、データ インデックスが再構築されます。 インデックスの再作成が完了すると、検索インデックスに依存する機能が影響を受ける可能性があります。

- 組織で引き続き SharePoint 2010 ワークフローを使用している場合は、2021 年 12 月 31 日より後に機能しなくなります。 SharePoint 2013 ワークフローは引き続きサポートされます。ただし、2020 年 11 月 1 日から新しいテナントでは既定でオフになっています。 SharePoint Online サービスへの移行が完了したら、Power Automate または他のサポートされているソリューションに移行することをお勧めします。

- ドイツリージョンへの OneDrive の移行が完了すると、データ インデックスが再構築されます。 インデックスの再作成中は、検索インデックスに依存する機能が影響を受ける可能性があります。

- SharePoint Online インスタンスがまだ移行されていない Microsoft Cloud Deutschland のお客様は、SharePoint Online PowerShell モジュール/Microsoft.SharePointOnline.CSOM バージョン 16.0.20616.12000 以下を使用する必要があります。 そうしないと、PowerShell またはクライアント側オブジェクト モデルを介した SharePoint Online への接続が失敗します。

- SharePoint Online インスタンスが移行された Microsoft Cloud Deutschland のお客様は、SharePoint Online PowerShell モジュール/Microsoft.SharePointOnline.CSOM をバージョン 16.0.20717.12000 以上に更新する必要があります。 そうしないと、PowerShell またはクライアント側オブジェクト モデルを介した SharePoint Online への接続が失敗します。


## <a name="exchange-online-phase-5-of-9"></a>Exchange Online (フェーズ 5/9)

| 手順 | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| 新しいドイツ地域が既存の組織のセットアップに追加され、メールボックスは 365 Officeに移動されます。 | Exchange Online 構成は、移行中の組織に新しいドイツ語の新しい地域を追加します。 このOffice 365 サービス地域が既定として設定され、内部負荷分散サービスが Office 365 サービスの適切な既定の地域にメールボックスを再配布できます。 この移行では、どちらの側 (ドイツまたは Office 365 サービス) のユーザーも同じ組織内にいて、どちらの URL エンドポイントも使用できます。 | Exchange Online | - ユーザーとサービスをドイツの URL から 365 Office URL ( ) に移行します `https://outlook.office365.com` 。 <br><br> - 移行中、ユーザーは引き続き従来のドイツの URL 経由でサービスにアクセスします。 直ちにアクションを実行する必要はありません。 <br><br> - ユーザーは、オンライン機能 (予定表、メールoffice.comユーザー) Officeポータルの使用を開始する必要があります。 365 サービスにまだ移行されていないサービスOffice移行するまでは機能しません。 <br><br> - Outlook Web App中にパブリック フォルダーエクスペリエンスを提供しない場合。 |
|||||

その他の考慮事項:

- `myaccount.msft.com` は、365 年 1 月 365 日の一Office後にのみ機能します。 リンクは、それまで "問題が発生しました" というエラー メッセージを生成します。

- 他のOutlook Web App共有メールボックスにアクセスするユーザー (たとえば、ドイツ環境のユーザーがグローバル環境の共有メールボックスにアクセスする場合) は、2 回目の認証を求めるメッセージが表示されます。 ユーザーは、最初にメールボックスを認証してアクセスし、次に共有メールボックスを `outlook.office.de` 開く必要があります `outlook.office365.com` 。 他のサービスでホストされている共有リソースにアクセスするときに、2 回目の認証を行う必要があります。

- 既存の Microsoft Cloud Deutschland のお客様、または移行中のユーザーの場合、ファイル > 情報 **>** アカウントの追加を使用して共有メールボックスを Outlook に追加すると、予定表のアクセス許可の表示が失敗する場合があります (Outlook クライアントは Rest API を使用しようと試みる可能性があります `https://outlook.office.de/api/v2.0/Me/Calendars` )。予定表のアクセス許可を表示するアカウントを追加する必要があるお客様は [、「Outlook](https://support.microsoft.com/office/user-experience-changes-for-sharing-a-calendar-in-outlook-5978620a-fe6c-422a-93b2-8f80e488fdec) で予定表を共有するためのユーザー エクスペリエンスの変更」の説明に従ってレジストリ キーを追加して、このアクションが成功するようにすることができます。 このレジストリ キーは、グループ ポリシーを使用して組織全体に展開できます。

- 移行フェーズ中に、PowerShell コマンドレット **New-migrationEndpoint、Set-MigrationEndpoint、Test-MigrationsServerAvailability** を使用すると、エラー (プロキシでエラー) が発生する可能性があります。   これは、調停メールボックスが世界中に移行されたが、管理者メールボックスが移行または移行できない場合に発生します。 これを解決するには、テナント PowerShell セッションの作成時に **、ConnectionUri** のルーティング ヒントとして調停メールボックスを使用します。 例: `New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://outlook.office365.com/powershell-liveid?email=Migration.8f3e7716-2011-43e4-96b1-aba62d229136@TENANT.onmicrosoft.de" -Credential $UserCredential -Authentication Basic -AllowRedirection`

- Exchange Online ハイブリッドを使用している場合:

    - 移行前にハイブリッド構成ウィザード (HCW) を再実行して Microsoft Cloud Deutschland に対するオンプレミス構成を更新し、Office 365 サービスに対するクリーンアップ時に HCW を再実行する必要があります。 カスタム ドメインを使用する場合は、追加の DNS 更新が必要になる場合があります。

移行と Exchange Online リソースの移行後の組織の違いの詳細については、新しいドイツのデータセンター リージョンで [Office 365](ms-cloud-germany-transition-experience.md)サービスに移行する際のカスタマー エクスペリエンスの情報を確認してください。

## <a name="exchange-online-protection-phase-6-of-9"></a>Exchange Online Protection (フェーズ 6/9)

Exchange Online Protection (EOP) のバック エンド機能は、新しいドイツ地域にコピーされます。 

| 手順 | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| Exchange Online ルーティングの移行と履歴メッセージの詳細。 | Exchange Online を使用すると、外部ホストから 365 Officeルーティングできます。 外部 MX レコードは、EOP サービスへのルートに移行されます。 テナントの構成と履歴の詳細が移行されます。 | Exchange Online のお客様 | - Microsoft が管理する DNS エントリは、Office 365 Germany EOP から 365 サービスOffice更新されます。 <br><br> - お客様は、EOP 移行のために EOP デュアルライトの後、30 日間待機する必要があります。 それ以外の場合は、データ損失が発生する可能性があります。 |
|||||



## <a name="skype-for-business-online-phase-7-of-9"></a>Skype for Business Online (フェーズ 7/9)

| 手順 | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| Skype for Business から Teams への移行。 | 既存の Skype for Business のお客様は、ヨーロッパの Office 365 サービスに移行された後、Office 365 サービスのドイツリージョンの Microsoft Teams に移行されます。 | Skype for Business のお客様 | - ユーザーは移行日に Skype for Business にサインインできない。 移行の 10 日前に管理センターに投稿し、移行がいつ行われ、移行を開始するときにもう一度お知らせします。 <br><br> - ポリシー構成が移行されます。 <br><br> - ユーザーは Teams に移行され、移行後に Skype for Business は利用できなくなりました。 <br><br> - ユーザーには Teams デスクトップ クライアントがインストールされている必要があります。 インストールは 10 日間、Skype for Business インフラストラクチャのポリシーを使用して行われますが、これが失敗した場合でも、ユーザーはクライアントをダウンロードするか、サポートされているブラウザーで接続する必要があります。 <br><br> - 連絡先と会議は Teams に移行されます。 <br><br> - ユーザーは、顧客の DNS エントリが完了するまでではなく、タイム サービスが Office 365 サービスに移行するまで Skype for Business にサインインできない。 <br><br> - 連絡先と既存の会議は、引き続き Skype for Business 会議として機能します。 |
|||||


## <a name="office-apps-phase-8-of-9"></a>Office アプリ (フェーズ 8/9)

| 手順 | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| クライアントはOffice切りOffice、Azure AD 365 サービスをポイントするようにテナント スコープをOfficeします。 | この構成の変更によりOffice 365 サービス エンドポイントを更新し、Officeポイントできます。 | すべてのOffice顧客 | - すべての Officeアプリを閉じてから再びサインイン (またはクライアントを再起動し、ユーザーにサインインを強制する) をユーザーに通知して、Office クライアントが変更を受け取るのを有効にします。 <br><br> - カットオーバーから 72時間以内に Office アプリを再アクティブ化するように求める Office バナーがユーザーに表示される可能性がある場合は、ユーザーとヘルプ デスクのスタッフに通知します。 <br><br> - 個人用Officeのすべてのアプリケーションを閉じ、ユーザーはサインアウトしてから再度サインインする必要があります。 黄色のアクティブ化バーでサインインし、365 サービスOffice再アクティブ化します。 <br><br> - 共有コンピューターでは、個人用のコンピューターに似た操作が必要であり、特別な手順は必要とされます。 <br><br> - モバイル デバイスでは、ユーザーはアプリからサインアウトし、アプリを閉じてから、もう一度サインインする必要があります。 |
|||||


## <a name="office-services"></a>Office サービス

Office で最近使用された (MRU) サービスは、移行ではなく、ドイツのサービスから Office 365 サービスへのカットオーバーです。 Office 365 サービス側からの MRU リンクだけが、移行ポータルからの移行後にOffice.comされます。 ドイツ サービスからの MRU リンクは、Office 365 サービスでは MRU リンクとして表示されません。 365 Office、MRU リンクにアクセスできるのは、テナントの移行が完了した後のみです。

## <a name="subscription"></a>サブスクリプション

| 手順 | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| 同意がない場合、お客様を移行することはできません。 | Microsoft は 2 つの方法のいずれかを使用して移行する権利を取得します。これにより、Microsoft はデータとサービスの Office 365 サービス インスタンスへの移行を調整できます。 <br> 管理者は、Microsoft が行う移行にオプトインします。 <br> お客様は、2020 年 5 月 1 日より後に Microsoft Cloud Deutschland テナントのサブスクリプションを更新します。 これらのお客様には、毎月移行の権利を通知し、30 日間待機して、お客様にキャンセルの機会を与え、ICM で直接オプトインします。 | すべての Office 顧客 | - テナントは移行に同意済みとしてマークされ、管理センターに確認が表示されます。 <br><br> - 確認応答は Cloud Germany Message Center テナントに投稿されます。 サービス構成は、Microsoft Cloud Deutschland エンドポイントから続行されます。 <br><br> - 移行フェーズの状態に関する更新についてメッセージ センターを監視します。 |
| サブスクリプションが転送され、ライセンスが再割り当てされます。 | テナントが Office 365 サービスに移行すると、転送された Microsoft Cloud Deutschland サブスクリプションに対応する Office 365 サービス サブスクリプションが購入されます。 割り当てられた Microsoft Cloud Deutschland ライセンスを持つユーザーには、365 Office割り当てられます。 従来の Microsoft Cloud Deutschland サブスクリプションは、完了時に Office 365 サービス テナントから削除されます。 | すべてのOffice顧客 | - このフェーズでは、既存のサブスクリプションへの変更はブロックされます (たとえば、新しいサブスクリプションの購入やシート数の変更はありません)。 <br><br> - ライセンス割り当ての変更はブロックされます。 <br><br> - Microsoft Cloud Deutschland サブスクリプションは、対応する 365 サービス Officeに移行されます。 そのOffice 365 サービスプランは、Microsoft によって定義されます (プラン マッピングとも _呼ばれる_)。 <br><br> - Office 365 サービスによって提供される機能 (サービス プラン) の数は、Microsoft Cloud Deutschland の元のプランよりも多い場合があります。 Office 365 サービスのユーザー ライセンスは、同様の Microsoft Cloud Deutschland 機能 (サービス プラン) と同等に割り当てられます。 すべてのユーザーのユーザー ライセンスが新しい機能に自動的に割り当てられます。 管理者は、必要に応じて、これらのライセンスを無効にする明示的なアクションを実行する必要があります。 <br><br> - サブスクリプションの移行が完了すると、Office 365 サービスとドイツのサブスクリプションの両方が Office 365 管理ポータルに表示され、ドイツのサブスクリプションの状態はプロビジョニング解除 _されます。_ <br><br> - ユーザーは、新しい 365 サービス サブスクリプションに関連付Office再割り当てされます。 ドイツのサブスクリプションまたは SKU GUID に依存している顧客プロセスは壊れるので、Office 365 サービスを使用して修正する必要があります。 <br><br> - Office 365 サービスの新しいサブスクリプションは新しい期間 (月次/四半期/年) で購入され、お客様は Microsoft Cloud Deutschland サブスクリプションの未使用残高に対する日割り払い払いを受け取る予定です。 <br><br> - パートナー Microsoft Cloud Deutschland テナントは移行されません。 CSP のお客様は、同じOfficeの新しい Office 365 サービス テナントの下にある 365 サービスに移行されます。 顧客の移行後、パートナーは 365 サービステナントの Officeからのみこの顧客を管理できます。 <br><br> - テナント管理者によって無効にされていない限り、追加の機能 (Microsoft Planner や Microsoft Flow など) を利用できます。ユーザーのライセンスに割り当てられているサービス プランを無効にする方法については、「ユーザー ライセンスの割り当て中に [Microsoft 365](disable-access-to-services-while-assigning-user-licenses.md)サービスへのアクセスを無効にする」を参照してください。  |
|||||

## <a name="next-step"></a>次の手順

[追加の作業前作業を実行する](ms-cloud-germany-transition-add-pre-work.md)

## <a name="more-information"></a>詳細情報

はじめに:

- [Microsoft Cloud Deutschland から新しいドイツのデータセンター リージョンOffice 365 サービスへの移行](ms-cloud-germany-transition.md)
- [Microsoft Cloud Deutschland 移行アシスタント](https://aka.ms/germanymigrateassist)
- [移行のオプトイン方法](ms-cloud-germany-migration-opt-in.md)
- [移行中のカスタマー エクスペリエンス](ms-cloud-germany-transition-experience.md)

移行を進む:

- [追加の作業前作業](ms-cloud-germany-transition-add-pre-work.md)
- Azure [AD、](ms-cloud-germany-transition-add-devices.md)[デバイス](ms-cloud-germany-transition-azure-ad.md)、[エクスペリエンス、および](ms-cloud-germany-transition-add-experience.md)AD FS[に関する追加情報](ms-cloud-germany-transition-add-adfs.md)。

クラウド アプリ:

- [Dynamics 365 移行プログラム情報](https://aka.ms/d365ceoptin)
- [Power BI 移行プログラム情報](https://aka.ms/pbioptin)
- [Microsoft Teams へのアップグレードを開始する](https://aka.ms/SkypeToTeams-Home)
