---
title: VPN スプリット トンネリングの一般的なシナリオ (Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 3/3/2022
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- remotework
f1.keywords:
- NOCSH
description: VPN スプリット トンネリングの一般的なシナリオ (Microsoft 365
ms.openlocfilehash: 26f4cf10de3282c5257592a26ea61d073a0d3cd4
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63331142"
---
# <a name="common-vpn-split-tunneling-scenarios-for-microsoft-365"></a>VPN スプリット トンネリングの一般的なシナリオ (Microsoft 365

>[!NOTE]
>この記事は、リモート ユーザーの最適化に関するMicrosoft 365の一部です。

>- VPN スプリット トンネリングを使用してリモート ユーザー Microsoft 365接続を最適化する方法の概要については、「[Overview: VPN split tunneling for remoteing for remote」を参照](microsoft-365-vpn-split-tunnel.md)Microsoft 365。
>- VPN スプリット トンネリングの実装に関する詳細なガイダンスについては、「VPN スプリット トンネリングの実装」を参照[Microsoft 365。](microsoft-365-vpn-implement-split-tunnel.md)
>- VPN スプリット トンネリング環境でのTeamsメディア トラフィックのセキュリティ保護に関するガイダンスについては、「VPN スプリット トンネリングTeamsメディア トラフィックのセキュリティ[保護」を参照してください](microsoft-365-vpn-securing-teams.md)。
>- VPN 環境で Stream イベントとライブ イベントを構成する方法については、「VPN 環境での Stream イベントとライブ イベントに関する特別な考慮事項」 [を参照してください](microsoft-365-vpn-stream-and-live-events.md)。
>- 中国のユーザーに対するMicrosoft 365のパフォーマンスの最適化の詳細については、「中国のユーザー Microsoft 365[パフォーマンスの最適化」を参照してください](microsoft-365-networking-china.md)。

以下の一覧では、エンタープライズ環境で最も一般的な VPN シナリオが表示されます。 ほとんどの企業は、従来モデル 1 (VPN 強制トンネリング) を運用しています。 このセクションでは、比較的少ない労力で達成できるモデル **2** への迅速かつ安全な移行に役立ち、ネットワークパフォーマンスとユーザー エクスペリエンスに大きなメリットがあります。

| モデル | 説明 |
| --- | --- |
| [1. VPN 強制トンネリング](#1-vpn-forced-tunnel) | トラフィックの 100% は、オンプレミス、インターネット、およびすべての O365/M365 を含む VPN トンネルに入ります |
| [2. いくつかの例外を含む VPN 強制トンネリング](#2-vpn-forced-tunnel-with-a-small-number-of-trusted-exceptions) | VPN トンネルが既定で使用され (既定のルート ポイントが VPNに繋がっている)、直接のアクセスが許可される最も重要な除外シナリオはほとんど使用されない。 |
| [3. 広範囲な例外を含む VPN 強制トンネリング](#3-vpn-forced-tunnel-with-broad-exceptions) | VPN トンネルは既定で使用されます (既定のルート ポイントは VPN をポイントします)。直接移動できる広範な例外 (すべての Microsoft 365、All Salesforce、All Zoom など) |
| [4. VPN 選択的トンネリング](#4-vpn-selective-tunnel) | VPN トンネルは、corpnet ベースのサービスにのみ使用されます。 既定のルート (インターネットとすべてのインターネット ベースのサービス) は直接行きます。 |
| [5. VPN なし](#5-no-vpn) | #2 のバリエーション。 従来の VPN の代わりに、すべての corpnet サービスは、最新のセキュリティ アプローチ (Zscaler ZPA、Azure Active Directory (Azure AD) プロキシ/MCAS など) を通じて公開されます。 |

## <a name="1-vpn-forced-tunnel"></a>1. VPN 強制トンネリング

ほとんどのエンタープライズ顧客の最も一般的な開始シナリオ。 強制 VPN が使用されます。つまり、エンドポイントが企業ネットワーク内にあるかどうかに関なく、トラフィックの 100% が企業ネットワークに送信されます。 外部 (インターネット) にバインドされたトラフィック (Microsoft 365インターネットブラウズなど) は、プロキシなどのオンプレミスのセキュリティ機器からヘア ピン留めされます。 したがって、リモートで作業しているユーザーの 100% 近い現在の環境では、このモデルは VPN インフラストラクチャに大きな負荷を与え、すべての企業トラフィックのパフォーマンスを大幅に低下させる可能性が高く、企業が危機の時に効率的に運用する可能性があります。

![VPN 強制Tunnel モデル 1。](../media/vpn-split-tunneling/vpn-model-1.png)

## <a name="2-vpn-forced-tunnel-with-a-small-number-of-trusted-exceptions"></a>2. 少数の認可された例外を含む VPN 強制トンネル

企業の運用効率が大幅に向上しました。 このモデルを使用すると、高負荷と待機時間に敏感ないくつかの制御および定義されたエンドポイントが VPN トンネルをバイパスし、Microsoft 365 サービスに直接Microsoft 365できます。 これにより、オフロードされたサービスのパフォーマンスが大幅に向上し、VPN インフラストラクチャへの負荷も軽減され、リソースに対するより低いコンテンツで動作する必要がある要素も可能になります。 この記事では、単純で定義されたアクションを多数の肯定的な結果で迅速に実行できるので、移行の支援に集中しています。

![VPN Tunnel 2 を分割します。](../media/vpn-split-tunneling/vpn-model-2.png)

## <a name="3-vpn-forced-tunnel-with-broad-exceptions"></a>3. 広範囲な例外を含む VPN 強制トンネリング

モデル 2 の範囲を広げる。 定義されたエンドポイントの小さなグループを直接送信するのではなく、すべてのトラフィックを信頼できるサービス (Microsoft 365 や SalesForce など) に直接送信します。 これにより、企業の VPN インフラストラクチャの負荷がさらに軽減され、決められたサービスのパフォーマンスが向上します。 このモデルの実現可能性を評価して実装するには、より多くの時間がかかる可能性が高いから、モデル 2 が正常に実施されると、後日繰り返し実行できる手順になる可能性があります。

![VPN Tunnel 3 を分割します。](../media/vpn-split-tunneling/vpn-model-3.png)

## <a name="4-vpn-selective-tunnel"></a>4. VPN 選択的トンネリング

企業の IP アドレスを持つこととして識別されたトラフィックだけが VPN トンネルに送信され、インターネット パスが他のすべての既定のルートであるという点で、3 番目のモデルを反転します。 このモデルでは、組織が[ゼロ トラスト](https://www.microsoft.com/security/zero-trust?rtc=1)への道を歩み、安全な実装ができる必要があります。 このモデルまたはその一部のバリエーションは、企業ネットワークからクラウドに移動するサービスが多くなると、必要な既定になる可能性があります。

Microsoft では、このモデルを内部的に使用します。 Microsoft の VPN スプリット トンネリングの実装に関する詳細については、「 [RUNNING on VPN: Microsoft](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv) がリモート ワークフォースを接続し続ける方法」を参照してください。

![VPN Tunnel 4 を分割します。](../media/vpn-split-tunneling/vpn-model-4.png)

## <a name="5-no-vpn"></a>5. VPN なし

モデル番号 2 のより高度なバージョンで、内部サービスは、Azure AD Proxy、Defender for Cloud Apps、Zscaler ZPA などの最新のセキュリティ アプローチまたは SDWAN ソリューションを通じて公開されます。

![VPN Tunnel 5 を分割します。](../media/vpn-split-tunneling/vpn-model-5.png)

## <a name="related-articles"></a>関連記事

[概要: VPN スプリット トンネリング (Microsoft 365](microsoft-365-vpn-split-tunnel.md)

[VPN スプリット トンネリングを実装するMicrosoft 365](microsoft-365-vpn-implement-split-tunnel.md)

[VPN スプリット トンTeamsメディア トラフィックのセキュリティ保護](microsoft-365-vpn-securing-teams.md)

[VPN 環境での Stream イベントとライブ イベントに関する特別な考慮事項](microsoft-365-vpn-stream-and-live-events.md)

[Microsoft 365のパフォーマンスの最適化](microsoft-365-networking-china.md)

[Microsoft 365 ネットワーク接続の原則](microsoft-365-network-connectivity-principles.md)

[Microsoft 365 ネットワーク接続の評価](assessing-network-connectivity.md)

[Microsoft 365とパフォーマンスの調整](network-planning-and-performance.md)

[セキュリティ専門家と IT による、現代のユニークなリモート ワーク シナリオで最新のセキュリティ管理を実現するための代替的な方法 (Microsoft セキュリティ チーム ブログ)](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)

[Microsoft での VPN のパフォーマンス強化: Windows 10 の VPN プロファイルを使用して自動接続を許可する](https://www.microsoft.com/itshowcase/enhancing-remote-access-in-windows-10-with-an-automatic-vpn-profile)

[VPN で実行: Microsoft がリモート ワークの従業員をどのように接続させているか](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv)

[Microsoft グローバル ネットワーク](/azure/networking/microsoft-global-network)
