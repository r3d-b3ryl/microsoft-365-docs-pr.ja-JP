---
title: Microsoft 365の一般的な VPN 分割トンネリング シナリオ
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
description: Microsoft 365の一般的な VPN 分割トンネリング シナリオ
ms.openlocfilehash: 26f4cf10de3282c5257592a26ea61d073a0d3cd4
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63331142"
---
# <a name="common-vpn-split-tunneling-scenarios-for-microsoft-365"></a>Microsoft 365の一般的な VPN 分割トンネリング シナリオ

>[!NOTE]
>この記事は、リモート ユーザーの最適化Microsoft 365対処する一連の記事の一部です。

>- VPN 分割トンネリングを使用してリモート ユーザーのMicrosoft 365接続を最適化する方法の概要については、「[概要: Microsoft 365の VPN 分割トンネリング」を](microsoft-365-vpn-split-tunnel.md)参照してください。
>- VPN 分割トンネリングの実装に関する詳細なガイダンスについては、「[Microsoft 365用の VPN 分割トンネリングの実装」を](microsoft-365-vpn-implement-split-tunnel.md)参照してください。
>- VPN 分割トンネリング環境でのTeamsメディア トラフィックのセキュリティ保護に関するガイダンスについては、「VPN 分割トンネリング[のメディア トラフィックTeamsセキュリティ保護](microsoft-365-vpn-securing-teams.md)する」を参照してください。
>- VPN 環境で Stream イベントとライブ イベントを構成する方法については、「VPN 環境での [Stream イベントとライブ イベントに関する特別な考慮事項](microsoft-365-vpn-stream-and-live-events.md)」を参照してください。
>- 中国のユーザーに対Microsoft 365世界規模のテナント パフォーマンスを最適化する方法については、「中国ユーザー[のパフォーマンスの最適化Microsoft 365」を参照してください](microsoft-365-networking-china.md)。

次の一覧には、エンタープライズ環境で見られる最も一般的な VPN シナリオが表示されます。 ほとんどの企業は、従来モデル 1 (VPN 強制トンネリング) を運用しています。 このセクションは、比較的少ない労力で実現可能な **モデル 2** への迅速かつ安全な移行に役立ち、ネットワークのパフォーマンスとユーザー エクスペリエンスに大きな利点があります。

