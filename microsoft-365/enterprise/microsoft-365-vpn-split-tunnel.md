---
title: '概要: Office 365 の VPN スプリット トンネリング'
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 9/22/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- remotework
- m365initiative-coredeploy
f1.keywords:
- NOCSH
description: Office 365 で VPN スプリット トンネリングを使用して、リモート ユーザーの Office 365 の接続を最適化する方法のガイダンスです。
ms.openlocfilehash: dc9e9fa6b730ac6a98879c692f349b2480d3dcf14320c7817d5d5b14eb6ac825
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53848909"
---
# <a name="optimize-office-365-connectivity-for-remote-users-using-vpn-split-tunneling"></a>VPN スプリット トンネリングを使用してリモート ユーザーの Office 365 の接続を最適化する
<!---
>[!NOTE]
>This topic is part of a set of topics that address Office 365 optimization for remote users.
>- For VPN split tunnel implementation guidance, see [Implementing VPN split tunneling for Office 365](microsoft-365-vpn-implement-split-tunnel.md).
>- For information about optimizing Office 365 worldwide tenant performance for users in China, see [Office 365 performance optimization for China users](microsoft-365-networking-china.md).
-->

リモート ワーカー デバイスを VPN を使用して企業ネットワークまたはクラウド インフラストラクチャに接続する場合は、主要な Office 365 シナリオ **Microsoft Teams、SharePoint** **Online、** および **Exchange Online** を _VPN_ 分割トンネル構成でルーティングする必要があります。 これは、COVID-19 危機などの大規模な在宅作業時の従業員の生産性を高める最初のライン戦略として特に重要になります。

![スプリット トンネル VPN 構成](../media/vpn-split-tunneling/vpn-model-2.png)

_図 1: サービスに直接送信された、定義済み Office 365 例外を使用している VPN スプリット トンネル ソリューション。他のすべてのトラフィックは、接続先に関係なく VPN トンネルを通過します。_

このアプローチの本質は、企業が VPN インフラストラクチャの飽和リスクを軽減し、可能な限り短い時間枠で Office 365 のパフォーマンスを劇的に向上させるためのシンプルな方法を提供することにあります。 VPN クライアントを設定して、最も重要で大量の Office 365 トラフィックが VPN トンネルを迂回できるようにすると、次のようなメリットが得られます。

