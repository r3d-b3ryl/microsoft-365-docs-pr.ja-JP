---
title: Microsoft 365 サービスの IPv6 サポート
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 06/02/2022
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: c08786fb-298e-437c-8222-dab7625fc815
description: '概要: Microsoft 365 コンポーネントと Microsoft 365 政府機関向けサービスでの IPv6 サポートについて説明します。'
ms.openlocfilehash: 2619567e8dac6f4b87cba0108bcf105011c4a87c
ms.sourcegitcommit: 35f167725bec5fd4fe131781a53d96b060cf232d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/03/2022
ms.locfileid: "65872744"
---
# <a name="ipv6-support-in-microsoft-365-services"></a>Microsoft 365 サービスの IPv6 サポート

エンタープライズ ネットワーク、サービス プロバイダー、デバイス全体での IPv6 の導入とサポートの拡大に伴い、多くのお客様は、ユーザーが IPv6 クライアントと IPv6 ネットワークからMicrosoft 365サービスに引き続きアクセスできるかどうかを疑問に思っています。 Microsoft 365サービスは、IPv6 デュアル スタックと IPv6 専用デバイスの両方から正常に使用できます。 実際、IPv6 の導入拡大に向けて動いているお客様は、コンシューマーから大企業まで増えています。 ほとんどのお客様にとって、IPv4 はデジタル環境から完全に消えることはありません。そのため、IPv6 を必要としたり、Microsoft 365機能やサービスで IPv4 の優先順位を解除したりする予定はありません。

Microsoft 365に関する重要な優先事項の 1 つは、あらゆる場所から、あらゆるデバイスからインターネット経由でシームレスな顧客とユーザー エクスペリエンスを確保することです。 これには、デュアル スタック構成で IPv6 を使用しているお客様のデバイスからのMicrosoft 365へのアクセスと、IPv6 のみのクライアント展開への移行が含まれます。 ほとんどの場合、[ネットワーク接続の原則](microsoft-365-network-connectivity-principles.md)、Microsoft 365 [URL と IP アドレス範囲](urls-and-ip-address-ranges.md)、Microsoft 365ネットワーク[計画のベスト プラクティス](network-and-migration-planning.md#best-practices-for-network-planning-and-improving-migration-performance-for-office-365)Microsoft 365説明されているように、Microsoft 365に接続する標準的なインターネット ベースのモデルに従うときでは、IPv6 の切り替えがユーザー エクスペリエンスに影響を受けることはありません。

多くのMicrosoft 365 サービスは、現在ネイティブの IPv6 サポートを既に提供しており、IPv6 デュアル スタックと IPv6 専用クライアントから直接アクセスできます。 Microsoft 365では、従来の IPv6 から IPv4 への変換テクノロジ (ベース 64 プロキシや DNS64/NAT64 など) へのアクセスも許可されます。これは、お客様やネットワーク ソリューション プロバイダーが IPv4 インターネット リソースに接続するために一般的に使用されます。

SaaS サービスとインターネット全体と同様に、ネイティブ IPv6 対応のMicrosoft 365 インターフェイス、機能、API の範囲は、顧客の直接の操作や制御なしで継続的に拡大します。 Microsoft 365とインターネットへのアクセスが必要なネットワーク上で IPv6 または IPv6 専用サービスを実行している場合は、DNS64/NAT64 などの動的 IPv6/IPv4 遷移メカニズムを含めて、ネットワークの再構成を行わずに、Microsoft 365へのエンドツーエンドの IPv6 接続を確保することをお勧めします。

ほとんどのMicrosoft 365 サービスは、エンド ユーザーと IT 管理者に対して完全に透過的に IPv6 機能を使用して有効になっているか、有効になります。 一部のMicrosoft 365シナリオ (匿名受信電子メールなど) には、IPv6 と組み合わせて使用するための特別な要件と考慮事項があります。 シナリオ固有の IPv6 の要件と考慮事項の詳細については、Microsoft アカウント チームまたは Microsoft サポートにお問い合わせください。

ここに戻る場合は、次のショート リンクをご利用ください: [https://aka.ms/o365ip6](https://aka.ms/o365ip6)

## <a name="see-also"></a>関連項目

[Microsoft 365 ネットワーク接続の概要](microsoft-365-networking-overview.md)

[Office 365 エンドポイントの管理](managing-office-365-endpoints.md)

[Office 365 の URL および IP アドレスの範囲](urls-and-ip-address-ranges.md)

[Office 365 IP アドレスと URL の Web サービス ](microsoft-365-ip-web-service.md)

[Microsoft 365 ネットワーク接続の評価](assessing-network-connectivity.md)

[Microsoft 365 のネットワーク計画とパフォーマンス チューニング](network-planning-and-performance.md)

[ベースラインとパフォーマンス履歴を使用した、Office 365 のパフォーマンスのチューニング](performance-tuning-using-baselines-and-history.md)

[Office 365 のパフォーマンスに関するトラブルシューティングの計画](performance-troubleshooting-plan.md)

[Content Delivery Network](content-delivery-networks.md)

[Microsoft 365 の接続テスト](https://aka.ms/netonboard)

[Microsoft がそのファースト・信頼性の高いグローバルネットワークを構築する方法](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/)

[Office 365 ネットワークのしくみ](https://techcommunity.microsoft.com/t5/Office-365-Networking/bd-p/Office365Networking)
