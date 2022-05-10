---
title: '概要: Microsoft 365の VPN 分割トンネリング'
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
description: リモート ユーザーの接続を最適化するためのMicrosoft 365を使用した VPN 分割トンネリングの概要。
ms.openlocfilehash: 67ce8a38b536dab12af679ba860aac6d974db60e
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63329073"
---
# <a name="overview-vpn-split-tunneling-for-microsoft-365"></a>概要: Microsoft 365の VPN 分割トンネリング

>[!NOTE]
>この記事は、リモート ユーザーの最適化Microsoft 365対処する一連の記事の一部です。

>- VPN 分割トンネリングの実装に関する詳細なガイダンスについては、「[Microsoft 365用の VPN 分割トンネリングの実装」を](microsoft-365-vpn-implement-split-tunnel.md)参照してください。
>- VPN 分割トンネリングのシナリオの詳細な一覧については、「[Microsoft 365の一般的な VPN 分割トンネリング シナリオ」を](microsoft-365-vpn-common-scenarios.md)参照してください。
>- VPN 分割トンネリング環境でのTeamsメディア トラフィックのセキュリティ保護に関するガイダンスについては、「VPN 分割トンネリング[のメディア トラフィックTeamsセキュリティ保護](microsoft-365-vpn-securing-teams.md)する」を参照してください。
>- VPN 環境で Stream イベントとライブ イベントを構成する方法については、「VPN 環境での [Stream イベントとライブ イベントに関する特別な考慮事項](microsoft-365-vpn-stream-and-live-events.md)」を参照してください。
>- 中国のユーザーに対Microsoft 365世界規模のテナント パフォーマンスを最適化する方法については、「中国ユーザー[のパフォーマンスの最適化Microsoft 365」を参照してください](microsoft-365-networking-china.md)。

企業は従来、VPN を使用して、ユーザーのセキュリティで保護されたリモート エクスペリエンスをサポートしてきました。 コア ワークロードはオンプレミスのままでしたが、リモート ユーザーが企業リソースにアクセスするための主な方法は、企業ネットワーク上のデータセンターを経由してルーティングされるリモート クライアントからの VPN でした。 接続を保護するため、企業は VPN パスに沿ってネットワーク セキュリティ ソリューションのレイヤを構築します。 このセキュリティは、内部インフラストラクチャを保護し、VPN にトラフィックを再転送し、オンプレミスのインターネット境界を経由して外部 Web サイトのモバイル閲覧を保護するために構築されました。 VPN、ネットワーク境界、および関連するセキュリティ インフラストラクチャは、多くの場合、定義されたトラフィック量に対して目的を持って構築され、スケーリングされていました。通常、ほとんどの接続は企業ネットワーク内から開始され、そのほとんどは内部ネットワーク境界内に留まります。

長い間、リモート ユーザー デバイスからのすべての接続がオンプレミス ネットワークにルーティングされる VPN モデル (いわゆる _強制トンネリング_) は、リモート ユーザーの同時接続規模を控えめにし、VPN を横断するトラフィック量を少なく済ませる限りは、ほぼ持続可能でした。  一部のお客様は、アプリケーションが企業境界内からパブリック SaaS クラウドに移行した後も、VPN 強制トンネリングを現状のまま使用し続けていました。

分散およびパフォーマンスに影響を受けやすいクラウド アプリケーションへの接続に強制トンネリングされた VPN を使用することは最適ではありませんが、セキュリティの現状を維持するために、一部の企業では悪影響が受け入れられていました。 このシナリオの例となる図を次に示します。

![VPN 構成Tunnel強制されます。](../media/vpn-split-tunneling/enterprise-network-traditional.png)

_図 1: 従来の強制Tunnel VPN ソリューション。_

この問題は長年にわたって増加しており、多くのお客様がネットワーク トラフィック パターンの大きな変化を報告しています。 オンプレミスを維持するために使用されたトラフィックが、外部クラウド エンドポイントに接続されるようになりました。 多くの Microsoft のお客様は、以前、ネットワーク トラフィックの約 80% が内部ソースに対して行われたと報告しています (上の図の点線で表されます)。 2020 年には、主要なワークロードをクラウドに移行するにつれて、その数は約 20% 以下に減少しました。 これらの傾向は、他の企業でも一般的ではありません。 時間が経つにつれて、クラウド体験が進むにつれて、上記のモデルはますます煩雑になり、持続不可能になり、クラウドファーストの世界に移行する組織がアジャイルになるのを防ぎます。