- Office 365 のユーザー エクスペリエンスに影響を与えるエンタープライズ VPN アーキテクチャにおける、お客様から報告されたパフォーマンスとネットワーク キャパシティの問題の大半の根本的な原因を即座に軽減する
  
  推奨されるソリューションは、トピック「[Office 365 の URL と IP アドレスの範囲](./urls-and-ip-address-ranges.md)」で「**最適化**」として分類されている Office 365 のサービス エンドポイントを特に対象としています。 これらのエンドポイントへのトラフィックは、遅延と帯域幅調整に非常に敏感であり、VPN トンネルをバイパスすることで、エンド ユーザー エクスペリエンスが大幅に向上し、企業のネットワーク負荷が軽減されます。 帯域幅やユーザー エクスペリエンスのフットプリントの大部分を構成していない Office 365 接続は、残りのインターネット経由のトラフィックと一緒に VPN トンネルを経由し続けることができます。 詳細については、「[VPN スプリット トンネル戦略](#the-vpn-split-tunnel-strategy)」を参照してください。

- 顧客が迅速に構成、テスト、実装を行い、追加のインフラストラクチャやアプリケーションの要件が不要

  VPN プラットフォームやネットワーク アーキテクチャによっては、実装に数時間かかる場合があります。 詳細については、「[VPN スプリット トンネリングの実装](microsoft-365-vpn-implement-split-tunnel.md#implement-vpn-split-tunneling)」を参照してください。

- インターネットへのトラフィックを含む他の接続のルーティング方法を変更しないことで、お客様の VPN 実装のセキュリティ体制を維持する

  推奨される構成では、VPN トラフィックの例外に対する **最小限の特権** の原則に従い、ユーザーやインフラストラクチャを追加のセキュリティ リスクにさらすことなく、スプリット トンネル VPN を実装することができます。 Office 365 エンドポイントに直接ルーティングされるネットワーク トラフィックは暗号化され、Office クライアント アプリケーション スタックによって整合性が検証され、アプリケーション レベルとネットワーク レベルの両方で強化される Office 365 サービス専用の IP アドレスにスコープが設定されます。 詳細については、「[セキュリティ専門家と IT による、現代のユニークなリモート ワーク シナリオで最新のセキュリティ管理を実現するための代替的な方法 (Microsoft セキュリティ チーム ブログ)](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)」を参照してください。

- ほとんどのエンタープライズ VPN プラットフォームでネイティブにサポートされている

  Microsoft は引き続き商用 VPN ソリューションを製造している業界のパートナーと協力して、上記の推奨事項に沿ったソリューションのための、ターゲットを絞ったガイダンスや構成テンプレートをパートナーが開発できるように支援していきます。 詳細については、「[一般 VPN プラットフォームのHOWTO ガイド](microsoft-365-vpn-implement-split-tunnel.md#howto-guides-for-common-vpn-platforms)」を参照してください。

>[!TIP]
>Office 365 サービス用の文書化された専用 IP 範囲には、スプリット トンネル VPN 構成を集中させることをお勧めします。 特定の VPN クライアント プラットフォームで使用できる FQDN または AppID ベースのスプリット トンネル構成は、Office 365 の主要なシナリオを完全にカバーしていない可能性があります。また、IP ベースの VPN ルーティング ルールと競合する場合があります。 このため、スプリット トンネル VPN の構成に Office 365 FQDN を使用することはお勧めしません。 FQDN 構成の使用は、その他の関連するシナリオ (.pac ファイルのカスタマイズやプロキシ バイパスの実装など) に役立つ場合があります。

完全な実装の詳細については、「[Office 365 向け VPN スプリット トンネリングの実装](microsoft-365-vpn-implement-split-tunnel.md)」を参照してください。

リモート ワーカー用にユーザー を構成するMicrosoft 365手順については、「リモート作業用にインフラストラクチャを[セットアップする」を参照してください。](..\solutions\empower-people-to-work-remotely.md)

## <a name="the-vpn-split-tunnel-strategy"></a>VPN スプリット トンネリング戦略

従来の社内ネットワークは、大多数のユーザーがそうであるように、ほとんどの重要なデータ、サービス、アプリケーションが構内でホストされ、内部の社内ネットワークに直接接続するという、クラウド以前の環境で安全に動作するように設計されていることが多いです。 したがって、支社は _マルチプロトコル ラベル スイッチング (MPLS)_ ネットワークを介して本社に接続し、オンプレミスのエンドポイントとインターネットの両方にアクセスするリモート ユーザーは、VPN 経由で社内ネットワークに接続する必要があるという要素を中心に、ネットワーク インフラストラクチャが構築されます。 このモデルでは、リモート ユーザーからのすべてのトラフィックが社内ネットワークを通過し、共通の出口ポイントを通ってクラウド サービスにルーティングされます。

![強制 VPN 構成](../media/vpn-split-tunneling/vpn-model-1.png)

_図 2: 接続先に関係なく、すべてのトラフィックを社内ネットワークに強制的に戻すリモート ユーザー用の一般 VPN ソリューション_

組織がデータやアプリケーションをクラウドに移行するに当たって、このモデルは、ユーザーのネットワークパフォーマンスと効率に大きな影響を与え、変化するニーズに対応する組織の能力を制限し、迅速に面倒でコストが高く、スケールできないほど効果的になり始めました。 数年前にネットワーク トラフィックの 80% が内部宛先に送信されたと多くの Microsoft のお客様から報告されているが、2020 年には 80% 以上のトラフィックが外部クラウドベースのリソースに接続している。

新型コロナウイルス感染症の危機により、この問題はさらに悪化し、大多数の組織に即時のソリューションが必要になりました。 この危機で必要とされているような 100% リモート ワークのシナリオには、強制 VPN モデルでは十分なスケーラビリティやパフォーマンスが得られないことに、多くのお客様が気付きました。 これらの組織が効率的に運用を続けるには、迅速なソリューションが必要です。

Office 365 サービスでは、この問題を念頭に置いてサービスの接続要件を設計しました。この点を念頭に置いて、集中型、厳しく制御され、比較的静的な一連のサービス エンドポイントを非常に簡単かつ迅速に最適化して、サービスにアクセスするユーザーに高いパフォーマンスを提供し、VPN インフラストラクチャの負荷を軽減して、それでも必要なトラフィックで使用できます。

Office 365 では、Office 365 に必要なエンドポイントは 3 つのカテゴリ (**最適化**、**許可**、**既定**) に分類されています。 **最適化** のエンドポイントはここでの焦点であり、次の特徴があります。

- Microsoft インフラストラクチャにホストされている Microsoft が所有および管理するエンドポイントである
- Exchange Online、SharePoint Online、Skype for Business Online、Microsoft Teams など、Office 365 のコア ワークロード専用
- IP が提供されている
- 変化率が低く、数も少ないと予想される (現在 20 の IP サブネット)
- 大量のトラフィックや遅延の影響を受けやすい
- 必要なセキュリティ要素をネットワーク上で、インラインではなくサービスで提供することができる
- Office 365 サービスへのトラフィック量の約 70 - 80% を対象としたアカウント

このように範囲が厳密なエンドポイントは強制 VPN トンネルから切り離すことができ、ユーザーのローカル インターフェイスを介して、Office 365 サービスに安全に送信されます。 これは **スプリット トンネリング** と呼ばれます。

DLP、AV 保護、認証、アクセス制御などのセキュリティ要素はすべて、サービス内の異なる層でこれらのエンドポイントに対してはるかに効率的に配信できます。 また、トラフィック ボリュームの大部分を VPN ソリューションから遠く離すので、それでも依存しているビジネス クリティカル なトラフィックの VPN 容量が解放されます。 この新しい動作方法に対処するための、多くの場合長期にわたり費用のかかるアップグレード プログラムを実行する必要もなくなります。

![VPN Tunnel詳細の分割](../media/vpn-split-tunneling/vpn-split-tunnel-example.png)

_図 3: サービスに直接送信された、定義済み Office 365 例外を使用している VPN スプリット トンネル ソリューション。他のすべてのトラフィックは、接続先に関係なく社内ネットワークに強制的に戻されます。_

セキュリティの観点では、Microsoft には、オンプレミスのセキュリティ スタックによるインライン検査で提供されるセキュリティと同様の、またはより強化されたセキュリティを提供する機能が豊富に用意されています。 Microsoft セキュリティ チームのブログ投稿「[セキュリティ専門家と IT による、現代のユニークなリモート ワーク シナリオで最新のセキュリティ管理を実現するための代替的な方法](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)」には、利用可能な機能が明確にまとめられていますので、より詳細なガイダンスを確認できます。 また、Microsoft による VPN スプリット トンネリングの実装については、「[VPN で実行: Microsoft がリモート ワークの従業員の接続を維持している方法](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv)」を参照してください。

多くの場合、この実装は数時間のうちに実現できます。本格的なリモート ワークへの移行を急速に進めるにつれ、組織が直面している最も差し迫った問題の 1 つを迅速に解決することができます。 VPN スプリット トンネルの実装については、「[Office 365 向け VPN スプリット トンネリングの実装](microsoft-365-vpn-implement-split-tunnel.md)」を参照してください。

## <a name="related-topics"></a>関連項目

[Office 365 向け VPN スプリット トンネリングの実装](microsoft-365-vpn-implement-split-tunnel.md)

[中国ユーザー向けの Office 365 パフォーマンスの最適化](microsoft-365-networking-china.md)

[セキュリティ専門家と IT による、現代のユニークなリモート ワーク シナリオで最新のセキュリティ管理を実現するための代替的な方法 (Microsoft セキュリティ チーム ブログ)](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)

[Microsoft での VPN のパフォーマンス強化: Windows 10 の VPN プロファイルを使用して自動接続を許可する](https://www.microsoft.com/itshowcase/enhancing-remote-access-in-windows-10-with-an-automatic-vpn-profile)

[VPN で実行: Microsoft がリモート ワークの従業員をどのように接続させているか](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv)

[Office 365 ネットワーク接続の原則](microsoft-365-network-connectivity-principles.md)

[Office 365 のネットワーク接続の評価](assessing-network-connectivity.md)

[Microsoft 365 の接続テスト](https://aka.ms/netonboard)