---
title: 移行フェーズのアクションと影響
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
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
description: '概要: 新しいドイツデータセンターリージョンで、移行フェーズのアクションと Microsoft Cloud ドイツ (Microsoft Cloud Deut上陸陸地) から Office 365 サービスへの移行による影響について説明します。'
ms.openlocfilehash: 9ffdb0bbe60bdb96d6e110ac08cba4030272c7e9
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/02/2020
ms.locfileid: "49551659"
---
# <a name="migration-phases-actions-and-impacts"></a>移行フェーズのアクションと影響

Microsoft Cloud Deut上陸ランドから、Microsoft の Office 365 サービスのドイツ地域へのテナントの移行は、各ワークロードに対して構成された一連のアクションとして実行されます。 これらの操作によって、重要なデータとエクスペリエンスが Office 365 サービスに移行されます。 テナントが移行キューに追加されると、各ワークロードはバックエンドサービスで実行される一連の手順として完了します。 一部のワークロードでは、管理者 (またはユーザー) によるアクションが必要になることがあります。または、移行は、実行されるフェーズの使用に影響することがあり [ます。](ms-cloud-germany-transition.md#how-is-the-migration-organized)

以下のセクションには、移行のさまざまなフェーズを通過するときのワークロードのアクションと影響が含まれています。 表を確認して、組織に適用される操作または効果を確認します。 必要に応じて、各フェーズで手順を実行する準備が整っていることを確認します。 必要な手順を完了しなかった場合、サービスが停止し、Office 365 サービスへの移行の完了が遅れる可能性があります。

## <a name="exchange-online"></a>Exchange Online

| ステップ (s) | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| 既存の組織の設定に新しいドイツ地域が追加され、メールボックスは Office 365 サービスに移動されます。 | Exchange Online 構成は、移行中の組織に新しい go ローカルなドイツ地域を追加します。 この Office 365 サービス地域は既定として設定されています。これにより、内部の負荷分散サービスが、Office 365 services の適切な既定の地域にメールボックスを再配布できるようになります。 この移行では、いずれかの側 (ドイツまたは Office 365 services) のユーザーは同じ組織内にあり、いずれかの URL エンドポイントを使用できます。 | Exchange Online | -ユーザーおよびサービスをドイツの Url から Office 365 services の Url () に移行 `https://outlook.office365.com` します。 <br><br> -移行中は、ユーザーは従来のドイツの Url を使用して引き続きサービスにアクセスできます。 すぐに必要な操作はありません。 <br><br> -ユーザーは、Office Online 機能 (予定表、メール、ユーザー) の office.com ポータルの使用を開始する必要があります。 まだ Office 365 サービスに移行されていないサービスへの移動は、移行されるまでは機能しません。 <br><br> -移行中は、Outlook Web App はパブリックフォルダーの機能を提供しません。 |
|||||

移行における組織の相違点について、および Exchange Online のリソースを移行した後に、 [新しいドイツデータセンターリージョンで Office 365 サービスへの移行中にお客様の環境](ms-cloud-germany-transition-experience.md)に関する情報を確認します。

## <a name="exchange-online-protection"></a>Exchange Online Protection

バックエンド Exchange Online Protection (EOP) の機能は、新しいドイツ地域にコピーされます。 

| ステップ (s) | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| Exchange Online のルーティングと履歴メッセージの詳細の移行。 | Exchange Online は、外部ホストから Office 365 へのルーティングを有効にします。 外部 MX レコードは、EOP サービスへのルーティングに移行されます。 テナントの構成と履歴の詳細が移行されます。 | Exchange Online のお客様 | -Microsoft – managed DNS エントリは、Office 365 ドイツ EOP から Office 365 services に更新されています。 <br><br> -お客様は、EOP dual write for EOP migration の後30日間待つ必要があります。 そうしないと、データが失われる可能性があります。 |
|||||

## <a name="sharepoint-online"></a>SharePoint Online

<!--

| Step(s) | Description | Applies to | Impact |
|:-------|:-----|:-------|:-------|
| SharePoint and OneDrive are transitioned. | SharePoint and OneDrive are migrated from Microsoft Cloud Deutschland to Office 365 services in this phase. Existing Microsoft Cloud Deutschland URLs are preserved (for example, `contoso.sharepoint.de`). Tokens that were issued by Microsoft Cloud Deutschland or Office 365 services are valid during the transition. | SharePoint customers | - Content will be read-only for two brief periods (less than x minutes) during migration. During this time, expect a "you can't edit content" banner in SharePoint. <br><br> - The search index won't be preserved, and may take up to 10 days to be rebuilt. <br><br> - SharePoint/OneDrive content will be read-only for two brief periods (less than x minutes) during migration. Users will see a "you can't edit content" banner briefly during this time. <br><br> - The search index may be unavailable while the index is rebuilt. During this period, search queries might not return complete results. <br><br> - Existing sites are preserved. |
|||||

--> 

| ステップ (s) | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| SharePoint と OneDrive は移行されます。 | このフェーズでは、SharePoint と OneDrive を Microsoft Cloud Deut上陸ランドから Office 365 サービスに移行します。 既存の Microsoft Cloud Deut陸の Url は保持されます (例: `contoso.sharepoint.de` )。 Microsoft Cloud Deut上陸ランドまたは Office 365 サービスによって発行されたトークンは、移行中に有効になります。 | SharePoint のお客様 | -移行中は、コンテンツは2つの短い期間のみ読み取り専用になります。 この間、SharePoint の "コンテンツを編集できません" というバナーが期待されます。 <br><br> -検索インデックスは保持されないため、再構築するには最大10日かかる場合があります。 <br><br> -移行中は、SharePoint/OneDrive のコンテンツは2つの短い期間のみ読み取り専用になります。 この間、ユーザーには "コンテンツを編集できません" というバナーが短時間で表示されます。 <br><br> -インデックスが再構築されている間は検索インデックスを使用できない場合があります。 この期間中は、検索クエリが完全な結果を返さない場合があります。 <br><br> -既存のサイトは保持されます。 |
|||||


## <a name="skype-for-business-online"></a>Skype for Business Online

| ステップ (s) | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| Skype for Business から Teams への移行。 | 既存の Skype for Business のお客様は、ヨーロッパの Office 365 サービスに移行され、Office 365 サービスのドイツ地域で Microsoft Teams に移行しています。 | Skype for Business のお客様 | -ユーザーは移行日に Skype for Business にサインインすることはできません。 移行の10日後に、ユーザーが Teams にアップグレードされる Skype for Business クライアントのインバンドを介してエンドユーザーに通知します。 また、これらの変更は10日後に行われることを管理センターに投稿します。 <br><br> -ポリシー構成は移行されます。 <br><br> -ユーザーは Teams に移行され、移行後は Skype for Business を使用できなくなります。 <br><br> -ユーザーに Teams デスクトップクライアントがインストールされている必要があります。 Skype for Business インフラストラクチャのポリシーを使用して10日以内にインストールが行われますが、この操作が失敗した場合でも、ユーザーはクライアントをダウンロードするか、サポートされているブラウザーで接続する必要があります。 <br><br> -連絡先と会議は Teams に移行されます。 <br><br> -ユーザーは、Office 365 サービスへのタイムサービスの移行間で Skype for Business にサインインすることはできず、顧客の DNS エントリが完了するまではサインインできません。 <br><br> -連絡先と既存の会議は、引き続き Skype for Business 会議として機能します。 |
|||||
        
## <a name="subscription"></a>サブスクリプション

| ステップ (s) | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| 同意せずにお客様を移行することはできません。 | Microsoft は、2つの方法のいずれかで移行する権利を獲得しています。これにより、Microsoft は、データとサービスを Office 365 services インスタンスに移行することができます。 <br> 管理者は、Microsoft による移行にアクセスできます。 <br> お客様は、2020年5月1以降の Microsoft Cloud Deut上陸陸テナントのサブスクリプションを更新します。 これらのお客様には、毎月毎月移行を行うようにお客様に提供するために30日間待機してください。 | すべての Office のお客様 | -テナントは移行のために同意としてマークされ、管理センターには確認が表示されます。 <br><br> -受信確認は、Cloud ドイツのメッセージセンターテナントに投稿されます。 サービス構成は、Microsoft Cloud Deut上陸陸上エンドポイントから続行されます。 <br><br> -移行フェーズ状態の更新プログラムについてメッセージセンターを監視します。 |
| サブスクリプションが転送され、ライセンスが再割り当てされます。 | テナントが Office 365 services に移行されると、対応する Office 365 services サブスクリプションが、転送された Microsoft Cloud Deut/陸のサブスクリプションに対して購入されます。 Microsoft Cloud Deut陸のライセンスを割り当てられたユーザーには、Office 365 services のライセンスが割り当てられます。 従来の Microsoft Cloud Deut陸地のサブスクリプションは、完了時に Office 365 services のテナントから削除されます。 | すべての Office のお客様 | -このフェーズでは、既存のサブスクリプションに対する変更がブロックされます (たとえば、新しいサブスクリプションの購入や座席数の変更は行われません)。 <br><br> -ライセンスの割り当ての変更がブロックされます。 <br><br> -Microsoft Cloud Deut上陸陸サブスクリプションは、対応する Office 365 サービスサブスクリプションに移行されます。 このサブスクリプションの Office 365 サービス提供は、Microsoft ( _提供マッピング_ とも呼ばれる) によって定義されます。 <br><br> -Office 365 サービスによって提供される機能 (サービスプラン) の数は、元の Microsoft Cloud Deut土地提供者よりも大きくなる可能性があります。 Office 365 サービスのユーザーライセンスは、同様の Microsoft Cloud Deut上陸機能 (サービスプラン) に対して割り当てられます。 すべてのユーザーのユーザーライセンスが新しい機能に自動的に割り当てられます。 管理者は、必要に応じて、これらのライセンスを無効にするための明示的なアクションを実行する必要があります。 <br><br> -サブスクリプションの移行が完了すると、office 365 サービスとドイツの両方のサブスクリプションが Office 365 管理ポータルに表示され、 _停止_ としてドイツのサブスクリプションの状態が表示されます。 <br><br> -ユーザーは、新しい Office 365 サービスサブスクリプションに関連付けられているライセンスを再割り当てします。 ドイツのサブスクリプションまたは SKU Guid に依存しているお客様のプロセスは中断され、Office 365 サービスの提供によって改訂される必要があります。 <br><br> -Office 365 サービスの新しいサブスクリプションは新しい用語 (月額/四半期/年) で購入され、お客様は Microsoft Cloud Deut上陸陸サブスクリプションの未使用の残高に対して日割り計算が行われます。 <br><br> -パートナーの Microsoft Cloud Deut陸地のテナントは移行されません。 CSP のお客様は、同じパートナーの新しい Office 365 サービステナントの Office 365 サービスに移行されます。 お客様による移行後、パートナーは Office 365 services テナントからのみこのお客様を管理できます。 <br><br> -テナント管理者によって無効にされていない限り、追加機能 (たとえば、Microsoft Planner および Microsoft Flow) を使用できます。ユーザーのライセンスに割り当てられているサービスプランを無効にする方法については、「 [ユーザーライセンスの割り当て中に Microsoft 365 サービスへのアクセスを無効](disable-access-to-services-while-assigning-user-licenses.md)にする」を参照してください。  |
|||||

## <a name="next-step"></a>次のステップ

[追加の準備作業を実行する](ms-cloud-germany-transition-add-pre-work.md)

## <a name="more-information"></a>詳細情報

はじめに:

- [新しいドイツ語のデータセンターリージョンの Microsoft Cloud Deutランドから Office 365 サービスへの移行](ms-cloud-germany-transition.md)
- [Microsoft Cloud Deutschland 移行アシスタント](https://aka.ms/germanymigrateassist)
- [移行のオプトイン方法](ms-cloud-germany-migration-opt-in.md)
- [移行中の顧客の利便性](ms-cloud-germany-transition-experience.md)

遷移を移動します。

- [その他の準備作業](ms-cloud-germany-transition-add-pre-work.md)
- [サービス](ms-cloud-germany-transition-add-general.md)、[デバイス](ms-cloud-germany-transition-add-devices.md)、[エクスペリエンス](ms-cloud-germany-transition-add-experience.md)、 [AD FS](ms-cloud-germany-transition-add-adfs.md)の追加情報。

クラウドアプリ:

- [Dynamics 365 移行プログラム情報](https://aka.ms/d365ceoptin)
- [Power BI 移行プログラム情報](https://aka.ms/pbioptin)
- [Microsoft Teams へのアップグレードを開始する](https://aka.ms/SkypeToTeams-Home)
