---
title: Microsoft 365 の高度な電子情報開示ソリューションの概要
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- m365-security-compliance
- m365solution-aed
- m365initiative-compliance
- m365solution-overview
search.appverid:
- MOE150
- MET150
description: Microsoft 365 の高度な電子情報開示ソリューションについて説明します。 この記事では、内部調査と外部調査の管理に役立つツールである Microsoft 365 の高度な電子情報開示の概要について説明します。 また、高度な電子情報開示を使用して法的調査を管理するビジネス上の理由も枠に入ります。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0f6ae536f84190f81248bbf68ff66f438727e068
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927657"
---
# <a name="overview-of-microsoft-365-advanced-ediscovery"></a>Microsoft 365 Advanced eDiscovery の概要

Microsoft 365 の高度な電子情報開示ソリューションは、既存の Microsoft 電子情報開示機能と分析機能を基に構築されています。 Advanced eDiscovery は、組織の内部および外部調査に対応するコンテンツを保存、収集、分析、レビュー、分析、エクスポートするためのエンドツーエンドのワークフローを提供します。 また、法務チームが法的ホールド通知ワークフロー全体を管理して、ケースに関係する保管担当者と通信できます。

## <a name="advanced-ediscovery-capabilities"></a>高度な電子情報開示機能

高度な電子情報開示は、組織がどこに住んでいるデータを検出することで、法的な問題や内部調査に対応するのに役立ちます。 電子情報開示ワークフローをシームレスに管理するには、関心のある人物とそのデータ ソースを特定し、データを保持するためにホールドをシームレスに適用してから、法的ホールド通信プロセスを管理します。 ソースからデータを収集することで、ライブの Microsoft 365 プラットフォームを検索して、必要な情報をすばやく見つけ出します。 ディープ インデックス作成、電子メール スレッド、重複に近い検出などのインテリジェントな機械学習機能は、大量のデータを関連するデータ セットに削減するのにも役立ちます。

次のセクションでは、これらの高度な電子情報開示機能が組織に役立つ方法について説明します。

![高度な電子情報開示機能](../media/advanced-ediscovery-capabilities.png)

### <a name="discover-and-collect-data-in-place"></a>データを一インプレイスで検出して収集する

従来、複数のサード パーティ製の電子情報開示ソリューションに依存する組織では、大量のデータを Microsoft 365 からコピーして処理し、重複するデータをホストする必要があります。 これにより、関連するデータを見つける時間が増え、複数のソリューションを管理するリスク、コスト、複雑さも増します。

Microsoft 365 の高度な電子情報開示を使用すると、ソースでデータを検出し、Microsoft 365 のセキュリティとコンプライアンスの境界内にとどまることができます。  Advanced eDiscovery は、ライブ システムからデータを一元的に収集することで、ソースに戻る際の摩擦を軽減し、従来の電子情報開示ソリューションでジャーナリングの遅延が発生する場合が多い、不足しているコンテンツを見つけ出す必要のない作業を減らします。

Teams、Yammer、SharePoint Online、OneDrive for Business、および Exchange Online のデータのネイティブ検索および収集機能により、データ検出がさらに強化されます。 たとえば、高度な電子情報開示:

- Teams の会話を再構築します (会話から個々のメッセージを返す代わりに)。

- 電子メール メッセージと Teams チャットのリンクまたは最新の添付ファイルを使用して、ユーザーと共有されるクラウドベースのコンテンツを収集します。

- Microsoft 365 以外のファイルの種類の何百もの組み込みのサポートがあります。

- データ コネクタによって Microsoft 365 でインポートおよびアーカイブされるサードパーティソース (ブルームバーグ、Facebook、Slack、ズーム 会議など) からデータを収集[します。](archiving-third-party-data.md)

### <a name="manage-ediscovery-workflow-in-one-platform"></a>1 つのプラットフォームで電子情報開示ワークフローを管理する

