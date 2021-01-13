---
title: Microsoft 365 の Advanced eDiscovery ソリューションの概要
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
- M365-security-compliance
- m365solution-aed
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 365 の Advanced eDiscovery ソリューションについて説明します。 この記事では、内部および外部の調査を管理するのに役立つツールである Microsoft 365 の Advanced eDiscovery の概要について説明します。 また、Advanced eDiscovery を使用して法的調査を管理するビジネス上の理由も示します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1b2fa0b42a7f439aa65ae53e76e377ded92f97b7
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840880"
---
# <a name="overview-of-microsoft-365-advanced-ediscovery"></a>Microsoft 365 Advanced eDiscovery の概要

Microsoft 365 の Advanced eDiscovery ソリューションは、既存の Microsoft 電子情報開示および分析機能を基に構築されています。 Advanced eDiscovery は、組織の内部および外部の調査に対応するコンテンツを保持、収集、分析、レビュー、分析、エクスポートするためのエンドツーエンドのワークフローを提供します。 また、法務チームは、法的情報保留通知ワークフロー全体を管理して、ケースに関係する保管担当者と通信できます。

Advanced eDiscovery は、組織が保存されているデータを検出することで、法的事項や内部調査に対応するのに役立ちます。 電子情報開示ワークフローをシームレスに管理するには、関心のある人物とそのデータ ソースを特定し、保持をシームレスに適用してデータを保持し、法的情報保留の通信プロセスを管理します。 ソースからデータを収集することで、ライブの Microsoft 365 プラットフォームを検索して、必要な情報をすばやく見つけるできます。 深いインデックス処理、電子メールのスレッド処理、ほぼ重複した検出などのインテリジェントな機械学習機能は、大量のデータを関連するデータ セットに減らすのにも役立ちます。

以下のセクションでは、これらの Advanced eDiscovery 機能が組織に役立つ方法について説明します。

## <a name="discover-and-collect-data-in-place"></a>データをインサイトで検出して収集する

従来、複数のサード パーティの電子情報開示ソリューションを利用する組織では、大量のデータを Microsoft 365 からコピーして処理し、重複するデータをホストする必要があります。 これにより、関連するデータを検索する時間と、複数のソリューションを管理するリスク、コスト、および複雑さを増す必要があります。

Microsoft 365 の Advanced eDiscovery を使用すると、ソースでデータを検出し、Microsoft 365 のセキュリティとコンプライアンスの境界内にとどまることができます。  Advanced eDiscovery は、ライブ システムから一元的にデータを収集することで、ソースに戻る際のストレスを軽減し、失われるコンテンツを見つける必要があるという不要な作業を減らします。これは、従来の電子情報開示ソリューションのジャーナリングの時間差が生じるときによく発生します。

Teams、Yammer、SharePoint Online、OneDrive for Business、および Exchange Online のデータのネイティブ検索および収集機能により、データ検出がさらに強化されます。 たとえば、Advanced eDiscovery は次のようになります。

- Teams の会話を再構築します (会話から個々のメッセージを返す代わりに)。

- 電子メール メッセージと Teams チャットでリンクまたは最新の添付ファイルを使用して、ユーザーと共有するクラウドベースのコンテンツを収集します。

- Microsoft 365 以外の数百種類のファイルをサポートしています。

- データ コネクタによって Microsoft 365 にインポートおよびアーカイブされたサード パーティのソース (Bloomberg、Facebook、Slack、Zoom Meetings など) からデータを [収集します](archiving-third-party-data.md)。

## <a name="manage-ediscovery-workflow-in-one-platform"></a>1 つのプラットフォームで電子情報開示ワークフローを管理する

Advanced eDiscovery は、依存する必要がある電子情報開示ソリューションの数を減らすのに役立ちます。 Microsoft 365 内で発生する、効率化されたエンドツーエンドのワークフローを提供します。 Advanced eDiscovery は、固有のデータ ソースと共有データ ソースを関心のある人物 (保管担当者と呼ばれる) に自動的にマッピングし、分析と確認のために収集する前に、関連する可能性のあるデータに関するレポートと分析を提供することで、関連情報の潜在的なソースの特定と収集の問題を軽減するのに役立ちます。

さらに、Microsoft Graph API は、電子情報開示ワークフローを自動化し、カスタム ソリューションの Advanced eDiscovery を拡張するのに役立ちます。

## <a name="cull-data-intelligently"></a>データをインテリジェントにカイルする

Advanced eDiscovery のインテリジェントな機械学習機能は、レビューするデータの量を減らすのに役立ちます。 これらのインテリジェントな機能を使用すると、大量のデータを削減し、関連セットにカカル処理することができます。 たとえば、組み込みのレビュー セット クエリは、重複が近い場合に特定することで、一意のコンテンツのみをフィルター処理するのに役立ちます。 この機能を使用すると、確認するデータの量を大幅に削減できます。