世界規模の COVID-19 の危機により、この問題は迅速な修復を必要とするようにエスカレートしました。 IT 企業には、社員の安全を確保するため、大規模な在宅勤務の生産性を援助しなければいけないというこれまでにない要求が生じています。 Microsoft 365は、お客様がその需要を満たすのに役立ちますが、自宅で作業するユーザーのコンカレンシーが高い場合、大量のMicrosoft 365 トラフィックが生成されます。これは、強制トンネル VPN とオンプレミスネットワーク境界を経由する場合、急速な飽和を引き起こし、容量不足の VPN インフラストラクチャを実行します。 この新しい現実では、VPN を使用してMicrosoft 365にアクセスすることは、単なるパフォーマンスの障害ではなく、MICROSOFT 365に影響を与えるだけでなく、VPN に依存して運用する必要がある重要なビジネス操作にも影響を与えるハード ウォールです。

Microsoft は、お客様や広範な業界と緊密に連携し、これらの問題に対して効果的で最新のソリューションを自社のサービス内から提供し、業界のベスト プラクティスに合わせて取り組んでいます。 Microsoft 365 サービスの[接続の原則](./microsoft-365-network-connectivity-principles.md)は、リモート ユーザーに対して効率的に動作する一方で、組織が接続のセキュリティと制御を維持できるように設計されています。 これらのソリューションは、限られた作業で迅速に実装することもできますが、上で説明した問題に大きなプラスの効果を実現できます。

リモート ワーカー デバイスを VPN 経由で企業ネットワークまたはクラウド インフラストラクチャに接続する場合、Microsoft では、**Microsoft Teams、****SharePoint Online、Exchange Online** の主要なMicrosoft 365 **シナリオを** _VPN 分割トンネル_ 構成経由でルーティングすることをお勧めします。 これは、COVID-19 危機などの大規模な在宅勤務イベント中に従業員の生産性を継続的に向上させる最初のライン戦略として特に重要になります。

![VPN 構成Tunnel分割します。](../media/vpn-split-tunneling/vpn-model-2.png)

_図 2: 定義されたMicrosoft 365例外がサービスに直接送信された VPN 分割トンネル ソリューション。その他のすべてのトラフィックは、宛先に関係なく VPN トンネルを通過します。_

このアプローチの本質は、企業が VPN インフラストラクチャの飽和のリスクを軽減し、可能な限り短時間でMicrosoft 365パフォーマンスを大幅に向上させるための簡単な方法を提供することです。 VPN トンネルをバイパスするための最も重要で大量のMicrosoft 365 トラフィックを許可するように VPN クライアントを構成すると、次の利点が得られます。