高度な電子情報開示は、信頼する必要がある電子情報開示ソリューションの数を減らすのに役立ちます。 Microsoft 365 内で発生する、合理化されたエンドツーエンドのワークフローを提供します。 高度な電子情報開示は、一意で共有されたデータ ソースを関心のある人物 (保管担当者と呼ばれる) に自動的にマッピングし、分析とレビューのために収集する前に、潜在的に関連するデータに関するレポートと分析を提供することで、関連する情報の潜在的なソースを特定して収集する摩擦を軽減するのに役立ちます。

さらに、Microsoft Graph API を使用すると、電子情報開示ワークフローを自動化し、カスタム ソリューション用の高度な電子情報開示を拡張できます。

### <a name="cull-data-intelligently"></a>データをインテリジェントにカイルする

Advanced eDiscovery のインテリジェントな機械学習機能を使用すると、確認するデータ量を削減できます。 これらのインテリジェントな機能は、大量のデータを関連するセットに削減し、カイルするのに役立ちます。 たとえば、組み込みのレビュー セット クエリは、重複の近くを識別して一意のコンテンツのみをフィルター処理するのに役立ちます。 この機能により、確認するデータ量を大幅に削減できます。

機械学習機能を追加すると、関連性モジュールのようなスマート タグとテクノロジ支援レビュー ツールを使用して、関連するデータをさらに絞り込み、特定できます。

## <a name="advanced-ediscovery-alignment-with-the-electronic-discovery-reference-model"></a>電子情報開示参照モデルとの高度な電子情報開示の配置

Microsoft 365 の Advanced eDiscovery の組み込みのワークフローは、電子情報開示参照モデル (EDRM) で概説されている電子情報開示プロセスに合わせて調整されます。

![電子探索参照モデル (EDRM)](../media/EDRMv1.png)

