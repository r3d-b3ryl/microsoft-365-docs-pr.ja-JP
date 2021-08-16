---
title: データ損失防止の警告ダッシュボードについて
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
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: データ損失防止アラートとアラート ダッシュボードについて学習します。
ms.openlocfilehash: 0474c5609fcd979fa8db7e47857c099cbed7be365bb55ee80e507ad3375da660
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53895661"
---
# <a name="learn-about-the-data-loss-prevention-alerts-dashboard"></a>データ損失防止の警告ダッシュボードについて

データ損失防止 (DLP) ポリシーの条件が、ユーザーが機密性の高いアイテムに対して実行しているアクションと一致する場合、ポリシーはアラートを生成できます。 これにより、多くのアラートが発生する可能性があります。 DLP アラートは、アラート ダッシュボードで収集されます。 アラート ダッシュボードを使用すると、ポリシーの一致に関する詳細の詳細を詳細に調べることができます。  

<!-- [Microsoft 365 compliance center](https://compliance.microsoft.com/)-->

## <a name="workloads"></a>ワークロード

DLP[アラート管理ダッシュボードは](https://compliance.microsoft.com/datalossprevention?viewid=dlpalerts)、次[](https://compliance.microsoft.com/)のMicrosoft 365 コンプライアンス センターに DLP ポリシーのアラートを表示します。

- Exchange
- SharePoint
- OneDrive
- Teams
- Windows 10 デバイス 

> [!TIP]
> Teams [DLP](dlp-microsoft-teams.md)の対象となるエンドポイント[DLP](endpoint-dlp-learn-about.md)を使用しているお客様は、DLP アラート管理ダッシュボードにエンドポイント DLP ポリシーアラートと Teams DLP ポリシーアラートを表示します。

## <a name="single-alert-and-aggregate-alert"></a>単一のアラートと集約アラート

DLP ポリシーで構成できるアラートには、2 種類があります。

**通常** 、単一イベントアラートは、10 以上の顧客クレジット カード番号が組織外に送信される単一の電子メールなど、ボリュームが少ない状態で発生する機密性の高いイベントを監視するポリシーで使用されます。

**通常、集約イベントアラート** は、一期間に渡って大きなボリュームで発生するイベントを監視するポリシーで使用されます。 たとえば、1 つの顧客クレジット カード番号を持つ 10 個の個別の電子メールが組織外に 48 時間以上送信されると、集約アラートをトリガーできます。

## <a name="types-of-events"></a>イベントの種類

アラートに関連付けられているイベントの一部を次に示します。 UI では、特定のイベントを選択して詳細を表示できます。 

### <a name="event-details"></a>イベントの詳細

|プロパティ名  |Description  |イベントの種類  |
|---------|---------|---------|
|ID |イベントに関連付けられた一意の ID |すべてのイベント |
|場所 |イベントが検出されたワークロード|すべてのイベント |
|アクティビティの時間     |DLP ポリシーの条件に一致したユーザー アクティビティの時間 |

### <a name="impacted-entities"></a>影響を受け取ったエンティティ

|プロパティ名 |Description| イベントの種類|
|---------|---------|---------|
|ユーザー | ポリシーの一致を引き起こしたアクションを実行したユーザー | すべてのイベント|
|ホスト名 | DLP ポリシーの一致が発生したコンピューターのホスト名 | デバイス イベント|
|IP アドレス | DLP ポリシーの一致が発生したコンピューターの IP アドレス | デバイス イベント|
|sha1 |ファイルの SHA-1 ハッシュ | デバイス イベント|
|sha256 | ファイルの SHA-256 ハッシュ | デバイス イベント|
|MDATP デバイス ID | エンドポイント デバイス MDATP ID|
|ファイル サイズ | ファイルのサイズ| SharePoint、OneDrive、デバイス イベント|
|ファイル パス | DLP ポリシーの一致に関連するアイテムの絶対パス | SharePoint、OneDriveデバイス イベント|
|電子メールの受信者 |電子メールが DLP ポリシーと一致する機密性の高いアイテムである場合、このフィールドには、その電子メールの受信者が含まれます。| Exchangeイベント|
|電子メールの件名 |DLP ポリシーに一致した電子メールの件名 |Exchangeイベント|
|電子メールの添付ファイル | DLP ポリシーに一致した電子メール内の添付ファイルの名前| Exchangeイベント|
|サイトの所有者 |サイト所有者の名前| SharePointイベントOneDriveイベント|
|サイト URL |DLP ポリシーの一致が発生したSharePointまたはOneDriveサイトの URL の完全 |SharePointイベントOneDriveイベント|
|作成されたファイル |DLP ポリシーに一致したファイルの作成時間 |SharePointイベントOneDriveイベント|
|ファイルの最終変更 | DLP ポリシーに一致したファイルが最後に変更された時刻 | SharePointイベントOneDriveイベント|
|ファイル サイズ | DLP ポリシーに一致したファイルのサイズ |SharePointイベントOneDriveイベント|
|ファイルの所有者 |DLP ポリシーに一致したファイルの所有者 |SharePointイベントOneDriveイベント|  

### <a name="policy-details"></a>ポリシーの詳細

|プロパティ名 |Description |イベントの種類 |
|---------|---------|---------|
|DLP ポリシーの一致 |一致する DLP ポリシーの名前 |すべてのイベント|
|ルールの一致 |一致する DLP ポリシー ルールの名前 |すべてのイベント|
|機密情報の種類 (SIT) が検出されました|DLP ポリシーの一致の一部として検出された SIT |すべてのイベント|
|実行された処理 |DLP ポリシーの一致を引き起こしたアクション| すべてのイベント|
|違反アクション | DLP アラートを発生したエンドポイント デバイスのアクション| デバイス イベント | 
|ユーザーのオーバーロード ポリシー |ユーザーがポリシー ヒントを使用してポリシーを上書きしました | すべてのイベント|
|オーバーライドの位置合わせを使用する |オーバーライドのためにユーザーが提供する理由のテキスト | すべてのイベント|   

## <a name="see-also"></a>関連項目

- [データ損失防止の警告ダッシュボードを開始する](dlp-alerts-dashboard-get-started.md)
- [データ損失防止を開始する場所](create-test-tune-dlp-policy.md#where-to-start-with-data-loss-prevention)