---
title: Office 365 向け Azure ExpressRoute
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 6/5/2019
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
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
description: Office 365で Azure ExpressRoute を使用し、ネットワーク実装プロジェクトをデプロイする場合は計画する方法について説明します。
ms.openlocfilehash: 1350bf73fdddd2141a2df1cbcec5edebeacf7ad4
ms.sourcegitcommit: 6a981ca15bac84adbbed67341c89235029aad476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2022
ms.locfileid: "65754292"
---
# <a name="azure-expressroute-for-office-365"></a>Office 365 向け Azure ExpressRoute

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Office 365で Azure ExpressRoute を使用する方法と、Office 365で使用するために Azure ExpressRoute をデプロイする場合に必要なネットワーク実装プロジェクトを計画する方法について説明します。 Azure で実行されているインフラストラクチャとプラットフォーム サービスは、多くの場合、ネットワーク アーキテクチャとパフォーマンスに関する考慮事項に対処することでメリットを得られます。 このような場合は、Azure 用の ExpressRoute をお勧めします。 Office 365や Dynamics 365 などのサービスとしてのソフトウェアは、インターネット経由で安全かつ確実にアクセスできるように構築されています。 インターネットのパフォーマンスとセキュリティについて、また、Office 365に対して Azure ExpressRoute を検討する場合については、「[ネットワーク接続の評価Office 365」を参照](assessing-network-connectivity.md)してください。

> [!NOTE]
> Microsoft Defender for Endpointでは、Azure ExpressRoute との統合は提供されません。 これにより、プライベート ネットワークからクラウド サービスMicrosoft Defender for Endpointへの接続を可能にする ExpressRoute ルールの定義はお客様が停止することはありませんが、サービスまたはクラウド インフラストラクチャの進化に合わせてルールを維持するのはお客様次第です。