(画像ソース提供:edrm.net。 ソース イメージは、クリエイティブ コモンズ アトリビューション 3.0 [報告されていないライセンス] で利用できます。

高度な電子情報開示が EDRM ワークフローをサポートする方法は次の高レベルです。

- **ID。** 調査に関心のある潜在的な人物を特定した後、高度な電子情報開示ケースに保管担当者 (データ保管担当者とも呼ばれる)を追加できます。 ユーザーが保管担当者として追加された後、保管担当者のドキュメントを保存、収集、および確認するのは簡単です。

- **保持。** 調査に関連するデータを保持および保護するために、Advanced eDiscovery を使用すると、ケース内の保管担当者に関連付けられたデータ ソースに法的なホールドを設定できます。 保管以外のデータを保留に設定できます。 高度な電子情報開示には、通信ワークフローも組み込みなので、法的保持通知を保管担当者に送信し、確認応答を追跡できます。

- **コレクション。** 調査に関連するデータ ソースを特定 (および保存) した後、ケースに関連する可能性のある保管データ ソース (および該当する場合は保管されていないデータ ソース) のライブ データを高度な電子情報開示検索で組み込みの検索ツールを使用して収集できます。

- **処理。** ケースに関連するすべてのデータを収集した後、次の手順でケースを処理して、詳細なレビューと分析を行います。 Advanced eDiscovery では、コレクション フェーズで識別したインプレイス データが Azure Storage の場所 (レビュー セットと呼ばれる) にコピーされ、ケース データの静的ビューが提供されます。 

- **確認します。** データをレビュー セットに追加した後、特定のドキュメントを表示し、追加のクエリを実行して、データをケースに最も関連のあるものに減らします。 また、特定のドキュメントに注釈を付け、タグ付けできます。

- **分析。** 高度な電子情報開示には、調査に関連していないと判断したレビュー セットからデータをさらに作成するのに役立つ統合分析ツールが提供されています。 関連するデータの量を減らすだけでなく、Advance eDiscovery を使用すると、コンテンツを整理してレビュー プロセスをより簡単かつ効率的に行って、法的レビューコストを節約できます。

- **実稼働** と **プレゼンテーション。** 準備ができたら、法的レビュー用のレビュー セットからドキュメントをエクスポートできます。 ドキュメントをネイティブ形式または EDRM で指定した形式でエクスポートして、サードパーティのレビュー アプリケーションにインポートできます。

## <a name="subscriptions-and-licensing"></a>サブスクリプションとライセンス

Advanced eDiscovery のライセンスには、適切な組織のサブスクリプションとユーザーごとのライセンスが必要です。

- **組織のサブスクリプション:** Microsoft 365 コンプライアンス センターで Advanced eDiscovery にアクセスするには、組織で次のいずれかを使用する必要があります。

  - Microsoft 365 E5 または Office 365 E5 サブスクリプション
  
  - E5 コンプライアンス アドオンが含まれている Microsoft 365 E3 サブスクリプション

  - E5 電子情報開示と監査アドオンを使用した Microsoft 365 E3 サブスクリプション

  既存の Microsoft 365 E5 プランをお持ちで、Advanced eDiscovery を試す場合は、既存のサブスクリプションに Microsoft 365 を追加するか、Microsoft [365](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) E5 の試用版にサインアップできます。 [](https://www.microsoft.com/microsoft-365/enterprise)

- **ユーザーごとのライセンス:** Advance 電子情報開示ケースでユーザーを保管担当者として追加するには、組織のサブスクリプションに応じて、そのユーザーに次のいずれかのライセンスを割り当てる必要があります。

  - Microsoft 365: ユーザーには、Microsoft 365 E5 ライセンス、E5 コンプライアンス アドオン ライセンス、または E5 電子情報開示および監査アドオン ライセンスが割り当てられている必要があります。

  - Office 365: ユーザーには、365 E5 ライセンスOffice割り当てる必要があります。

   ライセンスを割り当てる方法については、「ユーザーにライセンスを割り当 [てる」を参照してください](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)。

> [!NOTE]
> ユーザーは、高度な電子情報開示ケースに保管担当者として追加する E5 ライセンス (または適切なアドオン ライセンス) のみを必要とします。 高度な電子情報開示を使用してケースを管理し、ケース データを確認する IT 管理者、電子情報開示管理者、弁護士、パラリーガル、または調査者は、E5 またはアドオン ライセンスを必要とします。

## <a name="get-started-with-advanced-ediscovery"></a>Advanced eDiscoveryを開始する

Advanced eDiscovery を使い始めるには、2 つの迅速かつ簡単な手順があります。

![高度な電子情報開示のワークフローの開始](../media/get-started-AeD.png)

|手順  |説明  |
|:---------|:---------|
|[Advanced eDiscovery を設定する](get-started-with-advanced-ediscovery.md)| サブスクリプションとライセンス要件を確認した後、アクセス許可を割り当て、組織全体の設定を構成して、高度な電子情報開示の使用を開始できます。|
|[ケースの作成と管理](create-and-manage-advanced-ediscoveryv2-case.md) | 組織内のすべての法的および他の種類の調査の高度な電子情報開示ワークフローを管理するケースを作成します。|
|||

## <a name="advanced-ediscovery-architecture"></a>高度な電子情報開示アーキテクチャ

単一地域環境と複数地域環境でのエンド to エンド のワークフローと [、EDRM](#advanced-ediscovery-alignment-with-the-electronic-discovery-reference-model)に沿ったエンドツーエンドのデータ フローを示す高度な電子情報開示アーキテクチャ図を次に示します。

[![モデル ポスター: Microsoft 365 の高度な電子情報開示アーキテクチャ](../media/solutions-architecture-center/ediscovery-poster-thumb.png)](../media/solutions-architecture-center/m365-advanced-ediscovery-architecture.png)

[画像として表示する](../media/solutions-architecture-center/m365-advanced-ediscovery-architecture.png)

[PDF ファイルとしてダウンロードする](https://download.microsoft.com/download/d/1/c/d1ce536d-9bcf-4d31-b75b-fcf0dc560665/m365-advanced-ediscovery-architecture.pdf)

[Visio ファイルとしてダウンロードする](https://download.microsoft.com/download/d/1/c/d1ce536d-9bcf-4d31-b75b-fcf0dc560665/m365-advanced-ediscovery-architecture.vsdx)
