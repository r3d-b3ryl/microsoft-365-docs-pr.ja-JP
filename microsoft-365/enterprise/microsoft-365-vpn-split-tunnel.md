---
title: '概要: VPN スプリット トンネリング (Microsoft 365'
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
- m365initiative-coredeploy
f1.keywords:
- NOCSH
description: リモート ユーザーの接続を最適化Microsoft 365 VPN スプリット トンネリングの概要。
ms.openlocfilehash: 67ce8a38b536dab12af679ba860aac6d974db60e
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63329073"
---
# <a name="overview-vpn-split-tunneling-for-microsoft-365"></a>概要: VPN スプリット トンネリング (Microsoft 365

>[!NOTE]
>この記事は、リモート ユーザーの最適化に関するMicrosoft 365の一部です。

>- VPN スプリット トンネリングの実装に関する詳細なガイダンスについては、「VPN スプリット トンネリングの実装」を参照[Microsoft 365。](microsoft-365-vpn-implement-split-tunnel.md)
>- VPN スプリット トンネリングのシナリオの詳細な一覧については、「VPN スプリット トンネリングの一般的なシナリオ」を参照[Microsoft 365。](microsoft-365-vpn-common-scenarios.md)
>- VPN スプリット トンネリング環境でのTeamsメディア トラフィックのセキュリティ保護に関するガイダンスについては、「VPN スプリット トンネリングTeamsメディア トラフィックのセキュリティ[保護」を参照してください](microsoft-365-vpn-securing-teams.md)。
>- VPN 環境で Stream イベントとライブ イベントを構成する方法については、「VPN 環境での Stream イベントとライブ イベントに関する特別な考慮事項」 [を参照してください](microsoft-365-vpn-stream-and-live-events.md)。
>- 中国のユーザーに対するMicrosoft 365のパフォーマンスの最適化の詳細については、「中国のユーザー Microsoft 365[パフォーマンスの最適化」を参照してください](microsoft-365-networking-china.md)。

企業は従来、VPN を使用して、ユーザーの安全なリモート エクスペリエンスをサポートしています。 コア ワークロードはオンプレミスのままですが、リモート クライアントからの VPN は企業ネットワーク上のデータセンターを経由してルーティングされ、リモート ユーザーが企業リソースにアクセスする主な方法でした。 接続を保護するため、企業は VPN パスに沿ってネットワーク セキュリティ ソリューションのレイヤを構築します。 このセキュリティは、内部インフラストラクチャを保護し、VPN にトラフィックをルーティングし、オンプレミスのインターネット境界を経由して外部 Web サイトのモバイル ブラウズを保護するために構築されました。 VPN、ネットワーク境界、および関連するセキュリティ インフラストラクチャは、通常、企業ネットワーク内から開始されるほとんどの接続で、そのほとんどが内部ネットワーク境界内にとどまる、定義されたトラフィック量に対して専用に構築され、スケーリングされました。

長い間、リモート ユーザー デバイスからのすべての接続がオンプレミス ネットワークにルーティングされる VPN モデル (いわゆる _強制トンネリング_) は、リモート ユーザーの同時接続規模を控えめにし、VPN を横断するトラフィック量を少なく済ませる限りは、ほぼ持続可能でした。  一部の顧客は、アプリケーションが企業境界内からパブリック SaaS クラウドに移行した後も、VPN フォース トンネリングを現状として使用し続けました。

分散およびパフォーマンスに敏感なクラウド アプリケーションへの接続に強制トンネリングされた VPN の使用は最適とは言え、一部の企業ではセキュリティの現状を維持するために悪影響が受け入れらされています。 このシナリオの例となる図を次に示します。

![VPN Tunnel強制的に設定します。](../media/vpn-split-tunneling/enterprise-network-traditional.png)

_図 1: 従来の強制的なTunnel VPN ソリューション。_

