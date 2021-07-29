---
title: エンドポイント向け Microsoft Defender での高度な検索の概要
description: Microsoft Defender for Endpoint の脅威検出機能を使用して、ネットワーク内の脅威と弱点を検出するクエリを作成する
keywords: 高度な狩猟、脅威の検出、サイバー脅威の検出、mdatp、microsoft Defender atp、エンドポイント用の microsoft Defender、wdatp、検索、クエリ、テレメトリ、カスタム検出、スキーマ、kusto、タイム ゾーン、UTC
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a73c54c989d33a5e3d4faacb286bfb551d74a3c6
ms.sourcegitcommit: af575ade7b187af70f94db904b03f0471f56452a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/26/2021
ms.locfileid: "53591237"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting"></a>高度な狩猟で脅威を積極的に探す

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

> Defender for Endpoint を体験してみませんか? [無料試用版にサインアップしてください。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

高度な捜索は、クエリ ベースの脅威の捜索ツールで、最大 30 日間のロー データを検索できます。 ネットワーク内のイベントを事前に検査して、脅威インジケーターとエンティティを特定できます。 データへの柔軟なアクセスにより、既知の脅威と潜在的な脅威の両方に対する拘束されていない検出が可能です。

このビデオでは、高度な狩猟の簡単な概要と、迅速に始める短いチュートリアルをご覧ください。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bGqo]

同じ脅威を捜索しているクエリを使用して、カスタムの検出ルールを作成できます。 これらのルールは自動的に実行され、侵害の疑いのあるアクティビティ、正しく構成されていないコンピューター、その他の結果を確認し、それに対応します。

> [!TIP]
> エンドポイント[の Defender、Microsoft 365 Defender、Microsoft](/microsoft-365/security/defender/advanced-hunting-overview) Defender for Office 365、Microsoft Cloud App Security、および Microsoft Defender for Identity のデータを使用して脅威を検出するには、Microsoft 365 Defender で高度な検索を使用します。 [[設定] をオンMicrosoft 365 Defender。](/microsoft-365/security/defender/m365d-enable)

高度なハンティング ワークフローを Microsoft Defender for Endpoint から Microsoft 365 Defender に移動する方法については、「Advanced Hunting [queries](/microsoft-365/security/defender/advanced-hunting-migrate-from-mde)を Microsoft Defender for Endpoint から移行する」を参照してください。

## <a name="get-started-with-advanced-hunting"></a>高度な捜索を開始する

高度な狩猟の知識を高くするには、次の手順を実行します。

高度な捜索をすぐに開始して実行するには、いくつかの手順に従うことをお勧めします。

<br>

****

|学習目標|説明|リソース|
|---|---|---|
|**言語を学ぶ**|高度な検索は [、同じ構文と](/azure/kusto/query/)演算子をサポートする Kusto クエリ言語に基づいて行います。 最初のクエリを実行して、クエリ言語を学習します。|[クエリ言語の概要](advanced-hunting-query-language.md)|
|**クエリ結果を使用する方法について**|グラフと、結果を表示またはエクスポートするさまざまな方法について学習します。 クエリをすばやく調整し、詳細な情報を取得するためにドリルダウンする方法について説明します。|[クエリ結果を操作する](advanced-hunting-query-results.md)|
|**スキーマを理解する**|スキーマとその列のテーブルについて、高レベルで十分に理解してください。 クエリを作成するときにデータを検索する場所について説明します。|[スキーマ リファレンス](advanced-hunting-schema-reference.md)|
|**定義済みクエリを使用する**|さまざまな脅威の捜索シナリオを網羅する定義済みクエリのコレクションを調べます。|[共有クエリ](advanced-hunting-shared-queries.md)|
|**クエリを最適化し、エラーを処理する**|効率的でエラーフリーのクエリを作成する方法を理解します。|- [クエリのベスト プラクティス](advanced-hunting-best-practices.md)<br>- [エラーの処理](advanced-hunting-errors.md)|
|**最も完全なカバレッジを取得する**|監査設定を使用して、組織のデータ範囲を向上します。|- [高度な狩猟範囲の拡張](advanced-hunting-extend-data.md)|
|**クイック調査の実行**|高度な検索クエリをすばやく実行して、疑わしいアクティビティを調査します。|- [go hunt を使用してエンティティまたはイベント情報をすばやく *検索する*](advanced-hunting-go-hunt.md)|
|**脅威を含め、侵害に対処する**|ファイルの quarantining、アプリの実行の制限、その他のアクションによる攻撃への対応|- [高度な検索クエリの結果に対してアクションを実行する](advanced-hunting-take-action.md)|
|**検出ルールの作成**|高度な検索クエリを使用してアラートをトリガーし、応答アクションを自動的に実行する方法について説明します。|- [カスタム検出の概要](overview-custom-detections.md)<br>- [カスタム検出ルール](custom-detection-rules.md)|
|


## <a name="data-freshness-and-update-frequency"></a>データの鮮度と更新頻度

高度な狩猟データは、それぞれ異なる方法で統合された 2 つの異なる種類に分類できます。

- **イベントまたはアクティビティ データ**: アラート、セキュリティ イベント、システム イベント、およびルーチン評価に関するテーブルを設定します。 高度な検出は、センサーを収集したセンサーが Defender for Endpoint に正常に送信した直後に、このデータを受信します。
- **エンティティ データ**: ユーザーとデバイスに関する統合された情報を表に設定します。 このデータは、比較的静的なデータ ソースと、Active Directory エントリやイベント ログなどの動的ソースの両方から取得されます。 新しいデータを提供するために、テーブルは 15 分ごとに新しい情報で更新され、完全に入力されない可能性のある行が追加されます。 24 時間ごとにデータが統合され、各エンティティに関する最新の最も包括的なデータ セットを含むレコードが挿入されます。

## <a name="time-zone"></a>タイム ゾーン

高度な検索の時間情報は現在、UTC タイム ゾーンにあります。

## <a name="related-topics"></a>関連項目

- [クエリ言語の説明](advanced-hunting-query-language.md)
- [クエリ結果を操作する](advanced-hunting-query-results.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [スキーマを理解する](advanced-hunting-schema-reference.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
- [カスタム検出の概要](overview-custom-detections.md)
