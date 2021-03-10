---
title: 移行フェーズアクションと Microsoft Cloud Deutschland からの移行への影響 (全般)
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
ms.openlocfilehash: 045e29cba293dd74d3a77beae80d78380eaa4147
ms.sourcegitcommit: 9adb89206daa075af34a73bcb7e8fb86d7c2919a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/10/2021
ms.locfileid: "50604010"
---
# <a name="migration-phases-actions-and-impacts-for-the-migration-from-microsoft-cloud-deutschland-general"></a>移行フェーズアクションと Microsoft Cloud Deutschland からの移行への影響 (全般)

Microsoft Cloud Deutschland (MCD) から Microsoft の Office 365 グローバル サービスの地域 "ドイツ" へのテナント移行は、一連のフェーズと、ワークロードごとに構成されたアクションとして実行されます。 次の図は、新しいドイツのデータセンターへの移行の 9 つのフェーズを示しています。

![新しいドイツのデータセンターへの移行の 9 つのフェーズ](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

移行プロセスは、組織の全体的な規模と複雑さによって、何週間にも渡って完了します。 移行が進行中の間、ユーザーと管理者は、このドキュメントで詳しく説明されている変更点を使用して、サービスを引き続き利用できます。 グラフィックとテーブルは、移行中のフェーズと手順を定義します。

|手順|Duration|責任ある当事者|説明|
|:--------|:--------|:--------|:--------|
|Opt-In|時間|顧客|組織に移行を選択します。|
|プレワーク|日数|顧客|ユーザー、ワークステーション、およびネットワークを移行用に準備するために必要な作業を完了します。|
|Azure Active Directory (Azure AD)|1~ 2 日|Microsoft|Azure AD組織を世界中に移行します。|
|Azure|週|顧客|新しい世界中の Azure サブスクリプションを作成し、Azure サービスを移行します。|
|サブスクリプション&ライセンス移行|1~ 2 日|Microsoft|世界中のサブスクリプションを購入し、Microsoft Cloud Deutschland サブスクリプションをキャンセルし、ユーザー ライセンスを移行します。|
|SharePoint および OneDrive|15 日以上|Microsoft|SharePoint と OneDrive for Business コンテンツを移行し、URL sharepoint.de保持します。|
|Exchange Online|15 日以上|Microsoft|Exchange Online コンテンツを移行し、世界中の URL に移行します。|
|セキュリティとコンプライアンス|1~ 2 日|Microsoft|コンプライアンス ポリシー&コンテンツに対するセキュリティの移行。|
|Skype for Business|1~ 2 日|Microsoft|Skype for Business から Microsoft Teams への移行。|
|Power BI & Dynamics 365|15 日以上|Microsoft|Power BI および Dynamics 365 コンテンツを移行します。|
|Azure の最終AD|1~ 2 日|Microsoft|テナントを世界中に切り替えます。|
|Clean-Up|1~ 2 日|顧客|Active Directory フェデレーション サービス (AD FS) 証明書利用者信頼、Azure AD Connect、および Office クライアントの再起動など、Microsoft Cloud Deutschland への従来の接続をクリーンアップします。|

フェーズとそのアクションにより、重要なデータとエクスペリエンスが 365 グローバル Officeに移行されます。 テナントが移行キューに追加されると、各ワークロードは、バックエンド サービスで実行される一連の手順として完了します。 一部のワークロードでは、管理者 (またはユーザー) によるアクションが必要な場合や、移行が実行および説明されているフェーズの使用状況に影響を与える場合があります。「移行の整理方法」を [参照してください。](ms-cloud-germany-transition.md#how-is-the-migration-organized)

次のセクションには、移行のさまざまなフェーズを進むワークロードのアクションと効果が含まれています。 表を確認し、組織に適用できるアクションまたは効果を決定します。 必要に応じて、それぞれのフェーズで手順を実行する準備ができているか確認します。 必要な手順を完了できないと、サービスが停止し、365 サービスへの移行がOffice可能性があります。

## <a name="opt-in"></a>Opt-In

**適用対象**: Microsoft Cloud Deutschland (MCD) でホストOffice 365 テナントを持つすべてのお客様
| Step(s) | 説明 | 影響 |
|:-------|:-----|:-------|
| MCD でホストOffice 365 テナントを、同意なしに移行することはできません。 | Microsoft は 2 つの方法のいずれかを使用して移行する権利を取得します。これにより、Microsoft はデータとサービスの Office 365 Global services インスタンスへの移行を調整できます。 <ol><li>365 Office管理者は、Microsoft が駆動する移行にオプトインします。 </li><li> お客様は、2020 年 5 月 1 日Office MCD テナント 365 テナント内のすべてのサブスクリプションを更新します。 毎月、これらの顧客に移行の権利を通知し、30 日待って顧客にキャンセルの機会を与え、その後直接オプトインします。</li></ol> | <ul><li>テナントは移行に同意済みとしてマークされ、管理センターには確認が表示されます。 </li><li>受信確認は、Office 365 テナント メッセージ センターに投稿されます。 サービス構成は、Microsoft Cloud Deutschland エンドポイントから続行されます。 </li><li>テナント administatror は、Office 365 メッセージ センターで、igration フェーズの状態に関する更新プログラムを監視する必要があります。 </li></ul>|

## <a name="subscription-phase-3"></a>サブスクリプション (フェーズ 3)

**適用対象**: Microsoft Cloud Deutschland (MCD) でホストOffice 365 テナントを持つすべてのお客様

| Step(s) | 説明 | 影響 |
|:-------|:-------|:-------|
| サブスクリプションが転送され、ライセンスが再割り当てされます。 | 対応Office 365 グローバル サービス サブスクリプションは、転送された Microsoft Cloud Deutschland サブスクリプションの Office 365 Global インスタンスで購入されます。 割り当てられた Microsoft Cloud Deutschland ライセンスを持つユーザーには、365 Global インスタンスOfficeライセンスが割り当てられます。 従来の Microsoft Cloud Deutschland サブスクリプションは、Office 365 サービス テナントから削除されます。| <ul><li>既存のサブスクリプションへの変更は、このフェーズ中にブロックされます (たとえば、新しいサブスクリプション購入やシート 数の変更はありません)。</li><li>ライセンス割り当ての変更はブロックされます。</li><li>Microsoft Cloud Deutschland サブスクリプションは、対応する 365 Global services サブスクリプションOfficeに移行されます。 このサブスクリプションOffice 365 Global Services オファーは、Microsoft (オファー マッピングとも呼ばれる) _によって定義されます_。</li><li>365 サービスによって提供される機能 (サービス プラン) の数は、Office Microsoft Cloud Deutschland オファーよりも大きくなる可能性があります。 365 サービスOfficeユーザー ライセンスは、同様の Microsoft Cloud Deutschland 機能 (サービス プラン) と同等に割り当てられます。 すべてのユーザーのユーザー ライセンスが新しい機能に自動的に割り当てられます。 管理者は、必要に応じて、これらのライセンスを無効にする明示的なアクションを実行する必要があります。 </li><li>サブスクリプションの移行が完了すると、Office 365 サービスと Microsoft Cloud Deutschland サブスクリプションの両方が Office 365 管理ポータルに表示され、Microsoft Cloud Deutschland サブスクリプションの状態がプロビジョニング解除されます。 </li><li>ユーザーは、新しい 365 サービス サブスクリプションに関連付Office再割り当てされます。 MCD サブスクリプションまたは SKU GUID に依存している顧客プロセスは壊れ、Office 365 サービスを提供する必要があります。 </li><li>Office 365 サービスの新しいサブスクリプションは、新しい用語 (毎月/四半期/年) で購入され、お客様は Microsoft Cloud Deutschland サブスクリプションの未使用残高に対して日割り払い払いを受け取る予定です。 </li><li>パートナーの Microsoft Cloud Deutschland テナントは移行されません。 CSP のお客様は、同Officeの新しいサービス 365 サービス テナントOffice 365 サービスに移行されます。 顧客の移行後、パートナーは 365 サービス テナントOfficeこの顧客を管理できます。 </li><li>テナント管理者が無効にしない限り、追加の機能 (Microsoft Planner や Microsoft Flow など) を使用できます。ユーザーのライセンスに割り当てられているサービス プランを無効にする方法については、「ユーザー ライセンスの割り当て中に [Microsoft 365](disable-access-to-services-while-assigning-user-licenses.md)サービスへのアクセスを無効にする」を参照してください。</li></ul> |
||||

## <a name="sharepoint-online-phase-4"></a>SharePoint Online (フェーズ 4)

**適用対象**: SharePoint Online を使用しているすべてのお客様

| Step(s) | 説明 | 影響 |
|:-------|:-----|:-------|
| SharePoint と OneDrive が移行される | SharePoint Online と OneDrive for Business は、このフェーズで Microsoft Cloud Deutschland から Office 365 グローバル サービスに移行されます。<br><ul><li>既存の Microsoft Cloud Deutschland URL は保持されます (たとえば `contoso.sharepoint.de` )。</li><li>既存のサイトは保持されます。</li><li>Microsoft Cloud Deutschland または Office 365 Global services インスタンスのセキュリティ トークン サービス (STS) によって発行されたクライアント側認証トークンは、移行中に有効です。</li></ul>|<ul><li>移行中の 2 つの短い期間、コンテンツは読み取り専用になります。 この間、SharePoint で "コンテンツを編集できない" バナーが表示されます。</li><li>検索インデックスは保持されません。再構築には最大 10 日かかる場合があります。</li><li>SharePoint Online および OneDrive for Business コンテンツは、移行中に 2 つの短い期間の読み取り専用になります。 この間、ユーザーには「コンテンツを編集できない」バナーが簡単に表示されます。</li><li>SharePoint Online の移行が完了すると、インデックスの再構築中に SharePoint Online および OneDrive for Business コンテンツの検索結果が使用できなくなる場合があります。 この期間中、検索クエリで完全な結果が返されない場合があります。 SharePoint Online News などの検索インデックスに依存する機能は、インデックスの再作成が完了する間に影響を受ける可能性があります。</li></ul>|
||||

その他の考慮事項:

- 組織で引き続き SharePoint 2010 ワークフローを使用している場合、2021 年 12 月 31 日以降は機能しなくなりました。 SharePoint 2013 ワークフローは引き続きサポートされます。ただし、2020 年 11 月 1 日から新しいテナントでは既定でオフになっています。 SharePoint Online サービスへの移行が完了したら、Power Automate または他のサポートされているソリューションに移動することをお勧めします。

- SharePoint Online インスタンスがまだ移行されていない Microsoft Cloud Deutschland のお客様は、SharePoint Online PowerShell モジュール/Microsoft.SharePointOnline.CSOM バージョン 16.0.20616.12000 以下に滞在する必要があります。 それ以外の場合、PowerShell またはクライアント側のオブジェクト モデルを介して SharePoint Online への接続が失敗します。

- SharePoint Online インスタンスが移行される Microsoft Cloud Deutschland のお客様は、SharePoint Online PowerShell モジュール/Microsoft.SharePointOnline.CSOM をバージョン 16.0.20717.12000 以上に更新する必要があります。 それ以外の場合、PowerShell またはクライアント側のオブジェクト モデルを介して SharePoint Online への接続が失敗します。

## <a name="exchange-online-phase-5"></a>Exchange Online (フェーズ 5)

**適用対象:** Exchange Online を使用しているすべてのお客様

Exchange Online ハイブリッドを使用している場合:Exchange Online ハイブリッド管理者は、この移行の一環としてハイブリッド構成ウィザード  **(HCW)** を複数回実行する必要があります。 Exchange の [事前作業の高度な移行手順を参照してください。](ms-cloud-germany-transition-add-experience.md#Exchange-Online-before-phase-5)

移行の事前作業で [](ms-cloud-germany-transition-add-pre-work.md#exchange-online)説明したように、移行手順 **フェーズ 5** が開始する前に、Exchange Online ハイブリッドのお客様は、Office 365 グローバル サービスへの移行用のオンプレミス構成を準備するために、「Office 365 Germany」モードで最新バージョンの Exchange ハイブリッド構成ウィザード (HCW) を実行する必要があります。

移行 **フェーズ 5** が完了すると (メッセージ センター通知が公開されている場合)、Office 365 Worldwide 設定を使用して HCW を再度実行して、オンプレミス システムを Office 365 Global サービスに接続する必要があります。 カスタム ドメインを使用する場合は、追加の DNS 更新プログラムが必要になる場合があります。

| Step(s) | 説明 | 影響 |
|:-------|:-------|:-------|
| Exchange Online メールボックスは、Microsoft Cloud Deutschland から 365 グローバル Officeに移動されます。| Exchange Online の構成では、移行中の組織に新しい移動先のドイツ語地域が追加されます。 365 Officeグローバル サービス領域は既定として設定され、内部負荷分散サービスはメールボックスを 365 サービス内の適切な既定の領域に再配布Officeできます。 この移行では、どちらの側 (MCD またはグローバル サービス) のユーザーも同じ組織内にいて、いずれかの URL エンドポイントを使用できます。 |<ul><li>ユーザーとサービスを従来の MCD URL (outlook.office.de) から新しいサービス 365 Office URL ( ) に移行します `https://outlook.office365.com` 。</li><li>ユーザーは移行中に従来の MCD URL を通じてサービスに引き続きアクセスすることができますが、移行が完了すると、従来の URL の使用を停止する必要があります。</li><li>ユーザーは、オンライン機能 (予定表、メールOfficeユーザー) Office のOfficeポータルを使用するに移行する必要があります。 365 サービスにまだ移行されていないサービスOffice移行するまでは機能しません。 </li><li>移行Outlook Web Appパブリック フォルダーエクスペリエンスは提供しない場合があります。 </li></ul>|
| 自動検出のカスタム DNS 設定を更新する| 現在 Microsoft Cloud Deutschland を指している AutoDiscover の顧客管理 DNS 設定を更新して、Exchange Online フェーズ (フェーズ 5) の完了時に Office 365 Global エンドポイントを参照する必要があります。 <br> CNAME を指す既存の DNS エントリautodiscover-outlook.office.deをポイントするために更新するautodiscover.outlook.com。 |  AutoDiscover 経由の可用性要求とサービス検出呼び出しは、365 サービスOffice直接ポイントします。 これらの DNS 更新を実行しないお客様は、移行が完了すると自動検出サービスの問題が発生する可能性があります。 |
||||

その他の考慮事項:
<!--
    The statement below is not clear. What does myaccount.microsoft.com mean?
-->

- `myaccount.microsoft.com` は、フェーズ 9 のテナントカットオーバー後にのみ機能します。 リンクは、その時間まで "何か問題が発生しました" というエラー メッセージを生成します。

- 他のOutlook Web Appの共有メールボックスにアクセスするユーザー (たとえば、MCD 環境のユーザーがグローバル環境の共有メールボックスにアクセスする場合など) は、2 回目の認証を求めるメッセージが表示されます。 ユーザーは、最初に自分のメールボックスを認証してアクセスし、次に共有メールボックスを `outlook.office.de` 開く必要があります `outlook.office365.com` 。 他のサービスでホストされている共有リソースにアクセスする場合は、2 回目の認証が必要です。

- 既存の Microsoft Cloud Deutschland のお客様または移行中のユーザーの場合、共有メールボックスが File **> Info >** Add Account を使用して Outlook に追加された場合、予定表のアクセス許可の表示が失敗する場合があります (Outlook クライアントは Rest API を使用しようと試み `https://outlook.office.de/api/v2.0/Me/Calendars` .)予定表のアクセス許可を表示するアカウントを追加する場合は [、「Outlook](https://support.microsoft.com/office/user-experience-changes-for-sharing-a-calendar-in-outlook-5978620a-fe6c-422a-93b2-8f80e488fdec) で予定表を共有するためのユーザー エクスペリエンスの変更」の説明に従ってレジストリ キーを追加して、このアクションが成功するようにすることができます。 このレジストリ キーは、グループ ポリシーを使用して組織全体に展開できます。

- 移行フェーズ中に、PowerShell コマンドレット **New-migrationEndpoint、Set-MigrationEndpoint、** および **Test-MigrationsServerAvailability** を使用すると、エラー (プロキシでエラー) が発生する可能性があります。  これは、調停メールボックスが世界中に移行されたが、管理者メールボックスが移行または逆の場合に発生します。 これを解決するには、テナント PowerShell セッションの作成中に **、ConnectionUri** のルーティング ヒントとして調停メールボックスを使用します。 次に例を示します。

```powershell
New-PSSession 
    -ConfigurationName Microsoft.Exchange 
    -ConnectionUri "https://outlook.office365.com/powershell-liveid?email=Migration.8f3e7716-2011-43e4-96b1-aba62d229136@TENANT.onmicrosoft.de"
    -Credential $UserCredential
    -Authentication Basic
    -AllowRedirection
```

移行および Exchange Online リソースの移行後の組織の違いの詳細については、「新しいドイツのデータセンター地域の [Office 365](ms-cloud-germany-transition-experience.md)サービスへの移行中のカスタマー エクスペリエンス」の情報を確認してください。

## <a name="exchange-online-protection--security-and-compliance-phase-6"></a>Exchange Online Protection / Security and Compliance (フェーズ 6)

**適用対象:** Exchange Online を使用しているすべてのお客様<br>

Exchange Online Protection (EOP) のバック エンド機能は、新しい地域 "ドイツ" にコピーされます。

| Step(s) | 説明 | 影響 |
|:-------|:-------|:-------|
| Exchange Online ルーティングと履歴メッセージの詳細の移行。 | Exchange Online を使用すると、外部ホストから 365 Officeルーティングできます。 外部 MX レコードは、EOP サービスにルーティングするために移行されます。 テナントの構成と履歴の詳細が移行されます。 |<ul><li>Microsoft が管理する DNS エントリは、365 ドイツ EOP Office 365 サービスOffice更新されます。</li><li>EOP のデュアル書き込みで EOP の移行を行った後、お客様は 30 日間待機する必要があります。 それ以外の場合は、データ損失が発生する可能性があります。</li></ul>|
||||

## <a name="skype-for-business-online-phase-7"></a>Skype for Business Online (フェーズ 7)

**適用対象:** SharePoint Online を使用しているすべてのユーザー

<!--
    Question from ckinder
    the PowerShell command seems to be incomplete
-->
| Step(s) | 説明 | 影響 |
|:-------|:-------|:-------|
| Skype for Business から Teams への移行。 | 既存の Skype for Business のお客様は、ヨーロッパの Office 365 グローバル サービスに移行され、Office 365 サービスの地域 "ドイツ" の Microsoft Teams に移行されます。 |<ul><li>ユーザーは移行日に Skype for Business にサインインできない。 移行の 10 日前に管理センターに投稿し、移行がいつ行われ、移行を開始するときにもう一度知らせます。</li><li> ポリシー構成が移行されます。 </li><li>ユーザーは Teams に移行され、移行後に Skype for Business を使用できなくなりました。 </li><li>ユーザーには Teams デスクトップ クライアントがインストールされている必要があります。 インストールは、Skype for Business インフラストラクチャのポリシーを介して 10 日間に行われますが、失敗した場合でも、ユーザーはクライアントをダウンロードするか、サポートされているブラウザーに接続する必要があります。 </li><li>連絡先と会議は Teams に移行されます。</li><li>タイム サービスが Office 365 サービスに移行するまで、顧客の DNS エントリが完了するまで、ユーザーは Skype for Business にサインインできない。 </li><li>連絡先と既存の会議は、引き続き Skype for Business 会議として機能します。 </li><li>PowerShell は、テナントとユーザーの設定とポリシーを管理するために使用します。 PowerShell セッションに接続する場合は、次の項目を追加します。 <br><br> `-OverridePowershellUri "https://admin4E.online.lync.com/OcsPowershellOAuth"`</li></ul>|
||||

## <a name="dynamics-365-phase-8"></a>Dynamics 365 (フェーズ 8)

**適用対象:** Microsoft Dynamics 365 を使用しているすべてのお客様

Dynamics 365 をお持ちのお客様は、組織の Dynamics 組織を個別に移行するために追加の契約が必要です。

| Step(s) | 説明 | 影響 |
|:-------|:-------|:-------|
| Microsoft Dynamics リソース | Microsoft Dynamics をお持ちのお客様は、Microsoft Engineering または Microsoft FastTrack が Microsoft Dynamics 365 を Office 365 Global services インスタンスに移行します。* |<ul><li>移行後、管理者は組織を検証します。 <</li><li>管理者は、必要に応じてワークフローを変更します。 </li><li>管理者は、必要に応じて AdminOnly モードをクリアします。</li><li>管理者は、必要に応じて _サンドボックスから組織_ の種類を変更します。</li><li>インスタンス (org) にアクセスする新しい URL をエンド ユーザーに通知します。</li><li>新しいエンドポイント URL への受信接続を更新します。 </li><li>移行中は、ユーザーが Dynamics サービスを利用できません。 </li><li>ユーザーは、各組織の移行後に組織の正常性と機能を検証する必要があります。</li></ul>|
|||||

\* (i) Microsoft Dynamics 365 をお持ちのお客様は、提供される移行プロセスで定義されているこの移行シナリオでアクションを実行する必要があります。 (ii) お客様がアクションを実行できなかった場合、Microsoft は移行を完了できません。 (iii) お客様の不作為により Microsoft が移行を完了できない場合、お客様のサブスクリプションは 2021 年 10 月 29 日に期限切れになります。

## <a name="power-bi-phase-8-of-9"></a>Power BI (フェーズ 8 / 9)

**適用対象:** Microsoft Power BI (PBI) を使用しているすべてのお客様

| Step(s) | 説明 | 影響 |
|:-------|:-------|:-------|
| Power BI リソースの移行 | Microsoft Power BI (PBI) をお持ちのお客様は、既存の PBI 移行ツールを手動でトリガーして Power BI を Office 365 グローバル サービス インスタンスに移行した後、Microsoft Engineering または Microsoft FastTrack に参加します。\*\* |<ul><li>次の Power BIアイテムは移行されないので、次のアイテムを再作成する必要<</li><li>リアルタイム データセット (ストリーミング データセットやプッシュ データセットなど)。 </li><li>Power BI オンプレミス データ ゲートウェイの構成とデータ ソース。 </li><li>リアルタイム データセットの上に構築されたレポートは、移行後に使用できないので、再作成する必要があります。 </li><li>Power BI サービスは、移行中にユーザーが利用できません。 サービスが利用できない時間は 24 時間を超えてはならない。</li><li>移行後、ユーザーは Power BI サービスを使用してデータ ソースとオンプレミス のデータ ゲートウェイを再構成する必要があります。  そうするまで、ユーザーは、これらのデータ ソースを使用して、スケジュールされた更新を実行したり、これらのデータ ソースに対して直接クエリを実行したりすることはできません。 </li><li>容量とプレミアム ワークスペースは移行できません。 移行前にすべての容量を削除し、移行後に再作成する必要があります。 ワークスペースを必要に応じて容量に戻します。</li></ul>  |
||||

\*\* (i) Microsoft Power BI をお持ちのお客様は、提供される移行プロセスで定義されているこの移行シナリオでアクションを実行する必要があります。 (ii) お客様がアクションを実行できなかった場合、Microsoft は移行を完了できません。 (iii) お客様の不作為により Microsoft が移行を完了できない場合、お客様のサブスクリプションは 2021 年 10 月 29 日に期限切れになります。

## <a name="office-apps"></a>Office アプリ

**適用対象:** デスクトップ アプリケーションをOfficeしているすべてのお客様 (Word、Excel、PowerPoint、Outlook、...)

Office "ドイツ" に移行する 365 テナントでは、テナント移行がフェーズ 9 に達した後、すべてのユーザーが Office 365 からサインアウトし、Office デスクトップ アプリケーション (Word、Excel、PowerPoint、Outlook など) および OneDrive for Business クライアントに戻る必要があります。 サインアウトしてサインインすると、Officeサービスは、グローバル Azure AD サービスから新しい認証トークンを取得できます。

| Step(s) | 説明 | 影響 |
|:-------|:-------|:-------|
| クライアントはOffice切りOffice、Azure ADは、365 サービスを指すテナント スコープをOfficeします。 | この構成変更により、Office 365 サービス エンドポイントを更新し、Officeポイントできます。 | <ul><li>すべての Office _アプリを_ 閉じてからサインイン (またはクライアントの再起動とユーザーのサインインを強制する) をユーザーに通知して、Office クライアントが変更を受け取るのを有効にします。 </li><li>カットオーバーから 72時間以内に、Office アプリの再アクティブ化を求める Office バナーが表示される可能性があるユーザーとヘルプ デスク スタッフに通知します。 </li><li>個人用Office上のすべてのアプリケーションを閉じ、ユーザーはサインアウトしてからもう一度サインインする必要があります。 [黄色のライセンス認証] バーでサインインし、365 サービスOffice再アクティブ化します。</li><li>共有コンピューターでは、個人用のコンピューターに似たアクションが必要であり、特別な手順は必要とします。 </li><li>モバイル デバイスでは、ユーザーはアプリからサインアウトして閉じてから、もう一度サインインする必要があります。 </li></ul>|
||||

## <a name="office-services"></a>Office サービス

Office で最も最近使用された (MRU) サービスは、移行ではなく、MCD Office 365 Global サービスへの切り替えです。 365 Global services 側Office MRU リンクだけが、ポータルから移行した後Office.comされます。 MCD からの MRU リンクは、365 グローバル サービスOffice MRU リンクとして表示されません。 365 Officeグローバル サービスでは、MRU リンクにアクセスできるのは、テナントの移行がフェーズ 9 に達した後のみです。

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
