---
title: 概要-高度な検索
description: Microsoft 365 の高度な捜索クエリと、それらを使用してネットワーク内の脅威と弱点を積極的に発見する方法について学習する
keywords: 高度な検索、脅威の探し、サイバー脅威の検索、microsoft threat protection、microsoft 365、mtp、m365、search、query、テレメトリ、カスタム検出、スキーマ、kusto、microsoft 365、Microsoft Threat Protection
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
ms.collection: M365-security-compliance
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8e586050465464def02c7787a5fb218b0b6071c7
ms.sourcegitcommit: 0f48beaca3afa4df12d41847014975d50a4ebe7d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2020
ms.locfileid: "48338475"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-threat-protection"></a>Microsoft Threat Protection の高度な捜索により、脅威を積極的に捜索する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft Threat Protection

高度な捜索は、クエリ ベースの脅威の捜索ツールで、最大 30 日間のロー データを検索できます。 ネットワーク内のイベントを事前に検査して、脅威の指標とエンティティを見つけることができます。 データへの柔軟なアクセスにより、既知の脅威と潜在的な脅威を無制限に探すことができます。
<p></p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]

同じ脅威を捜索しているクエリを使用して、カスタムの検出ルールを作成できます。 これらのルールは自動的に実行され、疑わしい違反活動、不適切な構成のコンピューター、およびその他の結果をチェックして応答します。

この機能は、 [Microsoft DEFENDER ATP での高度な](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)検索に似ています。 Microsoft 365 セキュリティセンターで利用可能です。この機能により、次のような幅広いデータセットをチェックするクエリがサポートされます。

- Microsoft Defender Advanced Threat Protection
- Office 365 Advanced Threat Protection
- Microsoft Cloud App Security
- Azure Advanced Threat Protection

高度な捜索を使用するには、[Microsoft Threat Protection を有効](mtp-enable.md)にします。

## <a name="get-started-with-advanced-hunting"></a>高度な捜索を開始する

高度な検索をすばやく始めるには、いくつかの手順を実行することをお勧めします。

| 学習目標 | 説明 | リソース |
|--|--|--|
| **言語について** | 高度な検索は、 [Kusto クエリ言語](https://docs.microsoft.com/azure/kusto/query/)に基づいており、同じ構文および演算子をサポートしています。 最初のクエリを実行して、クエリ言語を学習します。 | [クエリ言語の概要](advanced-hunting-query-language.md) |
| **クエリ結果の使用方法について説明します。** | グラフと、結果を表示またはエクスポートするさまざまな方法について説明します。 クエリをすばやく調整する方法、豊富な情報を取得するためのドリルダウン、および応答アクションを実行する方法について説明します。 | - [クエリ結果を操作する](advanced-hunting-query-results.md)<br>- [クエリ結果に対してアクションを実行する](advanced-hunting-take-action.md) |
| **スキーマを理解する** | スキーマとその列のテーブルについて、高レベルで十分に理解してください。 クエリを作成するときにデータを検索する場所について説明します。 | - [スキーマリファレンス](advanced-hunting-schema-tables.md)<br>- [Microsoft Defender ATP からの移行](advanced-hunting-migrate-from-mdatp.md) |
| **エキスパートのヒントと例を取得する** | Microsoft の専門家のガイドを使用して無料でトレーニングを行います。 さまざまな脅威の捜索シナリオを網羅する定義済みクエリのコレクションを調べます。 | - [エキスパートトレーニングを受ける](advanced-hunting-expert-training.md)<br>- [共有クエリを使用する](advanced-hunting-shared-queries.md)<br>- [ハントに移動](advanced-hunting-go-hunt.md)<br>- [デバイス、メール、アプリ、および id 間の脅威を探します。](advanced-hunting-query-emails-devices.md) |
| **クエリを最適化してエラーを処理する** | 効率的でエラーのないクエリを作成する方法について説明します。 | - [クエリのベストプラクティス](advanced-hunting-best-practices.md)<br>- [エラーを処理する](advanced-hunting-errors.md) |
| **検出ルールの作成** | 高度な検索クエリを使用して、通知をトリガーし、応答アクションを自動的に実行する方法を理解します。 | - [ユーザー設定の検出の概要](custom-detections-overview.md)<br>- [カスタム検出ルール](custom-detection-rules.md) |

## <a name="get-access"></a>アクセス権を取得する
高度な検索やその他の [Microsoft の脅威保護](microsoft-threat-protection.md) 機能を使用するには、Azure Active Directory に適切なロールが必要です。 また、エンドポイントデータへのアクセスは、Microsoft Defender ATP の役割ベースのアクセス制御 (RBAC) 設定によって決まります。 [Microsoft の脅威保護へのアクセスの管理について確認する](mtp-permissions.md)

## <a name="data-freshness-and-update-frequency"></a>データの鮮度と更新頻度
高度な検索データは、それぞれ異なる方法で2つの異なる種類に分類できます。

- **イベントまたはアクティビティのデータ**—アラート、セキュリティイベント、システムイベント、および定期的な評価に関する表について説明します。 高度な検索では、このデータを収集するセンサーが、対応するクラウドサービスに正常に送信された直後に受信します。 たとえば、Microsoft Defender ATP および Azure ATP で利用可能になった直後のワークステーションまたはドメインコントローラーで、正常なセンサーのイベントデータをクエリできます。
- **エンティティデータ**—ユーザーとデバイスに関する情報をテーブルに格納します。 このデータは、比較的静的なデータソースと、Active Directory エントリやイベントログなどの動的ソースから取得されます。 新しいデータを提供するために、15分ごとに、完全には設定されていない可能性のある行を追加して、すべての新しい情報でテーブルを更新します。 24時間ごとにデータが統合され、各エンティティについての最新の最も包括的なデータセットを含むレコードが挿入されます。

## <a name="time-zone"></a>タイム ゾーン
高度な検索の時間情報は UTC タイムゾーンにあります。

## <a name="related-topics"></a>関連項目
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [エキスパート トレーニングを受ける](advanced-hunting-expert-training.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
- [カスタム検出の概要](custom-detections-overview.md)

