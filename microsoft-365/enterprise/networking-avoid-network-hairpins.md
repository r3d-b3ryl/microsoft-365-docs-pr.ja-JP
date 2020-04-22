---
title: '手順 3: ネットワーク ヘアピンを回避する'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/20/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: ネットワーク ヘアピンについて理解して削除することにより、パフォーマンスの向上を図ります。
ms.openlocfilehash: 1d5e10bdd8b79f5c7ccd646ac08f83bb2c48b6ee
ms.sourcegitcommit: d818828c66cf98b0b0037ba8b3cb790c940281b7
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43583427"
---
# <a name="step-3-avoid-network-hairpins"></a>手順 3: ネットワーク ヘアピンを回避する

*この手順は必須であり、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます。*

![フェーズ 1 - ネットワーキング](../media/deploy-foundation-infrastructure/networking_icon-small.png)

[ネットワーク ヘアピン](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P3)は、宛先に向けられたトラフィックが最初にオンプレミス セキュリティ スタック、クラウド アクセス ブローカー、クラウドベースの Web ゲートウェイなどの別の中間場所に向けられたときに発生します。 次に例を示します。

![ネットワーク ヘアピンの例](../media/networking-avoid-network-hairpins/network-hairpin-example.png)

ネットワーク ヘアピンは、ネットワーク サービス プロバイダーが原因でインターネット上のルーティングが不十分な場合にも発生する可能性があります。 

ヘアピンは待機時間を追加し、潜在的にトラフィックを地理的に離れた場所にリダイレクトできます。

Microsoft 365 のクラウドベース サービスに対するトラフィックのパフォーマンスを最適化するには、ローカルのインターネット接続を提供する ISP と、その場所と近接した Microsoft のグローバル ネットワークの間に直接のピアリング関係があるかを確認します。そのような接続では、ヘアピンは生じません。

Microsoft 365 のトラフィックにクラウドベースのネットワークやセキュリティ サービスを使用している場合は、ヘアピンの影響を評価し、パフォーマンスに与える影響を理解する必要があります。次の点を確認します。

- 支店や Microsoft グローバル ネットワークのピアリング ポイントとの関係においてトラフィックの転送経路となるサービス プロバイダーの数および場所。 
- サービス プロバイダーと ISP や Microsoft とのネットワーク ピアリング関係の品質。 
- サービス プロバイダーのインフラストラクチャ内で生じるバックホーリングがパフォーマンスに与える影響。

可能であれば、インターネット トラフィックを処理するサード パーティのクラウドやクラウドベース ネットワーク セキュリティ ベンダーを介したプロキシ処理やトンネリング処理を行うのではなく、信頼済みの Microsoft 365 トラフィックを直接送信するようにエッジ ルーターを構成します。 

![ネットワーク ヘアピンをバイパスする例](../media/networking-avoid-network-hairpins/bypassing-network-hairpin.png)

Microsoft のグローバルネットワークのエントリポイントまでの距離と、組織のネットワークが ISP に接続するポイントまでの距離をテストするには、[Office 365 ネットワーク オンボードツール](https://connectivity.office.com/)を使用します。

中間チェックポイントとして、この手順の[終了条件](networking-exit-criteria.md#crit-networking-step3)を確認できます。

## <a name="next-step"></a>次の手順

|||
|:-------|:-----|
|![手順 4](../media/stepnumbers/Step4.png)|[トラフィック バイパスを構成する](networking-configure-proxies-firewalls.md)|
