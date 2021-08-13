---
title: Office 365 向け Azure ExpressRoute
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/5/2019
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 6d2534a2-c19c-4a99-be5e-33a0cee5d3bd
description: Azure ExpressRoute を使用してネットワークOffice 365展開する場合は、ネットワーク実装プロジェクトを計画する方法について説明します。
ms.openlocfilehash: 742beb28db325b61c837d205b9463be3fcc551087628d39e3c1ce3839a1fd3d5
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53830403"
---
# <a name="azure-expressroute-for-office-365"></a>Office 365 向け Azure ExpressRoute

*この記事は、Microsoft 365 Enterprise と Office 365 Enterprise の両方に適用されます。*

azure ExpressRoute を Office 365 で使用する方法と、Azure ExpressRoute を Office 365 で使用するために展開する場合に必要となるネットワーク実装プロジェクトを計画する方法について説明します。 Azure で実行されるインフラストラクチャサービスとプラットフォーム サービスは、多くの場合、ネットワーク アーキテクチャとパフォーマンスに関する考慮事項に対処することでメリットがあります。 このような場合は、ExpressRoute for Azure をお勧めします。 ソフトウェア as a Service offerings Office 365 Dynamics 365 は、インターネットを介して安全かつ確実にアクセスするために構築されています。 インターネットのパフォーマンスとセキュリティについて、また Azure ExpressRoute のセキュリティに関する記事Office 365「ネットワーク接続の評価」Office 365[参照してください](assessing-network-connectivity.md)。

> [!NOTE]
> Microsoft Defender for Endpoint では、Azure ExpressRoute との統合は提供されない。 これにより、プライベート ネットワークから Microsoft Defender for Endpoint クラウド サービスへの接続を有効にする ExpressRoute ルールの定義はユーザーに止まらなくが、サービスまたはクラウド インフラストラクチャの進化に合わせてルールを維持する必要があります。

