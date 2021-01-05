---
title: Advanced eDiscovery ケースのエクスポート ジョブをダウンロードする
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
ROBOTS: NOINDEX, NOFOLLOW
ms.custom: seo-marvel-mar2020
description: Azure Storage Explorer をインストールして使用して、Advanced eDiscovery のレビュー セットからエクスポートされたドキュメントをダウンロードします。
ms.openlocfilehash: 094dcb4ecc8b1ca73a7ec0238ed20b27d4c16e72
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751294"
---
# <a name="download-export-jobs-in-an-advanced-ediscovery-case"></a>Advanced eDiscovery ケースでエクスポート ジョブをダウンロードする

Advanced eDiscovery ケースのレビュー セットからドキュメントをエクスポートすると、ドキュメントは Microsoft が提供する Azure Storage の場所、または組織が管理する Azure Storage の場所にアップロードされます。 使用される Azure Storage の場所の種類は、ドキュメントのエクスポート時に選択されたオプションによって異なります。

この記事では、Microsoft Azure Storage Explorer を使用して Azure Storage の場所に接続し、エクスポートされたドキュメントを参照してダウンロードする方法について説明します。 Azure Storage Explorer の詳細については、「クイック スタート: Azure Storage Explorer を使用する [」を参照してください](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-storage-explorer)。

## <a name="step-1-install-the-azure-storage-explorer"></a>手順 1: Azure Storage Explorer をインストールする

