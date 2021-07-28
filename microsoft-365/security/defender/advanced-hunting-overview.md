---
title: 概要 - 高度な検索
description: Microsoft 365 の高度な捜索クエリと、それらを使用してネットワーク内の脅威と弱点を積極的に発見する方法について学習する
keywords: 高度な狩猟、脅威の検出、サイバー脅威の検出、Microsoft 365 Defender、microsoft 365、m365、検索、クエリ、テレメトリ、カスタム検出、スキーマ、kusto
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: b59ff2a32ef5a067576c43b9b0a394590e30b666
ms.sourcegitcommit: bef7bd019531317d083c1125f7d339750c450b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/26/2021
ms.locfileid: "53587959"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-365-defender"></a>高度な検索機能を使用して、脅威を事前に検出Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

> Microsoft 365 Defender を体験してみませんか? [ラボ環境で評価する](m365d-evaluation.md?ocid=cx-docs-MTPtriallab)ことも、[実稼働環境でパイロット プロジェクトを実行する](m365d-pilot.md?ocid=cx-evalpilot)こともできます。
>

高度な検索はクエリベースの脅威検出ツールで、最大 30 日間の生データを探索できます。 ネットワーク内のイベントを事前に検査して、脅威インジケーターとエンティティを特定できます。 データへの柔軟なアクセスにより、既知の脅威と潜在的な脅威の両方に対する拘束されていない検出が可能です。
<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]

同じ脅威検出クエリを使用して、カスタム検出ルールを作成できます。 これらのルールは自動的に実行され、侵害の疑いのあるアクティビティ、正しく構成されていないコンピューター、その他の結果を確認し、それに対応します。

この機能は [、Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) の高度な検索に似ています。より広範なデータ セットを次からチェックするクエリをサポートしています。

- Microsoft Defender for Endpoint
- Microsoft Defender for Office 365
- Microsoft Cloud App Security
- Microsoft Defender for Identity

高度な検索を使用するには[、次のMicrosoft 365 Defender。](m365d-enable.md)

データの高度な検索の詳細についてはMicrosoft Cloud App Securityビデオを参照[してください](https://www.microsoft.com/en-us/videoplayer/embed/RWFISa)。 

## <a name="get-started-with-advanced-hunting"></a>高度な捜索を開始する

高度な検索をすぐに開始するには、いくつかの手順を実行することをお勧めします。

| 学習目標 | 説明 | リソース |
|--|--|--|
| **言語を学ぶ** | 高度な検索は [、同じ構文と](/azure/kusto/query/)演算子をサポートする Kusto クエリ言語に基づいて行います。 最初のクエリを実行して、クエリ言語を学習します。 | [クエリ言語の概要](advanced-hunting-query-language.md) |
| **クエリ結果を使用する方法について** | グラフと、結果を表示またはエクスポートするさまざまな方法について学習します。 クエリをすばやく調整し、詳細な情報を取得するためにドリルダウンし、応答アクションを実行する方法について説明します。 | - [クエリ結果の処理](advanced-hunting-query-results.md)<br /> - [クエリ結果に対してアクションを実行する](advanced-hunting-take-action.md) |
| **スキーマを理解する** | スキーマとその列のテーブルについて、高レベルで十分に理解してください。 クエリを作成するときにデータを検索する場所について説明します。 | - [スキーマ参照](advanced-hunting-schema-tables.md) <br />- [Microsoft Defender for Endpoint からの移行](advanced-hunting-migrate-from-mde.md) |
| **エキスパートのヒントと例を取得する** | Microsoft の専門家からのガイドを使用して無料でトレーニングします。 さまざまな脅威の捜索シナリオを網羅する定義済みクエリのコレクションを調べます。 | - [専門家のトレーニングを受け取る](advanced-hunting-expert-training.md) <br />- [共有クエリの使用](advanced-hunting-shared-queries.md) <br />- [Go hunt](advanced-hunting-go-hunt.md) <br />- [デバイス、電子メール、アプリ、および ID 間の脅威を検出する](advanced-hunting-query-emails-devices.md) |
| **クエリを最適化し、エラーを処理する** | 効率的でエラーフリーのクエリを作成する方法を理解します。 | - [クエリのベスト プラクティス](advanced-hunting-best-practices.md)<br />- [エラーの処理](advanced-hunting-errors.md) |
| **検出ルールの作成** | 高度な検索クエリを使用してアラートをトリガーし、応答アクションを自動的に実行する方法について説明します。 | - [カスタム検出の概要](custom-detections-overview.md) <br />- [カスタム検出ルール](custom-detection-rules.md) |

## <a name="get-access"></a>アクセス権の取得
高度な検索機能[や他の](microsoft-365-defender.md)Microsoft 365 Defender機能を使用するには、この機能で適切な役割Azure Active Directory。 [高度な検索に必要な役割とアクセス許可についてお読みください](custom-roles.md)。

また、エンドポイント データへのアクセスは、Microsoft Defender for Endpoint の役割ベースのアクセス制御 (RBAC) 設定によって決まります。 [アクセスの管理に関する記事をMicrosoft 365 Defender。](m365d-permissions.md)


## <a name="data-freshness-and-update-frequency"></a>データの鮮度と更新頻度
高度な狩猟データは、それぞれ異なる方法で統合された 2 つの異なる種類に分類できます。

- **イベントまたはアクティビティ データ**— アラート、セキュリティ イベント、システム イベント、および定期的な評価に関するテーブルを設定します。 高度な検出は、センサーを収集したセンサーが対応するクラウド サービスに正常に送信した直後に、このデータを受信します。 たとえば、ワークステーションまたはドメイン コントローラー上の正常なセンサーのイベント データは、Microsoft Defender for Endpoint および Microsoft Defender for Identity で使用できる直後にクエリを実行できます。
- **エンティティ データ**— ユーザーとデバイスに関する情報を表に設定します。 このデータは、比較的静的なデータ ソースと、Active Directory エントリやイベント ログなどの動的ソースの両方から取得されます。 新しいデータを提供するために、テーブルは 15 分ごとに新しい情報で更新され、完全に入力されない可能性のある行が追加されます。 24 時間ごとにデータが統合され、各エンティティに関する最新の最も包括的なデータ セットを含むレコードが挿入されます。

## <a name="time-zone"></a>タイム ゾーン
高度な検索の時間情報は、UTC タイム ゾーンにあります。

## <a name="related-topics"></a>関連項目
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [エキスパート トレーニングを受ける](advanced-hunting-expert-training.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
- [カスタム検出の概要](custom-detections-overview.md)
