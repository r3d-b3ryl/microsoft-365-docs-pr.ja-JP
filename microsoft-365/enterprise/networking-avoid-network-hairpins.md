---
title: '手順 3: ネットワーク ヘアピンを回避する'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: ネットワーク ヘアピンについて理解して削除することにより、パフォーマンスの向上を図ります。
ms.openlocfilehash: 7277b8f5c07bc156599f946e032c3345da3316e9
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869638"
---
# <a name="step-3-avoid-network-hairpins"></a>手順 3: ネットワーク ヘアピンを回避する

*この手順は必須であり、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます。*

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

[ネットワーク ヘアピン](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P3)は、ある宛先に送信されたトラフィックが、オンプレミスのセキュリティ スタックや、クラウド アクセス ブローカー、クラウドベースの Web ゲートウェイなど、宛先以外の中間の場所に最初に差し向けられると発生します。ネットワーク ヘアピンは、ネットワーク サービス プロバイダーが原因のインターネット上の不適切なルーティングによっても発生する可能性があります。ヘアピンが発生すると、待機時間が増え、地理的に離れた場所にトラフィックがリダイレクトされる場合もあります。

Microsoft 365 のクラウドベース サービスに対するトラフィックのパフォーマンスを最適化するには、ローカルのインターネット接続を提供する ISP と、その場所と近接した Microsoft のグローバル ネットワークの間に直接のピアリング関係があるかを確認します。そのような接続では、ヘアピンは生じません。

Microsoft 365 のトラフィックにクラウドベースのネットワークやセキュリティ サービスを使用している場合は、ヘアピンの影響を評価し、パフォーマンスに与える影響を理解する必要があります。次の点を確認します。

- 支店や Microsoft グローバル ネットワークのピアリング ポイントとの関係においてトラフィックの転送経路となるサービス プロバイダーの数および場所。 
- サービス プロバイダーと ISP や Microsoft とのネットワーク ピアリング関係の品質。 
- サービス プロバイダーのインフラストラクチャ内で生じるバックホーリングがパフォーマンスに与える影響。

可能であれば、インターネット トラフィックを処理するサード パーティのクラウドやクラウドベース ネットワーク セキュリティ ベンダーを介したプロキシ処理やトンネリング処理を行うのではなく、信頼済みの Microsoft 365 トラフィックを直接送信するようにエッジ ルーターを構成します。 

中間チェックポイントとして、この手順の[終了条件](networking-exit-criteria.md#crit-networking-step3)を確認できます。

## <a name="next-step"></a>次の手順

|||
|:-------|:-----|
|![](./media/stepnumbers/Step4.png)|[トラフィック バイパスを構成する](networking-configure-proxies-firewalls.md)|
