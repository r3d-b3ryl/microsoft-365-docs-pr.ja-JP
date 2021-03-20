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
description: Microsoft 365 は、世界中のお客様がインターネット接続を使用してサービスに接続できるよう設計されています。 サービスの進化に伴い、Microsoft 365 のセキュリティ、パフォーマンス、および信頼性は、インターネットを使用してサービスへの接続を確立する顧客に基づいて向上します。
ms.openlocfilehash: 4d80bdf5642b2456ac8293291c720429f7f18fb1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905478"
---
# <a name="assessing-microsoft-365-network-connectivity"></a>Microsoft 365 ネットワーク接続の評価

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Microsoft 365 は、世界中のお客様がインターネット接続を使用してサービスに接続できるよう設計されています。 サービスの進化に伴い、Microsoft 365 のセキュリティ、パフォーマンス、および信頼性は、インターネットを使用してサービスへの接続を確立する顧客に基づいて向上します。
  
Microsoft 365 の使用を計画しているお客様は、展開プロジェクトの一環として、既存の予測されたインターネット接続ニーズを評価する必要があります。 エンタープライズ クラスの展開では、Microsoft 365 の機能とシナリオを使用する上で、信頼できる適切なサイズのインターネット接続が重要です。
  
ネットワーク評価は、サイズや好みに応じて、さまざまなユーザーや組織によって実行できます。 評価のネットワーク スコープは、展開プロセスの場所によっても異なります。 ネットワーク評価の実行に必要な情報をより深く理解するために、利用可能なオプションを理解するためのネットワーク評価ガイドを作成しました。 この評価は、Microsoft 365 を正常に採用するために展開プロジェクトに追加する必要がある手順とリソースを決定します。
  
包括的なネットワーク評価は、ネットワーク設計の課題に対する可能な解決策と実装の詳細を提供します。 一部のネットワーク評価では、Microsoft 365 への最適なネットワーク接続が、既存のネットワークおよびインターネット出力インフラストラクチャのわずかな構成または設計変更に対応できると示されます。

