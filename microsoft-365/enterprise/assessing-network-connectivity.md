---
title: Microsoft 365 ネットワーク接続の評価
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/23/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 64b420ef-0218-48f6-8a34-74bb27633b10
description: Microsoft 365は、世界中のお客様がインターネット接続を使用してサービスに接続できるよう設計されています。 サービスが進化するにつれて、Microsoft 365 のセキュリティ、パフォーマンス、および信頼性は、インターネットを使用してサービスへの接続を確立する顧客に基づいて向上します。
ms.openlocfilehash: 4d80bdf5642b2456ac8293291c720429f7f18fb1
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59213894"
---
# <a name="assessing-microsoft-365-network-connectivity"></a>Microsoft 365 ネットワーク接続の評価

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Microsoft 365は、世界中のお客様がインターネット接続を使用してサービスに接続できるよう設計されています。 サービスが進化するにつれて、Microsoft 365 のセキュリティ、パフォーマンス、および信頼性は、インターネットを使用してサービスへの接続を確立する顧客に基づいて向上します。
  
既存のインターネット接続Microsoft 365を展開プロジェクトの一部として評価する必要があります。 エンタープライズ クラスの展開では、信頼性が高く、適切なサイズのインターネット接続が、ユーザーの機能とシナリオを使用Microsoft 365重要な部分です。
  
ネットワーク評価は、サイズや好みに応じて、さまざまなユーザーや組織によって実行できます。 評価のネットワーク スコープは、展開プロセスの場所によっても異なります。 ネットワーク評価の実行に必要な情報をより深く理解するために、利用可能なオプションを理解するためのネットワーク評価ガイドを作成しました。 この評価では、展開プロジェクトに追加する必要がある手順とリソースを決定し、この手順を正常に採用Microsoft 365。
  
包括的なネットワーク評価は、ネットワーク設計の課題に対する可能な解決策と実装の詳細を提供します。 一部のネットワーク評価では、Microsoft 365 への最適なネットワーク接続が、既存のネットワークおよびインターネット出力インフラストラクチャに対するマイナーな構成または設計変更に対応できると示されます。

