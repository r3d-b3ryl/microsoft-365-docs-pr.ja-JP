---
title: Microsoft Purview の電子情報開示 (Premium) ソリューションの概要
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
ms.date: 07/08/2022
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- m365-security-compliance
- m365solution-aed
- m365initiative-compliance
- m365solution-overview
search.appverid:
- MOE150
- MET150
description: Microsoft Purview の電子情報開示 (Premium) ソリューションについて説明します。 この記事では、Microsoft Purview の電子情報開示 (Premium) の概要について説明します。これは、内部および外部の調査を管理するのに役立つツールです。 また、電子情報開示 (Premium) を使用して法的調査を管理するビジネス上の理由も取り上げられます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7d534012466300675a7143cdada0b43468027104
ms.sourcegitcommit: 75d0403b4114bdd1d228ca05a284b9e514f6f2f3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/19/2022
ms.locfileid: "66855089"
---
# <a name="overview-of-microsoft-purview-ediscovery-premium"></a>Microsoft Purview eDiscovery (Premium) の概要

Microsoft Purview eDiscovery (Premium) ソリューションは、既存の Microsoft 電子情報開示と分析機能に基づいています。 電子情報開示 (Premium) は、組織の内部および外部の調査に対応するコンテンツを保持、収集、分析、レビュー、エクスポートするためのエンドツーエンドのワークフローを提供します。 また、訴訟チームが法的情報保留通知ワークフロー全体を管理して、ケースに関係するカストディアンとコミュニケーションを取ることができます。

## <a name="ediscovery-premium-capabilities"></a>電子情報開示 (Premium) 機能

電子情報開示 (Premium) は、組織が存在するデータを検出することで、法的事項や内部調査に対応するのに役立ちます。 電子情報開示ワークフローをシームレスに管理するには、関心のあるユーザーとそのデータ ソースを識別し、データを保持するために保留をシームレスに適用し、訴訟ホールド通信プロセスを管理します。 ソースからデータを収集することで、ライブ Microsoft 365 プラットフォームを検索して、必要な情報をすばやく見つけることができます。 ディープ インデックス作成、電子メール スレッド処理、ほぼ重複データ検出などのインテリジェントな機械学習機能も、大量のデータを関連するデータ セットに削減するのに役立ちます。

次のセクションでは、これらの電子情報開示 (Premium) 機能が組織にどのように役立つかについて説明します。

![電子情報開示 (Premium) 機能。](../media/advanced-ediscovery-capabilities.png)

### <a name="discover-and-collect-data-in-place"></a>インプレース でデータを検出して収集する

従来、複数のサードパーティの電子情報開示ソリューションに依存している組織では、処理するために大量のデータを Microsoft 365 からコピーし、重複するデータをホストする必要がありました。 この必要性により、関連するデータを見つける時間が長くなり、複数のソリューションを管理するリスク、コスト、複雑さが増します。

Microsoft 365 の電子情報開示 (Premium) を使用すると、ソースでデータを検出し、Microsoft 365 のセキュリティとコンプライアンスの境界内に留まります。  ライブ システムからインプレース データを収集することで、電子情報開示 (Premium) はソースに戻る手間を軽減し、不足しているコンテンツを見つける必要のない作業を減らします。これは、従来の電子情報開示ソリューションでラグを記録するときに発生することがよくあります。

Teams、Yammer、SharePoint Online、OneDrive for Business、Exchange Onlineのデータのネイティブ検索機能と収集機能により、データ検出がさらに強化されます。 たとえば、電子情報開示 (Premium):

- Teams の会話を再構築します (会話から個々のメッセージを返すのではなく)。

- 電子メール メッセージと Teams チャット内のリンクまたは最新の添付ファイルを使用して、ユーザーと共有されるクラウドベースのコンテンツを収集します。

- Microsoft 365 以外の何百ものファイルの種類に対するサポートが組み込まれています。

