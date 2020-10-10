---
title: Microsoft Threat Protection の新機能
description: Microsoft の脅威保護の新機能の一覧を掲載しています。
keywords: microsoft の脅威保護、ga、一般提供される機能、利用可能な新機能、新規
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: secure
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365-initiative-m365-defender
ms.topic: conceptual
ms.openlocfilehash: 670b020e3c15ac99b06bc8615b2693ba73497b8a
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412036"
---
# <a name="whats-new-in-microsoft-threat-protection"></a>Microsoft Threat Protection の新機能

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


Microsoft の脅威保護の最新リリースでは、次の機能が一般公開 (GA) されています。

RSS フィード: このページが更新されたときに通知を取得するには、次の URL をフィードリーダーにコピーして貼り付けます。
```http
https://docs.microsoft.com/api/search/rss?search=%22Lists+the+new+features+and+functionality+in+Microsoft+Threat+Protection%22&locale=en-us
```
## <a name="september-2020"></a>2020 年 9 月
- [Identity Directoryevents テーブル](advanced-hunting-identitydirectoryevents-table.md) <br> Active Directory (AD) を実行しているオンプレミスのドメインコントローラーを含むイベントを検索します。 この [高度な](advanced-hunting-overview.md) 検索スキーマテーブルは、ドメインコントローラー上の id 関連イベントとシステムイベントの範囲をカバーしています。
- [AssignedIPAddresses () 関数](advanced-hunting-assignedipaddresses-function.md) <br> 詳細な検索クエリでこの関数を使用して、デバイスに割り当てられている最新の IP アドレスまたは特定の時刻からの最新の IP アドレスをすばやく取得します。

## <a name="july-2020"></a>2020 年7 月
- [FileProfile () 関数](advanced-hunting-fileprofile-function.md) <br> 高度な検索のクエリでこの関数を使用して、包括的なファイル情報を使用して結果を充実させます。
- [Id とアプリのテーブル](advanced-hunting-schema-tables.md)<br> 高度な検索スキーマで、認証イベント、Active Directory クエリ、アプリに関連するアクティビティの可視性を取得します。これには、詳細な検索スキーマのイベントテーブル[、イベント](advanced-hunting-identityqueryevents-table.md)[テーブル、および](advanced-hunting-identitylogonevents-table.md) [appfileevents](advanced-hunting-appfileevents-table.md)テーブルが含まれます。
- [検出する](advanced-hunting-go-hunt.md)<br> 高度な検索の際に、特定のイベント、ユーザー、デバイス、またはその他のエンティティの種類を調査するインシデントの調査からすばやくピボットします。

## <a name="june-2020"></a>2020 年 6 月
- Twitter フィード <br> 最新のセキュリティ研究、脅威インテリジェンス、製品ニュース、およびダッシュボード内部の詳細を取得します。
- [EmailPostDeliveryEvents スキーマテーブル](advanced-hunting-emailpostdeliveryevents-table.md) <br> 高度な検索クエリで電子メールメッセージに対して実行された配信後の処理に関する情報を組み込みます。
- [高度な検索でレコードを検査する](advanced-hunting-query-results.md#drill-down-from-query-results) <br> 新しい [詳細] パネルを使用して、クエリ結果のレコードをすばやく検査します。

## <a name="may-2020"></a>2020 年 5 月
- [カスタム検出](custom-detections-overview.md) <br> 高度な検索クエリを使用して、セキュリティイベントやシステム状態を自動的に監視し、応答するカスタムの検出ルールを作成します。

## <a name="february-2020"></a>2020 年 2 月
- [インシデント](incidents-overview.md) <br> 攻撃が開始された場所とその他の詳細を正確に把握して、攻撃の範囲を確認します。
- [自動調査および対応](mtp-autoir.md) <br> セキュリティ運用チームは AIR を使用することで、セキュリティの警告やインシデントへの組織の対応能力を大幅に向上させることが可能です。
- [高度な検索機能強化](advanced-hunting-overview.md) <br> Kusto クエリ言語とセキュリティで最適化されたスキーマを使用して、モダンワークスペース全体にわたる脅威を事前に探します。

## <a name="march-2019"></a>2019 年 3 月
- 高度な検出 <br> 電子メール、データ、デバイス、および id に影響を与える脅威を事前に発見できる、さまざまな検索機能に対するランディングページ。
- [Microsoft セキュア スコア](microsoft-secure-score.md) <br> 組織のセキュリティ姿勢の測定、向上したアクションが実行されたことを示すより高い数値。 セキュリティ スコアの推奨事項を実行することにより、組織を脅威から保護できます。 
- [レポート](monitoring-and-reporting.md) <br>  セキュリティアナリストや管理者が日常業務の一部として追跡するさまざまな領域をカバーするカードのホストが機能します。