| モデル | 説明 |
| --- | --- |
| [1. VPN 強制トンネリング](#1-vpn-forced-tunnel) | トラフィックの 100% がオンプレミス、インターネット、すべての O365/M365 を含む VPN トンネルに入ります |
| [2. いくつかの例外を含む VPN 強制トンネリング](#2-vpn-forced-tunnel-with-a-small-number-of-trusted-exceptions) | VPN トンネルが既定で使用され (既定のルート ポイントが VPNに繋がっている)、直接のアクセスが許可される最も重要な除外シナリオはほとんど使用されない。 |
| [3. 広範囲な例外を含む VPN 強制トンネリング](#3-vpn-forced-tunnel-with-broad-exceptions) | VPN トンネルは既定で使用されます (VPN への既定のルート ポイント)、直接移動できる広範な例外 (すべてのMicrosoft 365、All Salesforce、All Zoom など) |
| [4. VPN 選択的トンネリング](#4-vpn-selective-tunnel) | VPN トンネルは、コーネット ベースのサービスにのみ使用されます。 既定のルート (インターネットとすべてのインターネット ベースのサービス) は直接行われます。 |
| [5. VPN なし](#5-no-vpn) | #2 のバリエーション。 従来の VPN の代わりに、すべてのコーネット サービスは、最新のセキュリティアプローチ (Zscaler ZPA、Azure Active Directory (Azure AD) プロキシ/MCASなど) を通じて公開されます。 |

## <a name="1-vpn-forced-tunnel"></a>1. VPN 強制トンネリング

ほとんどの企業のお客様にとって最も一般的な開始シナリオです。 強制 VPN が使用されます。つまり、エンドポイントが企業ネットワーク内に存在するかどうかに関係なく、トラフィックの 100% が企業ネットワークに送信されます。 その後、Microsoft 365やインターネットの閲覧などの外部 (インターネット) のバインドされたトラフィックはすべて、プロキシなどのオンプレミスのセキュリティ機器からヘアピンで固定されます。 現在の環境では、ユーザーの約 100% がリモートで作業しているため、このモデルは VPN インフラストラクチャに高い負荷を加え、すべての企業トラフィックのパフォーマンスを大幅に低下させ、企業が危機時に効率的に運用する可能性が高くなります。

![VPN 強制Tunnel モデル 1。](../media/vpn-split-tunneling/vpn-model-1.png)

## <a name="2-vpn-forced-tunnel-with-a-small-number-of-trusted-exceptions"></a>2. 少数の認可された例外を含む VPN 強制トンネル

企業の運用効率が大幅に向上しました。 このモデルでは、負荷と待機時間に影響を受けやすい制御された定義済みのエンドポイントをいくつか使用して、VPN トンネルをバイパスし、Microsoft 365 サービスに直接アクセスできます。 これにより、オフロードされたサービスのパフォーマンスが大幅に向上し、VPN インフラストラクチャの負荷も低下するため、リソースの競合を減らしながら動作する必要がある要素が引き続き可能になります。 この記事では、多数の肯定的な結果を得て、簡単で定義されたアクションを迅速に実行できるため、この記事では移行を支援することに重点を置いたモデルです。

![VPN モデル 2 Tunnel分割します。](../media/vpn-split-tunneling/vpn-model-2.png)

## <a name="3-vpn-forced-tunnel-with-broad-exceptions"></a>3. 広範囲な例外を含む VPN 強制トンネリング

モデル 2 の範囲を広げる。 定義されたエンドポイントの小さなグループを直接送信するのではなく、代わりにすべてのトラフィックを信頼されたサービス (Microsoft 365や SalesForce など) に直接送信します。 これにより、企業の VPN インフラストラクチャの負荷がさらに軽減され、決められたサービスのパフォーマンスが向上します。 このモデルの実現可能性を評価して実装するには、より多くの時間がかかる可能性があるため、モデル 2 が正常に配置されると、後で反復的に実行できるステップになる可能性があります。

![VPN モデル 3 Tunnel分割します。](../media/vpn-split-tunneling/vpn-model-3.png)

## <a name="4-vpn-selective-tunnel"></a>4. VPN 選択的トンネリング

会社の IP アドレスを持つものとして識別されたトラフィックのみが VPN トンネルに送信されるため、インターネット パスが他のすべての既定のルートであるという点で、3 番目のモデルを反転します。 このモデルでは、組織が[ゼロ トラスト](https://www.microsoft.com/security/zero-trust?rtc=1)への道を歩み、安全な実装ができる必要があります。 このモデルまたはその一部のバリエーションは、企業ネットワークからクラウドに移行するサービスが増えるにつれて、時間の経過と共に必要な既定値になる可能性があることに注意してください。

Microsoft では、このモデルを内部的に使用しています。 Microsoft による VPN 分割トンネリングの実装の詳細については、「 [Running on VPN: Microsoft がリモート ワークフォースを接続し続ける方法](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv)」を参照してください。

![VPN モデル 4 Tunnel分割します。](../media/vpn-split-tunneling/vpn-model-4.png)

## <a name="5-no-vpn"></a>5. VPN なし

モデル番号 2 のより高度なバージョン。これにより、Azure AD プロキシ、Defender for Cloud Apps、Zscaler ZPA などの最新のセキュリティ アプローチまたは SDWAN ソリューションを通じて内部サービスが発行されます。

![VPN モデル 5 Tunnel分割します。](../media/vpn-split-tunneling/vpn-model-5.png)

## <a name="related-articles"></a>関連記事

[概要: Microsoft 365の VPN 分割トンネリング](microsoft-365-vpn-split-tunnel.md)

[Microsoft 365用の VPN 分割トンネリングの実装](microsoft-365-vpn-implement-split-tunnel.md)

[VPN 分割トンネリングのための Teams メディア トラフィックのセキュリティ保護](microsoft-365-vpn-securing-teams.md)

[VPN 環境での Stream イベントとライブ イベントに関する特別な考慮事項](microsoft-365-vpn-stream-and-live-events.md)

[中国ユーザーのMicrosoft 365パフォーマンスの最適化](microsoft-365-networking-china.md)

[Microsoft 365 ネットワーク接続の原則](microsoft-365-network-connectivity-principles.md)

[Microsoft 365 ネットワーク接続の評価](assessing-network-connectivity.md)

[Microsoft 365ネットワークとパフォーマンスのチューニング](network-planning-and-performance.md)

[セキュリティ専門家と IT による、現代のユニークなリモート ワーク シナリオで最新のセキュリティ管理を実現するための代替的な方法 (Microsoft セキュリティ チーム ブログ)](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)

[Microsoft での VPN のパフォーマンス強化: Windows 10 の VPN プロファイルを使用して自動接続を許可する](https://www.microsoft.com/itshowcase/enhancing-remote-access-in-windows-10-with-an-automatic-vpn-profile)

[VPN で実行: Microsoft がリモート ワークの従業員をどのように接続させているか](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv)

[Microsoft グローバル ネットワーク](/azure/networking/microsoft-global-network)