> [!NOTE]
> ほとんどの状況でサービスに最適な接続モデルが提供されないため、Microsoft 365には ExpressRoute はお勧めしません。 そのため、この接続モデルをMicrosoft 365に使用するには、Microsoft の承認が必要です。 お客様のすべての要求を確認し、ExpressRoute が必要なまれなシナリオでのみMicrosoft 365を承認します。 詳細については[、expressRoute for Microsoft 365 ガイド](https://aka.ms/erguide)を参照してください。また、生産性、ネットワーク、セキュリティ チームを含むドキュメントの包括的なレビューに従って、Microsoft アカウント チームと協力して、必要に応じて例外を送信してください。 Office 365のルート フィルターを作成しようとしている未承認のサブスクリプションには[、エラー メッセージが表示](https://support.microsoft.com/kb/3181709)されます。

## <a name="planning-azure-expressroute-for-office-365"></a>Office 365用の Azure ExpressRoute の計画

インターネット接続に加えて、Microsoft ネットワーク コンポーネントの予測可能性と 99.95% アップタイム SLA を提供する直接接続経由で、Office 365ネットワーク トラフィックのサブセットをルーティングすることもできます。 Azure ExpressRoute では、Office 365およびその他の Microsoft クラウド サービスへのこの専用ネットワーク接続が提供されます。

既存の MPLS WAN があるかどうかに関係なく、ExpressRoute は 3 つの方法のいずれかでネットワーク アーキテクチャに追加できます。サポートされているクラウド交換共同場所プロバイダー、イーサネット ポイント対ポイント接続プロバイダー、または MPLS 接続プロバイダーを介して。 [リージョンで使用できるプロバイダーを](/azure/expressroute/expressroute-locations)確認します。 ExpressRoute 直接接続を使用すると、以下に示すサービスOffice 365説明されているアプリケーションへの接続[が](azure-expressroute.md#BKMK_WhatDoIGet)可能になります。 他のすべてのアプリケーションとサービスのネットワーク トラフィックは、引き続きインターネットを通過します。

Office 365、Windows Update、TechNet など、すべての Microsoft アプリケーションにアクセスするために、インターネット経由で Microsoft のデータセンターに接続する一般的なOffice 365顧客を示す、次の高レベルのネットワーク図を検討してください。 お客様は、オンプレミス ネットワークから接続しているか、独立したインターネット接続から接続しているかに関係なく、同様のネットワーク パスを使用します。

![ネットワーク接続をOffice 365します。](../media/9d8bc622-4a38-4a3b-a0f3-68657712d460.png)

次に、更新された図を見てみましょう。これは、インターネットと ExpressRoute の両方を使用してOffice 365に接続するOffice 365顧客を示しています。 パブリック DNS ノードやコンテンツ配信ネットワーク ノードなどの一部の接続では、パブリック インターネット接続が引き続き必要であることに注意してください。 また、ExpressRoute 接続されている建物にいない顧客のユーザーがインターネット経由で接続されていることにも注意してください。

![ExpressRoute との接続をOffice 365します。](../media/251788c4-0937-4584-9b2c-df08e11611fc.png)

さらに詳しい情報が必要ですか? [Azure ExpressRoute for Office 365でネットワーク トラフィックを管理](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408)する方法と、Office 365[用に Azure ExpressRoute を構成](/azure/expressroute/expressroute-faqs)する方法について説明します。 また、10 部の [Azure ExpressRoute for Office 365 Training](https://channel9.msdn.com/series/aer) シリーズをチャネル 9 に記録し、概念をより詳しく説明しました。

## <a name="what-office-365-services-are-included"></a>どのようなOffice 365サービスが含まれていますか?
<a name="BKMK_WhatDoIGet"> </a>

次の表に、ExpressRoute でサポートされているOffice 365 サービスを示します。 これらのアプリケーションに対してどのネットワーク要求にインターネット接続が必要かを理解するには、[Office 365 エンドポイント](./urls-and-ip-address-ranges.md)に関する記事を参照してください。

| 含まれるアプリケーション |
|:-----|
|Exchange Online <sup>1</sup> <br/> Exchange Online Protection <sup>1</sup> <br/> Delve <sup>1</sup> <br/> |
|Skype for Business Online<sup>1</sup> <br/> Microsoft Teams <sup>1</sup> <br/> |
|SharePoint Online<sup>1</sup> <br/> OneDrive for Business <sup>1</sup> <br/> Project Online <sup>1</sup> <br/> |
|ポータルと共有<sup>1</sup> <br/> Azure Active Directory (Azure AD) <sup>1</sup> <br/> Azure AD Connect <sup>1</sup> <br/> Office <sup>1</sup> <br/> |

<sup>1</sup> これらの各アプリケーションには、ExpressRoute ではサポートされていないインターネット接続要件があります。詳細については、[Office 365 エンドポイントに関する記事](./urls-and-ip-address-ranges.md)を参照してください。

expressRoute for Office 365に含まれていないサービスは、Microsoft 365 Apps for enterpriseクライアントダウンロード、オンプレミス ID プロバイダー サインイン、および中国の Office 365 (21 Vianet によって運営) サービスです。

## <a name="implementing-expressroute-for-office-365"></a>Office 365 向け ExpressRoute の実装

ExpressRoute を実装するには、ネットワークとアプリケーションの所有者が関与する必要があり、新しい [ネットワーク ルーティング アーキテクチャ](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408)、帯域幅要件、セキュリティが実装される場所、高可用性などを決定するための慎重な計画が必要です。 ExpressRoute を実装するには、次の操作を行う必要があります。

1. expressRoute がOffice 365接続計画で満たす必要性を完全に理解します。 インターネットまたは ExpressRoute を使用するアプリケーションを理解し、トラフィックをOffice 365するためにインターネットと ExpressRoute の両方を使用するコンテキストで、ネットワーク容量、セキュリティ、および高可用性のニーズを完全に計画します。

2. インターネットトラフィックと ExpressRoute トラフィック 1 の両方のエグレスとピアリングの場所を決定<sup>します</sup>。

3. インターネット接続と ExpressRoute 接続で必要な容量を決定します。

4. セキュリティとその他の標準境界制御<sup>1</sup> を実装するための計画を立てる。

5. ExpressRoute をサブスクライブするための有効なMicrosoft Azure アカウントを持っています。

6. 接続モデルと [承認済みプロバイダー](/azure/expressroute/expressroute-locations)を選択します。 顧客は複数の接続モデルまたはパートナーを選択でき、パートナーは既存のネットワーク プロバイダーと同じである必要はありません。

7. ExpressRoute にトラフィックを転送する前にデプロイを検証します。

8. 必要に応じて [QoS を実装](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d) し、地域の拡大を評価します。

<sup>1</sup> パフォーマンスに関する重要な考慮事項。 ここでの決定は待機時間に大きな影響を与える可能性があります。これは、Skype for Businessなどのアプリケーションにとって非常に重要です。

その他の参照については、[ExpressRoute のドキュメント](/azure/expressroute/expressroute-introduction)に加えて[、ルーティング ガイド](https://support.office.com/article/Routing-with-ExpressRoute-for-Office-365-e1da26c6-2d39-4379-af6f-4da213218408)を使用してください。

Office 365用に ExpressRoute を購入するには、1 つ以上の[承認済みプロバイダー](/azure/expressroute/expressroute-locations)と連携して、ExpressRoute プレミアム サブスクリプションで目的の番号とサイズの回線をプロビジョニングする必要があります。 Office 365から購入する追加のライセンスはありません。

ここに戻る場合は、次のショート リンクをご利用ください: [https://aka.ms/expressrouteoffice365]()

[expressRoute for Office 365](https://aka.ms/ert) にサインアップする準備はできましたか?

## <a name="related-topics"></a>関連項目

[Office 365 ネットワーク接続の評価](assessing-network-connectivity.md)

[Office 365 向け ExpressRoute の管理](managing-expressroute-for-connectivity.md)

[Office 365 向け ExpressRoute でのルーティング](routing-with-expressroute.md)

[Office 365 向け ExpressRoute でのネットワーク計画](network-planning-with-expressroute.md)

[Office 365 向け ExpressRoute の実装](implementing-expressroute.md)

[Office 365シナリオでの ExpressRoute での BGP コミュニティの使用](bgp-communities-in-expressroute.md)

[Skype for Business Online でのメディア品質とネットワーク接続のパフォーマンス](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)

[ベースラインとパフォーマンス履歴を使用した、Office 365 のパフォーマンスのチューニング](performance-tuning-using-baselines-and-history.md)

[Office 365 のパフォーマンスに関するトラブルシューティングの計画](performance-troubleshooting-plan.md)

[Office 365 の URL および IP アドレスの範囲](urls-and-ip-address-ranges.md)

[Office 365 のネットワークとパフォーマンスのチューニング](network-planning-and-performance.md)

## <a name="see-also"></a>関連項目

[Microsoft 365 Enterprise の概要](microsoft-365-overview.md)
