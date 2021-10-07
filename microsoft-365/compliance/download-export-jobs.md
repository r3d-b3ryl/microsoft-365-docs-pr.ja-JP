---
title: 組織のアカウントにドキュメントをAzure Storageする
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom: seo-marvel-mar2020
description: レビュー セット内のドキュメントを Azure Storage アカウントにエクスポートし、Azure Storage Explorerを使用してローカル コンピューターにダウンロードします。
ms.openlocfilehash: 8f3110ef386fd5c5d8adc641aa223435caf0da67
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60203125"
---
# <a name="export-documents-in-a-review-set-to-an-azure-storage-account"></a>レビュー セット内のドキュメントをアカウントにAzure Storageする

Advanced eDiscovery ケースのレビュー セットからドキュメントをエクスポートする場合は、組織が管理する Azure Storage アカウントにエクスポートできます。 このオプションを使用すると、ドキュメントはユーザーの場所にAzure Storageされます。 ドキュメントをエクスポートした後、ドキュメントにアクセスし (ローカル コンピューターまたは他の場所にダウンロードする) には、Azure Storage Explorer。 この記事では、Azure Storage アカウントにドキュメントをエクスポートする方法と、Azure Storage Explorer を使用して Azure Storage の場所に接続してエクスポートされたドキュメントをダウンロードする方法について説明します。 詳細については、「Use [Azure Storage Explorer」を参照Azure Storage Explorer。](/azure/storage/blobs/storage-quickstart-blobs-storage-explorer)

## <a name="before-you-export-documents-from-a-review-set"></a>レビュー セットからドキュメントをエクスポートする前に

- レビュー セットからドキュメントをエクスポートするには、Azure Storage アカウントの共有アクセス署名 (SAS) トークンと、ストレージ アカウント内の特定のコンテナーの URL を指定する必要があります。 手順 2 を実行する際は、必ず手に (たとえば、テキスト ファイルにコピーする) 必要があります。

  - **SAS トークン**: SAS トークンを取得するには、必ず、Azure Storageアカウント用 (コンテナー用ではなく) を取得してください。 アカウントの SAS トークンを生成するには、Azure Storage。 これを行うには、Azure Storage アカウントに移動し、[ストレージ アカウント]ブレードの [設定設定]**で [アクセス署名の** 共有] を選択します。 SAS トークンを生成するときに、既定の設定を使用し、すべてのリソースの種類を許可します。

  - **コンテナー URL**: レビュー セットドキュメントをアップロードするコンテナーを作成し、そのコンテナーの URL のコピーを取得する必要があります。たとえば、 `https://ediscoverydata.blob.core.windows.net/exportdata` . URL を取得するには、Azure Storage のコンテナーに移動し、コンテナー ブレードの [設定] セクション **で [** プロパティ] を選択します。

