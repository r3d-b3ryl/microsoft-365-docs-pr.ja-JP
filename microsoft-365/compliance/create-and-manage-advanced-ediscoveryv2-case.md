---
title: Microsoft 365 での Advanced eDiscovery ケースの作成と管理
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-aed
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: この記事では、Advanced eDiscovery ケースを作成および管理する方法について説明します。 最初の手順では、ケースを作成し、Advanced eDiscovery の機能の使用を開始します。
ms.openlocfilehash: c95994b3706880b40ff6306c02a4bdb5dba7748b
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841622"
---
# <a name="create-and-manage-an-advanced-ediscovery-case"></a>Advanced eDiscovery ケースの作成と管理

Advanced eDiscovery を設定し、ケースを管理する組織内の [電子](get-started-with-advanced-ediscovery.md#step-2-assign-ediscovery-permissions) 情報開示管理者にアクセス許可を割り当て終わると、次の手順はケースの作成と管理です。

この記事では、法的調査のためにケースを使用して Advanced eDiscovery ワークフローを管理する方法の概要も説明します。

## <a name="create-a-case"></a>ケースを作成する

ケースを作成してメンバーを追加するには、次の手順を実行します。 ケースを作成したユーザーは、自動的にメンバーとして追加されます。

1. 電子情報開示 [https://compliance.microsoft.com](https://compliance.microsoft.com) のアクセス許可が割り当てられているユーザー アカウントの資格情報を使用して、アクセスしてサインインします。 組織の管理役割グループのメンバーは、Advanced eDiscovery ケースを作成することもできます。

2. Microsoft 365 コンプライアンス センターの左側のナビゲーション ウィンドウで、[**すべてを表示**] をクリックし、**[eDiscovery] > [Advanced]** をクリックします。

3. [Advanced **eDiscovery] ページで** 、[ **ケース** ] タブをクリックし、[ケースの **作成] をクリックします**。

4. [ **新しい電子情報開示ケース** ] フライアウト ページで、ケースに名前 (必須) を付け、オプションのケース番号と説明を入力します。 ケース名は、組織内で一意である必要があります。

5. [ **保存] を** クリックしてケースを作成します。

   新しいケースが作成され、新しいケース **の** [設定] タブが表示されます。

6. In the **Access & permissions** tile on the **Settings** tab, click **Select,** and then click **Update**.

7. **[更新]** をクリックします。

8. [このケース **の管理]** フライアウトページの [メンバーの管理] で、[追加]**をクリックして** ケースにメンバーを追加します。

9. ユーザーの一覧で、ケースに追加するユーザーの名前の横にあるチェック ボックスをオンにします。 前に説明したように、ケースに追加するユーザーに適切な電子情報開示のアクセス許可が割り当てられている必要があります。

10. ケースのメンバーとして追加するユーザーを選択した後、[追加] をクリック **します**。

11. [**このケースを管理**] で、[**保存**] をクリックして、ケース メンバーの新しいリストを保存します。

12. [ホーム **] タブ** をクリックして、ケースのホーム ページに移動します。

## <a name="manage-the-workflow"></a>ワークフローを管理する

Advanced eDiscovery の使用を開始するには、一般的な電子情報開示のプラクティスに沿った基本的 [なワークフローを次に示します](advanced-ediscovery-edrm.md)。 これらの各手順では、探索できる拡張された Advanced eDiscovery 機能もいくつか説明します。

![Advanced eDiscovery ワークフロー](../media/AeDWorkflow.png)

1. **[カストディアンと](add-custodians-to-case.md) 保管 [されていないデータ](non-custodial-data-sources.md) ソースをケースに追加します**。 ケースを作成した後の最初の手順は、カストディアンを追加します。 保管 *担当者とは* 、ケースに関連する可能性のあるドキュメントまたは電子ファイルの管理制御を持つ人物です。 さらに、特定のユーザーには関連付けされていないが、ケースに関連する可能性があるデータ ソースを追加できます。

   カストディアンをケースに追加すると、次のことが起こります (または実行できます)。

   - 保管担当者の Exchange メールボックス、OneDrive アカウント、および保管担当者がメンバーである Microsoft Teams または Yammer グループのデータは、ケース内の保管データとして 「マーク」できます。
  
   - 保管担当者のデータは、(高度なインデックス作成と呼ばれるプロセスによって) *再インデックス化されます*。 これは、次の手順で検索を最適化するのに役立ちます。
  
   - 保管担当者のデータを保留にできます。 これにより、調査中にケースに関連する可能性のあるデータが保持されます。
  
   - 他のデータ ソースを保管担当者に関連付けることができます (たとえば、SharePoint サイトまたは Microsoft 365 グループを保管担当者に関連付けることができます)。これにより、保管担当者のメールボックスまたは OneDrive アカウントのデータと同様に、このデータのインデックスを再作成したり、保留にしたり、検索することができます。

   - Advanced eDiscovery の [通信ワークフロー](managing-custodian-communications.md) を使用して、保管担当者に法的情報保留通知を送信できます。

2. **[ケースに関連するデータのデータ ソースを検索します](collecting-data-for-ediscovery.md)**。 カストディアンと保管されていないデータ ソースをケースに追加した後、組み込みの検索ツールを使用して、これらのデータ ソースでケースに関連する可能性のあるデータを検索します。 キーワード、プロパティ、条件を使用して、ケース[](building-search-queries.md)に最も関連する可能性が高いデータを含む検索結果を返す検索クエリを作成します。 以下のことも実行できます。

   - 検索 [クエリを絞](search-statistics-in-advanced-ediscovery.md) り込み、結果を絞り込むのに役立つ検索統計を表示します。

   - 検索結果をプレビューして、関連するデータが見つかったかどうかを迅速に確認します。

   - クエリを修正し、検索を再実行します。

3. **[レビュー セットにデータを追加します](add-data-to-review-set.md)**。 検索が目的のデータを返す構成と検証が完了したら、次の手順では、検索結果をレビュー セットに追加します。 レビュー セットにデータを追加すると、アイテムは元の場所からセキュリティで保護された Azure Storage の場所にコピーされます。 データは再インデックス化され、レビュー セット内のアイテムを確認および分析するときに、徹底的かつ迅速な検索に最適化されます。 さらに、レビュー セットに [365 Office以外のデータを追加できます](load-non-office-365-data-into-a-review-set.md)。

   また、会話レビュー セットと呼ばれる、データを追加できる特別な *種類のレビュー セットがあります*。 これらの種類のレビュー セットは、Microsoft Teams のようなスレッド会話を再構築、レビュー、エクスポートする会話再構築機能を提供します。 詳細については [、「Advanced eDiscovery での会話の確認」を参照してください](conversation-review-sets.md)。

4. **レビュー セット内のデータを確認および分析します**。 これで、データはレビュー セットに含まれています。さまざまなツールと機能を使用して、調査中のケースに最も関連のあるデータ セットにデータ セットを減らすことを目標に、ケース データを表示および分析できます。 このプロセスで使用できるいくつかのツールと機能の一覧を次に示します。

   - [ドキュメントを表示します](view-documents-in-review-set.md)。 これには、レビュー セット内の各ドキュメントのメタデータの表示、ネイティブ バージョンまたはテキスト バージョンでのドキュメントの表示が含まれます。

   - [クエリとフィルターを作成します](review-set-search.md)。 さまざまな検索条件 (すべてのファイル メタデータ プロパティを検索する機能を含 [む)](document-metadata-fields-in-advanced-ediscovery.md)を使用して検索クエリを作成し、ケース データをさらに絞り込み、ケースに最も関連のあるものに絞り込む。 レビュー セット フィルターを使用して、検索クエリの結果に他の条件をすばやく適用し、さらに結果を絞り込む方法も使用できます。 

   - [タグを作成して使用します](tagging-documents.md)。 レビュー セット内のドキュメントにタグを適用して、応答するドキュメント (またはケースに対して応答しないタグ) を特定し、タグ付けされたドキュメントを含めるまたは除外する検索クエリを作成するときにそれらのタグを使用できます。 また、タグを付け、エクスポートするドキュメントを決定できます。

   - [ドキュメントに注釈を付け、変更します](view-documents-in-review-set.md#annotate-view)。 レビューで注釈ツールを使用すると、ドキュメントに注釈を付け、ドキュメント内のコンテンツを作業生産物として編集できます。 レビュー中に注釈付きまたは編集されたドキュメントの PDF バージョンを生成し、未編集のネイティブ バージョンのドキュメントをエクスポートするリスクを軽減します。

   - [ケース データを分析します](analyzing-data-in-review-set.md)。 Advanced eDiscovery の分析機能は強力です。 レビュー セット内のデータに対して分析を実行すると、ほぼ重複する検出、メールスレッド、テーマなどの分析が実行され、確認する必要があるドキュメントの量を減らすのに役立ちます。 また、分析を実行した結果を要約する分析レポートも生成します。 前に説明したように、分析を実行すると、弁護士/依頼人 [特権の検出モデルも実行されます](attorney-privilege-detection.md#use-the-attorney-client-privilege-detection-model)。

5. **ケース データをエクスポートおよびダウンロードします**。 ケース データを収集、確認、および分析した後の最後の手順は、外部レビュー用に Advanced eDiscovery からエクスポートするか、調査チーム外のユーザーによるレビュー用にエクスポートすることです。 データのエクスポートは、2 段階のプロセスです。 最初の手順は、[](export-documents-from-review-set.md)レビュー セットからデータをエクスポートし、別の Azure Storage の場所 (Microsoft によって提供される場所または組織によって管理されている場所) にコピーすることです。 次に、Azure Storage Explorer を使用 [してデータ](download-export-jobs.md) をローカル コンピューターにダウンロードします。 エクスポートされたデータ ファイルに加えて、エクスポート パッケージの格納には、エクスポート レポート、概要レポート、およびエラー レポートも含まれます。