その他の機械学習機能では、関連性モジュールのようなスマート タグやテクノロジ支援レビュー ツールを使用して、関連データをさらに絞り込み、特定できます。

## <a name="advanced-ediscovery-architecture"></a>Advanced eDiscovery アーキテクチャ

次の Advanced eDiscovery アーキテクチャ図は、単一地域環境と複数地域環境でのエンド 間ワークフローと、電子情報開示参照モデル (EDRM) に沿ったエンド 間のデータ フロー[](advanced-ediscovery-edrm.md)を示しています。

[![モデル ポスター: Microsoft 365 の Advanced eDiscovery アーキテクチャ](../media/solutions-architecture-center/ediscovery-poster-thumb.png)](../media/solutions-architecture-center/m365-advanced-ediscovery-architecture.png)

[画像として表示](../media/solutions-architecture-center/m365-advanced-ediscovery-architecture.png)

[PDF ファイルとしてダウンロードする](https://download.microsoft.com/download/d/1/c/d1ce536d-9bcf-4d31-b75b-fcf0dc560665/m365-advanced-ediscovery-architecture.pdf)

[Visio ファイルとしてダウンロードする](https://download.microsoft.com/download/d/1/c/d1ce536d-9bcf-4d31-b75b-fcf0dc560665/m365-advanced-ediscovery-architecture.vsdx)

Advanced eDiscovery のエンドツーエンド ワークフローの詳細については、この Microsoft Mechanics のビデオ [を参照してください](https://go.microsoft.com/fwlink/?linkid=2066133)。

## <a name="advanced-ediscovery-workflow"></a>Advanced eDiscovery ワークフロー

次のセクションでは、Microsoft 365 コンプライアンス センターの Advanced eDiscovery ツールの組み込みワークフローの各手順について説明します。 次のスクリーンショットは *、2020.11.03 - Contoso v. Fabrikam* という名前のケースの [概要] タブを示しています。 

![組み込みの Advanced eDiscovery ワークフローのタブ](../media/AeD-Case-Screenshot1.png)

詳細については、「Advanced eDiscovery ワークフローの管理 [」を参照してください](create-and-manage-advanced-ediscoveryv2-case.md#manage-the-workflow)。

### <a name="managing-custodians-and-non-custodial-data-sources"></a>カストディアンと保管されていないデータ ソースの管理

[データ ソース **]** タブを使用して、ケースに関心のある人物として特定した人物や、保管担当者に関連付けできない可能性のあるその他のデータ ソースを追加および管理します。 カストディアンまたは保管されていないデータ ソースを追加すると、保管担当者と保管されていないデータ ソースを法的に保留にしたり、保管担当者と通信したり、保管担当者や保管されていないデータ ソースを検索して、ケースに関連するコンテンツを収集したりするアクションをすばやく実行できます。 ケースが進むにつれて、新しい保管担当者や保管されていない日付ソースを追加したり、ケースから解放したりするのは簡単です。 詳細については、「カストディアン [との作業」を参照してください](managing-custodians.md)。

### <a name="managing-legal-hold-notifications"></a>法的情報保留通知の管理

[通信 **] タブ** を使用して、ケースの保管担当者と通信するプロセスを管理します。 法的情報保留通知は、カストディアンに対して、ケースに関連するすべてのコンテンツを保持するよう指示します。 法務チームは、保管担当者が受信、読み取り、確認した通知を追跡できる必要があります。 Advanced eDiscovery の通信ワークフローを使用すると、保管担当者が保留通知を確認できなかった場合に、最初の通知、リマインダー、リリース通知、エスカレーションを作成して送信できます。 詳細については、「通信の使用 [」を参照してください](managing-custodian-communications.md)。

### <a name="managing-content-preservation"></a>コンテンツ保持の管理

カストディアンをケースに追加すると、保管データを保留にできます。 [保留 **] タブ** を使用して、カストディアンを追加するときに作成された保留を管理し、ケースに関連付けられている他の法的情報保留を管理します。たとえば、保管されていないデータ ソースを特定して保留にできます。 ケース内の保留リストを編集してクエリ ベースの保留リストにし、クエリに一致するコンテンツのみを保持することもできます。 たとえば、保持された特定の日付内に作成されたコンテンツのみを保持するために、保留リストに日付範囲を追加できます。 保留にされているコンテンツに関する統計情報を取得したり、ケースに関連しなくなった後に保留リストを削除したり、保留リストを削除したりもできます。 詳細については、「保留の [管理」を参照してください](managing-holds.md)。

### <a name="indexing-custodian-data"></a>カストディアン データのインデックス作成

カストディアンと対応する保管データ ソースをケースに追加すると、カストディアン データ ソースから部分的にインデックスが作成されたアイテムは、高度なインデックス作成と呼ばれるプロセスによって再インデックス化 *されます*。 これにより、検索を実行してケースのデータを収集するときに、画像、サポートされていないファイルの種類、その他のインデックスのない可能性のあるコンテンツなどの保管コンテンツを完全に検索できます。 [処理 **] タブ** を使用して、高度なインデックス作成の状態を監視し、エラー修復と呼ばれるプロセスを使用して処理エラー *を修正します*。 詳細については、「修正処理エラー [」を参照してください](processing-data-for-case.md)。

### <a name="collecting-case-data"></a>ケース データの収集

[検索 **] タブを使用** して検索を作成し、ケースに関連するコンテンツのインサイト 保管データ ソースと保管されていないデータ ソースを検索します。 クエリ ベースの検索 (キーワードと条件を使用) を作成して実行し、ケースに関連する一連の電子メール メッセージとドキュメントを特定し、電子情報開示ワークフローの後続の手順でさらに確認および分析できます。 ケースに関連付けられた 1 つ以上の検索を作成できます。 また、検索ツールを使用してサンプル ドキュメントをプレビューし、検索結果の絞り込みと改善に役立つ検索統計を表示することもできます。 検索結果にケースに関連するすべてのデータが含まれている場合は、さらにレビュー、分析、およびカリングを行うレビュー セットに検索結果を追加します。 詳細については、「ケースの [データを収集する」を参照してください](collecting-data-for-ediscovery.md)。

### <a name="reviewing-and-analyzing-case-data"></a>ケース データの確認と分析

[ **レビュー セット] タブ** を使用して、ライブ システムから収集し、レビュー セットに追加したコンテンツを確認および分析します。 レビュー セットは、電子情報開示ワークフローの前のフェーズで収集した保管データ (および該当する場合は保管されていないデータ) のデータ (つまり、データのオフライン コピー) の静的なコレクションです。 検索結果をレビュー セットに追加すると、コンテナーからファイルを抽出し、メタデータを抽出し、テキストを抽出するプロセスがトリガーされます。 このプロセスが完了すると、保管担当者から収集されたデータの新しいインデックスが作成され、レビュー セットに追加されます。 レビュー セットにデータを追加した後、さらにクエリを実行してケース データを絞り込み、データをテキストまたはネイティブ ファイル形式で表示し、レビュー セット内のドキュメントに注釈、編集、タグを付けることもできます。 ドキュメントの重複、電子メールのスレッド処理、テーマの識別など、高度な分析を実行できます。 ケースに関連するデータのみを収集した後は、ドキュメントを直接ダウンロードするか、ファイル メタデータ、注釈、タグと共にエクスポートできます。 詳しくは、以下を参照してください。

- [レビュー セット内のドキュメントを表示する](view-documents-in-review-set.md)

- [レビュー セット内のデータをクエリする](review-set-search.md)

- [レビュー セット内のドキュメントをタグ付けする](tagging-documents.md)

- [レビュー セット内のデータを分析する](analyzing-data-in-review-set.md)

### <a name="exporting-data-for-review-and-presentation"></a>レビューおよびプレゼンテーション用のデータのエクスポート

レビュー セットからデータをエクスポートした後、[エクスポート]タブを使用してエクスポート ジョブを管理し、レビュー セットからデータをダウンロードします。 レビュー セットをエクスポートすると、データは Microsoft が提供する Azure Storage の場所 (または組織によって管理される Azure Storage の場所) にアップロードされます。 Azure にアップロードすると、ローカル コンピューターにダウンロードできます。 エクスポートされたデータをダウンロードするために必要なストレージ評価キーは、[エクスポート] タブ **で取得** できます。詳細については、「ケース データを [エクスポートする」を参照してください](exporting-data-ediscover20.md)。

### <a name="managing-jobs"></a>ジョブの管理

[ジョブ **] タブ** を使用して、開始したケース関連のタスクについて長時間実行されるプロセスを監視します。 ジョブの例としては、ケース データのインデックスの再作成、検索、エクスポートに関連するジョブがあります。 たとえば、[検索] タブに多数のデータソースを含む検索を作成すると、この検索プロセスの状態が [ジョブ] タブに **表示** されます。詳細については、「ジョブの管理 [」を参照してください](managing-jobs-ediscovery20.md)。

### <a name="configuring-case-settings"></a>ケース設定の構成

[設定 **] タブを** 使用して、ケース全体の設定を構成します。 これには、ケースへのメンバーの追加、ケースのクローズまたは削除、検索と分析の設定の構成が含まれます。 詳しくは、以下を参照してください。

- [ケースにメンバーを追加する](add-or-remove-members-from-a-case-in-advanced-ediscovery.md)

- [ケースを閉じるか、削除する](close-or-delete-case.md)

- [検索と分析の設定を構成する](configure-search-and-analytics-settings-in-advanced-ediscovery.md)
