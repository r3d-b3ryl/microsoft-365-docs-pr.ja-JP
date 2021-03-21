---
title: 高度な電子情報開示ケースのエクスポート ジョブをダウンロードする
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
ms.openlocfilehash: 0a73d157b2661202507883dd6542cdf6c6b482f8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926623"
---
# <a name="download-export-jobs-in-an-advanced-ediscovery-case"></a>高度な電子情報開示ケースでエクスポート ジョブをダウンロードする

Advanced eDiscovery ケースのレビュー セットからドキュメントをエクスポートすると、ドキュメントは Microsoft が提供する Azure Storage の場所、または組織が管理する Azure Storage の場所にアップロードされます。 使用される Azure Storage の場所の種類は、ドキュメントのエクスポート時に選択されたオプションによって異なります。

この記事では、Microsoft Azure Storage Explorer を使用して Azure Storage の場所に接続してエクスポートされたドキュメントを参照およびダウンロードする方法について説明します。 Azure Storage Explorer の詳細については [、「Quickstart: Use Azure Storage Explorer」を参照してください](/azure/storage/blobs/storage-quickstart-blobs-storage-explorer)。

## <a name="step-1-install-the-azure-storage-explorer"></a>手順 1: Azure ストレージ エクスプローラーをインストールする

最初の手順は、Azure Storage Explorer をダウンロードしてインストールすることです。 手順については [、「Azure Storage Explorer ツール」を参照してください](https://go.microsoft.com/fwlink/p/?LinkId=544842)。 このツールを使用して、手順 3 でエクスポートしたドキュメントに接続してダウンロードします。

## <a name="step-2-obtain-the-sas-url-from-the-export-job"></a>手順 2: エクスポート ジョブから SAS URL を取得する

次の手順では、レビュー セットからドキュメントをエクスポートするエクスポート ジョブの作成時に生成される共有アクセス署名 (SAS) URL [を取得します](export-documents-from-review-set.md)。 Microsoft が提供する Azure Storage の場所または組織が管理する Azure Storage の場所にアップロードされたドキュメントの SAS URL をコピーできます。 どちらの場合も、手順 3 で SAS URL を使用して Azure Storage の場所に接続します。

1. [高度 **な電子情報開示] ページ** で、ケースに移動し、[エクスポート] タブ **をクリック** します。

2. [**エクスポート**]タブで、ダウンロードするエクスポートジョブをクリックします。

3. [フライアウト] ページの [場所] **で**、表示される SAS URL をコピーします。 必要に応じて、ファイルに保存して、手順 3 でアクセスできます。
 
   ![[場所] の下に表示される SAS URL をコピーする](../media/eDiscoExportJob.png)

## <a name="step-3-connect-to-the-azure-storage-location"></a>手順 3: Azure Storage の場所に接続する

最後に、Azure Storage Explorer と SAS URL を使用して Azure Storage の場所に接続し、ローカル コンピューターにエクスポートしたドキュメントをダウンロードします。

1. 手順 1 でインストールした Azure Storage Explorer を開きます。

2. [アカウントの **追加] アイコンをクリック** します。 または、[ストレージ アカウント] を右 **クリックすることもできます**。

   ![[アカウントの追加] アイコンをクリックします。](../media/AzureStorageConnect.png)

3. [Azure **ストレージへの接続] ページで** 、[共有アクセス署名 **(SAS) URI** を使用する] をクリックし、[次へ] を **クリックします**。

    ![[共有アクセス署名 (SAS) URI を使用する] をクリックし、[次へ] をクリックします。](../media/AzureStorageConnect2.png)

4. [SAS **URI に添付する** ] ページで、[URI] ボックスをクリックし、手順 2 で取得した SAS URL を貼り付けます。 

    ![[URI] ボックスに SAS URL を貼り付ける](../media/AzureStorageConnect3.png)

    SAS URL の一部が [表示名] ボックス **に表示されます** 。 これは、ストレージの場所に接続した後にストレージ アカウントの下に作成されたコンテナーの表示名として使用されます。 この名前は、Advanced eDiscovery ケースの ID と一意の識別子で構成されます。 デフォルトの表示名をそのまま使用することも、変更することもできます。 変更する場合、表示名は一意でなければなりません。

5. **[次へ]** をクリックします。

    [ **接続の概要] ページ** が表示されます。

    ![[接続の概要] ページの [接続] をクリックして、Azure Storage の場所に接続します。](../media/AzureStorageConnect4.png)

6. [接続 **の概要] ページで** 、接続情報を確認し、[接続] を **クリックします**。

    [Blob **コンテナー]** ノード **([ストレージ アカウント**  >  **] (接続されたコンテナー) が** \> 開きます。

    ![Blobs コンテナー ノードのジョブのエクスポート](../media/AzureStorageConnect5.png)

    手順 4 の表示名を持つコンテナーが含まれる。 このコンテナーには、作成したエクスポート ジョブごとにフォルダーが含まれる。 これらのフォルダーの名前は、エクスポート ジョブの ID に対応する ID です。 これらのエクスポートの ID (およびエクスポートの名前) は、[ジョブ] タブに一覧表示されているエクスポートジョブの準備データのフライアウト ページの[サポート情報] にあります。 

7. エクスポート ジョブ フォルダーをダブルクリックして開きます。

   フォルダーとエクスポート レポートの一覧が表示されます。
   
    ![エクスポート フォルダーには、エクスポートされたファイルとエクスポート レポートが含まれる](../media/AzureStorageConnect6.png)

   エクスポート ジョブ フォルダーには、次の項目が含まれます。 エクスポート フォルダー内の実際のアイテムは、エクスポート ジョブの作成時に構成されたエクスポート オプションによって決まります。 詳細については、「レビュー セット [からドキュメントをエクスポートする」を参照してください](export-documents-from-review-set.md)。

    - Export_load_file.csv: この CSV ファイルは、エクスポートされた各ドキュメントに関する情報を含む詳細エクスポート レポートです。 ファイルは、ドキュメントの各メタデータ プロパティの列で構成されます。 このレポートに含まれるメタデータの一覧と説明については、「Advanced eDiscoveryのドキュメント メタデータ フィールド」の表の「エクスポートされたフィールド名」[列を参照してください](document-metadata-fields-in-advanced-ediscovery.md)。
    
    - Summary.txt: エクスポート統計を含むエクスポートの概要を含むテキスト ファイル。
    
    - Extracted_text_files: このフォルダーには、エクスポートされた各ドキュメントのテキスト ファイル バージョンが含まれる。
     
    - NativeFiles: このフォルダーには、エクスポートされた各ドキュメントのネイティブ ファイル バージョンが含まれる。
    
    - Error_files: エクスポート ジョブにエラー ファイルが含まれている場合、このフォルダーには次の項目が含まれます。 
        
      - ExtractionError.csv: この CSV ファイルには、親アイテムから適切に抽出されていないファイルに使用可能なメタデータが含まれています。
        
      - ProcessingError: このフォルダーには、処理エラーのあるドキュメントが含まれています。 このコンテンツはアイテム レベルです。つまり、添付ファイルに処理エラーが発生した場合、添付ファイルを含むドキュメントもこのフォルダーに含まれます。
 
8. エクスポート内のすべてのコンテンツをエクスポートするには、エクスポートフォルダーを選択し、[**ダウンロード**]をクリックします。

9. エクスポートしたファイルをダウンロードする場所を指定して、[フォルダを選択]をクリックします。

    Azure Storage Explorer はエクスポート プロセスを開始します。 エクスポートしたアイテムのダウンロードの状態が [アクティビティ] ウィンドウ **に表示** されます。 ダウンロードが完了すると、メッセージが表示されます。

    ![ダウンロードが完了するとメッセージが表示される](../media/AzureStorageConnect8.png)

> [!NOTE]
> エクスポートジョブ全体をダウンロードする代わりに、ダウンロードする特定のアイテムを選択できます。 また、アイテムをダウンロードする代わりに、アイテムをダブルクリックして表示できます。