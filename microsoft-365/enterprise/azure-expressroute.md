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
description: Azure ExpressRoute を 365 で使用Office、展開する場合はネットワーク実装プロジェクトを計画する方法について説明します。
ms.openlocfilehash: 8047cdaa1325df487709660b558420609afffd42
ms.sourcegitcommit: 9063c7a50a1d7dd6d2e1ca44f53d3c26f21f4ae8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2021
ms.locfileid: "52073951"
---
# <a name="azure-expressroute-for-office-365"></a>Office 365 向け Azure ExpressRoute

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Office 365 で Azure ExpressRoute を使用する方法と、Azure ExpressRoute を Office 365 で使用する場合に必要となるネットワーク実装プロジェクトを計画する方法について説明します。 Azure で実行されるインフラストラクチャサービスとプラットフォーム サービスは、多くの場合、ネットワーク アーキテクチャとパフォーマンスに関する考慮事項に対処することでメリットがあります。 このような場合は、ExpressRoute for Azure をお勧めします。 Office 365 や Dynamics 365 などのサービス製品は、インターネット経由で安全かつ確実にアクセスするために構築されています。 インターネットのパフォーマンスとセキュリティについて、また、Azure ExpressRoute for Office 365 について検討する場合は [、「365](assessing-network-connectivity.md)ネットワーク接続の評価Office参照してください。

> [!NOTE]
> Microsoft Defender for Endpoint は Azure Express Route ではサポートされていません。