- エンタープライズ VPN アーキテクチャにおける顧客から報告されたパフォーマンスとネットワーク容量の問題の大部分がユーザー エクスペリエンスに影響を与える根本原因を直ちに軽減Microsoft 365
  
  推奨されるソリューションは、特に、[URL と IP アドレス範囲](./urls-and-ip-address-ranges.md)Microsoft 365トピックで **最適化** として分類Microsoft 365サービス エンドポイントを対象とします。 これらのエンドポイントへのトラフィックは、待機時間と帯域幅の調整に対して非常に機密性が高く、VPN トンネルをバイパスできるようにすることで、エンド ユーザー エクスペリエンスを大幅に向上させ、企業のネットワーク負荷を軽減できます。 帯域幅やユーザー エクスペリエンスのフットプリントの大部分を構成しないMicrosoft 365接続は、インターネットにバインドされた残りのトラフィックと共に VPN トンネル経由で引き続きルーティングできます。 詳細については、「[VPN スプリット トンネル戦略](#the-vpn-split-tunnel-strategy)」を参照してください。

- 追加のインフラストラクチャやアプリケーションの要件なしで、お客様が迅速に構成、テスト、実装できます。

  VPN プラットフォームやネットワーク アーキテクチャによっては、実装に数時間かかる場合があります。 詳細については、「[VPN スプリット トンネリングの実装](microsoft-365-vpn-implement-split-tunnel.md#implement-vpn-split-tunneling)」を参照してください。

- インターネットへのトラフィックを含む他の接続のルーティング方法を変更しないことで、お客様の VPN 実装のセキュリティ体制を維持する

  推奨される構成では、VPN トラフィックの例外に対する **最小限の特権** の原則に従い、ユーザーやインフラストラクチャを追加のセキュリティ リスクにさらすことなく、スプリット トンネル VPN を実装することができます。 Microsoft 365 エンドポイントに直接ルーティングされるネットワーク トラフィックは暗号化され、クライアント アプリケーション スタックをOfficeして整合性が検証され、アプリケーションレベルとネットワーク レベルの両方で強化されるMicrosoft 365 サービス専用の IP アドレスにスコープされます。 詳細については、「[セキュリティ専門家と IT による、現代のユニークなリモート ワーク シナリオで最新のセキュリティ管理を実現するための代替的な方法 (Microsoft セキュリティ チーム ブログ)](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)」を参照してください。

- ほとんどのエンタープライズ VPN プラットフォームでネイティブにサポートされている

  Microsoft は引き続き商用 VPN ソリューションを製造している業界のパートナーと協力して、上記の推奨事項に沿ったソリューションのための、ターゲットを絞ったガイダンスや構成テンプレートをパートナーが開発できるように支援していきます。 詳細については、「[一般 VPN プラットフォームのHOWTO ガイド](microsoft-365-vpn-implement-split-tunnel.md#howto-guides-for-common-vpn-platforms)」を参照してください。

>[!TIP]
>Microsoft では、Microsoft 365 サービス用に文書化された専用 IP 範囲に分割トンネル VPN 構成を集中することをお勧めします。 FQDN または AppID ベースの分割トンネル構成は、特定の VPN クライアント プラットフォームでは可能ですが、主要なMicrosoft 365シナリオを完全にカバーできず、IP ベースの VPN ルーティング規則と競合する可能性があります。 このため、Microsoft 365 FQDN を使用して分割トンネル VPN を構成することはお勧めしません。 FQDN 構成の使用は、その他の関連するシナリオ (.pac ファイルのカスタマイズやプロキシ バイパスの実装など) に役立つ場合があります。

完全な実装ガイダンスについては、「[Microsoft 365用の VPN 分割トンネリングの実装」を](microsoft-365-vpn-implement-split-tunnel.md)参照してください。

リモート ワーカーのMicrosoft 365を構成するためのステップ バイ ステップ プロセスについては、「リモート[作業用のインフラストラクチャを設定する](..\solutions\empower-people-to-work-remotely.md)」を参照してください。

## <a name="the-vpn-split-tunnel-strategy"></a>VPN スプリット トンネリング戦略

従来の社内ネットワークは、大多数のユーザーがそうであるように、ほとんどの重要なデータ、サービス、アプリケーションが構内でホストされ、内部の社内ネットワークに直接接続するという、クラウド以前の環境で安全に動作するように設計されていることが多いです。 したがって、支社は _マルチプロトコル ラベル スイッチング (MPLS)_ ネットワークを介して本社に接続し、オンプレミスのエンドポイントとインターネットの両方にアクセスするリモート ユーザーは、VPN 経由で社内ネットワークに接続する必要があるという要素を中心に、ネットワーク インフラストラクチャが構築されます。 このモデルでは、リモート ユーザーからのすべてのトラフィックが社内ネットワークを通過し、共通の出口ポイントを通ってクラウド サービスにルーティングされます。

![強制 VPN 構成。](../media/vpn-split-tunneling/vpn-model-1.png)

_図 2: 接続先に関係なく、すべてのトラフィックを社内ネットワークに強制的に戻すリモート ユーザー用の一般 VPN ソリューション_

組織がデータとアプリケーションをクラウドに移行するにつれて、このモデルは、すぐに煩雑で高価で、節減し、ユーザーのネットワークパフォーマンスと効率に大きな影響を与え、変化するニーズに適応する組織の能力を制限するにつれて、効果が低下し始めています。 多くの Microsoft のお客様は、数年前にネットワーク トラフィックの 80% が内部宛先に送信されたと報告していますが、2020 年にはトラフィックの 80% と外部のクラウドベースのリソースに接続しています。

新型コロナウイルス感染症の危機により、この問題はさらに悪化し、大多数の組織に即時のソリューションが必要になりました。 この危機で必要とされているような 100% リモート ワークのシナリオには、強制 VPN モデルでは十分なスケーラビリティやパフォーマンスが得られないことに、多くのお客様が気付きました。 これらの組織が効率的に運用を続けるには、迅速なソリューションが必要です。

Microsoft 365 サービスの場合、Microsoft は、この問題を念頭に置いて、サービスにアクセスするユーザーに高いパフォーマンスを提供し、必要なトラフィックで使用できるように VPN インフラストラクチャの負担を軽減するために、集中した厳密に制御された比較的静的なサービス エンドポイントのセットを非常に簡単かつ迅速に最適化できる、サービスの接続要件を正方形に設計しました。

Microsoft 365 Microsoft 365に必要なエンドポイントを **、最適化**、**許可**、既定の 3 つのカテゴリに分類 **します**。 **最適化** のエンドポイントはここでの焦点であり、次の特徴があります。

- Microsoft インフラストラクチャにホストされている Microsoft が所有および管理するエンドポイントである
- Exchange Online、SharePoint Online、Skype for Business Online、Microsoft Teamsなどのコア Microsoft 365 ワークロード専用です
- IP が提供されている
- 変化率が低く、数も少ないと予想される (現在 20 の IP サブネット)
- 大量のトラフィックや遅延の影響を受けやすい
- 必要なセキュリティ要素をネットワーク上で、インラインではなくサービスで提供することができる
- Microsoft 365 サービスへのトラフィック量の約 70 ~ 80% を占める

この厳密にスコープが設定された一連のエンドポイントは、強制 VPN トンネルから分割し、ユーザーのローカル インターフェイスを介してMicrosoft 365 サービスに安全かつ直接送信できます。 これは **スプリット トンネリング** と呼ばれます。

DLP、AV 保護、認証、アクセス制御などのセキュリティ要素はすべて、サービス内のさまざまなレイヤーで、これらのエンドポイントに対してはるかに効率的に配信できます。 また、トラフィック量の大部分を VPN ソリューションから遠ざけるので、それに依存しているビジネス クリティカルなトラフィックの VPN 容量が解放されます。 この新しい動作方法に対処するための、多くの場合長期にわたり費用のかかるアップグレード プログラムを実行する必要もなくなります。

![VPN 構成の詳細Tunnel分割します。](../media/vpn-split-tunneling/vpn-split-tunnel-example.png)

_図 3: 定義されたMicrosoft 365例外がサービスに直接送信された VPN 分割トンネル ソリューション。その他のすべてのトラフィックは、宛先に関係なく企業ネットワークに強制的に戻されます。_

セキュリティの観点では、Microsoft には、オンプレミスのセキュリティ スタックによるインライン検査で提供されるセキュリティと同様の、またはより強化されたセキュリティを提供する機能が豊富に用意されています。 Microsoft セキュリティ チームのブログ投稿「[セキュリティ専門家と IT による、現代のユニークなリモート ワーク シナリオで最新のセキュリティ管理を実現するための代替的な方法](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)」には、利用可能な機能が明確にまとめられていますので、より詳細なガイダンスを確認できます。 また、Microsoft による VPN スプリット トンネリングの実装については、「[VPN で実行: Microsoft がリモート ワークの従業員の接続を維持している方法](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv)」を参照してください。

多くの場合、この実装は数時間のうちに実現できます。本格的なリモート ワークへの移行を急速に進めるにつれ、組織が直面している最も差し迫った問題の 1 つを迅速に解決することができます。 VPN 分割トンネルの実装に関するガイダンスについては、「[Microsoft 365用の VPN 分割トンネリングの実装」を](microsoft-365-vpn-implement-split-tunnel.md)参照してください。

## <a name="faq"></a>よくあるご質問 (FAQ)

Microsoft Security Team は、 [セキュリティプロフェッショナルと IT が、今日の一意のリモート作業シナリオで最新のセキュリティ制御を実現するための代替方法](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/) (ブログ記事) を公開しました。この記事では、セキュリティプロフェッショナルと IT 担当者が現在の一意のリモート作業シナリオで最新のセキュリティ制御を実現するための主要な方法について説明しています。 さらに、この件に関してお客様からよく寄せられる質問と回答を以下に示します。

### <a name="how-do-i-stop-users-accessing-other-tenants-i-do-not-trust-where-they-could-exfiltrate-data"></a>データを引き出される可能性がある、信頼していない他のテナントにユーザーがアクセスすることを防ぐにはどうすればいいですか？

[「テナントの制限」と呼ばれる機能](/azure/active-directory/manage-apps/tenant-restrictions)が回答になります。 認証トラフィックは高ボリュームでも特に待機時間に影響を受けないため、VPN ソリューションを介して、機能が適用されているオンプレミス プロキシに送信できます。 信頼されたテナントの許可リストはここで保持され、クライアントが信頼されていないテナントへのトークンを取得しようとすると、プロキシは要求を拒否するだけです。 信頼されているテナントの場合、ユーザーが適切な資格情報とアクセス権限を持っていると、トークンを取得できます。

そのため、ユーザーは上記の Optimize マークされたエンドポイントに TCP/UDP 接続を行うことができますが、問題のテナントにアクセスするための有効なトークンがなくても、データにログインしてアクセス/移動することはできません。

### <a name="does-this-model-allow-access-to-consumer-services-such-as-personal-onedrive-accounts"></a>このモデルでは、個人の OneDrive アカウントなど、コンシューマー サービスへのアクセスはできますか？

いいえ、Microsoft 365 エンドポイントはコンシューマー サービスと同じではないため (例として Onedrive.live.com)、分割トンネルではユーザーがコンシューマー サービスに直接アクセスすることはできません。 コンシューマー エンドポイントへのトラフィックは引き続き VPN トンネルを使用し、既存のポリシーが引き続き適用されます。

### <a name="how-do-i-apply-dlp-and-protect-my-sensitive-data-when-the-traffic-no-longer-flows-through-my-on-premises-solution"></a>トラフィックがオンプレミスのソリューションを通過しなくなったときに、DLP を適用して機密データを保護するにはどうすればよいですか？

機密情報が誤って漏えいするのを防ぐため、Microsoft 365には豊富なツールセットが[組み込まれています](../compliance/information-protection.md)。 Teams と SharePoint の組み込みの [ DLP 機能](../compliance/dlp-learn-about-dlp.md)を使用して、不適切に保存または共有された機密情報を検出できます。 リモート作業戦略の一部に持ち込みデバイス (BYOD) ポリシーが含まれている場合は、 [アプリベースの条件付きアクセス](/azure/active-directory/conditional-access/app-based-conditional-access) を使用して、機密データがユーザーの個人用デバイスにダウンロードされないようにすることができます

### <a name="how-do-i-evaluate-and-maintain-control-of-the-users-authentication-when-they-are-connecting-directly"></a>ユーザーが直接接続を行っている時に、ユーザーの認証制御を評価、維持するにはどうすればよいですか？

Q1 に記載されているテナント制限機能に加えて、「[条件付きアクセス ポリシー](/azure/active-directory/conditional-access/overview)」を適用して、認証リクエストのリスクを動的に評価し、適切な対応を行うことができます。 Microsoft では[、ゼロ トラスト モデル](https://www.microsoft.com/security/zero-trust?rtc=1)を時間の経過と共に実装することをお勧めします。また、Azure AD条件付きアクセス ポリシーを使用して、モバイルとクラウドファーストの世界で制御を維持できます。 条件付きアクセス ポリシーを使用すると、次のようなさまざまな要因に基づいて、認証要求が成功したかどうかをリアルタイムで判断できます。

- デバイス、デバイスは既知/信頼済み/ドメインに参加しているか？
- IP アドレス – 認証要求は既知の企業 IP アドレスからのものか？ または信頼していない場所からのものか？
- アプリケーション – ユーザーはこのアプリケーションの使用を許可されているか？

次に、承認、MFA のトリガー、またはこれらのポリシーに基づく認証のブロックなどのポリシーをトリガーできます。

### <a name="how-do-i-protect-against-viruses-and-malware"></a>ウイルスやマルウェアからの保護はどうすればいいですか？

ここでも、Microsoft 365は、[このドキュメントで説明する](/office365/Enterprise/office-365-malware-and-ransomware-protection)サービス自体のさまざまなレイヤーで、マークされたエンドポイントを最適化するための保護を提供します。 既に説明したように、これらのセキュリティ要素をサービス自体に提供する方が、プロトコルやトラフィックを完全に理解していない可能性のあるデバイスに沿って行おうとするよりも、非常に効率的です。 既定では、SharePoint Online では、既知のマルウェア[のファイルアップロードが自動的にスキャンされます](../security/office-365-security/virus-detection-in-spo.md)

上記のExchange エンドポイントでは、[Exchange Online Protection](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)と [Microsoft Defender for Microsoft 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)は、サービスへのトラフィックのセキュリティを提供する優れた仕事をします。

### <a name="can-i-send-more-than-just-the-optimize-traffic-direct"></a>「最適化」トラフィック以外にも直接送信は行えますか？

「**最適化**」マークの付いたエンドポイントが優先されます。これらのエンドポイントは、下位レベルでの作業に最大の利益をもたらすからです。 ただし、必要に応じて、サービスを機能させるにはマークされたエンドポイントを許可する必要があり、必要に応じて使用できるエンドポイントに対して IP アドレスが指定されています。

また、セキュリティで _保護された Web ゲートウェイ_ と呼ばれるクラウドベースのプロキシ/セキュリティ ソリューションを提供するさまざまなベンダーも存在し、一般的な Web 閲覧に中央のセキュリティ、制御、および企業ポリシー アプリケーションを提供します。 これらのソリューションは、クラウドファーストの世界では、ユーザーに近いクラウドベースの場所からセキュリティで保護されたインターネット アクセスを提供できるようにすることで、高可用性、パフォーマンス、プロビジョニングがユーザーに近い場合に適切に機能します。 これにより、一般的な閲覧トラフィックに対して VPN/企業ネットワークを介してヘアピンを使用する必要がなくなり、一元的なセキュリティ制御が可能になります。

ただし、これらのソリューションが用意されていても、オプティマイズでマークされたMicrosoft 365トラフィックをサービスに直接送信することを強くお勧めします。

Azure Virtual Networkへの直接アクセスを許可する方法については、「[Azure VPN Gatewayポイント対サイトを使用したリモート作業」を](/azure/vpn-gateway/work-remotely-support)参照してください。

### <a name="why-is-port-80-required-is-traffic-sent-in-the-clear"></a>なぜポート 80 が必要なのですか？ トラフィックは平文で送信されていますか？

ポート 80 はポート 443 セッションへのリダイレクトなどにのみ使用され、顧客データは送信されないか、ポート 80 経由ではアクセスできません。 [暗号化](../compliance/encryption.md)では、転送中のデータとMicrosoft 365の保存時のデータの暗号化の概要が示され、[トラフィックの種類](/microsoftteams/microsoft-teams-online-call-flows#types-of-traffic)では、SRTP を使用してメディア トラフィックTeams保護する方法について説明します。

### <a name="does-this-advice-apply-to-users-in-china-using-a-worldwide-instance-of-microsoft-365"></a>このアドバイスは、Microsoft 365の世界的なインスタンスを使用して中国のユーザーに適用されますか?

**いいえ**、されません。  上記のアドバイスの 1 つの注意点は、MICROSOFT 365の世界的なインスタンスに接続している PRC のユーザーです。 この地域ではクロスボーダー ネットワークの混雑が頻繁に発生するため、直接のインターネットの下りのパフォーマンスは変動する可能性があります。 当地域のほとんどのユーザーは、VPN を使用して企業ネットワークにトラフィックを取り込み、許可された MPLS 回線などを利用し、最適化されたパスを介して国外への送信を行っています。 これについては、[中国ユーザーのパフォーマンスの最適化Microsoft 365](microsoft-365-networking-china.md)記事で詳しく説明しています。

### <a name="does-split-tunnel-configuration-work-for-teams-running-in-a-browser"></a>ブラウザーで実行されているTeamsの分割トンネル構成は機能しますか?

はい。注意が必要です。 ほとんどのTeams機能は、[Microsoft Teamsのクライアントの取得](/microsoftteams/get-clients#web-client)に関するページに記載されているブラウザーでサポートされています。

さらに、Microsoft Edge **96 以降** では、Edge [WebRtcRespectOsRoutingTableEnabled](/deployedge/microsoft-edge-policies#webrtcrespectosroutingtableenabled) ポリシーを有効にすることで、ピアツーピア トラフィックの VPN 分割トンネリングがサポートされています。 現時点では、他のブラウザーでは、ピアツーピア トラフィックの VPN 分割トンネリングがサポートされていない可能性があります。

## <a name="related-articles"></a>関連記事

[Microsoft 365用の VPN 分割トンネリングの実装](microsoft-365-vpn-implement-split-tunnel.md)

[Microsoft 365の一般的な VPN 分割トンネリング シナリオ](microsoft-365-vpn-common-scenarios.md)

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