この問題は何年も前から増加し続け、多くのお客様がネットワーク トラフィック パターンの大幅な変化を報告しています。 オンプレミスに滞在するために使用されたトラフィックは、外部クラウド エンドポイントに接続されます。 多くの Microsoft のお客様は、ネットワーク トラフィックの約 80% が内部ソース (上の図の点線で表される) に送信されたと報告しています。 2020 年には、主要なワークロードをクラウドに移行した後、その数は約 20% 以下に減少しました。 これらの傾向は、他の企業では珍しくありません。 時間が経過するにつれて、クラウドジャーニーが進むにつれて、上記のモデルはますます面倒で持続不可能になり、クラウドファーストの世界に移行するにつれて組織が機敏になるのを防ぐ。

世界的な COVID-19 危機は、この問題を迅速に修復するためにエスカレートしました。 IT 企業には、社員の安全を確保するため、大規模な在宅勤務の生産性を援助しなければいけないというこれまでにない要求が生じています。 Microsoft 365 は、お客様が需要を満たすのに役立つ十分な位置にありますが、自宅で作業するユーザーの同時実行性が高い場合、大量の Microsoft 365 トラフィックが生成され、強制トンネル VPN とオンプレミス ネットワーク境界を経由してルーティングされると、急速な飽和状態が発生し、VPN インフラストラクチャが容量を使い果たします。 この新しい現実では、VPN を使用して Microsoft 365 にアクセスするのはパフォーマンスの障害ではなく、Microsoft 365 に影響を与えるだけでなく、運用するために VPN に依存する必要がある重要なビジネス操作に影響を与えるハードウォールです。

Microsoft は、お客様や幅広い業界と密接に取り組み、独自のサービス内からこれらの問題に対する効果的でモダンなソリューションを提供し、業界のベスト プラクティスに合わせて取り組み続けしてきました。 [](./microsoft-365-network-connectivity-principles.md) Microsoft 365 サービスの接続の原則は、リモート ユーザーが効率的に動作するように設計されている一方で、組織がセキュリティを維持し、接続を制御できるように設計されています。 これらのソリューションは、限られた作業でも迅速に実装することができますが、上記の問題に大きなプラスの影響を及ぼす可能性があります。

リモート ワーカー デバイスを VPN を使用して企業ネットワークまたはクラウド インフラストラクチャに接続する場合は、主要な **Microsoft 365 シナリオ Microsoft Teams**、**SharePoint Online**、および **Exchange Online** を _VPN_ 分割トンネル構成でルーティングする必要があります。 これは、COVID-19 危機などの大規模な在宅作業時の従業員の生産性を高める最初のライン戦略として特に重要になります。

![VPN 構成Tunnel分割します。](../media/vpn-split-tunneling/vpn-model-2.png)

_図 2: サービスに直接送信される例外Microsoft 365定義された VPN スプリット トンネル ソリューション。他のすべてのトラフィックは、宛先に関係なく VPN トンネルを通過します。_

このアプローチの本質は、企業が VPN インフラストラクチャの飽和のリスクを軽減し、可能な限り短い時間枠でMicrosoft 365パフォーマンスを大幅に向上させる簡単な方法を提供することです。 VPN トンネルをバイパスするために最も重要でMicrosoft 365トラフィックを許可する VPN クライアントを構成すると、次のような利点があります。

