---
title: DLP アラート ダッシュボードの詳細
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
- admindeeplinkCOMPLIANCE
description: データ損失防止アラートとアラート ダッシュボードについて説明します。
ms.openlocfilehash: 1551b247e3302af6dc8ed9af62a88f2c24415122
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66636163"
---
# <a name="learn-about-the-data-loss-prevention-alerts-dashboard"></a>データ損失防止の警告ダッシュボードについて

Microsoft Purview データ損失防止 (DLP) ポリシーの条件が、ユーザーが機密アイテムに対して実行しているアクションと一致する場合、ポリシーはアラートを生成できます。 この状況により、大量のアラートが発生する可能性があります。 DLP アラートは、アラート ダッシュボードに収集されます。 アラート ダッシュボードでは、ポリシー一致に関するすべての詳細を詳細に調査するための 1 つの場所を提供します。  

<!-- [Microsoft Purview compliance portal](https://compliance.microsoft.com/)-->

## <a name="workloads"></a>ワークロード

[MICROSOFT PURVIEW コンプライアンス ポータルの DLP アラート管理ダッシュボード](https://compliance.microsoft.com/datalossprevention?viewid=dlpalerts)<a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">には、これらの</a>ワークロードに対する DLP ポリシーのアラートが表示されます。

- Exchange
- SharePoint
- OneDrive
- Teams
- Windows 10 デバイス 

> [!TIP]
> Teams DLP の対象となる [エンドポイント DLP](endpoint-dlp-learn-about.md) を使用しているお客様は、 [エンドポイント](dlp-microsoft-teams.md) DLP ポリシー アラートと Teams DLP ポリシー アラートが DLP アラート管理ダッシュボードに表示されます。

## <a name="single-alert-and-aggregate-alert"></a>単一のアラートと集計アラート

DLP ポリシーで構成できるアラートには、2 種類あります。

**通常、単一イベント アラート** は、組織の外部で送信される 10 個以上の顧客クレジット カード番号を含む 1 つのメールなど、大量に発生する機密性の高いイベントを監視するポリシーで使用されます。

**集計イベント アラート** は、通常、一定期間にわたって大量に発生するイベントを監視するポリシーで使用されます。 たとえば、1 つの顧客クレジット カード番号を持つ個々のメールがそれぞれ 10 件、組織外で 48 時間にわたって送信されると、集計アラートをトリガーできます。

## <a name="types-of-events"></a>イベントの種類

アラートに関連付けられているイベントの一部を次に示します。 UI では、特定のイベントを選択してその詳細を表示できます。 

### <a name="event-details"></a>イベントの詳細

|プロパティ名  |説明  |イベントの種類  |
|---------|---------|---------|
|ID |イベントに関連付けられた一意の ID |すべてのイベント |
|場所 |イベントが検出されたワークロード|すべてのイベント |
|アクティビティの時間     |DLP ポリシーの条件に一致したユーザー アクティビティの時間 |

### <a name="affected-entities"></a>影響を受けるエンティティ

|プロパティ名 |説明| イベントの種類|
|---------|---------|---------|
|ユーザー | ポリシー一致の原因となったアクションを実行したユーザー | すべてのイベント|
|ホスト | DLP ポリシーが一致したコンピューターのホスト名 | デバイス イベント|
|IP アドレス | DLP ポリシーが一致したコンピューターの IP アドレス | デバイス イベント|
|sha1 |ファイルの SHA-1 ハッシュ | デバイス イベント|
|sha256 | ファイルの SHA-256 ハッシュ | デバイス イベント|
|MDATP デバイス ID | エンドポイント デバイス MDATP ID|
|ファイル サイズ | ファイルのサイズ| SharePoint、OneDrive、およびデバイス イベント|
|ファイル パス | DLP ポリシー一致に関連するアイテムの絶対パス | SharePoint、OneDrive、デバイスのイベント|
|電子メール受信者 |電子メールが DLP ポリシーと一致する機密アイテムであった場合、このフィールドにはその電子メールの受信者が含まれます| Exchange イベント|
|電子メールの件名 |DLP ポリシーに一致した電子メールの件名 |Exchange イベント|
|電子メールの添付ファイル | DLP ポリシーに一致した電子メール内の添付ファイルの名前| Exchange イベント|
|サイト所有者 |サイト所有者の名前| SharePoint イベントと OneDrive イベント|
|サイト URL |DLP ポリシーが一致した SharePoint サイトまたは OneDrive サイトの URL がいっぱい |SharePoint イベントと OneDrive イベント|
|ファイルが作成されました |DLP ポリシーに一致したファイルの作成時間 |SharePoint イベントと OneDrive イベント|
|最後に変更されたファイル | DLP ポリシーに一致したファイルが最後に変更された時刻 | SharePoint イベントと OneDrive イベント|
|ファイル サイズ | DLP ポリシーに一致したファイルのサイズ |SharePoint イベントと OneDrive イベント|
|ファイル所有者 |DLP ポリシーに一致したファイルの所有者 |SharePoint イベントと OneDrive イベント|  

### <a name="policy-details"></a>ポリシーの詳細

|プロパティ名 |説明 |イベントの種類 |
|---------|---------|---------|
|DLP ポリシーの一致 |一致する DLP ポリシーの名前 |すべてのイベント|
|一致するルール |一致する DLP ポリシー ルールの名前 |すべてのイベント|
|検出された機密情報の種類 (SIT)|DLP ポリシー一致の一部として検出された SIT |すべてのイベント|
|実行された処理 |DLP ポリシーの一致の原因となった実行されたアクション| すべてのイベント|
|違反アクション | DLP アラートを発生させたエンドポイント デバイスのアクション| デバイス イベント | 
|ユーザー オーバーロード ポリシー |ユーザーがポリシー ヒントを使用してポリシーをオーバーライドしました | すべてのイベント|
|オーバーライドの理由を使用する |オーバーライドのためにユーザーが指定した理由のテキスト | すべてのイベント|   

## <a name="see-also"></a>関連項目

- [データ損失防止の警告ダッシュボードを開始する](dlp-alerts-dashboard-get-started.md)
- [データ損失防止を開始する場所](create-test-tune-dlp-policy.md#where-to-start-with-data-loss-prevention)