一部の評価では、ネットワーク コンポーネントへのネットワークMicrosoft 365追加の投資が必要な場合があります。 たとえば、ブランチ オフィスと複数の地理的地域にまたがるエンタープライズ ネットワークでは、SD-WAN ソリューションへの投資や、ネットワークへのインターネット接続をサポートするための最適化されたルーティング インフラストラクチャが必要Microsoft 365。 場合によっては、評価は、オンライン メディア品質などのシナリオMicrosoft 365規制やパフォーマンス要件の影響を受けるネットワーク接続を示Skype for Business[場合があります](https://support.office.com/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)。 これらの追加の要件は、インターネット接続インフラストラクチャ、ルーティングの最適化、および専用の直接接続への投資につながる可能性があります。

ネットワークの評価に役立ついくつかのリソース:

- ネットワーク[Microsoft 365に関する](microsoft-365-networking-overview.md)概念的な情報については、「ネットワーク接続の概要」をMicrosoft 365してください。
- トラフィック[Microsoft 365を](./microsoft-365-network-connectivity-principles.md)安全に管理し、可能な限り最高のパフォーマンスを得るMicrosoft 365の原則を理解するには、「ネットワーク接続の原則」を参照してください。
- 計画、設計、展開[FastTrack](https://www.microsoft.com/fasttrack)ガイド付きサポートを受Microsoft 365 Microsoft Microsoft 365サインアップします。 
- 以下の[Microsoft 365 接続](assessing-network-connectivity.md#the-microsoft-365-connectivity-test)テスト セクションを参照して、特定のユーザーの場所とユーザー間で行えるネットワーク接続の改善に関する具体的なガイダンスを提供する基本的な接続テストを実行Microsoft 365。

> [!NOTE]
> Microsoft の承認は、ExpressRoute を使用してユーザーにOffice 365。 Microsoft は、すべての顧客要求を確認し、お客様の規制要件が直接接続をOffice 365場合にのみ、ExpressRoute の使用を承認します。 そのような要件がある場合は、Microsoft のレビューを開始するために[ExpressRoute](https://aka.ms/O365ERReview) for Office 365 要求フォームで直接接続が必要と解釈される規制へのテキスト抜粋と Web リンクを提供してください。 未承認のサブスクリプションがルート フィルターを作成しようとOffice 365エラー メッセージが[表示されます](https://support.microsoft.com/kb/3181709)。
  
ネットワーク評価を計画する際に考慮すべき重要なMicrosoft 365。
  
- Microsoft 365は、パブリック インターネット上で実行される、セキュリティで保護された、信頼性の高い、高性能なサービスです。 サービスのこれらの側面を強化するために引き続き投資を行っています。 すべてのMicrosoft 365サービスは、インターネット接続経由で利用できます。

- インターネット ベースの接続の可用性、グローバルリーチMicrosoft 365パフォーマンスなど、ユーザーの主要な側面を継続的に最適化しています。 たとえば、多くのMicrosoft 365は、インターネットに接続するエッジ ノードの拡張セットを利用します。 このエッジ ネットワークは、インターネットを越える接続に最適な近接性とパフォーマンスを提供します。

- Teams や Skype for Business Online の音声、ビデオ、会議の機能など、含まれるサービスに Microsoft 365 を使用する場合は、エンド to エンドのネットワーク評価を完了し、Microsoft FastTrack を使用して接続要件を[満たす必要があります](https://www.microsoft.com/fasttrack)。

Microsoft 365 を評価する場合や、ネットワーク評価の開始場所が不明な場合や、克服するための支援が必要なネットワーク設計上の課題が見つかった場合は、Microsoft アカウント チームと協力してください。

## <a name="the-microsoft-365-connectivity-test"></a>接続Microsoft 365テスト

Microsoft 365[](https://aka.ms/netonboard)接続テストは概念実証 (POC) ネットワーク評価ツールであり、Microsoft 365 テナントに対して基本的な接続テストを実行し、最適な Microsoft 365 パフォーマンスを実現するために特定のネットワーク設計の推奨事項を作成します。 このツールでは、インターネット Web ブラウズに役立つ一般的な大規模なエンタープライズ ネットワーク境界設計の選択肢が強調表示されますが、大規模な SaaS アプリケーション (Microsoft 365 など) のパフォーマンスに影響します。

ネットワーク オンボーディング ツールは、次の手順を実行します。

- 場所を検出するか、テストする場所を指定できます
- ネットワーク出力の場所を確認する
- 最も近いサービス フロント ドアMicrosoft 365パスをテストする
- プロキシ サーバー、ファイアウォール、DNS に関連Windows 10境界ネットワーク設計の推奨事項を作成する、ダウンロード可能なアプリケーションを使用して高度なテストを提供します。 また、このツールは、オンライン、オンライン、Skype for Business、Microsoft Teams、SharePointのパフォーマンス テストExchange Online。

このツールには、基本的な接続情報を収集するブラウザー ベースの UI と、高度なテストを実行し、追加の評価データを返すダウンロード可能な Windows 10 アプリケーションの 2 つのコンポーネントがあります。

ブラウザー ベースのツールには、次の情報が表示されます。

- [結果と影響] タブ
  - 使用中のサービス フロント ドアのマップ上の場所
  - 最適な接続を提供する他のサービス フロント ドアのマップ上の場所
  - お近くの他の顧客と比較Microsoft 365相対的なパフォーマンス
- [詳細とソリューション] タブ
  - 都市と国別のユーザーの場所
  - 都市、州、国別のネットワーク出力場所
  - ユーザーからネットワークへの出力距離
  - Microsoft 365 Exchange Onlineフロント ドアの場所
  - ユーザー Microsoft 365 Exchange Online最適なサービス フロント ドア
  - パフォーマンスの向上を実現するメトロエリアのお客様

Advanced Tests ダウンロード可能アプリケーションには、次の追加情報が含まれます。

- [詳細とソリューション] タブ (追加)
  - ユーザーの既定のゲートウェイ
  - クライアント DNS サーバー
  - クライアント DNS 再帰的リゾルバー
  - Exchange OnlineDNS サーバー
  - SharePointオンライン DNS サーバー
  - プロキシ サーバーの ID
  - メディア接続チェック
  - メディア品質のパケット損失
  - メディア品質の待機時間
  - メディア品質ジッター
  - メディア品質のパケットの並べ替え
- 複数の機能固有のエンドポイントへの接続テスト
- ネットワーク パスの診断:オンライン サービス、Exchange Onlineサービス、SharePointサービスTeams。

接続テストの詳細Microsoft 365、新しいネットワーク設計の推奨事項ブログ記事を含む更新された Microsoft 365 接続テスト[POC](https://techcommunity.microsoft.com/t5/Office-365-Networking/Updated-Office-365-Network-Onboarding-Tool-POC-with-new-network/m-p/711130#M130)でフィードバックを提供できます。 このツールの今後の更新やネットワーク更新プログラムMicrosoft 365に関する情報は、ネットワーク ブログのOffice 365[されます](https://techcommunity.microsoft.com/t5/Office-365-Networking/bd-p/Office365Networking)。
  
戻って来るのに使用できる短いリンクを次に示します[ https://aka.ms/o365networkconnectivity 。](./microsoft-365-network-connectivity-principles.md)
  
## <a name="related-topics"></a>関連項目

[Microsoft 365 ネットワーク接続の概要](microsoft-365-networking-overview.md)

[Microsoft 365 ネットワーク接続の原則](./microsoft-365-network-connectivity-principles.md)

[Office 365 エンドポイントの管理](managing-office-365-endpoints.md)

[Office 365 の URL および IP アドレスの範囲](urls-and-ip-address-ranges.md)

[Office 365 IP アドレスと URL の Web サービス ](microsoft-365-ip-web-service.md)

[Microsoft 365とパフォーマンスの調整](network-planning-and-performance.md)

[Microsoft 365 Enterprise の概要](microsoft-365-overview.md)