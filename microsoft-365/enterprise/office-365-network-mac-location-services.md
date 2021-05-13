---
title: Microsoft 365ネットワーク接続位置情報サービス
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365ネットワーク接続位置情報サービス
ms.openlocfilehash: ed78d7ba48cd9666ce1aae1af5478e3b7536e1e1
ms.sourcegitcommit: fb6c5e04ade1e82b26b2f911577b5ac721f1c544
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2021
ms.locfileid: "52470450"
---
# <a name="microsoft-365-network-connectivity-location-services"></a>Microsoft 365ネットワーク接続位置情報サービス

[Microsoft 365管理センターには、ネットワークインサイトとパフォーマンスに関する推奨事項が表示されます。これは、テナントから収集されたライブ パフォーマンスMicrosoft 365です。 これらの指標は、テナントの管理ユーザーだけが表示できます。 組織のネットワーク接続は、インターネットへのネットワーク出力場所を介して、オフィスの場所ごとに設計されています。 Microsoft 365接続では、そのルートを使用し、インターネットを通して Microsoft サービスのフロント ドア サーバーに接続します。 これらのネットワークインサイトを表示するには、オフィスの場所を特定する必要があります。

## <a name="location-in-network-measurements"></a>ネットワーク測定値の場所

組織の管理者は、この機能で使用されるネットワーク測定値に含める場所を選択できます。 これにより、各オフィスがある都市の自動検出が可能です。 位置情報は正確ではなく、300m に難読化され、都市別に分類されます。 デバイスで場所がキャプチャされた時点Windowsツール トレイに [場所の使用] アイコンが表示されます。 管理者は、このアイコンの外観をユーザーに通知することができます。 この処理では、場所は組織のオフィスの場所として扱われるので、人やデバイスの場所として扱われるのではありません。 ネットワークの分析情報は、これらの検出されたオフィスの場所の都市で表示できます。 推奨事項の精度を高くする場合は、特定のオフィスの場所の住所を入力できます。 ネットワークインサイトは、代わりにそれらの場所に集約されます。 Office 300 メートルを超える場所を集計することはできません。

## <a name="location-in-the-microsoft-365-admin-center"></a>管理センター Microsoft 365場所

管理センター Microsoft 365、Bingマップ コントロールを使用して、組織のオフィスの場所を表示します。 コントロールには、選択したオフィスの場所のネットワーク境界トポロジも表示されます。 管理者がオフィスの場所に特定の住所の詳細を追加すると、Bing地図を提案してデータ入力を容易にするためにも使用されます。

## <a name="terms-of-use"></a>使用条件

ジオコードを含むBing地図提供されるコンテンツは、コンテンツが提供される製品内でのみ使用できます。 Bing地図 を利用した Microsoft 365 管理センターの位置情報サービス機能の使用は、Bing地図 End-User で利用可能な _Bing地図 End-User_ 利用規約および Microsoft プライバシーに関する声明によって <https://go.microsoft.com/?linkid=9710837> [管理されます](https://go.microsoft.com/fwlink/?LinkID=248686)。

この機能は **、tomTom** Bing地図によって提供されます。 TomTom の製品とサービスの詳細については、以下を参照してください [https://www.tomtom.com/legal](https://www.tomtom.com/legal) 。

## <a name="related-topics"></a>関連項目

[管理センターでのネットワークMicrosoft 365 (プレビュー)](office-365-network-mac-perf-overview.md)

[Microsoft 365パフォーマンス分析情報 (プレビュー)](office-365-network-mac-perf-insights.md)

[Microsoft 365評価 (プレビュー)](office-365-network-mac-perf-score.md)

[Microsoft 365管理センターでの接続Microsoft 365テスト (プレビュー)](office-365-network-mac-perf-onboarding-tool.md)