- データ コネクタによって Microsoft 365 にインポートおよびアーカイブされたサード パーティのソース (Bloomberg、Facebook、Slack、Zoom Meetings など) からデータを収集 [します](archiving-third-party-data.md)。

### <a name="manage-ediscovery-workflow-in-one-platform"></a>1 つのプラットフォームで電子情報開示ワークフローを管理する

電子情報開示 (Premium) は、信頼する必要がある電子情報開示ソリューションの数を減らすのに役立ちます。 これにより、Microsoft 365 内で発生する、合理化されたエンドツーエンドのワークフローが提供されます。 電子情報開示 (Premium) は、一意の共有データ ソースを対象人物 ( *カストディアン* と呼ばれる) に自動的にマッピングし、分析とレビューのために収集する前に、潜在的に関連するデータに関するレポートと分析を提供することで、関連情報の潜在的なソースを特定して収集する際の摩擦を軽減するのに役立ちます。

さらに、Microsoft Graph API は、電子情報開示ワークフローを自動化し、カスタム ソリューションの電子情報開示 (Premium) を拡張するのに役立ちます。

### <a name="cull-data-intelligently"></a>データをインテリジェントにカリングする

電子情報開示 (Premium) のインテリジェントな機械学習機能は、確認するデータの量を減らすのに役立ちます。 これらのインテリジェントな機能は、大量のデータを適切なセットに削減し、カリングするのに役立ちます。 たとえば、組み込みのレビュー セット クエリは、ほぼ重複を識別することで、一意のコンテンツのみをフィルター処理するのに役立ちます。 この機能により、確認するデータの量を大幅に削減できます。

追加の機械学習機能を使用すると、関連性モジュールなどのスマート タグとテクノロジ支援レビュー ツールを使用して、関連するデータをさらに絞り込んで識別できます。

## <a name="ediscovery-premium-alignment-with-the-electronic-discovery-reference-model"></a>電子情報開示参照モデルとの電子情報開示 (Premium) の配置

Microsoft 365 の電子情報開示 (Premium) の組み込みのワークフローは、電子情報開示参照モデル (EDRM) で概説されている電子情報開示プロセスと一致します。

![電子探索参照モデル (EDRM)。](../media/EDRMv2.png)

(edrm.net の EDRM モデルに基づく画像)

高いレベルでは、電子情報開示 (Premium) が EDRM ワークフローをサポートする方法を次に示します。

- **識別。** 調査に関心のある潜在的な人物を特定した後、電子情報開示 (Premium) ケースにカストディアン ( *データカストディアン* とも呼ばれます) を追加できます。 ユーザーをカストディアンとして追加すると、カストディアン ドキュメントを簡単に保持、収集、および確認できます。

- **保存。** 調査に関連するデータを保持および保護するために、電子情報開示 (Premium) を使用すると、ケース内のカストディアンに関連付けられているデータ ソースを法的に保持できます。 非カストディアン データを保留にすることもできます。 電子情報開示 (Premium) には通信ワークフローも組み込まれているため、訴訟ホールド通知をカストディアンに送信し、確認を追跡できます。

