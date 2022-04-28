---
title: Microsoft 365 ネットワーク接続の評価
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 6/23/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
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
description: Microsoft 365は、世界中のお客様がインターネット接続を使用してサービスに接続できるように設計されています。 サービスが進化するにつれて、インターネットを使用してサービスへの接続を確立する顧客に基づいて、Microsoft 365のセキュリティ、パフォーマンス、信頼性が向上します。
ms.openlocfilehash: 88664966a7451f342a140feb2ff31186cfc3c818
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65099435"
---
# <a name="assessing-microsoft-365-network-connectivity"></a>Microsoft 365 ネットワーク接続の評価

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Microsoft 365は、世界中のお客様がインターネット接続を使用してサービスに接続できるように設計されています。 サービスが進化するにつれて、インターネットを使用してサービスへの接続を確立する顧客に基づいて、Microsoft 365のセキュリティ、パフォーマンス、信頼性が向上します。
  
Microsoft 365を使用する予定のお客様は、デプロイ プロジェクトの一環として、既存のインターネット接続ニーズと予測されたインターネット接続のニーズを評価する必要があります。 エンタープライズ クラスのデプロイでは、信頼性が高く、適切なサイズのインターネット接続が、Microsoft 365機能とシナリオを消費するうえで重要な部分です。
  
ネットワーク評価は、サイズや好みに応じて、さまざまなユーザーや組織によって実行できます。 評価のネットワーク スコープは、デプロイ プロセスの場所によって異なる場合もあります。 ネットワーク評価の実行に必要な内容の理解を深めるために、利用可能なオプションを理解するのに役立つネットワーク評価ガイドを作成しました。 この評価により、Microsoft 365を正常に導入するためにデプロイ プロジェクトに追加する必要がある手順とリソースが決定されます。
  
包括的なネットワーク評価は、実装の詳細と共にネットワーク設計の課題に対して可能なソリューションを提供します。 一部のネットワーク評価では、Microsoft 365への最適なネットワーク接続を、既存のネットワークおよびインターネットエグレス インフラストラクチャに対する小規模な構成または設計変更に対応できることが示されます。

