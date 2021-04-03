---
title: 組織の Azure Storage アカウントにドキュメントをエクスポートする
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom: seo-marvel-mar2020
description: レビュー セット内のドキュメントを Azure Storage アカウントにエクスポートし、Azure Storage Explorer を使用してローカル コンピューターにダウンロードします。
ms.openlocfilehash: dfb3892f31e857d4744f6da337c924efaa87ab11
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574729"
---
# <a name="export-documents-in-a-review-set-to-an-azure-storage-account"></a>レビュー セット内のドキュメントを Azure Storage アカウントにエクスポートする

Advanced eDiscovery ケースのレビュー セットからドキュメントをエクスポートする場合は、組織が管理する Azure Storage アカウントにドキュメントをエクスポートできます。 このオプションを使用した場合、ドキュメントは Azure Storage の場所にアップロードされます。 ドキュメントがエクスポートされた後は、Azure Storage Explorer を使用してドキュメントにアクセス (およびローカル コンピューターまたは他の場所にダウンロード) できます。 この記事では、ドキュメントを Azure Storage アカウントにエクスポートする方法と、Azure Storage Explorer を使用して Azure Storage の場所に接続してエクスポートされたドキュメントをダウンロードする方法について説明します。 Azure Storage Explorer の詳細については、「Use Azure Storage [Explorer」を参照してください](/azure/storage/blobs/storage-quickstart-blobs-storage-explorer)。

## <a name="before-you-export-documents-from-a-review-set"></a>レビュー セットからドキュメントをエクスポートする前に

- レビュー セットからドキュメントをエクスポートするには、Azure Storage アカウントの共有アクセス署名 (SAS) トークンと、ストレージ アカウント内の特定のコンテナーの URL を指定する必要があります。 手順 2 を実行する際は、必ず手に (たとえば、テキスト ファイルにコピーする) 必要があります。

  - **SAS トークン**: SAS トークンを取得するには、Azure Storage アカウント用 (コンテナー用ではなく) を取得してください。 Azure Storage でアカウントの SAS トークンを生成できます。 これを行うには、Azure Storage アカウントに移動し、[ストレージ アカウント]ブレードの [設定] で [アクセス署名の共有] を選択します。 SAS トークンを生成するときに、既定の設定を使用し、すべてのリソースの種類を許可します。

  - **コンテナー URL**: レビュー セットドキュメントをアップロードするコンテナーを作成し、そのコンテナーの URL のコピーを取得する必要があります。たとえば、 `https://ediscoverydata.blob.core.windows.net/exportdata` . URL を取得するには、Azure Storage のコンテナーに移動し、コンテナーブレードの [設定] セクションの [プロパティ] を選択します。

