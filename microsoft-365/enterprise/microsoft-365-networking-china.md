---
title: 中国ユーザー向け Microsoft 365 グローバル テナントのパフォーマンスの最適化
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/23/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- remotework
search.appverid: MET150
f1.keywords:
- NOCSH
description: この記事では、グローバル Microsoft 365 テナントの中国ユーザー向けにネットワーク パフォーマンスを最適化するためのガイダンスを提供します。
ms.openlocfilehash: 2ba0509425b60aec35d29b23b84e3b6346d2f5cb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923196"
---
# <a name="microsoft-365-global-tenant-performance-optimization-for-china-users"></a>中国ユーザー向け Microsoft 365 グローバル テナントのパフォーマンスの最適化

>[!IMPORTANT]
>このガイダンスは、中国にある **エンタープライズ Microsoft 365** ユーザーがグローバル Microsoft 365 テナントに接続する使用シナリオ **に固有のガイダンスです**。 このガイダンス **は** 、21Vianet がOffice 365 のテナントには適用されません。

グローバルな Microsoft 365 テナントと中国での企業プレゼンスを持つ企業では、中国に拠点を置くユーザー向け Microsoft 365 クライアントのパフォーマンスは、中国電話会社のインターネット アーキテクチャに固有の要因によって複雑になる可能性があります。

中国 ISP は、国境を越えたネットワークの混雑が高レベルになりやすい境界デバイスを経由するグローバルパブリック インターネットへのオフショア接続を規制しています。 この輻輳により、中国に入り出るすべてのインターネット トラフィックに対してパケット損失と遅延が発生します。

![Microsoft 365 トラフィック - 最適化されていない](../media/O365-networking/China-O365-unoptimized.png)

パケット損失と待機時間は、ネットワーク サービスのパフォーマンス、特に大規模なデータ交換 (ファイル転送の大規模な転送など) を必要とするサービス、またはほぼリアルタイムのパフォーマンス (オーディオおよびビデオ アプリケーション) を必要とするサービスに影響します。

このトピックの目的は、中国の国境を越えたネットワークの混雑が Microsoft 365 サービスに及ぼす影響を軽減するためのベスト プラクティスを提供します。 このトピックでは、中国のキャリア内での複雑なルーティングによる高いパケット遅延の問題など、他の一般的なラストマイルのパフォーマンスの問題については説明します。

## <a name="corporate-network-best-practices"></a>企業ネットワークのベスト プラクティス

グローバルな Microsoft 365 テナントと中国のユーザーを持つ多くの企業は、中国のオフィスの場所と世界中のオフショアの場所間の企業ネットワーク トラフィックを運ぶプライベート ネットワークを実装しています。 これらの企業は、このネットワーク インフラストラクチャを活用して、国境を越えたネットワークの混雑を回避し、中国での Microsoft 365 サービスのパフォーマンスを最適化できます。

>[!IMPORTANT]
>すべてのプライベート WAN 実装と同様に、ネットワーク構成が準拠していることを確認するために、国や地域の規制要件を常に確認する必要があります。

最初の手順として [、Microsoft 365](./network-planning-and-performance.md)のネットワーク計画とパフォーマンスチューニングのベンチマーク ネットワーク ガイダンスに従う必要があります。 主な目標は、可能であれば中国のインターネットからグローバル Microsoft 365 サービスにアクセスしないようにすることです。