> [!NOTE]
> ほとんどの場合、サービスに最適な接続モデルを提供していないので、Microsoft 365 の ExpressRoute はお勧めしません。 そのため、Microsoft 365 に対してこの接続モデルを使用するには、Microsoft の承認が必要です。 Microsoft 365 のすべての顧客要求を確認し、必要なまれなシナリオでのみ ExpressRoute を承認します。 [詳細については、ExpressRoute for Microsoft 365](https://aka.ms/erguide)ガイドを参照し、生産性、ネットワーク、およびセキュリティ チームを含むドキュメントの包括的なレビューに従って、必要に応じて Microsoft アカウント チームと一緒に例外を提出してください。 365 のルート フィルターを作成しようとしている未承認のサブスクリプションOfficeエラー メッセージが [表示されます](https://support.microsoft.com/kb/3181709)。

## <a name="planning-azure-expressroute-for-office-365"></a>Azure ExpressRoute for Office 365

インターネット接続に加えて、予測可能性と Microsoft ネットワーク コンポーネントの 99.95% のアップタイム SLA を提供する直接接続を通して、Office 365 ネットワーク トラフィックのサブセットをルーティングすることができます。 Azure ExpressRoute は、365 および他の Microsoft クラウド サービスOffice専用のネットワーク接続を提供します。

既存の MPLS WAN を持っているかどうかに関係なく、ExpressRoute は 3 つの方法の 1 つでネットワーク アーキテクチャに追加できます。は、サポートされているクラウド交換の共同場所プロバイダー、イーサネット ポイント間接続プロバイダー、または MPLS 接続プロバイダーを介して行います。 地域 [で利用できるプロバイダーを確認します](/azure/expressroute/expressroute-locations)。 直接 ExpressRoute 接続を使用すると、「What [Office 365 サービスが含まれているか」で説明されているアプリケーションへの接続が可能](azure-expressroute.md#BKMK_WhatDoIGet) になります。 他のすべてのアプリケーションとサービスのネットワーク トラフィックは、引き続きインターネットを通過します。

Office 365、Windows Update、TechNet などのすべての Microsoft アプリケーションにアクセスするために、インターネットを通して Microsoft のデータセンターに接続する一般的な Office 365 のお客様を示す、次の高レベルネットワーク図を検討してください。 顧客は、オンプレミス ネットワークから接続しているか、独立したインターネット接続から接続しているかに関係なく、同様のネットワーク パスを使用します。

![Office 365 ネットワーク接続](../media/9d8bc622-4a38-4a3b-a0f3-68657712d460.png)

次に、インターネットと ExpressRoute の両方を使用して 365 に接続する Office 365 の顧客を示す更新されたOfficeします。 パブリック DNS ノードやコンテンツ配信ネットワーク ノードなどの一部の接続では、引き続きパブリック インターネット接続が必要です。 また、ExpressRoute 接続ビル内に位置していないお客様のユーザーがインターネットを通じて接続している場合にも注意してください。

![Office 365 接続と ExpressRoute](../media/251788c4-0937-4584-9b2c-df08e11611fc.png)

さらに詳しい情報が必要ですか? Azure ExpressRoute for [Office 365](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408) でネットワーク トラフィックを管理する方法と、Azure ExpressRoute for Office [365](/azure/expressroute/expressroute-faqs)について説明します。 また、チャネル 9 の Office [365 トレーニング](https://channel9.msdn.com/series/aer) シリーズ用の 10 パーツの Azure ExpressRoute を記録し、概念の詳細な説明を行いました。

## <a name="what-office-365-services-are-included"></a>365 Officeには何が含まれていますか?
<a name="BKMK_WhatDoIGet"> </a>

次の表に、ExpressRoute でOfficeされている 365 サービスの一覧を示します。 これらのアプリケーションに [対するOfficeインターネット](./urls-and-ip-address-ranges.md) 接続が必要なネットワーク要求を理解するには、365 エンドポイントに関する記事を参照してください。

| 含まれるアプリケーション |
|:-----|
|Exchange Online<sup>1</sup> <br/> Exchange Online Protection<sup>1</sup> <br/> Delve<sup>1</sup> <br/> |
|Skype for Business Online<sup>1</sup> <br/> Microsoft Teams <sup>1</sup> <br/> |
|SharePoint Online<sup>1</sup> <br/> OneDrive for Business<sup>1</sup> <br/> Project Online<sup>1</sup> <br/> |
|ポータルと共有<sup>1</sup> <br/> Azure Active Directory (Azure AD) <sup>1</sup> <br/> Azure AD接続<sup>1</sup> <br/> Office<sup>1</sup> <br/> |

<sup>1</sup> これらの各アプリケーションには、ExpressRoute でサポートされていないインターネット接続要件があります。詳細については、「Office [365 エンドポイント](./urls-and-ip-address-ranges.md) 」の記事を参照してください。

Office 365 の ExpressRoute に含まれていないサービスは、Microsoft 365 Apps for enterprise クライアント ダウンロード、オンプレミス ID プロバイダー サインイン、および中国の Office 365 (21 Vianet が運営) サービスです。

## <a name="implementing-expressroute-for-office-365"></a>Office 365 向け ExpressRoute の実装

ExpressRoute を実装するには、ネットワークとアプリケーションの所有者の関与が必要であり、新しい[](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408)ネットワーク ルーティング アーキテクチャ、帯域幅要件、セキュリティの実装場所、高可用性などについて慎重に計画する必要があります。 ExpressRoute を実装するには、次の必要があります。

1. ExpressRoute が 365 の接続計画で満たす必要Office十分に理解します。 インターネットまたは ExpressRoute を使用するアプリケーションを理解し、Office 365 トラフィックに対してインターネットと ExpressRoute の両方を使用するコンテキストで、ネットワーク容量、セキュリティ、高可用性のニーズを完全に計画します。

2. インターネットトラフィックと ExpressRoute トラフィック 1 の両方の出力とピアリングの場所を<sup>決定します</sup>。

3. インターネット接続と ExpressRoute 接続で必要な容量を決定します。

4. セキュリティおよび他の標準境界コントロール 1 を実装するための計画を<sup>立てます</sup>。

5. ExpressRoute をサブスクライブする有効な Microsoft Azure アカウントを持っている。

6. 接続モデルと承認済みプロバイダー [を選択します](/azure/expressroute/expressroute-locations)。 顧客は複数の接続モデルまたはパートナーを選択できます。パートナーは既存のネットワーク プロバイダーと同じである必要はなかっています。

7. ExpressRoute にトラフィックを送信する前に展開を検証します。

8. 必要に応 [じて QoS を実装し](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d) 、地域の拡張を評価します。

<sup>1</sup> 重要なパフォーマンスに関する考慮事項。 ここでの決定は、Skype for Business などのアプリケーションにとって重要な遅延に大きな影響を与える可能性があります。

その他の参照については、ExpressRoute [のドキュメントに加えて](https://support.office.com/article/Routing-with-ExpressRoute-for-Office-365-e1da26c6-2d39-4379-af6f-4da213218408) 、ルーティング ガイド [を使用してください](/azure/expressroute/expressroute-introduction)。

Office 365 用の ExpressRoute を購入するには、1 つ以上の承認済[](/azure/expressroute/expressroute-locations)みプロバイダーと作業して、ExpressRoute Premium サブスクリプションで必要な数とサイズの回線をプロビジョニングする必要があります。 365 から購入する追加のOfficeはありません。

ここに戻る場合は、次のショート リンクをご利用ください: [https://aka.ms/expressrouteoffice365]()

ExpressRoute for Office [365 にサインアップする準備ができましたか](https://aka.ms/ert)?

## <a name="related-topics"></a>関連トピック

[Office 365 のネットワーク接続の評価](assessing-network-connectivity.md)

[Office 365 向け ExpressRoute の管理](managing-expressroute-for-connectivity.md)

[Office 365 向け ExpressRoute でのルーティング](routing-with-expressroute.md)

[Office 365 向け ExpressRoute でのネットワーク計画](network-planning-with-expressroute.md)

[Office 365 向け ExpressRoute の実装](implementing-expressroute.md)

[ExpressRoute での BGP コミュニティの 365 Office使用する](bgp-communities-in-expressroute.md)

[Skype for Business Online でのメディア品質とネットワーク接続のパフォーマンス](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)

[ベースラインとパフォーマンス履歴を使用した、Office 365 のパフォーマンスのチューニング](performance-tuning-using-baselines-and-history.md)

[Office 365 のパフォーマンスに関するトラブルシューティングの計画](performance-troubleshooting-plan.md)

[Office 365 の URL および IP アドレスの範囲](urls-and-ip-address-ranges.md)

[Office 365 のネットワークとパフォーマンスのチューニング](network-planning-and-performance.md)

## <a name="see-also"></a>関連項目

[Microsoft 365 Enterprise の概要](microsoft-365-overview.md)