> [!NOTE]
> ほとんどの場合、サービスに最適Microsoft 365接続モデルを提供していないので、ExpressRoute を使用することをお勧めしません。 そのため、Microsoft の認証は、この接続モデルをユーザーに使用するためにMicrosoft 365。 すべての顧客要求を確認し、必要なまれなMicrosoft 365場合にのみ ExpressRoute を承認します。 詳細については[、ExpressRoute for Microsoft 365](https://aka.ms/erguide)ガイドを参照し、生産性、ネットワーク、およびセキュリティ チームとドキュメントの包括的なレビューに従って、必要に応じて Microsoft アカウント チームと一緒に作業して例外を提出してください。 未承認のサブスクリプションがルート フィルターを作成しようとOffice 365エラー メッセージが[表示されます](https://support.microsoft.com/kb/3181709)。

## <a name="planning-azure-expressroute-for-office-365"></a>Azure ExpressRoute for Office 365

インターネット接続に加えて、予測可能性と Microsoft ネットワーク コンポーネントの 99.95% のアップタイム SLA を提供する直接接続を通して、Office 365 ネットワーク トラフィックのサブセットをルーティングすることができます。 Azure ExpressRoute は、この専用ネットワーク接続を提供し、Office 365 Microsoft クラウド サービスに接続します。

既存の MPLS WAN を持っているかどうかに関係なく、ExpressRoute は 3 つの方法の 1 つでネットワーク アーキテクチャに追加できます。は、サポートされているクラウド交換の共同場所プロバイダー、イーサネット ポイント間接続プロバイダー、または MPLS 接続プロバイダーを介して行います。 地域 [で利用できるプロバイダーを確認します](/azure/expressroute/expressroute-locations)。 直接 ExpressRoute 接続を使用すると、以下の「サービスに含まれるOffice 365アプリケーションへの接続[が可能](azure-expressroute.md#BKMK_WhatDoIGet)になります。 他のすべてのアプリケーションとサービスのネットワーク トラフィックは、引き続きインターネットを通過します。

Office 365、Windows Update、TechNet などのすべての Microsoft アプリケーションにアクセスするために、インターネットを通して Microsoft のデータセンターに接続する一般的な Office 365 顧客を示す、次の高レベルネットワーク図を検討してください。 顧客は、オンプレミス ネットワークから接続しているか、独立したインターネット接続から接続しているかに関係なく、同様のネットワーク パスを使用します。

![Office 365接続](../media/9d8bc622-4a38-4a3b-a0f3-68657712d460.png)

次に、インターネットと ExpressRoute の両方を使用してユーザーに接続Office 365顧客を示す更新された図をOffice 365。 パブリック DNS やネットワーク ノードなどの一部の接続Content Delivery Networkパブリック インターネット接続が必要な場合があります。 また、ExpressRoute 接続ビル内に位置していないお客様のユーザーがインターネットを通じて接続している場合にも注意してください。

![Office 365 ExpressRoute との接続](../media/251788c4-0937-4584-9b2c-df08e11611fc.png)

さらに詳しい情報が必要ですか? Azure [ExpressRoute を使用して](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408)ネットワーク トラフィックを管理する方法Office 365、Azure ExpressRoute for Office 365 を[構成する方法について説明します](/azure/expressroute/expressroute-faqs)。 また、チャネル 9 で 10 部の[Azure ExpressRoute](https://channel9.msdn.com/series/aer) for Office 365トレーニング シリーズを記録し、概念の詳細な説明を行いました。

## <a name="what-office-365-services-are-included"></a>どのOffice 365サービスが含まれていますか?
<a name="BKMK_WhatDoIGet"> </a>

次の表に、ExpressRoute でOffice 365されているサービスの一覧を示します。 これらのアプリケーション[に対してOffice 365](./urls-and-ip-address-ranges.md)インターネット接続が必要なネットワーク要求を理解するには、エンドポイントに関する記事を参照してください。

| 含まれるアプリケーション |
|:-----|
|Exchange Online<sup>1</sup> <br/> Exchange Online Protection<sup>1</sup> <br/> Delve<sup>1</sup> <br/> |
|Skype for Businessオンライン<sup>1</sup> <br/> Microsoft Teams <sup>1</sup> <br/> |
|SharePointオンライン<sup>1</sup> <br/> OneDrive for Business<sup>1</sup> <br/> Project Online<sup>1</sup> <br/> |
|ポータルと共有<sup>1</sup> <br/> Azure Active Directory (Azure AD) <sup>1</sup> <br/> Azure AD Connect<sup>1</sup> <br/> Office<sup>1</sup> <br/> |

<sup>1</sup>これらの各アプリケーションには、ExpressRoute でサポートされていないインターネット[接続](./urls-and-ip-address-ranges.md)要件があります。詳細については、「Office 365 エンドポイント」の記事を参照してください。

Office 365 用 ExpressRoute に含まれていないサービスは、Microsoft 365 Apps for enterprise クライアントダウンロード、オンプレミス ID プロバイダー サインイン、および中国の Office 365 (21 Vianet が運営) サービスです。

## <a name="implementing-expressroute-for-office-365"></a>Office 365 向け ExpressRoute の実装

ExpressRoute を実装するには、ネットワークとアプリケーションの所有者の関与が必要であり、新しい[](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408)ネットワーク ルーティング アーキテクチャ、帯域幅要件、セキュリティの実装場所、高可用性などについて慎重に計画する必要があります。 ExpressRoute を実装するには、次の必要があります。

1. ExpressRoute が接続計画で満たす必要Office 365十分に理解します。 インターネットまたは ExpressRoute を使用するアプリケーションを理解し、Office 365 トラフィックにインターネットと ExpressRoute の両方を使用するコンテキストで、ネットワーク容量、セキュリティ、高可用性のニーズを完全に計画します。

2. インターネットトラフィックと ExpressRoute トラフィック 1 の両方の出力とピアリングの場所を<sup>決定します</sup>。

3. インターネット接続と ExpressRoute 接続で必要な容量を決定します。

4. セキュリティおよび他の標準境界コントロール 1 を実装するための計画を<sup>立てます</sup>。

5. ExpressRoute をサブスクライブMicrosoft Azure有効なアカウントを持っている。

6. 接続モデルと承認済みプロバイダー [を選択します](/azure/expressroute/expressroute-locations)。 顧客は複数の接続モデルまたはパートナーを選択できます。パートナーは既存のネットワーク プロバイダーと同じである必要はなかっています。

7. ExpressRoute にトラフィックを送信する前に展開を検証します。

8. 必要に応 [じて QoS を実装し](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d) 、地域の拡張を評価します。

<sup>1</sup> 重要なパフォーマンスに関する考慮事項。 ここでの決定は、待ち時間に大きな影響を与える可能性があります。これは、Skype for Business。

その他の参照については、ExpressRoute [のドキュメントに加えて](https://support.office.com/article/Routing-with-ExpressRoute-for-Office-365-e1da26c6-2d39-4379-af6f-4da213218408) 、ルーティング ガイド [を使用してください](/azure/expressroute/expressroute-introduction)。

Office 365 用の ExpressRoute を購入するには、1 つ以上の承認済み[](/azure/expressroute/expressroute-locations)プロバイダーと作業して、ExpressRoute プレミアム サブスクリプションを使用して目的の数とサイズの回線をプロビジョニングする必要があります。 ユーザーから購入する追加のライセンスOffice 365。

ここに戻る場合は、次の短いリンクをご利用ください: [https://aka.ms/expressrouteoffice365]()

ExpressRoute for Office 365 に[サインアップする準備ができましたか](https://aka.ms/ert)?

## <a name="related-topics"></a>関連項目

[Office 365 ネットワーク接続の評価](assessing-network-connectivity.md)

[Office 365 向け ExpressRoute の管理](managing-expressroute-for-connectivity.md)

[Office 365 向け ExpressRoute でのルーティング](routing-with-expressroute.md)

[Office 365 向け ExpressRoute でのネットワーク計画](network-planning-with-expressroute.md)

[Office 365 向け ExpressRoute の実装](implementing-expressroute.md)

[ExpressRoute での BGP コミュニティの使用によるOffice 365シナリオ](bgp-communities-in-expressroute.md)

[Skype for Business Online でのメディア品質とネットワーク接続のパフォーマンス](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)

[ベースラインとパフォーマンス履歴を使用した、Office 365 のパフォーマンスのチューニング](performance-tuning-using-baselines-and-history.md)

[Office 365 のパフォーマンスに関するトラブルシューティングの計画](performance-troubleshooting-plan.md)

[Office 365 URL および IP アドレス範囲](urls-and-ip-address-ranges.md)

[Office 365 のネットワークとパフォーマンスのチューニング](network-planning-and-performance.md)

## <a name="see-also"></a>関連項目

[Microsoft 365 Enterprise の概要](microsoft-365-overview.md)
