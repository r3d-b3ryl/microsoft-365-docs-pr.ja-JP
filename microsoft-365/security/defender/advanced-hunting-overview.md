---
title: 概要 - 高度なハンティング
description: Microsoft 365 の高度な捜索クエリと、それらを使用してネットワーク内の脅威と弱点を積極的に発見する方法について学習する
keywords: 高度な捜索, 脅威の捜索, サイバー脅威の捜索, Microsoft 365 Defender, microsoft 365, m365, 検索, クエリ, テレメトリ, カスタム検出, スキーマ, kusto
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: 1ee8d8fbd3b1a56f83106ffaf6be937fa984c272
ms.sourcegitcommit: dd7e5b67ff4ae4e7f74490e437c1795933c74cc7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2022
ms.locfileid: "64731441"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-365-defender"></a>Microsoft 365 Defender の高度な捜索により、脅威を積極的に捜索する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

高度なハンティングは、最大 30 日間の生データを探索できるクエリベースの脅威検出ツールです。 ネットワーク内のイベントを事前に検査して、脅威インジケーターとエンティティを見つけることができます。 データへの柔軟なアクセスにより、既知の脅威と潜在的な脅威の両方に対する制約のない捜索が可能になります。
<br><br>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4G6DO]

同じ脅威検出クエリを使用して、カスタム検出ルールを作成できます。 これらのルールは自動的に実行され、侵害の疑いのあるアクティビティ、不適切な構成されたマシン、およびその他の結果を確認して対応します。

この機能は、[Microsoft Defender for Endpointの高度なハンティング](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)に似ています。次のようなより広範なデータ セットをチェックするクエリがサポートされます。

- Microsoft Defender for Endpoint
- Microsoft Defender for Office 365
- Microsoft Defender for Cloud Apps
- Microsoft Defender for Identity

高度なハンティングを使用するには、[Microsoft 365 Defenderをオンにします](m365d-enable.md)。

Microsoft Defender for Cloud Apps データの高度な捜索の詳細については、[ビデオ](https://www.microsoft.com/en-us/videoplayer/embed/RWFISa)を参照してください。 

## <a name="get-started-with-advanced-hunting"></a>高度な捜索を開始する

高度な捜索をすばやく開始するには、いくつかの手順を実行することをお勧めします。

| 学習目標 | 説明 | リソース |
|--|--|--|
| **言語を学習する** | 高度な検索は、[Kustoクエリ言語](/azure/kusto/query/)に基づいており、同じ構文と演算子をサポートしています。 最初のクエリを実行して、クエリ言語を学習します。 | [クエリ言語の概要](advanced-hunting-query-language.md) |
| **クエリ結果を使用する方法について説明します** | グラフと、結果を表示またはエクスポートするさまざまな方法について説明します。 クエリをすばやく調整し、ドリルダウンしてより豊富な情報を取得し、応答アクションを実行する方法について説明します。 | - [クエリ結果を操作する](advanced-hunting-query-results.md)<br /> - [クエリ結果に対してアクションを実行する](advanced-hunting-take-action.md) |
| **スキーマを理解する** | スキーマとその列のテーブルについて、高レベルで十分に理解してください。 クエリを作成するときにデータを検索する場所について説明します。 | - [スキーマリファレンス](advanced-hunting-schema-tables.md) <br />- [Microsoft Defender for Endpointからの移行](advanced-hunting-migrate-from-mde.md) |
| **エキスパートのヒントと例を入手する** | Microsoft エキスパートのガイドを使用して無料でトレーニングします。 さまざまな脅威の捜索シナリオを網羅する定義済みクエリのコレクションを調べます。 | - [エキスパート トレーニングを受ける](advanced-hunting-expert-training.md) <br />- [共有クエリを使用する](advanced-hunting-shared-queries.md) <br />- [ハントに行く](advanced-hunting-go-hunt.md) <br />- [デバイス、電子メール、アプリ、ID 間で脅威を検出する](advanced-hunting-query-emails-devices.md) |
| **クエリを最適化し、エラーを処理する** | 効率的でエラーのないクエリを作成する方法について説明します。 | - [クエリのベスト プラクティス](advanced-hunting-best-practices.md)<br />- [エラーを処理する](advanced-hunting-errors.md) |
| **検出ルールの作成** | 高度なハンティング クエリを使用してアラートをトリガーし、応答アクションを自動的に実行する方法について説明します。 | - [カスタム検出の概要](custom-detections-overview.md) <br />- [カスタム検出ルール](custom-detection-rules.md) |

## <a name="get-access"></a>アクセスを取得する
高度なハンティングやその他[のMicrosoft 365 Defender](microsoft-365-defender.md)機能を使用するには、Azure Active Directoryに適切なロールが必要です。 [高度な捜索に必要なロールとアクセス許可について説明](custom-roles.md)します。

また、エンドポイント データへのアクセスは、Microsoft Defender for Endpointのロールベースのアクセス制御 (RBAC) 設定によって決まります。 [Microsoft 365 Defenderへのアクセスの管理について説明します](m365d-permissions.md)。


## <a name="data-freshness-and-update-frequency"></a>データの鮮度と更新頻度
高度な捜索データは、2 つの異なるタイプに分類され、それぞれが異なる形で集約されます。

- **イベントまたはアクティビティ データ** - アラート、セキュリティ イベント、システム イベント、およびルーチン評価に関するテーブルを設定します。 高度な捜索は、このデータは、センサーが収集したデータを対応するクラウド サービスに転送した後、ほぼ瞬間的に受け取ります。 たとえば、ワークステーションまたはドメイン コントローラー上の正常なセンサーから、Microsoft Defender for EndpointとMicrosoft Defender for Identityで使用可能になった直後にイベント データに対してクエリを実行できます。
- **エンティティ データ** - ユーザーとデバイスに関する情報をテーブルに設定します。 このデータは、比較的静的なデータ ソースと、Active Directory エントリやイベント ログなどの動的なソースの両方から取得します。 新しいデータを提供するために、テーブルは 15 分ごとに新しい情報で更新され、完全に設定されていない可能性のある行が追加されます。 24 時間ごとにデータが統合され、各エンティティに関する最新の最も包括的なデータ セットを含むレコードが挿入されます。

## <a name="time-zone"></a>タイム ゾーン
高度な捜索の時刻情報は UTC タイム ゾーンにあります。

## <a name="related-topics"></a>関連項目
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [エキスパート トレーニングを受ける](advanced-hunting-expert-training.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
- [カスタム検出の概要](custom-detections-overview.md)
