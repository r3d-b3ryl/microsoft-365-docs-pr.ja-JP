---
title: Microsoft 365 ネットワーク接続場所サービス
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 12/06/2021
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: admindeeplinkMAC
description: Microsoft 365 ネットワーク接続場所サービス
ms.openlocfilehash: 6150102471b03fbc83be09b503a6969ca6615a87
ms.sourcegitcommit: 388279e10a160b85b345a8ad760f6816dda4e2ad
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/07/2021
ms.locfileid: "61327671"
---
# <a name="microsoft-365-network-connectivity-location-services"></a>Microsoft 365 ネットワーク接続場所サービス

<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理センター</a>には **、ネットワークのインサイトとパフォーマンスに関する推奨事項** が表示されます。これは、Microsoft 365 テナントから収集されるライブ パフォーマンス メトリックです。 これらのメトリックは、テナント内の管理者ユーザーのみが表示できます。 組織のネットワーク接続は、インターネットへのネットワークエグレスの場所を通じて、オフィスの場所ごとに設計されています。 Microsoft 365クライアント接続では、そのルートを使用してから、インターネット経由で Microsoft サービス フロント ドア サーバーに接続します。 これらのネットワーク分析情報を表示するには、オフィスの場所を特定することが重要です。

## <a name="location-in-network-measurements"></a>ネットワーク測定値内の場所

組織の管理者は、この機能で使用されるネットワーク測定値に含める場所を選択できます。 これにより、各オフィスがある都市の自動検出が可能になります。 位置情報は正確ではなく、300m に難読化され、都市別に分類されます。 Windows デバイスで場所がキャプチャされた時点で、デバイスはツール トレイに **[使用中の場所]** アイコンを表示します。 管理者は、このアイコンの外観をユーザーに通知することができます。 この処理では、場所は組織のオフィスの場所として扱われ、人やデバイスの場所として扱われません。 ネットワーク分析情報は、これらの検出されたオフィスの場所の都市に表示できます。 推奨事項の精度を高める場合は、特定のオフィスの場所のアドレスを入力できます。 代わりに、ネットワーク分析情報がそれらの場所に集計されます。 Officeの場所は、300 メートルを超える近くに集計することはできません。

## <a name="location-in-the-microsoft-365-admin-center"></a>Microsoft 365 管理 センター内の場所

<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理センター</a>では、Bing マップ コントロールを使用して、組織のオフィスの場所を表示します。 コントロールには、選択したオフィスの場所のネットワーク境界トポロジも表示されます。 管理者がオフィスの場所の特定の住所の詳細を追加すると、Bing地図は、データ入力を簡単にするために住所を提案するためにも使用されます。

## <a name="terms-of-use"></a>使用条件

ジオコードを含むBing地図を通じて提供されるコンテンツは、コンテンツが提供される製品内でのみ使用できます。 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Bing地図</a>を利用したお客様のMicrosoft 365 管理センター Location Services 機能の使用は、[Microsoft のプライバシーに](https://go.microsoft.com/fwlink/?LinkID=248686)関する声明で<https://go.microsoft.com/?linkid=9710837>入手可能な _Bing地図 End-User利用規約_ に準拠します。

この機能は、Bing地図を通じて提供され、**TomTom** でもサポートされています。 TomTom の製品とサービスの詳細については、以下をご覧 [https://www.tomtom.com/legal](https://www.tomtom.com/legal)ください。

## <a name="related-topics"></a>関連項目

[Microsoft 365 管理 センターでのネットワーク接続](office-365-network-mac-perf-overview.md)

[ネットワーク パフォーマンスの分析情報をMicrosoft 365する](office-365-network-mac-perf-insights.md)

[Microsoft 365 ネットワーク評価](office-365-network-mac-perf-score.md)

[Microsoft 365 管理センターで接続テストをMicrosoft 365する](office-365-network-mac-perf-onboarding-tool.md)