- 既存のプライベート ネットワークを活用して、中国のオフィス ネットワークと、中国外のパブリック インターネットに送信するオフショアの場所との間で Microsoft 365 ネットワーク トラフィックを伝送します。 中国以外のほぼすべての場所が明確な利点を提供します。 ネットワーク管理者は、Microsoft グローバル ネットワークとの低遅延相互接続領域で出力することで、さらに [最適化できます](/azure/networking/microsoft-global-network)。 香港、日本、韓国が例です。
- VPN 接続を使用して企業ネットワークにアクセスするユーザー デバイスを構成して、Microsoft 365 トラフィックが企業ネットワークのプライベート オフショア リンクを通過できます。 VPN クライアントがスプリット トンネリングを使用するように構成されていないか、Microsoft 365 トラフィックの分割トンネリングを無視するようにユーザー デバイスが構成されていることを確認します。
- すべての Microsoft 365 トラフィックをプライベートのオフショア リンクにルーティングするネットワークを構成します。 プライベート リンク上のトラフィックの量を最小限に抑える必要がある場合は、[最適化] カテゴリのエンドポイントのみをルーティングし、[許可]および[既定のエンドポイント] への要求でインターネットを中継できます。  これにより、高遅延とパケット損失に最も敏感な重要なサービスに最適化されたトラフィックを制限することで、パフォーマンスを向上し、帯域幅の消費を最小限に抑えます。
- 可能であれば、Teams などのライブ メディア ストリーミング トラフィックに TCP の代わりに UDP を使用します。 UDP は、TCP よりも優れたライブ メディア ストリーミング パフォーマンスを提供します。

Microsoft 365 トラフィックを選択的にルーティングする方法については [、「365](managing-office-365-endpoints.md)エンドポイントの管理Officeを参照してください。 365 の URL と IP アドレスOfficeの一覧については [、「365](urls-and-ip-address-ranges.md)URL Office IP アドレス範囲」を参照してください。

![Microsoft 365 トラフィック - 最適化](../media/O365-networking/China-O365-optimized.png)

## <a name="user-best-practices"></a>ユーザーのベスト プラクティス

企業ネットワークに接続できない家庭、喫茶店、ホテル、ブランチ オフィスなどのリモートの場所からグローバルな Microsoft 365 テナントに接続する中国のユーザーは、デバイスと Microsoft 365 間のトラフィックが中国の混雑したクロスボーダー ネットワーク回線を通過する必要があるため、ネットワークパフォーマンスが低下する可能性があります。

国境を越えたプライベート ネットワークや企業ネットワークへの VPN アクセスがオプションではない場合でも、中国に拠点を置くユーザーがこれらのベスト プラクティスに従うトレーニングを行って、ユーザーごとのパフォーマンスの問題を軽減できます。

- キャッシュをOfficeするリッチ クライアント (Outlook、Teams、OneDrive など) を利用し、Web ベースのクライアントを回避します。 Officeキャッシュ機能とオフライン アクセス機能を使用すると、ネットワークの輻輳と待機時間の影響を大幅に軽減できます。
- Microsoft 365 テナントが電話会議機能で構成されている場合、Teams ユーザーは公衆交換電話網 (PSTN) を介して会議に参加できます。 詳細については、「電話会議 in [Office 365」を参照してください](/microsoftteams/audio-conferencing-in-office-365)。
- ネットワーク パフォーマンスの問題が発生した場合は、トラブルシューティングのために IT 部門に報告し、Microsoft 365 サービスの問題が疑われる場合は Microsoft サポートにエスカレートする必要があります。 一部の問題は、国境を越えたネットワークのパフォーマンスによって引き起こされるという問題ではありません。

Microsoft は、Microsoft 365 のユーザー エクスペリエンスと、可能な限り幅広いネットワーク アーキテクチャと特性に対するクライアントのパフォーマンスの向上に継続的に取り組み続け中です。 Office [365 Tech Community](https://techcommunity.microsoft.com/t5/office-365/bd-p/Office365General) にアクセスして、会話を開始または参加し、リソースを検索し、機能の要求と提案を送信します。

## <a name="related-topics"></a>関連項目

[Microsoft 365 のネットワーク計画とパフォーマンス チューニング](./network-planning-and-performance.md)

[Microsoft 365 ネットワーク接続の原則](microsoft-365-network-connectivity-principles.md)

[Office 365 エンドポイントの管理](managing-office-365-endpoints.md)

[Office 365 の URL および IP アドレスの範囲](urls-and-ip-address-ranges.md)

[Microsoft グローバル ネットワーク](/azure/networking/microsoft-global-network)