一部の評価では、Microsoft 365 へのネットワーク接続にネットワーク コンポーネントへの追加投資が必要な場合があります。 たとえば、ブランチ オフィスと複数の地理的地域にまたがるエンタープライズ ネットワークでは、Microsoft 365 へのインターネット接続をサポートするために、SD-WAN ソリューションや最適化されたルーティング インフラストラクチャへの投資が必要な場合があります。 場合によっては、評価は、Microsoft 365 へのネットワーク接続が [、Skype for Business Online](https://support.office.com/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)メディア品質などのシナリオの規制やパフォーマンス要件の影響を受ける可能性を示します。 これらの追加の要件は、インターネット接続インフラストラクチャ、ルーティングの最適化、および専用の直接接続への投資につながる可能性があります。

ネットワークの評価に役立ついくつかのリソース:

- [Microsoft 365 ネットワーク](microsoft-365-networking-overview.md)に関する概念的な情報については、「Microsoft 365 ネットワーク接続の概要」を参照してください。
- Microsoft 365 トラフィックを安全に管理し、可能な限り最高のパフォーマンスを得る接続の原則については [、「Microsoft 365](./microsoft-365-network-connectivity-principles.md) ネットワーク接続の原則」を参照してください。
- Microsoft 365 の計画、設計、展開に関するガイド付きサポートについては、Microsoft [FastTrack](https://www.microsoft.com/fasttrack) にサインアップしてください。 
- 特定のユーザーの場所と Microsoft 365 の間で行えるネットワーク接続の改善に関する具体的なガイダンスを提供する基本的な接続テストを実行するには、以下の [「Microsoft 365](assessing-network-connectivity.md#the-microsoft-365-connectivity-test) 接続テスト」セクションを参照してください。

> [!NOTE]
> Microsoft の承認は、ExpressRoute を 365 にOfficeです。 Microsoft は、すべての顧客要求を確認し、お客様の規制要件が直接接続をOffice 365 の使用に対する ExpressRoute のみを承認します。 そのような要件がある場合は、Microsoft のレビューを開始するために [、ExpressRoute for Office 365 Request Form](https://aka.ms/O365ERReview) で直接接続が必要と解釈される規制へのテキスト抜粋と Web リンクを提供してください。 365 のルート フィルターを作成しようとしている未承認のサブスクリプションOfficeエラー メッセージが [表示されます](https://support.microsoft.com/kb/3181709)。
  
Microsoft 365 のネットワーク評価を計画する際に考慮すべき重要な点:
  
- Microsoft 365 は、パブリック インターネット上で実行される、安全で信頼性の高い高性能サービスです。 サービスのこれらの側面を強化するために引き続き投資を行っています。 すべての Microsoft 365 サービスは、インターネット接続経由で利用できます。

- Microsoft 365 の主要な側面 (可用性、グローバルリーチ、インターネット ベースの接続のパフォーマンスなど) を継続的に最適化しています。 たとえば、多くの Microsoft 365 サービスは、インターネットに接続するエッジ ノードの拡張セットを利用します。 このエッジ ネットワークは、インターネットを越える接続に最適な近接性とパフォーマンスを提供します。

- Teams や Skype for Business Online の音声、ビデオ、会議の機能など、含まれるサービスに Microsoft 365 を使用する場合は、エンド to エンドのネットワーク評価を完了し [、Microsoft FastTrack](https://www.microsoft.com/fasttrack)を使用して接続要件を満たす必要があります。

Microsoft 365 を評価する場合で、ネットワーク評価の開始場所が不明な場合や、克服するための支援が必要なネットワーク設計上の課題が見つかった場合は、Microsoft アカウント チームと協力してください。

## <a name="the-microsoft-365-connectivity-test"></a>Microsoft 365 接続テスト

[Microsoft 365](https://aka.ms/netonboard)接続テストは概念実証 (POC) ネットワーク評価ツールであり、Microsoft 365 テナントに対して基本的な接続テストを実行し、最適な Microsoft 365 パフォーマンスを実現するために特定のネットワーク設計の推奨事項を作成します。 このツールでは、一般的な大規模なエンタープライズ ネットワーク境界設計の選択肢が強調表示され、インターネット Web ブラウズに役立ちますが、Microsoft 365 などの大規模な SaaS アプリケーションのパフォーマンスに影響を与えます。

ネットワーク オンボーディング ツールは、次の手順を実行します。

- 場所を検出するか、テストする場所を指定できます
- ネットワーク出力の場所を確認する
- 最も近い Microsoft 365 サービス フロント ドアへのネットワーク パスをテストする
- プロキシ サーバー、ファイアウォール、DNS に関連する境界ネットワーク設計の推奨事項を作成する、ダウンロード可能な Windows 10 アプリケーションを使用した高度なテストを提供します。 このツールでは、Skype for Business Online、Microsoft Teams、SharePoint Online、Exchange Online のパフォーマンス テストも実行します。

このツールには、基本的な接続情報を収集するブラウザー ベースの UI と、高度なテストを実行し、追加の評価データを返すダウンロード可能な Windows 10 アプリケーションの 2 つのコンポーネントがあります。

ブラウザー ベースのツールには、次の情報が表示されます。

- [結果と影響] タブ
  - 使用中のサービス フロント ドアのマップ上の場所
  - 最適な接続を提供する他のサービス フロント ドアのマップ上の場所
  - お近くの他の Microsoft 365 のお客様と比較した相対的なパフォーマンス
- [詳細とソリューション] タブ
  - 都市と国別のユーザーの場所
  - 都市、州、国別のネットワーク出力場所
  - ユーザーからネットワークへの出力距離
  - Microsoft 365 Exchange Online サービスのフロント ドアの場所
  - ユーザーの場所に最適な Microsoft 365 Exchange Online サービスのフロント ドア
  - パフォーマンスの向上を実現するメトロエリアのお客様

Advanced Tests ダウンロード可能アプリケーションには、次の追加情報が含まれます。

- [詳細とソリューション] タブ (追加)
  - ユーザーの既定のゲートウェイ
  - クライアント DNS サーバー
  - クライアント DNS 再帰的リゾルバー
  - Exchange Online DNS サーバー
  - SharePoint Online DNS サーバー
  - プロキシ サーバーの ID
  - メディア接続チェック
  - メディア品質のパケット損失
  - メディア品質の待機時間
  - メディア品質ジッター
  - メディア品質のパケットの並べ替え
- 複数の機能固有のエンドポイントへの接続テスト
- Exchange Online、SharePoint Online、Teams サービスの tracert および待機時間データを含むネットワーク パス診断

Microsoft 365 接続テストについて読み、フィードバックを提供するには、 [更新された Microsoft 365 接続テスト POC](https://techcommunity.microsoft.com/t5/Office-365-Networking/Updated-Office-365-Network-Onboarding-Tool-POC-with-new-network/m-p/711130#M130) で、新しいネットワーク設計の推奨事項に関するブログ投稿を参照してください。 このツールと他の Microsoft 365 ネットワーク更新プログラムの今後の更新に関する情報は、Office [365 Networking](https://techcommunity.microsoft.com/t5/Office-365-Networking/bd-p/Office365Networking) ブログに投稿されます。
  
戻って来るのに使用できる短いリンクを次に示します[ https://aka.ms/o365networkconnectivity 。](./microsoft-365-network-connectivity-principles.md)
  
## <a name="related-topics"></a>関連項目

[Microsoft 365 ネットワーク接続の概要](microsoft-365-networking-overview.md)

[Microsoft 365 ネットワーク接続の原則](./microsoft-365-network-connectivity-principles.md)

[Office 365 エンドポイントの管理](managing-office-365-endpoints.md)

[Office 365 の URL および IP アドレスの範囲](urls-and-ip-address-ranges.md)

[Office 365 IP アドレスと URL の Web サービス ](microsoft-365-ip-web-service.md)

[Microsoft 365 ネットワークとパフォーマンスのチューニング](network-planning-and-performance.md)

[Microsoft 365 Enterprise の概要](microsoft-365-overview.md)