- アプリケーションをダウンロードしてインストールAzure Storage Explorer。 手順については[、「Azure Storage Explorer」を参照してください](https://go.microsoft.com/fwlink/p/?LinkId=544842)。 このツールを使用して、Azure Storageアカウントのコンテナーに接続し、手順 1 でエクスポートしたドキュメントをダウンロードします。

## <a name="step-1-export-the-documents-from-a-review-set"></a>手順 1: レビュー セットからドキュメントをエクスポートする

最初の手順は、レビュー セットからドキュメントをエクスポートするエクスポート ジョブを作成します。 すべてのエクスポート オプションの詳細な手順については、「レビュー セットからドキュメントをエクスポート [する」を参照してください](export-documents-from-review-set.md)。 次の手順では、組織のアカウントにドキュメントをエクスポートする設定Azure Storageします。

1. 次のMicrosoft 365 コンプライアンス センターケースを開Advanced eDiscovery、[レビュー セット] タブを選択し、エクスポートするレビュー セットを選択します。

2. レビュー セットで、[アクションのエクスポート]**を**  >  **クリックします**。

3. [エクスポート **オプション] フライ** アウト ページで、エクスポートの名前 (必須) と説明 (オプション) を入力します。

4. ドキュメント、メタデータ、コンテンツ、およびオプションセクションの設定を構成します。 これらの設定の詳細については、「レビュー セットからドキュメントをエクスポート [する」を参照してください](export-documents-from-review-set.md)。

5. [出力 **オプション] セクション** で、[アカウントにエクスポートされた圧縮ディレクトリ構造 **Azure Storage選択** します。

6. 対応するフィールドにストレージ アカウントのコンテナー URL と SAS トークンを貼り付けます。

   ![接続 URL と SAS トークンを対応するフィールドに貼り付けます。](../media/AzureStorageOutputOptions.png)

7. [エクスポート **] を** クリックしてエクスポート ジョブを作成します。

## <a name="step-2-obtain-the-sas-url-from-the-export-job"></a>手順 2: エクスポート ジョブから SAS URL を取得する

次の手順では、手順 1 でエクスポート ジョブを作成した後に生成される SAS URL を取得します。 SAS URL を使用して、レビュー セット ドキュメントをエクスポートAzure Storageアカウント内のコンテナーに接続します。

1. [ファイルの **Advanced eDiscovery]** ページで、ケースに移動し、[エクスポート] タブ **をクリック** します。

2. [**エクスポート**]タブで、ダウンロードするエクスポートジョブをクリックします。 これは、手順 1 で作成したエクスポート ジョブです。

3. [フライアウト] ページの [場所] **で**、表示される SAS URL をコピーします。 必要に応じて、テキスト ファイルに保存して、手順 3 でアクセスできます。

   ![[場所] の下に表示される SAS URL をコピーします。](../media/eDiscoExportJob.png)

   > [!TIP]
   > エクスポート ジョブに表示される SAS URL は、コンテナー URL と、ユーザーアカウントの SAS トークンAzure Storageです。 エクスポート ジョブからコピーするか、URL と SAS トークンを組み合わせて作成できます。

## <a name="step-3-connect-to-the-azure-storage-container"></a>手順 3: ConnectコンテナーにAzure Storageする

最後に、Azure Storage Explorer と SAS URL を使用して Azure Storage アカウントのコンテナーに接続し、エクスポートしたドキュメントをローカル コンピューターにダウンロードします。

1. ダウンロードしてインストールAzure Storage Explorerを開始します。

2. [開く **] ダイアログ Connectクリック** します。

   ![[アカウントの追加] アイコンをクリックします。](../media/AzureStorageConnect.png)

3. [アクセスする **Connect] ページAzure Storage** Blob コンテナー]**をクリックします**。

4. [認証方法 **の選択] ページ** で、[共有アクセス署名 **(SAS)** ] オプションを選択し、[次へ] を **クリックします**。

5. [接続 **情報の入力]** ページで、[BLOB コンテナーの SAS URL] ボックスに SAS URL (手順 2 のエクスポート ジョブで取得した) **を貼り付** けます。

    ![[URI] ボックスに SAS URL を貼り付けます。](../media/AzureStorageConnect3.png)

    コンテナー名が [表示名] ボックス **に表示されます** 。 この名前は編集できます。

6. [**次へ]** をクリックして **概要ページを表示** し、[次へ]**をConnect。**

    Blob **コンテナー ノード**([アカウント] の **Storage**  >  **(接続されたコンテナー)** \> が開きます。

    ![Blobs コンテナー ノードのジョブをエクスポートします。](../media/AzureStorageConnect5.png)

    手順 5 の表示名を持つコンテナーが含まれる。 このコンテナーには、エクスポート アカウントのコンテナーにダウンロードしたエクスポート ジョブごとにフォルダー Azure Storageされます。 これらのフォルダーの名前は、エクスポート ジョブの ID に対応する ID です。 これらのエクスポートの ID (およびエクスポートの名前) は、Advanced eDiscovery ケースの [ジョブ] タブに一覧表示されているエクスポート ジョブの各準備データのフライアウト ページの [サポート情報] にあります。 

7. エクスポート ジョブ フォルダーをダブルクリックして開きます。

   フォルダーとエクスポート レポートの一覧が表示されます。

    ![エクスポート フォルダーには、エクスポートされたファイルとエクスポート レポートが含まれる。](../media/AzureStorageConnect6.png)

8. エクスポート ジョブからすべてのコンテンツをエクスポートするには、上矢印をクリックしてエクスポート ジョブ フォルダーに戻り、[ダウンロード] を **クリックします**。

9. エクスポートしたファイルをダウンロードする場所を指定して、[フォルダを選択]をクリックします。

    このAzure Storage Explorerダウンロード プロセスを開始します。 エクスポートしたアイテムのダウンロードの状態が [アクティビティ] ウィンドウ **に表示** されます。 ダウンロードが完了すると、メッセージが表示されます。

> [!NOTE]
> エクスポート ジョブ全体をダウンロードする代わりにAzure Storage Explorerダウンロードして表示する特定のアイテムを選択できます。

## <a name="more-information"></a>詳細情報

- エクスポート ジョブ フォルダーには、次の項目が含まれます。 エクスポート フォルダー内の実際のアイテムは、エクスポート ジョブの作成時に構成されたエクスポート オプションによって決まります。 これらのオプションの詳細については、「レビュー セットからドキュメントをエクスポート [する」を参照してください](export-documents-from-review-set.md)。

  - Export_load_file.csv: この CSV ファイルは、エクスポートされた各ドキュメントに関する情報を含む詳細エクスポート レポートです。 ファイルは、ドキュメントの各メタデータ プロパティの列で構成されます。 このレポートに含まれるメタデータの一覧と説明については、「ドキュメント メタデータ フィールド」の表の「エクスポートされたフィールド名」列を参照[Advanced eDiscovery。](document-metadata-fields-in-advanced-ediscovery.md)

  - Summary.txt: エクスポート統計を含むエクスポートの概要を含むテキスト ファイル。

  - Extracted_text_files: このフォルダーには、エクスポートされた各ドキュメントのテキスト ファイル バージョンが含まれる。

  - NativeFiles: このフォルダーには、エクスポートされた各ドキュメントのネイティブ ファイル バージョンが含まれる。

  - Error_files: エクスポート ジョブにエラー ファイルが含まれている場合、このフォルダーには次の項目が含まれます。

    - ExtractionError.csv: この CSV ファイルには、親アイテムから適切に抽出されていないファイルに使用可能なメタデータが含まれています。

    - ProcessingError: このフォルダーには、処理エラーのあるドキュメントが含まれています。 このコンテンツはアイテム レベルです。つまり、添付ファイルに処理エラーが発生した場合、添付ファイルを含むドキュメントもこのフォルダーに含まれます。
