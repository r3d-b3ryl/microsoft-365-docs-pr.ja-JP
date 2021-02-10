---
title: Microsoft 365 Defender の新機能
description: Microsoft 365 Defender の新機能の一覧
keywords: Microsoft Threat Protection の新機能, ga, 一般提供, 機能, 利用可能, 新しい
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 4e065ff4da80b50ea11ff2069e8938c59f16f962
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165993"
---
# <a name="whats-new-in-microsoft-365-defender"></a>Microsoft 365 Defender の新機能

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> Microsoft 365 Defender を体験したい場合 ラボ環境 [で評価したり、](https://aka.ms/mtp-trial-lab) パイロット プロジェクトを実 [稼働環境で実行することができます](https://aka.ms/m365d-pilotplaybook)。
>

次の機能は、Microsoft 365 Defender の最新リリースで一般公開 (GA) されます。

RSS フィード: 次の URL をコピーしてフィード リーダーに貼り付け、このページが更新された場合に通知を受け取ります。
```http
https://docs.microsoft.com/api/search/rss?search=%22Lists+the+new+features+and+functionality+in+Microsoft+Threat+Protection%22&locale=en-us
```

## <a name="february-2021"></a>2021 年 2 月
- (プレビュー)拡張[された Microsoft 365 https://security.microsoft.com) セキュリティ センター (](https://security.microsoft.com)パブリック プレビューで利用できる。 この新しいエクスペリエンスにより、Defender for Endpoint と Defender for Office 365 がセンターに表示されます。 [変更された情報について詳しくは、次のリンクを参照してください](https://docs.microsoft.com/microsoft-365/security/mtp/overview-security-center)。

## <a name="september-2020"></a>2020 年 9 月
- [IdentityDirectoryEvents テーブル](advanced-hunting-identitydirectoryevents-table.md) <br> Active Directory を実行しているオンプレミスのドメイン コントローラーに関連するイベントを検索します (AD)。 この [高度な検索](advanced-hunting-overview.md) スキーマ の表では、ドメイン コントローラー上の ID 関連のイベントとシステム イベントの範囲について説明します。
- [AssignedIPAddresses() 関数](advanced-hunting-assignedipaddresses-function.md) <br> 高度な検索クエリでこの関数を使用して、デバイスに割り当てられた最新の IP アドレスまたは最新の IP アドレスを特定の時間から迅速に取得します。

## <a name="july-2020"></a>2020 年7 月
- [FileProfile() 関数](advanced-hunting-fileprofile-function.md) <br> この関数は、高度な検索クエリで使用して、包括的なファイル情報で結果を充実します。
- [ID テーブルとアプリ テーブル](advanced-hunting-schema-tables.md)<br> 高度な検索スキーマの[IdentityLogonEvents、IdentityQueryEvents、](advanced-hunting-identitylogonevents-table.md)[および AppFileEvents](advanced-hunting-appfileevents-table.md)テーブル[](advanced-hunting-identityqueryevents-table.md)を使用して、認証イベント、Active Directory クエリ、およびアプリ関連のアクティビティを確認できます。
- [検出する](advanced-hunting-go-hunt.md)<br> インシデントの調査から、特定のイベント、ユーザー、デバイス、または高度な検索に関するその他のエンティティの種類の検査にすばやくピボットできます。

## <a name="june-2020"></a>2020 年 6 月
- Twitter フィード <br> ダッシュボード内で最新のセキュリティ調査、脅威インテリジェンス、製品ニュースなどをご利用ください。
- [EmailPostDeliveryEvents スキーマ テーブル](advanced-hunting-emailpostdeliveryevents-table.md) <br> 高度な検索クエリに、電子メール メッセージに対して実行された配信後の操作に関する情報を組み込む。
- [高度な検索でレコードを検査する](advanced-hunting-query-results.md#drill-down-from-query-results) <br> 新しい詳細パネルを使用して、クエリ結果のレコードをすばやく検査します。

## <a name="may-2020"></a>2020 年 5 月
- [カスタム検出](custom-detections-overview.md) <br> 高度な検索クエリを使用して、セキュリティ イベントとシステム状態を自動的に監視および応答するカスタム検出ルールを作成します。

## <a name="february-2020"></a>2020 年 2 月
- [インシデント](incidents-overview.md) <br> 攻撃が開始された場所と、攻撃の程度を確認するのに役立つその他の詳細を正確に知る。
- [自動調査および対応](mtp-autoir.md) <br> セキュリティ運用チームは AIR を使用することで、セキュリティの警告やインシデントへの組織の対応能力を大幅に向上させることが可能です。
- [高度な検索機能の強化](advanced-hunting-overview.md) <br> Kusto クエリ言語とセキュリティに最適化されたスキーマを使用して、モダン ワークスペース全体で脅威を事前に検出します。

## <a name="march-2019"></a>2019 年 3 月
- 高度な検出 <br> 電子メールとデータ、デバイス、ID に影響を与える脅威を事前に検出できる、さまざまな検索機能へのランディング ページ。
- [Microsoft セキュア スコア](microsoft-secure-score.md) <br> 組織のセキュリティ体制の測定。数値が大きいほど、改善の取り組みにより多くのことを示します。 セキュリティ スコアの推奨事項を実行することにより、組織を脅威から保護できます。 
- [レポート](monitoring-and-reporting.md) <br>  セキュリティ アナリストや管理者が毎日の業務の一部として追跡するさまざまな分野をカバーするカードのホストを備えます。
