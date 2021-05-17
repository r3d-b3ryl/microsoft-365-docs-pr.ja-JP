---
title: Microsoft 365 Defender の新機能
description: Defender の新機能と機能の一覧Microsoft 365します。
keywords: Defender、ga、一般Microsoft 365機能、利用可能、新しいの新機能
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: secure
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 91029f03e089f44f49800bfe2d18536a8d415411
ms.sourcegitcommit: e02cf5702af178ddd2968877a808874ecb49ed2c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2021
ms.locfileid: "52029030"
---
# <a name="whats-new-in-microsoft-365-defender"></a>Microsoft 365 Defender の新機能

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> Microsoft 365 Defender を体験してみませんか? [ラボ環境で評価する](m365d-evaluation.md?ocid=cx-docs-MTPtriallab)ことも、[実稼働環境でパイロット プロジェクトを実行する](m365d-pilot.md?ocid=cx-evalpilot)こともできます。
>

次の機能は、Defender の最新リリースで一般にMicrosoft 365されています。

RSS フィード: 次の URL をコピーしてフィード リーダーに貼り付け、このページが更新された場合に通知を受け取ります。
```http
https://docs.microsoft.com/api/search/rss?search=%22Lists+the+new+features+and+functionality+in+Microsoft+365+defender%22&locale=en-us
```

## <a name="april-2021"></a>2021 年 4 月
- セキュリティ センター Microsoft 365強化 <br> 改善された [Microsoft 365 セキュリティ センター](https://security.microsoft.com)がパブリック プレビューで利用できるようになりました。 この新しいエクスペリエンスにより、Defender for Endpoint、Defender for Office 365、Microsoft 365 Defender などが Microsoft 365 セキュリティ センターに導入されます。 これは、セキュリティコントロールを管理するための新しいホームです。 [新機能について説明します](./overview-security-center.md)。

- [Microsoft 365Defender の脅威分析レポート](threat-analytics.md)<br>
 脅威分析は、アクティブな攻撃に対応し、影響を最小限に抑えるのに役立ちます。 また、Defender ソリューションによってブロックされる攻撃の試みMicrosoft 365、さらなる暴露のリスクを軽減し、回復性を高める予防措置を講じてみることができます。 統合セキュリティ エクスペリエンスの一環として、Microsoft Defender for Endpoint および Microsoft Defender では、E5 ライセンス所有者向Office利用できます。

## <a name="march-2021"></a>2021 年 3 月
- [CloudAppEvents テーブル](advanced-hunting-cloudappevents-table.md) <br>さまざまなクラウド アプリとサービスのイベントに関する情報を、Microsoft Cloud App Security。 この表には、以前に使用した情報も含まれています `AppFileEvents` 。
## <a name="february-2021"></a>2021 年 2 月
- (プレビュー)拡張セキュリティ[Microsoft 365センター ( https://security.microsoft.com) ](https://security.microsoft.com)はパブリック プレビューで利用できます。 この新しいエクスペリエンスにより、Defender for Endpoint と Defender for Office 365が中央に表示されます。 [変更点についての詳細情報](./overview-security-center.md) はこちらを参照してください。

## <a name="september-2020"></a>2020 年 9 月
- [IdentityDirectoryEvents テーブル](advanced-hunting-identitydirectoryevents-table.md) <br> Active Directory を実行しているオンプレミスのドメイン コントローラーに関連するイベントを検索します (AD)。 この [高度な検索](advanced-hunting-overview.md) スキーマ テーブルでは、ドメイン コントローラー上の ID 関連のイベントとシステム イベントの範囲について説明します。
- [AssignedIPAddresses() 関数](advanced-hunting-assignedipaddresses-function.md) <br> 高度な検索クエリでこの関数を使用すると、デバイスに割り当てられた最新の IP アドレスや、特定の時刻から最新の IP アドレスをすばやく取得できます。

## <a name="july-2020"></a>2020 年 7 月
- [FileProfile() 関数](advanced-hunting-fileprofile-function.md) <br> 高度な検索クエリでこの関数を使用して、包括的なファイル情報で結果を強化します。
- [ID テーブルとアプリ テーブル](advanced-hunting-schema-tables.md)<br> 高度なハンティング スキーマの[IdentityLogonEvents、IdentityQueryEvents、](advanced-hunting-identitylogonevents-table.md)[および AppFileEvents](advanced-hunting-appfileevents-table.md)テーブルを使用して、認証イベント、Active Directory クエリ、およびアプリ関連のアクティビティを表示します。 [](advanced-hunting-identityqueryevents-table.md)
- [検出する](advanced-hunting-go-hunt.md)<br> インシデントの調査から、高度な検索で特定のイベント、ユーザー、デバイス、または他のエンティティの種類を調べにすばやくピボットします。

## <a name="june-2020"></a>2020 年 6 月
- Twitter フィード <br> ダッシュボード内で、最新のセキュリティ調査、脅威インテリジェンス、製品ニュースなどをご覧ください。
- [EmailPostDeliveryEvents スキーマ テーブル](advanced-hunting-emailpostdeliveryevents-table.md) <br> 高度な検索クエリに、電子メール メッセージに対して実行される配信後のアクションに関する情報を組み込む。
- [高度な検索でレコードを検査する](advanced-hunting-query-results.md#drill-down-from-query-results) <br> 新しい詳細パネルを使用して、クエリ結果のレコードをすばやく検査します。

## <a name="may-2020"></a>2020 年 5 月
- [カスタム検出](custom-detections-overview.md) <br> 高度な検索クエリを使用して、セキュリティ イベントとシステム状態を自動的に監視して対応するカスタム検出ルールを作成します。

## <a name="february-2020"></a>2020 年 2 月
- [インシデント](incidents-overview.md) <br> 攻撃の開始場所と、攻撃の範囲を確認するためのその他の詳細を正確に知る。
- [自動調査および対応](m365d-autoir.md) <br> セキュリティ運用チームは AIR を使用することで、セキュリティの警告やインシデントへの組織の対応能力を大幅に向上させることが可能です。
- [高度なハンティング機能の強化](advanced-hunting-overview.md) <br> Kusto クエリ言語とセキュリティに最適化されたスキーマを使用して、モダン ワークスペース全体で脅威を事前に検出します。

## <a name="march-2019"></a>2019 年 3 月
- 高度な検出 <br> 電子メールやデータ、デバイス、および ID に影響を与える脅威を積極的に検出できるさまざまな検索機能へのランディング ページ。
- [Microsoft セキュア スコア](microsoft-secure-score.md) <br> 組織のセキュリティ体制を測定し、より多くの改善アクションを示す数値が大きい。 セキュリティ スコアの推奨事項を実行することにより、組織を脅威から保護できます。 
- [レポート](overview-security-center.md) <br>  セキュリティ アナリストや管理者が毎日の操作の一環として追跡するさまざまな領域をカバーするカードのホストを備えます。