- Azure Storage Explorer をダウンロードしてインストールします。 手順については [、「Azure Storage Explorer ツール」を参照してください](https://go.microsoft.com/fwlink/p/?LinkId=544842)。 このツールを使用して、Azure Storage アカウントのコンテナーに接続し、手順 1 でエクスポートしたドキュメントをダウンロードします。

## <a name="step-1-export-the-documents-from-a-review-set"></a>手順 1: レビュー セットからドキュメントをエクスポートする

最初の手順は、レビュー セットからドキュメントをエクスポートするエクスポート ジョブを作成します。 すべてのエクスポート オプションの詳細な手順については、「レビュー セットからドキュメントをエクスポート [する」を参照してください](export-documents-from-review-set.md)。 次の手順では、組織の Azure Storage アカウントにドキュメントをエクスポートする設定を強調表示します。

1. Microsoft 365 コンプライアンス センターで、高度な電子情報開示ケースを開き、[レビュー セット] タブを選択し、エクスポートするレビュー セットを選択します。

2. レビュー セットで、[アクションのエクスポート]**を**  >  **クリックします**。

3. [エクスポート **オプション] フライ** アウト ページで、エクスポートの名前 (必須) と説明 (オプション) を入力します。

4. ドキュメント、メタデータ、コンテンツ、およびオプションセクションの設定を構成します。 これらの設定の詳細については、「レビュー セットからドキュメントをエクスポート [する」を参照してください](export-documents-from-review-set.md)。

5. [出力 **オプション] セクション** で **、[Azure Storage アカウント** にエクスポートされた圧縮ディレクトリ構造] オプションを選択します。

6. 対応するフィールドにストレージ アカウントのコンテナー URL と SAS トークンを貼り付けます。

   ![接続 URL と SAS トークンを対応するフィールドに貼り付ける](../media/AzureStorageOutputOptions.png)

7. [エクスポート **] を** クリックしてエクスポート ジョブを作成します。

## <a name="step-2-obtain-the-sas-url-from-the-export-job"></a>手順 2: エクスポート ジョブから SAS URL を取得する

次の手順では、手順 1 でエクスポート ジョブを作成した後に生成される SAS URL を取得します。 SAS URL を使用して、レビュー セット ドキュメントをエクスポートした Azure Storage アカウントのコンテナーに接続します。

1. [高度 **な電子情報開示] ページ** で、ケースに移動し、[エクスポート] タブ **をクリック** します。

2. [**エクスポート**]タブで、ダウンロードするエクスポートジョブをクリックします。 これは、手順 1 で作成したエクスポート ジョブです。

3. [フライアウト] ページの [場所] **で**、表示される SAS URL をコピーします。 必要に応じて、テキスト ファイルに保存して、手順 3 でアクセスできます。

   ![[場所] の下に表示される SAS URL をコピーする](../media/eDiscoExportJob.png)

   > [!TIP]
   > エクスポート ジョブに表示される SAS URL は、コンテナー URL と Azure Storage アカウントの SAS トークンの連結です。 エクスポート ジョブからコピーするか、URL と SAS トークンを組み合わせて作成できます。

## <a name="step-3-connect-to-the-azure-storage-container"></a>手順 3: Azure Storage コンテナーに接続する

最後に、Azure Storage Explorer と SAS URL を使用して Azure Storage アカウントのコンテナーに接続し、エクスポートされたドキュメントをローカル コンピューターにダウンロードします。

1. ダウンロードしてインストールした Azure Storage Explorer を起動します。

2. [接続ダイアログ **を開く] アイコンを** クリックします。

   ![[アカウントの追加] アイコンをクリックします。](../media/AzureStorageConnect.png)

3. [Azure **ストレージへの接続] ページで、[BLOB** コンテナー] **をクリックします**。

4. [認証方法 **の選択] ページ** で、[共有アクセス署名 **(SAS)** ] オプションを選択し、[次へ] を **クリックします**。

5. [接続 **情報の入力]** ページで、[BLOB コンテナーの SAS URL] ボックスに SAS URL (手順 2 のエクスポート ジョブで取得した) **を貼り付** けます。

    ![[URI] ボックスに SAS URL を貼り付ける](../media/AzureStorageConnect3.png)

    コンテナー名が [表示名] ボックス **に表示されます** 。 この名前は編集できます。

6. [ **次へ]** をクリックして **概要ページを表示** し、[接続] を **クリックします**。

    [Blob **コンテナー]** ノード **([ストレージ アカウント**  >  **] (接続されたコンテナー) が** \> 開きます。

    ![Blobs コンテナー ノードのジョブのエクスポート](../media/AzureStorageConnect5.png)

    手順 5 の表示名を持つコンテナーが含まれる。 このコンテナーには、Azure Storage アカウントのコンテナーにダウンロードしたエクスポート ジョブごとにフォルダーが含まれる。 これらのフォルダーの名前は、エクスポート ジョブの ID に対応する ID です。 これらのエクスポートの ID (およびエクスポートの名前) は、[高度な電子情報開示] ケースの [ジョブ] タブに一覧表示されているエクスポートジョブの各準備データのフライアウト ページの [サポート情報] にあります。 

7. エクスポート ジョブ フォルダーをダブルクリックして開きます。

   フォルダーとエクスポート レポートの一覧が表示されます。

    ![エクスポート フォルダーには、エクスポートされたファイルとエクスポート レポートが含まれる](../media/AzureStorageConnect6.png)

8. エクスポート ジョブからすべてのコンテンツをエクスポートするには、上矢印をクリックしてエクスポート ジョブ フォルダーに戻り、[ダウンロード] を **クリックします**。

9. エクスポートしたファイルをダウンロードする場所を指定して、[フォルダを選択]をクリックします。

    Azure Storage Explorer は、ダウンロード プロセスを開始します。 エクスポートしたアイテムのダウンロードの状態が [アクティビティ] ウィンドウ **に表示** されます。 ダウンロードが完了すると、メッセージが表示されます。

> [!NOTE]
> Azure Storage Explorer でエクスポート ジョブ全体をダウンロードする代わりに、ダウンロードして表示する特定のアイテムを選択できます。

## <a name="more-information"></a>詳細情報

- エクスポート ジョブ フォルダーには、次の項目が含まれます。 エクスポート フォルダー内の実際のアイテムは、エクスポート ジョブの作成時に構成されたエクスポート オプションによって決まります。 これらのオプションの詳細については、「レビュー セットからドキュメントをエクスポート [する」を参照してください](export-documents-from-review-set.md)。

  - Export_load_file.csv: この CSV ファイルは、エクスポートされた各ドキュメントに関する情報を含む詳細エクスポート レポートです。 ファイルは、ドキュメントの各メタデータ プロパティの列で構成されます。 このレポートに含まれるメタデータの一覧と説明については、「Advanced eDiscoveryのドキュメント メタデータ フィールド」の表の「エクスポートされたフィールド名」[列を参照してください](document-metadata-fields-in-advanced-ediscovery.md)。

  - Summary.txt: エクスポート統計を含むエクスポートの概要を含むテキスト ファイル。

  - Extracted_text_files: このフォルダーには、エクスポートされた各ドキュメントのテキスト ファイル バージョンが含まれる。

  - NativeFiles: このフォルダーには、エクスポートされた各ドキュメントのネイティブ ファイル バージョンが含まれる。

  - Error_files: エクスポート ジョブにエラー ファイルが含まれている場合、このフォルダーには次の項目が含まれます。

    - ExtractionError.csv: この CSV ファイルには、親アイテムから適切に抽出されていないファイルに使用可能なメタデータが含まれています。

    - ProcessingError: このフォルダーには、処理エラーのあるドキュメントが含まれています。 このコンテンツはアイテム レベルです。つまり、添付ファイルに処理エラーが発生した場合、添付ファイルを含むドキュメントもこのフォルダーに含まれます。