最初の手順は、Azure Storage Explorer をダウンロードしてインストールすることです。 手順については [、Azure Storage Explorer ツールを参照してください](https://go.microsoft.com/fwlink/p/?LinkId=544842)。 このツールを使用して、手順 3 でエクスポートしたドキュメントに接続してダウンロードします。

## <a name="step-2-obtain-the-sas-url-from-the-export-job"></a>手順 2: エクスポート ジョブから SAS URL を取得する

次の手順では、レビュー セットからドキュメントをエクスポートするエクスポート ジョブを作成するときに生成される共有アクセス署名 (SAS) URL [を取得します](export-documents-from-review-set.md)。 Microsoft 提供の Azure Storage の場所または組織で管理されている Azure Storage の場所にアップロードされたドキュメントの SAS URL をコピーできます。 どちらの場合も、SAS URL を使用して手順 3 で Azure Storage の場所に接続します。

1. [Advanced **eDiscovery] ページ** でケースに移動し、[エクスポート] タブ **をクリック** します。

2. [**エクスポート**]タブで、ダウンロードするエクスポートジョブをクリックします。

3. フライアウト ページの [ **場所] で、** 表示される SAS URL をコピーします。 必要に応じて、手順 3 でアクセスできるよう、ファイルに保存できます。
 
   ![[場所] の下に表示される SAS URL をコピーする](../media/eDiscoExportJob.png)

## <a name="step-3-connect-to-the-azure-storage-location"></a>手順 3: Azure Storage の場所に接続する

最後の手順では、Azure Storage Explorer と SAS URL を使用して Azure Storage の場所に接続し、ローカル コンピューターにエクスポートしたドキュメントをダウンロードします。

1. 手順 1 でインストールした Azure Storage Explorer を開きます。

2. [アカウントの **追加] アイコンをクリック** します。 または、[ストレージ アカウント] を右 **クリックすることもできます**。

   ![[アカウントの追加] アイコンをクリックします。](../media/AzureStorageConnect.png)

3. [Azure **Storage への接続** ] ページで、[共有アクセス署名 **(SAS) URI** を使用する] をクリックし、[次へ] をクリック **します**。

    ![[共有アクセス署名 (SAS) URI を使用する] をクリックし、[次へ] をクリックします。](../media/AzureStorageConnect2.png)

4. [SAS URI にアタッチ] ページで **、[URI]** ボックスをクリックし、手順 2 で取得した SAS URL を貼り付けます。 

    ![[URI] ボックスに SAS URL を貼り付ける](../media/AzureStorageConnect3.png)

    SAS URL の一部が [表示名] ボックスに **表示** されます。 これは、ストレージの場所に接続した後にストレージ アカウントの下に作成されるコンテナーの表示名として使用されます。 この名前は、Advanced eDiscovery ケースの ID と一意の識別子で構成されます。 デフォルトの表示名をそのまま使用することも、変更することもできます。 変更する場合、表示名は一意でなければなりません。

5. [**次へ**] をクリックします。

    [ **接続の概要]** ページが表示されます。

    ![Azure Storage の場所に接続するには、[接続の概要] ページで [接続] をクリックします。](../media/AzureStorageConnect4.png)

6. [接続 **の概要] ページ** で、接続情報を確認し、[接続] をクリック **します**。

    Blob **コンテナー ノード**([**ストレージ** アカウント]  >  **(添付コンテナー) の下)** \> が開きます。

    ![BLOB コンテナー ノード内のジョブをエクスポートする](../media/AzureStorageConnect5.png)

    手順 4 の表示名を持つコンテナーが含まれている。 このコンテナーには、作成した各エクスポート ジョブのフォルダーが含まれる。 これらのフォルダーの名前は、エクスポート ジョブの ID に対応する ID です。 これらのエクスポート ID (およびエクスポートの名前) は、[ジョブ] タブに表示されるエクスポート ジョブの準備データごとに、フライアウト ページの[サポート情報] にあります。 

7. エクスポート ジョブ フォルダーをダブルクリックして開きます。

   フォルダーとエクスポート レポートの一覧が表示されます。
   
    ![エクスポート フォルダーには、エクスポートされたファイルとエクスポート レポートが含まれている](../media/AzureStorageConnect6.png)

   エクスポート ジョブ フォルダーには、次のアイテムが含まれます。 エクスポート フォルダー内の実際のアイテムは、エクスポート ジョブの作成時に構成されたエクスポート オプションによって決まります。 詳細については、「レビュー セット [からドキュメントをエクスポートする」を参照してください](export-documents-from-review-set.md)。

    - Export_load_file.csv: この CSV ファイルは、エクスポートされた各ドキュメントに関する情報を含む詳細エクスポート レポートです。 ファイルは、ドキュメントの各メタデータ プロパティの列で構成されます。 このレポートに含まれるメタデータの一覧と説明については[、Advanced eDiscovery](document-metadata-fields-in-advanced-ediscovery.md)のドキュメント メタデータ フィールドの表の 「エクスポートされたフィールド名」列を参照してください。
    
    - Summary.txt: エクスポート統計を含むエクスポートの概要を含むテキスト ファイル。
    
    - Extracted_text_files: このフォルダーには、エクスポートされた各ドキュメントのテキスト ファイル バージョンが含まれる。
     
    - NativeFiles: このフォルダーには、エクスポートされた各ドキュメントのネイティブ ファイル バージョンが格納されます。
    
    - Error_files: エクスポート ジョブにエラー ファイルが含まれている場合、このフォルダーには次のアイテムが含まれます。 
        
      - ExtractionError.csv: この CSV ファイルには、親アイテムから適切に抽出されていないファイルに使用可能なメタデータが含まれています。
        
      - ProcessingError: このフォルダーには、処理エラーのあるドキュメントが含まれています。 このコンテンツはアイテム レベルです。つまり、添付ファイルで処理エラーが発生した場合、添付ファイルを含むドキュメントもこのフォルダーに含まれます。
 
8. エクスポート内のすべてのコンテンツをエクスポートするには、エクスポートフォルダーを選択し、[**ダウンロード**]をクリックします。

9. エクスポートしたファイルをダウンロードする場所を指定して、[フォルダを選択]をクリックします。

    Azure Storage Explorer がエクスポート プロセスを開始します。 エクスポートしたアイテムのダウンロードの状態が [アクティビティ] ウィンドウに **表示** されます。 ダウンロードが完了すると、メッセージが表示されます。

    ![ダウンロードが完了するとメッセージが表示される](../media/AzureStorageConnect8.png)

> [!NOTE]
> エクスポートジョブ全体をダウンロードする代わりに、ダウンロードする特定のアイテムを選択できます。 また、アイテムをダウンロードする代わりに、アイテムをダブルクリックして表示できます。
