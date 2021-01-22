---
title: 概要 - 高度な検索
description: Microsoft 365 の高度な捜索クエリと、それらを使用してネットワーク内の脅威と弱点を積極的に発見する方法について学習する
keywords: 高度な捜索、脅威の捜索、サイバー脅威の捜索、Microsoft Threat Protection、Microsoft 365、mtp、m365、検索、クエリ、テレメトリ、カスタム検出、スキーマ、kusto、Microsoft 365、Microsoft Threat Protection
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
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: 8fbf9c3d93434ec2dbc3f069bc0fbd3fe03fc260
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932276"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-365-defender"></a>Microsoft 365 Defender で高度な検索を使用して脅威を事前に探す

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

> Microsoft 365 Defender を体験したい場合 ラボ環境 [で評価したり、](https://aka.ms/mtp-trial-lab) パイロット プロジェクトを実 [稼働環境で実行することができます](https://aka.ms/m365d-pilotplaybook)。
>

高度な捜索は、クエリ ベースの脅威の捜索ツールで、最大 30 日間のロー データを検索できます。 ネットワーク内のイベントを事前に検査して、脅威インジケーターとエンティティを特定できます。 データへの柔軟なアクセスにより、既知の脅威と潜在的な脅威の両方に対する無条件の検出が可能です。
<p></p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]

同じ脅威を捜索しているクエリを使用して、カスタムの検出ルールを作成できます。 これらのルールは自動的に実行され、違反の疑いのあるアクティビティ、正しく構成されていないコンピューター、その他の検出に対応します。

この機能は、エンドポイント用 [Microsoft Defender の高度な検索に似ています](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)。 Microsoft 365 セキュリティ センターで使用できるこの機能は、次の広範なデータ セットをチェックするクエリをサポートします。

- Microsoft Defender for Endpoint
- Microsoft Defender for Office 365
- Microsoft Cloud App Security
- Microsoft Defender for Identity

高度なハンティングを使用するには [、Microsoft 365 Defender を有効にしてください](mtp-enable.md)。

## <a name="get-started-with-advanced-hunting"></a>高度な捜索を開始する

高度な検索をすぐに開始するには、いくつかの手順を実行することをお勧めします。

| 学習目標 | 説明 | リソース |
|--|--|--|
| **言語を学ぶ** | 高度な検索は [Kusto クエリ言語に基づいており](https://docs.microsoft.com/azure/kusto/query/)、同じ構文と演算子をサポートします。 最初のクエリを実行して、クエリ言語を学習します。 | [クエリ言語の概要](advanced-hunting-query-language.md) |
| **クエリ結果を使用する方法について** | グラフと、結果を表示またはエクスポートするさまざまな方法について学習します。 クエリをすばやく調整し、ドリルダウンしてより豊富な情報を取得し、対応アクションを実行する方法について説明します。 | - [クエリ結果を処理する](advanced-hunting-query-results.md)<br>- [クエリ結果に対してアクションを実行する](advanced-hunting-take-action.md) |
| **スキーマを理解する** | スキーマとその列のテーブルについて、高レベルで十分に理解してください。 クエリを作成するときにデータを検索する場所について説明します。 | - [スキーマ リファレンス](advanced-hunting-schema-tables.md)<br>- [Microsoft Defender for Endpoint からの移行](advanced-hunting-migrate-from-mdatp.md) |
| **エキスパートのヒントと例を取得する** | Microsoft の専門家によるガイドを使用して無料でトレーニングを行います。 さまざまな脅威の捜索シナリオを網羅する定義済みクエリのコレクションを調べます。 | - [エキスパート トレーニングを受け取る](advanced-hunting-expert-training.md)<br>- [共有クエリを使用する](advanced-hunting-shared-queries.md)<br>- [ハントを行う](advanced-hunting-go-hunt.md)<br>- [デバイス、メール、アプリ、ID 間で脅威を検出する](advanced-hunting-query-emails-devices.md) |
| **クエリを最適化し、エラーを処理する** | 効率的でエラーが発生していないクエリを作成する方法を理解します。 | - [クエリのベスト プラクティス](advanced-hunting-best-practices.md)<br>- [エラーの処理](advanced-hunting-errors.md) |
| **検出ルールの作成** | 高度な検索クエリを使用してアラートをトリガーし、応答アクションを自動的に実行する方法について説明します。 | - [カスタム検出の概要](custom-detections-overview.md)<br>- [カスタム検出ルール](custom-detection-rules.md) |

## <a name="get-access"></a>アクセス権を取得する
高度な検索機能または他の [Microsoft 365 Defender](microsoft-threat-protection.md) 機能を使用するには、Azure Active Directory で適切な役割が必要です。 また、エンドポイント データへのアクセスは、Microsoft Defender for Endpoint の役割ベースのアクセス制御 (RBAC) 設定によって決まります。 [Microsoft 365 Defender へのアクセスの管理に関する説明](mtp-permissions.md)

## <a name="data-freshness-and-update-frequency"></a>データの鮮度と更新頻度
高度なハンティング データは 2 つの異なる種類に分類できます。それぞれの種類は統合方法が異なります。

- **イベントまたはアクティビティ データ**— アラート、セキュリティ イベント、システム イベント、および定期的な評価に関するテーブルを設定します。 高度な検索では、収集したセンサーがデータを正常に対応するクラウド サービスに送信した直後に、このデータを受け取ります。 たとえば、ワークステーションまたはドメイン コントローラーで正常なセンサーから得たイベント データは、Microsoft Defender for Endpoint と Microsoft Defender for Identity で利用できる直後に照会できます。
- **エンティティ データ**— ユーザーとデバイスに関する情報をテーブルに設定します。 このデータは、比較的静的なデータ ソースと、Active Directory エントリやイベント ログなどの動的ソースの両方から取得されます。 新しいデータを提供するために、テーブルは 15 分ごとに新しい情報で更新され、完全に入力されていない可能性がある行が追加されます。 24 時間ごとにデータが統合され、各エンティティに関する最新の包括的なデータ セットを含むレコードが挿入されます。

## <a name="time-zone"></a>タイム ゾーン
高度な検索の時間情報は、UTC タイム ゾーンにあります。

## <a name="related-topics"></a>関連項目
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [エキスパート トレーニングを受ける](advanced-hunting-expert-training.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
- [カスタム検出の概要](custom-detections-overview.md)

