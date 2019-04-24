---
title: '手順 2: オフィスごとにローカルのインターネット接続を構成する'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: DNS 解決について理解し、パフォーマンスの良い DNS 解決を構成します。
ms.openlocfilehash: 6f276bd1fd90b8dee76a0b0d350f256956ded412
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291132"
---
# <a name="step-2-configure-local-internet-connections-for-each-office"></a>手順 2: オフィスごとにローカルのインターネット接続を構成する

*この手順は必須であり、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます。*

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

手順 2 では、オフィスごとにローカルのインターネット接続を構成し、ローカルの DNS サーバーを使用していることを確認します。どちらも、接続待機時間を削減し、オンプレミスのクライアント コンピューターが Microsoft 365 クラウドベース サービスの最寄りのエントリ ポイントに確実に接続するために必要な要素です。

大規模な組織向けの従来型ネットワークの場合、インターネット トラフィックはネットワーク バックボーンを通過してから中央インターネット接続に到達します。グローバルに分散した、Office 365 や Microsoft 365 の Enterprise Mobility + Security (EMS) 製品を含むサービスとしてのソフトウェア (SaaS) インフラストラクチャの場合、この方法ではパフォーマンスを最適化できません。

Microsoft のグローバル ネットワークには、Microsoft 365 の一連のクラウド サービスで使用するフロント エンド サーバーが世界中に配置されています。最適なパフォーマンスを実現するため、オンプレミスのクライアントは、ネットワーク バックボーンを介して組織の中央インターネット接続に最も近いフロントエンド サーバーにトラフィックを送信するのではなく、地理的に最も近いフロントエンド サーバーにアクセスする必要があります。

地理的に最も近いフロントエンド サーバーにクライアントの要求を送信するため、Microsoft の DNS サーバーは、クライアントの最初の接続要求に対応する DNS クエリを使用します。したがって、ネットワーク待ち時間を最短にするには、次のことが必要です。

- 組織のすべてのオフィスに、[最適化](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories)カテゴリのネットワーク トラフィック用のローカル インターネット接続が用意されている。
- 各ローカル インターネット接続で、その地点からの送信インターネット トラフィックに、地理的にローカルな DNS サーバーを使用している。

詳細については、「[ネットワーク接続のローカルの出口を提供する](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#egress-network-connections-locally)」を参照してください。 

中間チェックポイントとして、この手順の[終了条件](networking-exit-criteria.md#crit-networking-step2)を確認できます。

## <a name="next-step"></a>次の手順

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)|[ネットワーク ヘアピンを回避する](networking-avoid-network-hairpins.md)|
