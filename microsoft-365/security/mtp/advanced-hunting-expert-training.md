---
title: 高度な検索に関する専門的なトレーニングを受け取る
description: 高度な検索の専門家による無料のトレーニングとガイダンス
keywords: 高度な捜索、脅威の捜索、サイバー脅威の捜索、Microsoft Threat Protection、Microsoft 365、mtp、m365、検索、クエリ、言語、トレーニング、シナリオ、基本から高度、ビデオ、ステップ バイ ステップ
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: aba0a6ab2c82c038eda8e66890c0c95303dea947
ms.sourcegitcommit: ea8a096df5acedecdce1780969f2b189c3fadf73
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2021
ms.locfileid: "50053837"
---
# <a name="get-expert-training-on-advanced-hunting"></a>高度な検索に関する専門的なトレーニングを受け取る

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

新しいセキュリティ アナリストや経験豊富な脅威の脅威に関する Web キャスト シリーズである Tracking _the adversary_ を使用して、高度な検索に関する知識を迅速に高める。 このシリーズでは、独自の高度なクエリを作成するための基本を説明します。 基礎に関する最初のビデオから始めるか、エクスペリエンスのレベルに合った高度なビデオにジャンプします。


| タイトル | 説明 | ウォッチ | クエリ | 
|--|--|--|--|
| エピソード 1: KQL の基本 | このエピソードでは、Microsoft 365 Defender での高度な検索の基本について説明します。 利用可能な高度なハンティング データと基本的な KQL 構文と演算子について説明します。 | [YouTube](https://youtu.be/0D9TkGjeJwM?t=351) (54:14) | [CSL ファイル](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%201%20-%20KQL%20Fundamentals.csl) |
| エピソード 2: 参加 | 高度な検索のデータとテーブルを結合する方法について学習し続ける。 Kusto の既定の参加のニュアンスを理解し、理解 `inner` `outer` `unique` `semi` `innerunique` します。 | [YouTube](https://youtu.be/LMrO6K5TWOU?t=297) (53:33) | [CSL ファイル](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%202%20-%20Joins.csl) |
| エピソード 3: データの要約、ピボット、および視覚化 | データのフィルター処理、操作、結合を行う方法を学習しました。次に、概要、数値化、ピボット、視覚化を行います。 このエピソードでは、スキーマに追加のテーブルを導入しながら、演算子とさまざまな `summarize` 計算について説明します。 また、分析情報の抽出に役立つグラフにデータセットを変換する方法も学習します。 | [YouTube](https://youtu.be/UKnk9U1NH6Y?t=296) (48:52) | [CSL ファイル](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%203%20-%20Summarizing%2C%20Pivoting%2C%20and%20Joining.csl) |
| エピソード 4: ハントしましょう。 KQL をインシデント追跡に適用する | このエピソードでは、攻撃者のアクティビティを追跡する方法について説明します。 Kusto の強化された理解と高度なハンティングを使用して、攻撃を追跡します。 サイバーセキュリティの ABC やインシデント対応に適用する方法など、フィールドで使用される実際のコツについて学習します。 | [YouTube](https://youtu.be/2EUxOc_LNd8?t=291) (59:36) | [CSL ファイル](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%204%20-%20Lets%20Hunt.csl) 


*L33TSP3AK* を使ってより専門的なトレーニングを受け取る: Microsoft 365 Defender の高度な捜ティングは、Microsoft 365 Defender で高度な捜ティングを使用してセキュリティ調査を行う技術的な知識と実践的なスキルを拡張するアナリスト向け Web キャスト シリーズです。 

| タイトル | 説明 | ウォッチ | クエリ | 
|--|--|--|--|
| エピソード 1  | このエピソードでは、高度な検索クエリを実行する場合のさまざまなベスト プラクティスについて説明します。 説明されているトピックの中には、クエリを最適化する方法、ランサムウェアの高度な検索を使用する方法、JSON を動的型として処理する方法、外部データ演算子を操作する方法があります。 | [YouTube](https://www.youtube.com/watch?v=nMGbK-ALaVg&feature=youtu.be) (56:34) | [CSL ファイル](https://github.com/microsoft/Microsoft-365-Defender-Hunting-Queries/blob/master/Webcasts/l33tSpeak/Performance%2C%20Json%20and%20dynamics%20operator%2C%20external%20data.csl)


## <a name="how-to-use-the-csl-file"></a>CSL ファイルの使い方
エピソードを開始する前に、GitHub 上の対応する [Kusto CSL](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/tree/master/Webcasts/TrackingTheAdversary) ファイルにアクセスし、そのコンテンツを高度な検索クエリ エディターにコピーします。 エピソードを見ながら、コピーしたコンテンツを使用して、スピーカーをフォローし、クエリを実行できます。 

CSL ファイルからの次の抜粋は、コメントとしてマークされたガイダンスの包括的なセットを示しています `//` 。

```kusto
// DeviceLogonEvents
// A table containing a row for each logon a device enrolled in Microsoft Defender for Endpoint
// Contains
// - Account information associated with the logon
// - The device which the account logged onto
// - The process which performed the logon
// - Network information (for network logons)
// - Timestamp
```

以下に示すように、同じ CSL ファイルにコメントの前と後にクエリが含まれています。 エディターで複数のクエリを [使用して](advanced-hunting-query-language.md#work-with-multiple-queries-in-the-editor)特定のクエリを実行するには、カーソルをそのクエリに移動し、[クエリの実行] **を選択します**。   

```kusto
DeviceLogonEvents
| count

// DeviceLogonEvents
// A table containing a row for each logon a device enrolled in Microsoft Defender for Endpoint
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
- [デバイス、メール、アプリ、ID 全体で探す](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