- **コレクション。** 調査に関連するデータ ソースを特定 (および保持) した後は、電子情報開示 (Premium) の組み込み検索ツールを使用して、ケースに関連する可能性がある保管データ ソース (および非保管データ ソース (該当する場合) からライブ データを検索および収集できます。

- **処理。** ケースに関連するすべてのデータを収集したら、次の手順は、詳細確認と分析用のプロセスです。 電子情報開示 (Premium) では、コレクション フェーズで特定したインプレース データが Azure Storage の場所 ( *レビュー セット* と呼ばれます) にコピーされ、ケース データの静的ビューが提供されます。

- **レビュー。** レビュー セットにデータが追加された後、特定のドキュメントを表示し、追加のクエリを実行して、データをケースに最も関連するものに減らすことができます。 また、特定のドキュメントに注釈を付けたり、タグを付けたりすることもできます。

- **分析。** 電子情報開示 (Premium) には、調査に関連しないと判断したレビュー セットからデータをさらにカリングするのに役立つ統合分析ツールが用意されています。 Advanced eDiscovery では、関連するデータの量を減らすだけでなく、レビュー プロセスを簡易化して効率化するようにコンテンツを整理できるため、法的レビュー コストを節約するのにも役立ちます。

- **運用環境** と **プレゼンテーション。** 準備ができたら、法的レビュー用のレビュー セットからドキュメントをエクスポートできます。 ドキュメントをネイティブ形式または EDRM で指定された形式でエクスポートして、サード パーティ製のレビュー アプリケーションにインポートできます。

## <a name="subscriptions-and-licensing"></a>サブスクリプションとライセンス

ユーザーが電子情報開示 (Premium) の恩恵を受ける権利を提供するライセンスの詳細については、 [セキュリティ &コンプライアンスに関する Microsoft 365 のガイダンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#microsoft-purview-ediscovery) を参照してください。 [Microsoft 365 の比較表](https://go.microsoft.com/fwlink/?linkid=2139145)の「電子情報開示と監査」セクションを参照してください。

ライセンスを割り当てる方法については、「 [ユーザーにライセンスを割り当てる」を参照してください](/microsoft-365/admin/manage/assign-licenses-to-users)。

## <a name="get-started-with-ediscovery-premium"></a>電子情報開示 (プレミアム) を開始する

電子情報開示 (Premium) を使用するには、2 つの簡単で簡単な手順があります。

![電子情報開示 (Premium) の使用を開始するワークフロー。](../media/get-started-AeD.png)

|手順  |説明  |
|:---------|:---------|
|[電子情報開示 (プレミアム) を設定する](get-started-with-advanced-ediscovery.md)| サブスクリプションとライセンス要件を確認したら、アクセス許可を割り当て、組織全体の設定を構成して、電子情報開示 (Premium) の使用を開始できます。|
|[ケースの作成と管理](create-and-manage-advanced-ediscoveryv2-case.md) | 組織内のすべての法的および他の種類の調査に対して電子情報開示 (Premium) ワークフローを管理するケースを作成します。|
|||

## <a name="ediscovery-premium-architecture"></a>電子情報開示 (Premium) アーキテクチャ

単一地域環境と複数地域環境のエンド ツー エンド ワークフローと、 [EDRM](#ediscovery-premium-alignment-with-the-electronic-discovery-reference-model) に合わせたエンド ツー エンドのデータ フローを示す電子情報開示 (Premium) アーキテクチャ図を次に示します。

[![モデル ポスター: Microsoft 365 の電子情報開示 (Premium) アーキテクチャ。](../media/solutions-architecture-center/ediscovery-poster-thumb.png)](../media/solutions-architecture-center/m365-advanced-ediscovery-architecture.png)

[イメージとして表示する](../media/solutions-architecture-center/m365-advanced-ediscovery-architecture.png)

[PDF ファイルとしてダウンロードする](https://download.microsoft.com/download/d/1/c/d1ce536d-9bcf-4d31-b75b-fcf0dc560665/m365-advanced-ediscovery-architecture.pdf)

[Visio ファイルとしてダウンロードする](https://download.microsoft.com/download/d/1/c/d1ce536d-9bcf-4d31-b75b-fcf0dc560665/m365-advanced-ediscovery-architecture.vsdx)

## <a name="training"></a>トレーニング

電子情報開示 (Premium) の基本に関する IT 管理者、電子情報開示マネージャー、コンプライアンス調査チームのトレーニングは、Microsoft 365 電子情報開示ツールの使用を組織がより迅速に開始するのに役立ちます。 Microsoft 365 には、組織内のユーザーが電子情報開示を開始するのに役立つ次のリソースが用意されています。 [Microsoft 365 の電子情報開示と監査機能について説明します](/learn/modules/describe-ediscovery-capabilities-of-microsoft-365)。
