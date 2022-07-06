---
title: Microsoft 365 で電子情報開示 (Premium) ケースを作成および管理する
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
ms.date: 04/08/2022
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- m365solution-aed
- m365initiative-compliance
- m365solution-scenario
ms.custom: admindeeplinkCOMPLIANCE
search.appverid:
- MOE150
- MET150
description: この記事では、Microsoft Purview eDiscovery (Premium) ケースを作成および管理する方法について説明します。 最初の手順では、ケースを作成し、電子情報開示 (Premium) の機能の使用を開始します。
ms.openlocfilehash: b8577a8d44cb6860cd595d3f2f13c731c290ba12
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66630369"
---
# <a name="create-and-manage-an-ediscovery-premium-case"></a>電子情報開示 (Premium) ケースの作成と管理

Microsoft Purview eDiscovery (Premium) を設定し、ケースを管理する組織内の[電子情報開示マネージャーにアクセス許可を割り当てた](get-started-with-advanced-ediscovery.md#step-2-assign-ediscovery-permissions)後、次の手順ではケースを作成して管理します。

この記事では、訴訟やその他の種類の調査でケースを使用して電子情報開示 (Premium) ワークフローを管理する方法の概要についても説明します。

## <a name="create-a-case"></a>ケースを作成する

次の手順を実行してケースを作成し、メンバーを追加します。 ケースを作成したユーザーは、メンバーとして自動的に追加されます。 ケースのメンバーは、Microsoft Purview コンプライアンス ポータルのケースにアクセスし、電子情報開示 (Premium) タスクを実行できます。

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">コンプライアンス ポータル</a>に移動し、電子情報開示アクセス許可が割り当てられているユーザー アカウントの資格情報を使用してサインインします。 組織管理役割グループのメンバーは、電子情報開示 (Premium) ケースを作成することもできます。

2. コンプライアンス ポータルの左側のナビゲーション ウィンドウで、[ **すべて表示**] をクリックし、[ **電子情報開示** > **の詳細設定**] を選択し、[  <a href="https://go.microsoft.com/fwlink/p/?linkid=2173764" target="_blank">**ケース** ] タブ</a>を選択します。

3. [**ケースを作成する**] を選択します。

4. [ **新しい電子情報開示ケース** ] ポップアップ ページで、ケースに名前 (必須) を指定し、省略可能なケース番号と説明を入力します。 ケース名は、組織内で一意である必要があります。

5. [ **保存] を** クリックしてケースを作成します。

   新しいケースが作成され、新しいケースの **[設定]** タブが表示されます。

6. [**設定]** タブの **[アクセス&アクセス許可**] タイルで、[**選択**] をクリックします。

7. [ **このケースの管理** ] ポップアップ ページの [ **メンバーの管理**] で、[ **追加** ] をクリックしてケースにメンバーを追加します。

8. ユーザーの一覧で、ケースに追加するユーザーの名前の横にあるチェック ボックスをオンにします。 前に説明したように、ケースに追加するユーザーに適切な電子情報開示アクセス許可が割り当てられていることを確認してください。

9. ケースのメンバーとして追加するユーザーを選択したら、[ **追加**] をクリックします。

10. [**このケースを管理**] で、[**保存**] をクリックして、ケース メンバーの新しいリストを保存します。

11. [ **ホーム** ] タブをクリックしてケースのホーム ページに移動します。

## <a name="manage-the-workflow"></a>ワークフローを管理する

電子情報開示 (Premium) の使用を開始するには、 [一般的な電子情報開示のプラクティス](advanced-ediscovery-edrm.md)に沿った基本的なワークフローを次に示します。 これらの各手順では、探索できる拡張電子情報開示 (Premium) 機能についても説明します。

![電子情報開示 (Premium) ワークフロー。](../media/AeDWorkflow.png)

1. **[カストディアン](add-custodians-to-case.md) と [非カストディアン データ ソース](non-custodial-data-sources.md) をケースに追加します**。 ケースを作成した後の最初の手順は、カストディアンを追加することです。 *カストディアン* とは、ケースに関連するドキュメントまたは電子ファイルの管理制御を持つユーザーです。 さらに、特定のユーザーに関連付けられていないが、ケースに関連する可能性があるデータ ソースを追加できます。

   ケースにカストディアンを追加するときに発生する (または実行できる) いくつかのことを次に示します。

   - カストディアンの Exchange メールボックス、OneDrive アカウント、およびカストディアンがメンバーである Microsoft Teams または Yammer グループ内のデータは、ケースの保管データとして "マーク" できます。
  
   - カストディアン データのインデックスが再作成されます ( *高度なインデックス* 作成と呼ばれるプロセスによって)。 これにより、次の手順で検索を最適化できます。
  
   - 保管担当者データに保留を配置できます。 これにより、調査中にケースに関連する可能性があるデータが保持されます。
  
   - カストディアンのメールボックスや OneDrive アカウントのデータと同様に、他のデータ ソースをカストディアンに関連付けることができます (たとえば、SharePoint サイトまたは Microsoft 365 グループをカストディアンに関連付けることができます)。

   - 電子情報開示 (Premium) の [通信ワークフロー](managing-custodian-communications.md) を使用して、訴訟ホールド通知をカストディアンに送信できます。

2. **[データ ソースから関連するコンテンツを収集します](create-draft-collection.md)**。 ケースにカストディアンと非保管データ ソースを追加した後、組み込みのコレクション ツールを使用して、ケースに関連する可能性のあるコンテンツをこれらのデータ ソースで検索します。 キーワード、プロパティ、および条件を使用して、ケースに最も関連する可能性が高いデータで検索結果を返す検索 [クエリを作成](building-search-queries.md) します。 以下のことも実行できます。

   - [コレクションを](collection-statistics-reports.md)絞り込んで結果を絞り込むのに役立つコレクション統計を表示します。

   - コレクションのサンプルをプレビューして、関連するデータが見つかったかどうかを迅速に確認します。

   - クエリを修正し、コレクションを再実行します。

3. **[コレクションをレビュー セットにコミットします](commit-draft-collection.md)**。 検索で目的のデータが返されることを構成して確認したら、次の手順では検索結果をレビュー セットに追加します。 レビュー セットにデータを追加すると、アイテムは元の場所から安全な Azure Storage の場所にコピーされます。 レビュー セット内の項目を確認および分析するときに、データのインデックスが再作成され、徹底的かつ迅速な検索のために最適化されます。 また、[Office 365以外のデータをレビュー セットに追加](load-non-office-365-data-into-a-review-set.md)することもできます。

   また、会話レビュー セットと呼ばれる、データを追加できる特別な種類の *レビュー セット* もあります。 これらの種類のレビュー セットは、Microsoft Teams のようなスレッド会話を再構築、レビュー、エクスポートするための会話再構築機能を提供します。 詳細については、「 [電子情報開示 (Premium) で会話を確認する」](conversation-review-sets.md)を参照してください。

4. **レビュー セット内のデータを確認して分析します**。 データがレビュー セットに含まれるようになったので、さまざまなツールと機能を使用してケース データを表示および分析し、データ セットを調査対象のケースに最も関連するものに減らすことを目的としています。 このプロセスで使用できるツールと機能の一覧を次に示します。

   - [ドキュメントを表示します](view-documents-in-review-set.md)。 これには、レビュー セット内の各ドキュメントのメタデータの表示と、ネイティブ バージョンまたはテキスト バージョンでのドキュメントの表示が含まれます。

   - [クエリとフィルターを作成します](review-set-search.md)。 さまざまな検索条件を使用して検索クエリを作成します (ケース データをさらに絞り込み、ケースに最も関連するものにカリングするためにすべての [ファイル メタデータ プロパティ](document-metadata-fields-in-advanced-ediscovery.md) を検索する機能を含む)。 また、レビュー セット フィルターを使用して、検索クエリの結果に他の条件をすばやく適用して、それらの結果をさらに絞り込むこともできます。 

   - [タグを作成して使用します](tagging-documents.md)。 レビュー セット内のドキュメントにタグを適用して、応答性の高いドキュメント (またはケースに対して応答しない) を特定し、検索クエリを作成するときにそれらのタグを使用して、タグ付けされたドキュメントを含めたり除外したりできます。 また、タグ付けを使用して、エクスポートするドキュメントを決定することもできます。

   - [ドキュメントに注釈を付け、編集します](view-documents-in-review-set.md#annotate-view)。 レビューで注釈ツールを使用すると、ドキュメントに注釈を付け、ドキュメント内のコンテンツを作業製品として編集できます。 レビュー中に注釈付きまたは編集されたドキュメントの PDF バージョンを生成して、ドキュメントの未編集のネイティブ バージョンをエクスポートするリスクを軽減します。

   - [ケース データを分析します](analyzing-data-in-review-set.md)。 電子情報開示 (Premium) の分析機能は強力です。 レビュー セット内のデータに対して分析を実行すると、ほぼ重複検出、電子メール スレッド、レビューする必要があるドキュメントの量を減らすのに役立つテーマなどの分析が実行されます。 また、分析を実行した結果をまとめた分析レポートも生成されます。 前述のように、分析を実行すると [、弁護士とクライアントの特権検出モデル](attorney-privilege-detection.md#use-the-attorney-client-privilege-detection-model)も実行されます。

5. **ケース データをエクスポートしてダウンロードします**。 ケース データを収集、レビュー、分析した後の最後の手順は、外部レビューや調査チームの外部のユーザーによるレビューのために電子情報開示 (Premium) からエクスポートすることです。 データのエクスポートは 2 段階のプロセスです。 最初の手順は、レビュー セットからデータを [エクスポート](export-documents-from-review-set.md) し、別の Azure Storage の場所 (Microsoft が提供する場所、または組織によって管理されている場所) にコピーすることです。 次に、Azure Storage Explorerを使用してデータをローカル コンピューターに[ダウンロード](download-export-jobs.md)します。 エクスポートされたデータ ファイルに加えて、エクスポート パッケージの内容には、エクスポート レポート、概要レポート、エラー レポートも含まれます。

## <a name="ediscovery-premium-architecture"></a>電子情報開示 (Premium) アーキテクチャ

単一地域環境と複数地域環境における電子情報開示 (Premium) のエンド ツー エンド ワークフローと、 [電子検出参照モデル](overview-ediscovery-20.md#ediscovery-premium-alignment-with-the-electronic-discovery-reference-model)に合わせたエンド ツー エンドのデータ フローを示すアーキテクチャ図を次に示します。

[![モデル ポスター: Microsoft 365 の電子情報開示 (Premium) アーキテクチャ。](../media/solutions-architecture-center/ediscovery-poster-thumb.png)](../media/solutions-architecture-center/m365-advanced-ediscovery-architecture.png)

[イメージとして表示する](../media/solutions-architecture-center/m365-advanced-ediscovery-architecture.png)

[PDF ファイルとしてダウンロードする](https://download.microsoft.com/download/d/1/c/d1ce536d-9bcf-4d31-b75b-fcf0dc560665/m365-advanced-ediscovery-architecture.pdf)

[Visio ファイルとしてダウンロードする](https://download.microsoft.com/download/d/1/c/d1ce536d-9bcf-4d31-b75b-fcf0dc560665/m365-advanced-ediscovery-architecture.vsdx)