一部の評価では、Microsoft 365へのネットワーク接続にネットワーク コンポーネントへの追加の投資が必要であることを示します。 たとえば、ブランチ オフィスと複数の地理的リージョンにまたがるエンタープライズ ネットワークでは、Microsoft 365へのインターネット接続をサポートするために、SD-WAN ソリューションや最適化されたルーティング インフラストラクチャへの投資が必要になる場合があります。 評価では、Microsoft 365へのネットワーク接続が[、Skype for Business Online メディア品質](https://support.office.com/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)などのシナリオの規制やパフォーマンス要件の影響を受ける場合があります。 これらの追加要件は、インターネット接続インフラストラクチャへの投資、ルーティングの最適化、特殊な直接接続につながる可能性があります。

ネットワークの評価に役立ついくつかのリソース:

- [Microsoft 365 ネットワークの](microsoft-365-networking-overview.md)概念については、ネットワーク接続の概要Microsoft 365参照してください。
- [Microsoft 365ネットワーク接続の原則](./microsoft-365-network-connectivity-principles.md)を参照して、Microsoft 365 トラフィックを安全に管理し、可能な限り最高のパフォーマンスを得るための接続の原則を理解してください。
- [Microsoft 365](https://www.microsoft.com/fasttrack)の計画、設計、デプロイに関するガイド付きサポートについては、Microsoft FastTrackにサインアップしてください。 
- 以下の[Microsoft 365接続テスト](assessing-network-connectivity.md#the-microsoft-365-connectivity-test)セクションを参照して、特定のユーザーの場所とMicrosoft 365の間で行うことができるネットワーク接続の改善に関する具体的なガイダンスを提供する基本的な接続テストを実行します。

> [!NOTE]
> Office 365に ExpressRoute を使用するには、Microsoft の承認が必要です。 Microsoft は、お客様のすべての要求を確認し、お客様の規制要件で直接接続が義務付けられている場合にのみ、ExpressRoute の使用Office 365承認します。 このような要件がある場合は、Microsoft レビューを開始するために [ExpressRoute for Office 365 Request Form](https://aka.ms/O365ERReview) で直接接続が必要であると解釈する規制へのテキストの抜粋と Web リンクを提供してください。 Office 365のルート フィルターを作成しようとしている未承認のサブスクリプションには[、エラー メッセージが表示](https://support.microsoft.com/kb/3181709)されます。
  
Microsoft 365のネットワーク評価を計画する際に考慮すべき重要な点:
  
- Microsoft 365は、パブリック インターネット経由で実行される、セキュリティで保護された信頼性の高い高性能サービスです。 サービスのこれらの側面を強化するために、引き続き投資を行います。 すべてのMicrosoft 365 サービスは、インターネット接続を介して利用できます。

- インターネット ベースの接続の可用性、グローバル リーチ、パフォーマンスなど、Microsoft 365のコア側面を継続的に最適化しています。 たとえば、多くのMicrosoft 365 サービスは、インターネットに接続するエッジ ノードの拡張セットを利用しています。 このエッジ ネットワークは、インターネット経由の接続に最適な近接性とパフォーマンスを提供します。

- TeamsやSkype for Businessオンライン音声、ビデオ、会議の機能など、Microsoft 365の使用を検討する場合は、エンド ツー エンドのネットワーク評価を完了し、[Microsoft FastTrack](https://www.microsoft.com/fasttrack)を使用して接続要件を満たす必要があります。

Microsoft 365を評価していて、ネットワーク評価を開始する場所がわからない場合や、克服するために支援が必要なネットワーク設計の課題が見つかった場合は、Microsoft アカウント チームと協力してください。

## <a name="the-microsoft-365-connectivity-test"></a>Microsoft 365接続テスト

[Microsoft 365接続テスト](https://aka.ms/netonboard)は概念実証 (POC) ネットワーク評価ツールであり、Microsoft 365 テナントに対して基本的な接続テストを実行し、最適なMicrosoft 365パフォーマンスを実現するための特定のネットワーク設計の推奨事項を作成します。 このツールは、インターネット Web の閲覧に役立ちますが、Microsoft 365などの大規模 SaaS アプリケーションのパフォーマンスに影響を与える、一般的な大規模エンタープライズ ネットワーク境界設計の選択肢を強調しています。

ネットワーク オンボーディング ツールは、次の操作を行います。

- 場所を検出するか、テストする場所を指定できます
- ネットワークエグレスの場所を確認します
- 最も近いMicrosoft 365サービス フロント ドアへのネットワーク パスをテストします
- プロキシ サーバー、ファイアウォール、DNS に関連する境界ネットワーク設計の推奨事項を作成するダウンロード可能なWindows 10 アプリケーションを使用して高度なテストを提供します。 このツールでは、Skype for Business Online、Microsoft Teams、SharePoint Online、Exchange Onlineのパフォーマンス テストも実行されます。

このツールには、基本的な接続情報を収集するブラウザー ベースの UI と、高度なテストを実行して追加の評価データを返すダウンロード可能なWindows 10 アプリケーションの 2 つのコンポーネントがあります。

ブラウザー ベースのツールには、次の情報が表示されます。

- [結果と影響] タブ
  - 使用中のサービス フロント ドアのマップ上の場所
  - 最適な接続を提供する他のサービス フロント ドアのマップ上の場所
  - 近くの他のMicrosoft 365顧客と比較した相対的なパフォーマンス
- [詳細とソリューション] タブ
  - 都市と国別のユーザーの場所
  - 都市、州、国別のネットワークエグレスの場所
  - ユーザーからネットワークへのエグレス距離
  - Microsoft 365 Exchange Online サービス フロント ドアの場所
  - ユーザーの場所に最適なMicrosoft 365 Exchange Onlineサービス フロント ドア
  - より高いパフォーマンスを備えたメトロエリアのお客様

Advanced Tests のダウンロード可能なアプリケーションでは、次の追加情報が提供されます。

- [詳細とソリューション] タブ (追加)
  - ユーザーの既定のゲートウェイ
  - クライアント DNS サーバー
  - クライアント DNS 再帰リゾルバー
  - Exchange Online DNS サーバー
  - SharePoint オンライン DNS サーバー
  - プロキシ サーバーの識別
  - メディア接続チェック
  - メディア品質のパケット損失
  - メディア品質の待機時間
  - メディア品質ジッター
  - メディア品質パケットの並べ替え
- 複数の機能固有のエンドポイントへの接続テスト
- Exchange Online、SharePoint Online、Teams サービスの tracert データと待機時間データを含むネットワーク パス診断

Microsoft 365接続テストについて読み、[新しいネットワーク設計に関する推奨事項に関するブログ投稿の更新されたMicrosoft 365接続テスト POC](https://techcommunity.microsoft.com/t5/Office-365-Networking/Updated-Office-365-Network-Onboarding-Tool-POC-with-new-network/m-p/711130#M130) でフィードバックを提供できます。 このツールとその他のMicrosoft 365ネットワーク更新プログラムの今後の更新に関する情報は、[Office 365 ネットワーク](https://techcommunity.microsoft.com/t5/Office-365-Networking/bd-p/Office365Networking) ブログに投稿されます。
  
戻ってくるのに使用できる短いリンクを次に示します [https://aka.ms/o365networkconnectivity。](./microsoft-365-network-connectivity-principles.md)
  
## <a name="related-topics"></a>関連項目

[Microsoft 365 ネットワーク接続の概要](microsoft-365-networking-overview.md)

[Microsoft 365 ネットワーク接続の原則](./microsoft-365-network-connectivity-principles.md)

[Office 365 エンドポイントの管理](managing-office-365-endpoints.md)

[Office 365 の URL および IP アドレスの範囲](urls-and-ip-address-ranges.md)

[Office 365 IP アドレスと URL の Web サービス ](microsoft-365-ip-web-service.md)

[Microsoft 365ネットワークとパフォーマンスのチューニング](network-planning-and-performance.md)

[Microsoft 365 Enterprise の概要](microsoft-365-overview.md)