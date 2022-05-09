---
title: Microsoft Defender for Endpointでの高度なハンティングの概要
description: Microsoft Defender for Endpointで脅威の検出機能を使用して、ネットワーク内の脅威と弱点を見つけるクエリを構築する
keywords: 高度な捜索, 脅威の捜索, サイバー脅威の捜索, mdatp, microsoft defender atp, Microsoft Defender for endpoint, wdatp, 検索, クエリ, テレメトリ, カスタム検出, スキーマ, kusto, タイム ゾーン, UTC
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 2e1b6a5bb77dc757861a5d7f56d8a4380c6fc6c1
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/24/2021
ms.locfileid: "61168836"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting"></a>高度な捜索を使用して脅威をプロアクティブに検出する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-advancedhunting-abovefoldlink)

高度な捜索は、クエリ ベースの脅威の捜索ツールで、最大 30 日間のロー データを検索できます。 ネットワーク内のイベントを事前に検査して、脅威インジケーターとエンティティを見つけることができます。 データへの柔軟なアクセスにより、既知の脅威と潜在的な脅威の両方に対する制約のない捜索が可能になります。

高度なハンティングの概要と、高速な作業を開始するための短いチュートリアルについては、このビデオをご覧ください。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bGqo]

同じ脅威を捜索しているクエリを使用して、カスタムの検出ルールを作成できます。 これらのルールは自動的に実行され、侵害の疑いのあるアクティビティ、不適切な構成されたマシン、およびその他の結果を確認して対応します。

> [!TIP]
> [Microsoft 365 Defenderで高度なハンティング](/microsoft-365/security/defender/advanced-hunting-overview)を使用して、Defender for Endpoint、Microsoft Defender for Office 365、Microsoft Defender for Cloud Apps、およびMicrosoft Defender for Identity。 [Microsoft 365 Defenderをオンにします](/microsoft-365/security/defender/m365d-enable)。

高度なハンティング のワークフローをMicrosoft Defender for EndpointからMicrosoft 365 Defenderに移行する方法の詳細については、「[高度なハンティング クエリをMicrosoft Defender for Endpointから移行する」を参照](/microsoft-365/security/defender/advanced-hunting-migrate-from-mde)してください。

## <a name="get-started-with-advanced-hunting"></a>高度な捜索を開始する

次の手順に従って、高度なハンティング知識を強化します。

高度な捜索をすぐに開始して実行するには、いくつかの手順に従うことをお勧めします。

<br>

****

|学習目標|説明|リソース|
|---|---|---|
|**言語を学習する**|高度な検索は、[Kustoクエリ言語](/azure/kusto/query/)に基づいており、同じ構文と演算子をサポートしています。 最初のクエリを実行して、クエリ言語を学習します。|[クエリ言語の概要](advanced-hunting-query-language.md)|
|**クエリ結果を使用する方法について説明します**|グラフと、結果を表示またはエクスポートするさまざまな方法について説明します。 クエリをすばやく調整し、ドリルダウンしてより豊富な情報を取得する方法について説明します。|[クエリ結果を操作する](advanced-hunting-query-results.md)|
|**スキーマを理解する**|スキーマとその列のテーブルについて、高レベルで十分に理解してください。 クエリを作成するときにデータを検索する場所について説明します。|[スキーマ リファレンス](advanced-hunting-schema-reference.md)|
|**定義済みクエリを使用する**|さまざまな脅威の捜索シナリオを網羅する定義済みクエリのコレクションを調べます。|[共有クエリ](advanced-hunting-shared-queries.md)|
|**クエリを最適化し、エラーを処理する**|効率的でエラーのないクエリを作成する方法について説明します。|[クエリのベスト プラクティス](advanced-hunting-best-practices.md) <p> [エラーを処理する](advanced-hunting-errors.md)|
|**最も完全なカバレッジを取得する**|監査設定を使用して、組織のデータカバレッジを向上させます。|[高度なハンティング カバレッジを拡張する](advanced-hunting-extend-data.md)|
|**クイック調査を実行する**|高度なハンティング クエリをすばやく実行して、疑わしいアクティビティを調査します。|[Go hunt を使用してエンティティまたはイベント情報をすばやく *検索* する](advanced-hunting-go-hunt.md)|
|**脅威を含め、侵害に対処する**|ファイルを隔離し、アプリの実行を制限し、その他のアクションを行って攻撃に対応する|[高度なハンティング クエリの結果に対してアクションを実行する](advanced-hunting-take-action.md)|
|**検出ルールの作成**|高度なハンティング クエリを使用してアラートをトリガーし、応答アクションを自動的に実行する方法について説明します。|[カスタム検出の概要](overview-custom-detections.md) <p> [カスタム検出ルール](custom-detection-rules.md)|
|

## <a name="data-freshness-and-update-frequency"></a>データの鮮度と更新頻度

高度な捜索データは、2 つの異なるタイプに分類され、それぞれが異なる形で集約されます。

- **イベントまたはアクティビティ データ**: アラート、セキュリティ イベント、システム イベント、およびルーチン評価に関するテーブルを設定します。 高度な捜索では、それらを収集したセンサーが Defender for Endpoint に正常に送信した直後に、このデータが受信されます。
- **エンティティ データ**: ユーザーとデバイスに関する統合情報をテーブルに設定します。 このデータは、比較的静的なデータ ソースと、Active Directory エントリやイベント ログなどの動的なソースの両方から取得します。 新しいデータを提供するために、テーブルは 15 分ごとに新しい情報で更新され、完全に設定されていない可能性のある行が追加されます。 24 時間ごとにデータが統合され、各エンティティに関する最新の最も包括的なデータ セットを含むレコードが挿入されます。

## <a name="time-zone"></a>タイム ゾーン

高度な捜索の時刻情報は現在、UTC タイム ゾーンにあります。

## <a name="related-topics"></a>関連項目

- [クエリ言語の説明](advanced-hunting-query-language.md)
- [クエリ結果を操作する](advanced-hunting-query-results.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [スキーマを理解する](advanced-hunting-schema-reference.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
- [カスタム検出の概要](overview-custom-detections.md)
- [Storage アカウントの概要](/azure/storage/common/storage-account-overview)
- [Azure Event Hubs — ビッグ データ ストリーミング プラットフォームとイベント インジェスト サービス](/azure/event-hubs/event-hubs-about)
