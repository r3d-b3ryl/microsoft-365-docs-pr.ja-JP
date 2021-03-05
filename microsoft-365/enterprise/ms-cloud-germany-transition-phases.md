---
title: 移行フェーズアクションと Microsoft Cloud Deutschland からの移行への影響 (全般)
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
description: '概要: Microsoft Cloud Germany (Microsoft Cloud Deutschland) から新しいドイツデータセンター地域の Office 365 サービスへの移行フェーズのアクションと影響について説明します。'
ms.openlocfilehash: 1da3ff6b3347d0e996b017aa1f6243fd724ffccd
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2021
ms.locfileid: "50454409"
---
# <a name="migration-phases-actions-and-impacts-for-the-migration-from-microsoft-cloud-deutschland-general"></a>移行フェーズアクションと Microsoft Cloud Deutschland からの移行への影響 (全般)

Microsoft Cloud Deutschland から Microsoft の Office 365 サービスのドイツ地域へのテナント移行は、一連のフェーズと、ワークロードごとに構成されたアクションとして実行されます。 次の図は、新しいドイツのデータセンターへの移行の 9 つのフェーズを示しています。

![新しいドイツのデータセンターへの移行の 9 つのフェーズ](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

フェーズとそのアクションにより、重要なデータとエクスペリエンスが 365 サービスにOfficeされます。 テナントが移行キューに追加されると、各ワークロードは、バックエンド サービスで実行される一連の手順として完了します。 一部のワークロードでは、管理者 (またはユーザー) によるアクションが必要な場合や、移行が実行および説明されているフェーズの使用状況に影響を与える場合があります。「移行の整理方法」を [参照してください。](ms-cloud-germany-transition.md#how-is-the-migration-organized)

次のセクションには、移行のさまざまなフェーズを進むワークロードのアクションと効果が含まれています。 表を確認し、組織に適用できるアクションまたは効果を決定します。 必要に応じて、それぞれのフェーズで手順を実行する準備ができているか確認します。 必要な手順を完了できないと、サービスが停止し、365 サービスへの移行がOffice可能性があります。

## <a name="sharepoint-online-phase-4-of-9"></a>SharePoint Online (フェーズ 4 / 9)

| Step(s) | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| SharePoint と OneDrive が移行されます。 | SharePoint と OneDrive は、このフェーズで Microsoft Cloud Deutschland Office 365 サービスに移行されます。 既存の Microsoft Cloud Deutschland URL は保持されます (たとえば `contoso.sharepoint.de` )。 Microsoft Cloud Deutschland または 365 サービスOffice発行されたトークンは、移行中に有効です。 | SharePoint のお客様 | - 移行中の 2 つの短い期間、コンテンツは読み取り専用になります。 この間、SharePoint で "コンテンツを編集できない" バナーが表示されます。 <br><br> - 検索インデックスは保持されません。再構築には最大 10 日かかる場合があります。 <br><br> - SharePoint/OneDrive コンテンツは、移行中に 2 つの短い期間の読み取り専用になります。 この間、ユーザーには「コンテンツを編集できない」バナーが簡単に表示されます。 <br><br> - インデックスの再構築中に検索インデックスが使用できない場合があります。 この期間中、検索クエリで完全な結果が返されない場合があります。 <br><br> - 既存のサイトは保持されます。 |
|||||

その他の考慮事項:

- ドイツ リージョンへの SharePoint Online の移行が完了すると、データ インデックスが再構築されます。 インデックスの再作成が完了すると、検索インデックスに依存する機能が影響を受ける可能性があります。

- 組織で引き続き SharePoint 2010 ワークフローを使用している場合、2021 年 12 月 31 日以降は機能しなくなりました。 SharePoint 2013 ワークフローは引き続きサポートされます。ただし、2020 年 11 月 1 日から新しいテナントでは既定でオフになっています。 SharePoint Online サービスへの移行が完了したら、Power Automate または他のサポートされているソリューションに移動することをお勧めします。

- OneDrive からドイツ地域への移行が完了すると、データ インデックスが再構築されます。 インデックスの再作成中に、検索インデックスに依存する機能が影響を受ける可能性があります。

- SharePoint Online インスタンスがまだ移行されていない Microsoft Cloud Deutschland のお客様は、SharePoint Online PowerShell モジュール/Microsoft.SharePointOnline.CSOM バージョン 16.0.20616.12000 以下に滞在する必要があります。 それ以外の場合、PowerShell またはクライアント側のオブジェクト モデルを介して SharePoint Online への接続が失敗します。

- SharePoint Online インスタンスが移行される Microsoft Cloud Deutschland のお客様は、SharePoint Online PowerShell モジュール/Microsoft.SharePointOnline.CSOM をバージョン 16.0.20717.12000 以上に更新する必要があります。 それ以外の場合、PowerShell またはクライアント側のオブジェクト モデルを介して SharePoint Online への接続が失敗します。


## <a name="exchange-online-phase-5-of-9"></a>Exchange Online (フェーズ 5 / 9)

| Step(s) | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| 新しいドイツ地域が既存の組織のセットアップに追加され、メールボックスは 365 サービスOfficeに移動されます。 | Exchange Online の構成では、移行中の組織に新しい移動先のドイツ語地域が追加されます。 このOffice 365 サービス領域は既定として設定されています。これにより、内部負荷分散サービスは、メールボックスを 365 サービス内の適切な既定の領域に再配布Officeできます。 この移行では、いずれかの側 (ドイツまたは Office 365 サービス) のユーザーが同じ組織内にいて、いずれかの URL エンドポイントを使用できます。 | Exchange Online | - ユーザーとサービスを従来のドイツの URL (outlook.office.de) から新しいサービス Office 365 サービス URL ( ) に移行します `https://outlook.office365.com` 。 <br><br> - ユーザーは移行中に従来のドイツの URL を通じてサービスに引き続きアクセスすることができますが、移行の完了時に従来の URL の使用を停止する必要があります。 <br><br> - ユーザーは、オンライン機能 (予定表、メールOfficeユーザー) のOfficeポータルを使用するに移行する必要があります。 365 サービスにまだ移行されていないサービスOffice移行するまでは機能しません。 <br><br> - 移行Outlook Web Appパブリック フォルダーエクスペリエンスを提供しない場合。 |
| 自動検出のカスタム DNS 設定を更新する| 現在 Microsoft Cloud Deutschland を指している AutoDiscover の顧客管理 DNS 設定は、Exchange Online フェーズ (フェーズ 5) の完了時に Office 365 をポイントするために更新する必要があります。 <br> CNAME を指す既存の DNS エントリは、autodiscover-outlook.office.deをポイントするために更新するautodiscover.outlook.com。 | Exchange Online | AutoDiscover 経由の可用性要求とサービス検出呼び出しは、365 サービスOffice直接ポイントします。 これらの DNS 更新を実行しないお客様は、移行が完了すると自動検出サービスの問題が発生する可能性があります。 |
|||||

その他の考慮事項:

- `myaccount.msft.com` 365 のカットオーバー後にのみOfficeされます。 リンクは、その時間まで "何か問題が発生しました" というエラー メッセージを生成します。

- 他のOutlook Web App共有メールボックスにアクセスするユーザー (たとえば、ドイツ環境のユーザーがグローバル環境の共有メールボックスにアクセスする場合など) は、2 回目の認証を求めるメッセージが表示されます。 ユーザーは、最初に自分のメールボックスを認証してアクセスし、次に共有メールボックスを `outlook.office.de` 開く必要があります `outlook.office365.com` 。 他のサービスでホストされている共有リソースにアクセスする場合は、2 回目の認証が必要です。

- 既存の Microsoft Cloud Deutschland のお客様または移行中のユーザーの場合、共有メールボックスが File **> Info >** Add Account を使用して Outlook に追加された場合、予定表のアクセス許可の表示が失敗する場合があります (Outlook クライアントは Rest API を使用しようと試み `https://outlook.office.de/api/v2.0/Me/Calendars` .)予定表のアクセス許可を表示するアカウントを追加する場合は [、「Outlook](https://support.microsoft.com/office/user-experience-changes-for-sharing-a-calendar-in-outlook-5978620a-fe6c-422a-93b2-8f80e488fdec) で予定表を共有するためのユーザー エクスペリエンスの変更」の説明に従ってレジストリ キーを追加して、このアクションが成功するようにすることができます。 このレジストリ キーは、グループ ポリシーを使用して組織全体に展開できます。

- 移行フェーズ中に、PowerShell コマンドレット **New-migrationEndpoint、Set-MigrationEndpoint、** および **Test-MigrationsServerAvailability** を使用すると、エラー (プロキシでエラー) が発生する可能性があります。  これは、調停メールボックスが世界中に移行されたが、管理者メールボックスが移行または逆の場合に発生します。 これを解決するには、テナント PowerShell セッションの作成中に **、ConnectionUri** のルーティング ヒントとして調停メールボックスを使用します。 例: `New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://outlook.office365.com/powershell-liveid?email=Migration.8f3e7716-2011-43e4-96b1-aba62d229136@TENANT.onmicrosoft.de" -Credential $UserCredential -Authentication Basic -AllowRedirection`

- Exchange Online ハイブリッドを使用している場合:

    - Exchange Online Hybrid のお客様は、この移行の一環としてハイブリッド構成ウィザード (HCW) を複数回実行する必要があります。 移行手順フェーズ **5** が開始される前に、Exchange Online ハイブリッドのお客様は、Office 365 ドイツ モードで最新バージョンの HCW を実行して、Office 365 グローバルへの移行用のオンプレミス構成を準備する必要があります。 移行 **フェーズ 5** が完了すると (メッセージ センター通知が公開されている場合)、Office 365 Worldwide 設定を使用して、オンプレミス システムをグローバル サービスに向け、HCW を実行する必要があります。 カスタム ドメインを使用する場合は、追加の DNS 更新プログラムが必要になる場合があります。

移行および Exchange Online リソースの移行後の組織の違いの詳細については、「新しいドイツのデータセンター地域の [Office 365](ms-cloud-germany-transition-experience.md)サービスへの移行中のカスタマー エクスペリエンス」の情報を確認してください。

## <a name="exchange-online-protection-phase-6-of-9"></a>Exchange Online Protection (フェーズ 6 / 9)

Exchange Online Protection (EOP) のバック エンド機能は、新しいドイツ地域にコピーされます。 

| Step(s) | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| Exchange Online ルーティングと履歴メッセージの詳細の移行。 | Exchange Online を使用すると、外部ホストから 365 Officeルーティングできます。 外部 MX レコードは、EOP サービスにルーティングするために移行されます。 テナントの構成と履歴の詳細が移行されます。 | Exchange Online のお客様 | - Microsoft が管理する DNS エントリは、Office 365 ドイツ EOP から 365 Office更新されます。 <br><br> - EOP のデュアル書き込みで EOP の移行を行った後、お客様は 30 日間待機する必要があります。 それ以外の場合は、データ損失が発生する可能性があります。 |
|||||



## <a name="skype-for-business-online-phase-7-of-9"></a>Skype for Business Online (フェーズ 7 / 9)

| Step(s) | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| Skype for Business から Teams への移行。 | 既存の Skype for Business のお客様は、ヨーロッパの Office 365 サービスに移行され、Office 365 サービスのドイツ地域の Microsoft Teams に移行されます。 | Skype for Business のお客様 | - 移行日に Skype for Business にサインインできない。 移行の 10 日前に管理センターに投稿し、移行がいつ行われ、移行を開始するときにもう一度知らせます。 <br><br> - ポリシー構成が移行されます。 <br><br> - ユーザーは Teams に移行され、移行後は Skype for Business を使用しなくなりました。 <br><br> - ユーザーは Teams デスクトップ クライアントがインストールされている必要があります。 インストールは、Skype for Business インフラストラクチャのポリシーを介して 10 日間に行われますが、失敗した場合でも、ユーザーはクライアントをダウンロードするか、サポートされているブラウザーに接続する必要があります。 <br><br> - 連絡先と会議は Teams に移行されます。 <br><br> - タイム サービスが Office 365 サービスに移行するまで、顧客の DNS エントリが完了するまで、ユーザーは Skype for Business にサインインできない。 <br><br> - 連絡先と既存の会議は、Skype for Business 会議として引き続き機能します。 |
|||||


## <a name="office-apps-phase-8-of-9"></a>Officeアプリ (フェーズ 8 / 9)

| Step(s) | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| クライアントはOffice切りOffice、Azure ADは、365 サービスを指すテナント スコープをOfficeします。 | この構成変更により、Office 365 サービス エンドポイントを更新し、Officeポイントできます。 | すべてのOffice顧客 | - すべての Officeアプリを閉じてからサインイン (またはクライアントの再起動とユーザーのサインインを強制する) をユーザーに通知して、Office クライアントが変更を受け取るのを有効にします。 <br><br> - ユーザーとヘルプ デスク スタッフに、カットオーバーから 72 時間以内に Office アプリの再アクティブ化を求める Office バナーが表示される可能性を通知します。 <br><br> - 個人用Office上のすべてのアプリケーションを閉じ、ユーザーはサインアウトしてからもう一度サインインする必要があります。 [黄色のライセンス認証] バーでサインインし、365 サービスOffice再アクティブ化します。 <br><br> - 共有コンピューターは、個人用コンピューターに似たアクションを必要とします。特別な手順は必要とします。 <br><br> - モバイル デバイスでは、ユーザーはアプリからサインアウトして閉じてから、もう一度サインインする必要があります。 |
|||||


## <a name="office-services"></a>Office サービス

Office で最も最近使用された (MRU) サービスは、移行ではなく、Office 365 サービスへの切り替えです。 365 サービス側からの MRU Officeは、ポータルから移行した後Office.comされます。 ドイツ サービスからの MRU リンクは、365 サービス内の MRU Office表示されません。 365 Office、MRU リンクにアクセスできるのは、テナントの移行が完了した後のみです。

## <a name="subscription"></a>サブスクリプション

| Step(s) | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| 同意なしに顧客を移行することはできません。 | Microsoft は、2 つの方法のいずれかを使用して移行する権利を取得します。これにより、Microsoft はデータとサービスの 365 サービス インスタンスへの移行Office調整できます。 <br> 管理者は、Microsoft 駆動型の移行にオプトインします。 <br> お客様は、2020 年 5 月 1 日以降に Microsoft Cloud Deutschland テナント内のサブスクリプションを更新します。 毎月、移行の権利をこれらの顧客に通知し、30 日間待機して顧客にキャンセルの機会を与え、ICM で追跡された直接オプトインを行います。 | すべてのOffice顧客 | - テナントは移行に同意済みとしてマークされ、管理センターには確認が表示されます。 <br><br> - 確認応答が Cloud Germany Message Center テナントに投稿されます。 サービス構成は、Microsoft Cloud Deutschland エンドポイントから続行されます。 <br><br> - 移行フェーズの状態に関する更新プログラムについてメッセージ センターを監視します。 |
| サブスクリプションが転送され、ライセンスが再割り当てされます。 | テナントが Office 365 サービスに移行すると、転送された Microsoft Cloud Deutschland サブスクリプションに対応する Office 365 サービス サブスクリプションが購入されます。 Microsoft Cloud Deutschland ライセンスが割り当てられているユーザーには、365 サービス Office割り当てられます。 従来の Microsoft Cloud Deutschland サブスクリプションは、Office 365 サービス テナントから削除されます。 | すべてのOffice顧客 | - 既存のサブスクリプションへの変更は、このフェーズ中にブロックされます (たとえば、新しいサブスクリプション購入やシート 数の変更はありません)。 <br><br> - ライセンス割り当ての変更はブロックされます。 <br><br> - Microsoft Cloud Deutschland サブスクリプションは、対応する 365 サービス Officeに移行されます。 このサブスクリプションOffice 365 サービスの提供は、Microsoft (プラン マッピングとも呼ばれる) _によって定義されます_。 <br><br> - 365 サービスによって提供される機能 (サービス プラン) の数は、Office Microsoft Cloud Deutschland オファーよりも大きくなる可能性があります。 365 サービスOfficeユーザー ライセンスは、同様の Microsoft Cloud Deutschland 機能 (サービス プラン) と同等に割り当てられます。 すべてのユーザーのユーザー ライセンスが新しい機能に自動的に割り当てられます。 管理者は、必要に応じて、これらのライセンスを無効にする明示的なアクションを実行する必要があります。 <br><br> - サブスクリプションの移行が完了すると、Office 365 サービスとドイツのサブスクリプションの両方が Office 365 管理ポータルに表示され、ドイツのサブスクリプションの状態はプロビジョニング解除されます。 <br><br> - ユーザーは、新しい 365 サービス サブスクリプションに関連付Office再割り当てされます。 ドイツのサブスクリプションまたは SKU GUID に依存している顧客プロセスは壊れ、Office 365 サービスを提供する必要があります。 <br><br> - Office 365 サービスの新しいサブスクリプションは、新しい期間 (月次/四半期/年) で購入され、お客様は Microsoft Cloud Deutschland サブスクリプションの未使用残高に対して日割り払い払いを受け取る予定です。 <br><br> - パートナーの Microsoft Cloud Deutschland テナントは移行されません。 CSP のお客様は、同Officeの新しいサービス 365 サービス テナントOffice 365 サービスに移行されます。 顧客の移行後、パートナーは 365 サービス テナントOfficeこの顧客を管理できます。 <br><br> - テナント管理者が無効にしない限り、追加の機能 (Microsoft Planner や Microsoft Flow など) を使用できます。ユーザーのライセンスに割り当てられているサービス プランを無効にする方法については、「ユーザー ライセンスの割り当て中に [Microsoft 365](disable-access-to-services-while-assigning-user-licenses.md)サービスへのアクセスを無効にする」を参照してください。  |
|||||

## <a name="next-step"></a>次の手順

[追加の事前作業を実行する](ms-cloud-germany-transition-add-pre-work.md)

## <a name="more-information"></a>詳細情報

はじめに:

- [新しいドイツのデータセンター地域Office 365 サービスへの Microsoft Cloud Deutschland からの移行](ms-cloud-germany-transition.md)
- [Microsoft Cloud Deutschland 移行アシスタント](https://aka.ms/germanymigrateassist)
- [移行のオプトイン方法](ms-cloud-germany-migration-opt-in.md)
- [移行中のカスタマー エクスペリエンス](ms-cloud-germany-transition-experience.md)

切り替えの移動:

- [その他の作業前](ms-cloud-germany-transition-add-pre-work.md)
- Azure [AD、デバイス](ms-cloud-germany-transition-add-devices.md)[、](ms-cloud-germany-transition-azure-ad.md)[エクスペリエンス](ms-cloud-germany-transition-add-experience.md)、および FS のAD[情報](ms-cloud-germany-transition-add-adfs.md)です。

クラウド アプリ:

- [Dynamics 365 移行プログラム情報](https://aka.ms/d365ceoptin)
- [Power BI 移行プログラム情報](https://aka.ms/pbioptin)
- [Microsoft Teams へのアップグレードを開始する](https://aka.ms/SkypeToTeams-Home)