- エンタープライズ VPN アーキテクチャにおける顧客から報告されたパフォーマンスとネットワーク容量の問題の大部分がユーザー エクスペリエンスに影響を与える根本的な原因を直ちに軽減Microsoft 365軽減します。
  
  推奨されるソリューションは、Microsoft 365 URL と IP アドレス範囲のトピックでオプティマイズMicrosoft 365サービス [エンドポイントを対象とします](./urls-and-ip-address-ranges.md)。 これらのエンドポイントへのトラフィックは、遅延と帯域幅調整に非常に敏感であり、VPN トンネルをバイパスすることで、エンド ユーザー エクスペリエンスが大幅に向上し、企業のネットワーク負荷が軽減されます。 Microsoft 365またはユーザー エクスペリエンスのフットプリントの大部分を構成しない接続は、インターネットにバインドされた残りのトラフィックと共に VPN トンネルを経由して引き続きルーティングできます。 詳細については、「[VPN スプリット トンネル戦略](#the-vpn-split-tunnel-strategy)」を参照してください。

- 顧客が迅速に構成、テスト、実装を行い、追加のインフラストラクチャやアプリケーションの要件が不要

  VPN プラットフォームやネットワーク アーキテクチャによっては、実装に数時間かかる場合があります。 詳細については、「[VPN スプリット トンネリングの実装](microsoft-365-vpn-implement-split-tunnel.md#implement-vpn-split-tunneling)」を参照してください。

- インターネットへのトラフィックを含む他の接続のルーティング方法を変更しないことで、お客様の VPN 実装のセキュリティ体制を維持する

  推奨される構成では、VPN トラフィックの例外に対する **最小限の特権** の原則に従い、ユーザーやインフラストラクチャを追加のセキュリティ リスクにさらすことなく、スプリット トンネル VPN を実装することができます。 Microsoft 365 エンドポイントに直接ルーティングされるネットワーク トラフィックは暗号化され、Office クライアント アプリケーション スタックによって整合性が検証され、アプリケーション レベルとネットワーク レベルの両方で強化される Microsoft 365 サービス専用の IP アドレスにスコープ設定されます。 詳細については、「[セキュリティ専門家と IT による、現代のユニークなリモート ワーク シナリオで最新のセキュリティ管理を実現するための代替的な方法 (Microsoft セキュリティ チーム ブログ)](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)」を参照してください。

- ほとんどのエンタープライズ VPN プラットフォームでネイティブにサポートされている

  Microsoft は引き続き商用 VPN ソリューションを製造している業界のパートナーと協力して、上記の推奨事項に沿ったソリューションのための、ターゲットを絞ったガイダンスや構成テンプレートをパートナーが開発できるように支援していきます。 詳細については、「[一般 VPN プラットフォームのHOWTO ガイド](microsoft-365-vpn-implement-split-tunnel.md#howto-guides-for-common-vpn-platforms)」を参照してください。

>[!TIP]
>Microsoft では、ドキュメント化された専用 IP 範囲に分割トンネル VPN 構成を集中Microsoft 365勧めします。 FQDN または AppID ベースのスプリット トンネル構成は、特定の VPN クライアント プラットフォームでは可能ですが、主要な Microsoft 365 シナリオを完全にカバーしていない可能性があります。IP ベースの VPN ルーティング ルールと競合する可能性があります。 このため、Microsoft では、スプリット トンネル VPN を構成Microsoft 365 FQDN の使用はお勧めしません。 FQDN 構成の使用は、その他の関連するシナリオ (.pac ファイルのカスタマイズやプロキシ バイパスの実装など) に役立つ場合があります。

完全な実装ガイダンスについては、「[VPN](microsoft-365-vpn-implement-split-tunnel.md) スプリット トンネリングを実装する」を参照Microsoft 365。

リモート ワーカー用にユーザー を構成するMicrosoft 365手順については、「リモート作業用にインフラストラクチャをセットアップする」[を参照してください。](..\solutions\empower-people-to-work-remotely.md)

## <a name="the-vpn-split-tunnel-strategy"></a>VPN スプリット トンネリング戦略

従来の社内ネットワークは、大多数のユーザーがそうであるように、ほとんどの重要なデータ、サービス、アプリケーションが構内でホストされ、内部の社内ネットワークに直接接続するという、クラウド以前の環境で安全に動作するように設計されていることが多いです。 したがって、支社は _マルチプロトコル ラベル スイッチング (MPLS)_ ネットワークを介して本社に接続し、オンプレミスのエンドポイントとインターネットの両方にアクセスするリモート ユーザーは、VPN 経由で社内ネットワークに接続する必要があるという要素を中心に、ネットワーク インフラストラクチャが構築されます。 このモデルでは、リモート ユーザーからのすべてのトラフィックが社内ネットワークを通過し、共通の出口ポイントを通ってクラウド サービスにルーティングされます。

![VPN の強制構成。](../media/vpn-split-tunneling/vpn-model-1.png)

_図 2: 接続先に関係なく、すべてのトラフィックを社内ネットワークに強制的に戻すリモート ユーザー用の一般 VPN ソリューション_

組織がデータやアプリケーションをクラウドに移行するに当たって、このモデルは、ユーザーのネットワークパフォーマンスと効率に大きな影響を与え、変化するニーズに対応する組織の能力を制限し、迅速に面倒でコストが高く、スケールできないほど効果的になり始めました。 数年前にネットワーク トラフィックの 80% が内部宛先に送信されたと多くの Microsoft のお客様から報告されているが、2020 年には 80% 以上のトラフィックが外部クラウドベースのリソースに接続している。

新型コロナウイルス感染症の危機により、この問題はさらに悪化し、大多数の組織に即時のソリューションが必要になりました。 この危機で必要とされているような 100% リモート ワークのシナリオには、強制 VPN モデルでは十分なスケーラビリティやパフォーマンスが得られないことに、多くのお客様が気付きました。 これらの組織が効率的に運用を続けるには、迅速なソリューションが必要です。

Microsoft 365 サービスでは、この問題を念頭に置いてサービスの接続要件を設計しました。この点を念頭に置いて、集中型、厳しく制御され、比較的静的な一連のサービス エンドポイントを非常に簡単かつ迅速に最適化して、サービスにアクセスするユーザーに高いパフォーマンスを提供し、VPN インフラストラクチャの負荷を軽減して、それでも必要なトラフィックで使用できます。

Microsoft 365は、最適化、許可、および既定の 3 つの **Microsoft 365に分類****されます**。  **最適化** のエンドポイントはここでの焦点であり、次の特徴があります。

- Microsoft インフラストラクチャにホストされている Microsoft が所有および管理するエンドポイントである
- オンライン、Microsoft 365、Exchange Online、オンライン、SharePointなどのコア Skype for Business専用Microsoft Teams
- IP が提供されている
- 変化率が低く、数も少ないと予想される (現在 20 の IP サブネット)
- 大量のトラフィックや遅延の影響を受けやすい
- 必要なセキュリティ要素をネットワーク上で、インラインではなくサービスで提供することができる
- サービスへのトラフィック量の約 70 ~ 80% をMicrosoft 365します。

この一連のエンドポイントは、強制的な VPN トンネルから分割して、ユーザーのローカル インターフェイスを介して Microsoft 365 サービスに安全かつ直接送信できます。 これは **スプリット トンネリング** と呼ばれます。

DLP、AV 保護、認証、アクセス制御などのセキュリティ要素はすべて、サービス内の異なる層でこれらのエンドポイントに対してはるかに効率的に配信できます。 また、トラフィック ボリュームの大部分を VPN ソリューションから遠く離すので、それでも依存しているビジネス クリティカル なトラフィックの VPN 容量が解放されます。 この新しい動作方法に対処するための、多くの場合長期にわたり費用のかかるアップグレード プログラムを実行する必要もなくなります。

![VPN Tunnel詳細を分割します。](../media/vpn-split-tunneling/vpn-split-tunnel-example.png)

_図 3: サービスに直接送信される例外Microsoft 365定義された VPN スプリット トンネル ソリューション。その他のすべてのトラフィックは、宛先に関係なく企業ネットワークに強制的に戻されます。_

セキュリティの観点では、Microsoft には、オンプレミスのセキュリティ スタックによるインライン検査で提供されるセキュリティと同様の、またはより強化されたセキュリティを提供する機能が豊富に用意されています。 Microsoft セキュリティ チームのブログ投稿「[セキュリティ専門家と IT による、現代のユニークなリモート ワーク シナリオで最新のセキュリティ管理を実現するための代替的な方法](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)」には、利用可能な機能が明確にまとめられていますので、より詳細なガイダンスを確認できます。 また、Microsoft による VPN スプリット トンネリングの実装については、「[VPN で実行: Microsoft がリモート ワークの従業員の接続を維持している方法](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv)」を参照してください。

多くの場合、この実装は数時間のうちに実現できます。本格的なリモート ワークへの移行を急速に進めるにつれ、組織が直面している最も差し迫った問題の 1 つを迅速に解決することができます。 VPN スプリット トンネルの実装のガイダンスについては、「VPN スプリット トンネリングの実装」を参照[Microsoft 365](microsoft-365-vpn-implement-split-tunnel.md)。

## <a name="faq"></a>よくあるご質問 (FAQ)

Microsoft Security Team は、セキュリティ専門家と [IT](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/) 担当者が、今日の独自のリモート作業シナリオ (ブログ投稿) で最新のセキュリティ制御を実現するための代替手段を公開しました。この記事では、セキュリティ専門家の主要な方法の概要と、IT が今日の独自のリモート作業シナリオで最新のセキュリティ制御を実現できます。 さらに、この件に関してお客様からよく寄せられる質問と回答を以下に示します。

### <a name="how-do-i-stop-users-accessing-other-tenants-i-do-not-trust-where-they-could-exfiltrate-data"></a>データを引き出される可能性がある、信頼していない他のテナントにユーザーがアクセスすることを防ぐにはどうすればいいですか？

[「テナントの制限」と呼ばれる機能](/azure/active-directory/manage-apps/tenant-restrictions)が回答になります。 認証トラフィックは、ボリュームが大きく、特に待機時間に敏感ではないので、VPN ソリューションを介して、機能が適用されるオンプレミス プロキシに送信できます。 信頼できるテナントの許可リストはここで管理され、クライアントが信頼されていないテナントにトークンを取得しようとすると、プロキシは要求を拒否します。 信頼されているテナントの場合、ユーザーが適切な資格情報とアクセス権限を持っていると、トークンを取得できます。

したがって、ユーザーは上記の Optimize マークされたエンドポイントに TCP/UDP 接続を行えますが、問題のテナントにアクセスするための有効なトークンがなくても、単にログインしてデータにアクセス/移動することはできません。

### <a name="does-this-model-allow-access-to-consumer-services-such-as-personal-onedrive-accounts"></a>このモデルでは、個人の OneDrive アカウントなど、コンシューマー サービスへのアクセスはできますか？

いいえ、Microsoft 365 エンドポイントはコンシューマー サービス (例として Onedrive.live.com) と同じではないので、スプリット トンネルではユーザーがコンシューマー サービスに直接アクセスすることはできません。 コンシューマー エンドポイントへのトラフィックは引き続き VPN トンネルを使用し、既存のポリシーが引き続き適用されます。

### <a name="how-do-i-apply-dlp-and-protect-my-sensitive-data-when-the-traffic-no-longer-flows-through-my-on-premises-solution"></a>トラフィックがオンプレミスのソリューションを通過しなくなったときに、DLP を適用して機密データを保護するにはどうすればよいですか？

機密情報が偶発的に開示されないようにするために、Microsoft 365 には豊富な組み込みツール [が含まれています](../compliance/information-protection.md)。 Teams と SharePoint の組み込みの [ DLP 機能](../compliance/dlp-learn-about-dlp.md)を使用して、不適切に保存または共有された機密情報を検出できます。 リモート作業戦略の一部に独自デバイス (BYOD) ポリシーが含まれる場合は、アプリベースの条件付きアクセス[](/azure/active-directory/conditional-access/app-based-conditional-access)を使用して、機密データがユーザーの個人デバイスにダウンロードされるのを防ぐ

### <a name="how-do-i-evaluate-and-maintain-control-of-the-users-authentication-when-they-are-connecting-directly"></a>ユーザーが直接接続を行っている時に、ユーザーの認証制御を評価、維持するにはどうすればよいですか？

Q1 に記載されているテナント制限機能に加えて、「[条件付きアクセス ポリシー](/azure/active-directory/conditional-access/overview)」を適用して、認証リクエストのリスクを動的に評価し、適切な対応を行うことができます。 Microsoft では、 [ゼロトラスト](https://www.microsoft.com/security/zero-trust?rtc=1) モデルを時間の間に実装し、Azure AD 条件付きアクセス ポリシーを使用して、モバイルおよびクラウドファーストの世界での制御を維持できます。 条件付きアクセス ポリシーを使用すると、次のようなさまざまな要因に基づいて、認証要求が成功したかどうかをリアルタイムで判断できます。

- デバイス、デバイスは既知/信頼済み/ドメインに参加しているか？
- IP アドレス – 認証要求は既知の企業 IP アドレスからのものか？ または信頼していない場所からのものか？
- アプリケーション – ユーザーはこのアプリケーションの使用を許可されているか？

次に、承認、MFA のトリガー、またはこれらのポリシーに基づく認証のブロックなどのポリシーをトリガーできます。

### <a name="how-do-i-protect-against-viruses-and-malware"></a>ウイルスやマルウェアからの保護はどうすればいいですか？

繰り返しますが、Microsoft 365 は、このドキュメントで概説されている、サービス自体のさまざまなレイヤーで、オプティマイズマーク付きエンドポイントを [保護します](/office365/Enterprise/office-365-malware-and-ransomware-protection)。 上記のように、プロトコル/トラフィックを完全に理解していない可能性のあるデバイスに沿って実行するのではなく、サービス自体にこれらのセキュリティ要素を提供する方が非常に効率的です。 既定では、SharePoint Online は [既知のマルウェアのファイルアップロードを自動的](../security/office-365-security/virus-detection-in-spo.md) にスキャンします

上記の Exchange エンドポイントでは、 [Exchange Online Protection](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) と [Microsoft Defender for Microsoft 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) は、サービスへのトラフィックのセキュリティを提供する優れた仕事をします。

### <a name="can-i-send-more-than-just-the-optimize-traffic-direct"></a>「最適化」トラフィック以外にも直接送信は行えますか？

「**最適化**」マークの付いたエンドポイントが優先されます。これらのエンドポイントは、下位レベルでの作業に最大の利益をもたらすからです。 ただし、必要に応じて、サービスが機能し、必要に応じて使用できる IP アドレスがエンドポイントに提供される場合は、[マークされたエンドポイントを許可する] が必要です。

また、セキュリティ保護された Web ゲートウェイと呼ばれるクラウドベースのプロキシ/セキュリティ ソリューションを提供するさまざまなベンダーがいて、一般的な Web 閲覧用の中央セキュリティ、制御、および企業ポリシー アプリケーションを提供します。 これらのソリューションは、ユーザーに近いクラウドベースの場所から安全なインターネット アクセスを提供することで、高可用性、パフォーマンス、プロビジョニングがユーザーに近い場合、クラウドファーストの世界でうまく機能します。 これにより、一般的な閲覧トラフィック用の VPN/企業ネットワークを介したヘアピンの必要性が取り除かれ、一方で一般的なセキュリティ制御が可能です。

ただし、これらのソリューションが提供されている場合でも、Microsoft 365 のマークが付いたオプティマイズ トラフィックをサービスに直接送信する方法を強く推奨しています。

Azure Virtual Network への直接アクセスを許可する方法については、「 [Azure VPN Gateway Point-to-site](/azure/vpn-gateway/work-remotely-support) を使用したリモート作業」を参照してください。

### <a name="why-is-port-80-required-is-traffic-sent-in-the-clear"></a>なぜポート 80 が必要なのですか？ トラフィックは平文で送信されていますか？

ポート 80 はポート 443 セッションへのリダイレクトなどにのみ使用され、顧客データは送信されないか、ポート 80 経由ではアクセスできません。 [暗号化](../compliance/encryption.md)では、Microsoft 365 の転送中および保存中のデータの暗号化の概要[](/microsoftteams/microsoft-teams-online-call-flows#types-of-traffic)と、SrTP を使用して Teams メディア トラフィックを保護する方法について説明します。

### <a name="does-this-advice-apply-to-users-in-china-using-a-worldwide-instance-of-microsoft-365"></a>このアドバイスは、Microsoft 365 のワールドワイド インスタンスを使用している中国のユーザーに適用されますか?

**いいえ**、されません。  上記のアドバイスの 1 つの注意点は、MICROSOFT 365 のワールドワイド インスタンスに接続している PRC のユーザーです。 この地域ではクロスボーダー ネットワークの混雑が頻繁に発生するため、直接のインターネットの下りのパフォーマンスは変動する可能性があります。 当地域のほとんどのユーザーは、VPN を使用して企業ネットワークにトラフィックを取り込み、許可された MPLS 回線などを利用し、最適化されたパスを介して国外への送信を行っています。 詳しくは、中国ユーザー向け [Microsoft 365 パフォーマンスの最適化に関する記事をご覧ください](microsoft-365-networking-china.md)。

### <a name="does-split-tunnel-configuration-work-for-teams-running-in-a-browser"></a>ブラウザーで実行されている Teams でスプリット トンネル構成が機能しますか?

はい、注意点があります。 ほとんどの Teams 機能は、「Get clients for Microsoft Teams」に記載されているブラウザー [でサポートされています](/microsoftteams/get-clients#web-client)。

さらに、Microsoft Edge **96** 以上では、 [エッジ WebRtcRespectOsRoutingTableEnabled](/deployedge/microsoft-edge-policies#webrtcrespectosroutingtableenabled) ポリシーを有効にすることで、ピアツーピア トラフィックの VPN スプリット トンネリングをサポートしています。 現時点では、他のブラウザーがピアツーピア トラフィックの VPN スプリット トンネリングをサポートしていない場合があります。

## <a name="related-articles"></a>関連記事

[Microsoft 365 の VPN スプリット トンネリングの実装](microsoft-365-vpn-implement-split-tunnel.md)

[Microsoft 365 の一般的な VPN 分割トンネリングシナリオ](microsoft-365-vpn-common-scenarios.md)

[VPN スプリット トンネリングの Teams メディア トラフィックのセキュリティ保護](microsoft-365-vpn-securing-teams.md)

[VPN 環境での Stream イベントとライブ イベントに関する特別な考慮事項](microsoft-365-vpn-stream-and-live-events.md)

[中国ユーザー向け Microsoft 365 パフォーマンスの最適化](microsoft-365-networking-china.md)

[Microsoft 365 ネットワーク接続の原則](microsoft-365-network-connectivity-principles.md)

[Microsoft 365 ネットワーク接続の評価](assessing-network-connectivity.md)

[Microsoft 365 ネットワークとパフォーマンスのチューニング](network-planning-and-performance.md)

[セキュリティ専門家と IT による、現代のユニークなリモート ワーク シナリオで最新のセキュリティ管理を実現するための代替的な方法 (Microsoft セキュリティ チーム ブログ)](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)

[Microsoft での VPN のパフォーマンス強化: Windows 10 の VPN プロファイルを使用して自動接続を許可する](https://www.microsoft.com/itshowcase/enhancing-remote-access-in-windows-10-with-an-automatic-vpn-profile)

[VPN で実行: Microsoft がリモート ワークの従業員をどのように接続させているか](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv)

[Microsoft グローバル ネットワーク](/azure/networking/microsoft-global-network)
