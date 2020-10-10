---
title: 高度な検索に関するエキスパートトレーニングを受ける
description: 高度な検索の専門家から無料のトレーニングとガイダンスを提供
keywords: 高度な検索、脅威の探し、サイバーの脅威の検索、microsoft threat protection、microsoft 365、mtp、m365、検索、クエリ、言語、トレーニング、シナリオ、高度な操作、ビデオ、ステップバイステップ
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: f06cb4190f8932f3a472356ba45adcc3bc35423c
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2020
ms.locfileid: "48413320"
---
# <a name="get-expert-training-on-advanced-hunting"></a>高度な検索に関するエキスパートトレーニングを受ける

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft Threat Protection

新しいセキュリティアナリストおよび熟練した脅威 hunters について、敵対者を _追跡_することで、高度な検索に関する知識を迅速に向上させることができます。 このシリーズでは、独自の高度なクエリを作成するための基本的な手順を説明します。 基本的な最初のビデオから始めて、より高度なビデオにジャンプします。


| Title | 説明 | ウォッチ | クエリ | 
|--|--|--|--|
| エピソード 1: KQL の基礎 | このエピソードでは、Microsoft の脅威保護における高度な検索の基本事項について説明します。 使用できる高度な検索データと基本的な KQL 構文および演算子について説明します。 | [YouTube](https://youtu.be/0D9TkGjeJwM?t=351) (54:14) | [CSL ファイル](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%201%20-%20KQL%20Fundamentals.csl) |
| エピソード 2: 結合 | 高度な検索でデータについて学習を続け、テーブルを結合する方法について説明します。 、、、およびの結合について説明 `inner` `outer` し、既定の `unique` `semi` kusto join の微妙な違いについて理解し `innerunique` ます。 | [YouTube](https://youtu.be/LMrO6K5TWOU?t=297) (53:33) | [CSL ファイル](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%202%20-%20Joins.csl) |
| エピソード 3: データの集約、ピボット、および視覚化 | データをフィルター処理、操作、および結合する方法が習得できたので、次に、概要、定量化、ピボット、可視化の時間を示します。 このエピソードでは、演算子とさまざまな計算について説明し、 `summarize` スキーマに追加のテーブルを導入します。 また、データセットをグラフに変換して、洞察を深めることができるようにする方法についても説明します。 | [YouTube](https://youtu.be/UKnk9U1NH6Y?t=296) (48:52) | [CSL ファイル](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%203%20-%20Summarizing%2C%20Pivoting%2C%20and%20Joining.csl) |
| エピソード 4: ご利用いただけます。 KQL をインシデント追跡に適用する | このエピソードでは、攻撃者のアクティビティを追跡する方法について説明します。 弊社では、Kusto と高度な検索についての強化された理解を活用して、攻撃を追跡しています。 Cybersecurity の ABCs や、インシデントへの対応に適用する方法など、フィールドで使用されている実際のヒントについて説明します。 | [YouTube](https://youtu.be/2EUxOc_LNd8?t=291) (59:36) | [CSL ファイル](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%204%20-%20Lets%20Hunt.csl)

## <a name="how-to-use-the-csl-file"></a>CSL ファイルを使用する方法
エピソードを開始する前に、 [GitHub 上の対応する Kusto CSL ファイルに](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/tree/master/Webcasts/TrackingTheAdversary) アクセスして、その内容を高度な検索クエリエディターにコピーします。 エピソードを見たときに、コピーした内容を使用して、スピーカーをフォローし、クエリを実行することができます。 

CSL ファイルからの次の抜粋は、でコメントとしてマークされた総合的なガイダンスセットを示して `//` います。

```kusto
// DeviceLogonEvents
// A table containing a row for each logon a device enrolled in Defender ATP
// Contains
// - Account information associated with the logon
// - The device which the account logged onto
// - The process which performed the logon
// - Network information (for network logons)
// - Timestamp
```

同じ CSL ファイルには、次に示すように、コメントの前と後にクエリが含まれています。 [エディターで複数のクエリ](advanced-hunting-query-language.md#work-with-multiple-queries-in-the-editor)を使用して特定のクエリを実行するには、そのクエリにカーソルを移動して、[**クエリの実行**] を選択します。   

```kusto
DeviceLogonEvents
| count

// DeviceLogonEvents
// A table containing a row for each logon a device enrolled in Defender ATP
// Contains
// - Account information associated with the logon
// - The device which the account logged onto
// - The process which performed the logon
// - Network information (for network logons)
// - Timestamp

AppFileEvents
| take 100
| sort by Timestamp desc
```
     
## <a name="related-topics"></a>関連項目
- [高度な検出の概要](advanced-hunting-overview.md)
- [高度な捜索のクエリ言語について学習する](advanced-hunting-query-language.md)
- [クエリ結果を操作する](advanced-hunting-query-results.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 間での捜索](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
