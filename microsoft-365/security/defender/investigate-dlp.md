---
title: Microsoft 365 Defenderを使用してデータ損失インシデントを調査する
description: Microsoft 365 Defenderのデータ損失を調査します。
keywords: データ損失防止, インシデント, アラート, 調査, 分析, 応答, 相関関係, 攻撃, マシン, デバイス, ユーザー, ID, ID, メールボックス, 電子メール, 365, Microsoft, m365
f1.keywords:
- NOCSH
ms.service: microsoft-365-security
ms.subservice: m365d
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
ms.openlocfilehash: 275a05db866de90eada1d948fff9fe559502d45f
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67474536"
---
# <a name="investigate-data-loss-incidents-with-microsoft-365-defender"></a>Microsoft 365 Defenderを使用してデータ損失インシデントを調査する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**

- Microsoft 365 Defender

Microsoft Purview データ損失防止 (DLP) のインシデントは、Microsoft 365 Defender ポータルで管理できるようになりました。 Microsoft 365 Defender <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">ポータル</a>のクイック起動で、DLP インシデントと **インシデントからのセキュリティ インシデント&アラート** \> **インシデント** を管理できます。 このページでは、次のことができます。

- Microsoft 365 Defenderインシデント キュー内のインシデントにグループ化されたすべての DLP アラートを表示します。
- 1 つのインシデントでインテリジェントなソリューション間 (DLP-MDE、DLP-MDO) とソリューション内 (DLP-DLP) の相関アラートを表示します。
- Advanced Hunting のセキュリティと共にコンプライアンス ログを探します。
- ユーザー、ファイル、およびデバイスに対するインプレース管理者修復アクション。 
- カスタム タグを DLP インシデントに関連付け、それらをフィルター処理します。
- DLP ポリシー名、タグ、日付、サービス ソース、インシデントの状態、および統合インシデント キューのユーザーでフィルター処理します。 

また、Microsoft Sentinel のMicrosoft 365 Defender コネクタを使用して、調査と修復のために DLP インシデントとイベントと証拠を Microsoft Sentinel にプルすることもできます。

## <a name="licensing-requirements"></a>ライセンスの要件

Microsoft 365 Defender ポータルでMicrosoft Purview データ損失防止インシデントを調査するには、次のいずれかのサブスクリプションからのライセンスが必要です。 

- Microsoft Office 365 E5/A5
- Microsoft 365 E5/A5
- Microsoft 365 E5/A5 コンプライアンス
- Microsoft 365 E5/A5 セキュリティ
- Microsoft 365 E5/A5 情報の保護とガバナンス

> [!NOTE] 
> この機能のライセンスが付与され、対象になると、DLP アラートが自動的にMicrosoft 365 Defenderに流れ込みます。 この機能を無効にする場合は、サポート ケースを開きます。 

## <a name="dlp-investigation-experience-in-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender ポータルでの DLP 調査エクスペリエンス

開始する前に、<a href="https://purview.microsoft.com" target="_blank">Microsoft Purview コンプライアンス ポータル</a>[内のすべての DLP ポリシーのアラートをオンにします](/microsoft-365/compliance/dlp-configure-view-alerts-policies#alert-configuration-experience)。

1. Microsoft 365 Defender ポータルに移動し、左側のナビゲーション メニューで [**インシデント**] を選択してインシデント ページを開きます。

2. 右上の **[フィルター** ] を選択し、[ **サービス ソース: データ損失防止** ] を選択して、DLP アラートを含むすべてのインシデントを表示します。

3. 目的のアラートとインシデントの DLP ポリシー名を検索します。

4. インシデントの概要ページを表示するには、キューからインシデントを選択します。 同様に、アラートを選択して DLP アラート ページを表示します。

5. ポリシーと **アラート** で検出された機密情報の種類の詳細については、アラート ストーリーを表示します。 **[関連** イベント] セクションでイベントを選択して、ユーザー アクティビティの詳細を表示します。

6. 必要なアクセス許可がある場合は、[ **機密情報の種類** ] タブで一致する機密コンテンツを表示し、[ **ソース]** タブのファイル コンテンツを表示します (詳細 <a href="/microsoft-365/compliance/dlp-alerts-dashboard-get-started#roles" target="_blank">については、こちらを</a>参照してください)。

7. また、Advanced Hunting を使用して、調査のためにユーザー、ファイル、サイトの場所の監査ログを検索することもできます。 **CloudAppEvents** テーブルには、SharePoint、OneDrive、Exchange、デバイスなどのすべての場所のすべての監査ログが含まれています。

8. [**アクション**\>のダウンロード] メールを選択して **、電子メールをダウンロード** することもできます。 

9. SPO サイトまたは ODB サイト上のファイルに対する修復アクションについては、次のようなアクションが表示されます。

    - 保持ラベルを適用する
    - 秘密度ラベルを適用する
    - ファイルの共有を解除する
    - Delete

   修復アクションの場合は、アラート ページの上部にある **ユーザー カード** を選択して、ユーザーの詳細を開きます。

   デバイス DLP アラートの場合は、アラート ページの上部にあるデバイス カードを選択して、デバイスの詳細を表示し、デバイスで修復アクションを実行します。

10. インシデントの概要ページに移動し、[ **インシデントの管理** ] を選択して、インシデント タグの追加、インシデントの割り当て、または解決を行います。

## <a name="dlp-investigation-experience-in-microsoft-sentinel"></a>Microsoft Sentinel での DLP 調査エクスペリエンス

Microsoft Sentinel のMicrosoft 365 Defender コネクタを使用すると、Sentinel にすべての DLP インシデントをインポートして、他のデータ ソース間で相関関係、検出、および調査を拡張し、Sentinel のネイティブ SOAR 機能を使用して自動化されたオーケストレーション フローを拡張できます。 

1. Microsoft 365 Defenderから Microsoft Sentinel へのデータの接続に関する手順に従って、DLP インシデントやアラートを含むすべてのインシデントを Sentinel にインポートします。 イベント コネクタを有効にして `CloudAppEvents` 、すべての O365 監査ログを Sentinel にプルします。

   上記のコネクタを設定すると、Sentinel で DLP インシデントを確認できます。

2. **[アラート]** を選択して、アラート ページを表示します。

3. **AlertType**、**startTime**、**endTime** を使用して **CloudAppEvents** テーブルに対してクエリを実行し、アラートに貢献したすべてのユーザー アクティビティを取得できます。 次のクエリを使用して、基になるアクティビティを識別します。

```kusto
let Alert = SecurityAlert
| where TimeGenerated > ago(30d)
| where SystemAlertId == ""; // insert the systemAlertID here
CloudAppEvents
| extend correlationId1 = parse_json(tostring(RawEventData.Data)).cid
| extend correlationId = tostring(correlationId1)
| join kind=inner Alert on $left.correlationId == $right.AlertType
| where RawEventData.CreationTime > StartTime and RawEventData.CreationTime < EndTime
```

## <a name="related-articles"></a>関連記事

- [インシデントの概要](incidents-overview.md)
- [インシデントの優先度設定](incident-queue.md)
- [インシデントの管理](manage-incidents.md)
