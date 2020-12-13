---
title: Advanced eDiscovery でバッチ履歴を表示し、過去の結果をエクスポートする
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 35d52b41-75ab-4144-9edf-31e11453bd5d
description: 選択したエクスポート バッチ セッションの詳細情報を表示する方法と、Advanced eDiscovery で最後のエクスポート セッションを元に戻す方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 054fa4a88d8c61751b4064b3535de66881655631
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663276"
---
# <a name="view-batch-history-and-export-past-results-in-advanced-ediscovery-classic"></a><span data-ttu-id="ed541-103">Advanced eDiscovery (クラシック) でバッチ履歴を表示し、過去の結果をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="ed541-103">View batch history and export past results in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="ed541-p101">Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。</span><span class="sxs-lookup"><span data-stu-id="ed541-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="ed541-106">次のセクションでは、Advanced eDiscovery でデータをバッチ表示およびエクスポートするための追加オプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="ed541-106">The following section describes additional options for batch viewing and export of data in Advanced eDiscovery.</span></span> 
  
## <a name="viewing-export-batch-history-and-exporting-previous-batches"></a><span data-ttu-id="ed541-107">エクスポート バッチ履歴の表示と以前のバッチのエクスポート</span><span class="sxs-lookup"><span data-stu-id="ed541-107">Viewing Export batch history and exporting previous batches</span></span>

<span data-ttu-id="ed541-108">[エクスポート履歴] ダイアログには、選択したエクスポート バッチ セッションの詳細情報が表示され、最後のセッションを元に戻す機能も提供されます。</span><span class="sxs-lookup"><span data-stu-id="ed541-108">The Export history dialog provides detailed information of selected export batch sessions and also provides the ability to undo the last session.</span></span>
  
1. <span data-ttu-id="ed541-109">[ **エクスポート \> セットアップ]** で、[エクスポート バッチ] ドロップダウン リストから **バッチ名** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ed541-109">In **Export \> Setup**, select the batch name from the **Export batch** drop-down list.</span></span> 
    
2. <span data-ttu-id="ed541-110">エクスポート バッチ名の右側にある [バッチ履歴] **アイコンを選択** します。</span><span class="sxs-lookup"><span data-stu-id="ed541-110">To the right of the export batch name, select the **Batch history** icon:</span></span> 
    
    ![[バッチ履歴のエクスポート] アイコン](../media/a14f6ef9-0c3c-4851-b65d-9380f2d8a38a.gif)
  
    <span data-ttu-id="ed541-112">[バッチ履歴] ダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ed541-112">The Batch history dialog is displayed.</span></span>
    
    ![バッチ履歴のエクスポート](../media/04c5b75c-348c-491d-b4fe-716659333890.png)
  
3. <span data-ttu-id="ed541-114">前のセッションをロールバックする必要がある場合は、[最後のセッションを元に戻す] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="ed541-114">If it is necessary to roll back a previous session, click **Undo last session**.</span></span> <span data-ttu-id="ed541-115">ロールバックは複数回実行できます。この場合、最後のセッションが取り消されます。</span><span class="sxs-lookup"><span data-stu-id="ed541-115">Rollback can be performed multiple times, which cancels the last session.</span></span>
    
4. <span data-ttu-id="ed541-116">以前に実行したエクスポート バッチ セッションからいつでもデータをダウンロードする場合は、エクスポートするエクスポートバッチの横にある [ダウンロード] アイコン [エクスポート バッチ履歴のダウンロード] アイコンをクリックします ![ ](../media/de69b920-a6ac-4ddb-b93e-e1cc5888e6c4.gif) 。</span><span class="sxs-lookup"><span data-stu-id="ed541-116">If you want to download data at any time from a previously executed export batch session, click the **Download** icon ![Export batch history download icon](../media/de69b920-a6ac-4ddb-b93e-e1cc5888e6c4.gif) next to the desired export batch to be exported.</span></span> 
    
5. <span data-ttu-id="ed541-117">When the **Shared access signature dialog** is displayed, click Copy to clipboard to **copy** the export session data to the local machine, and then click **Close**.</span><span class="sxs-lookup"><span data-stu-id="ed541-117">When the **Shared access signature** dialog is displayed, click **Copy to clipboard** to copy the export session data to the local machine, and then click **Close**.</span></span> <span data-ttu-id="ed541-118">セキュリティ コンプライアンス &amp; センターの **電子情報開示エクスポート ツール** ダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ed541-118">The Security &amp; Compliance Center **eDiscovery Export Tool** dialog is displayed.</span></span> 
    
    ![[電子情報開示のエクスポート] ダイアログボックス](../media/01f79d2d-6da0-45e6-9c6f-ab12347572cb.gif)
  
6. <span data-ttu-id="ed541-120">電子情報開示 **エクスポート ツール ダイアログで、次の操作を** 行います。</span><span class="sxs-lookup"><span data-stu-id="ed541-120">In the **eDiscovery Export Tool** dialog:</span></span> 
    
1. <span data-ttu-id="ed541-121">ソース **への接続に** 使用する共有アクセス署名を貼り付け、以前にクリップボードにコピーした共有アクセス署名の値を貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="ed541-121">In **Paste the Shared Access Signature that will be used to connect to the source**, paste the **Shared access signature** value, which was previously copied to the clipboard.</span></span> 
    
2. <span data-ttu-id="ed541-122">[ **参照]** をクリックして、ダウンロードしたエクスポート ファイルをローカル コンピューターに保存する場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="ed541-122">Click **Browse** to select the target location for storing the downloaded export files on a local machine.</span></span> 
    
3. <span data-ttu-id="ed541-123">**[開始]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ed541-123">Click **Start**.</span></span> <span data-ttu-id="ed541-124">エクスポート ファイルがローカル コンピューターにダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="ed541-124">The export files are downloaded to the local machine.</span></span> 
    
## <a name="related-topics"></a><span data-ttu-id="ed541-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="ed541-125">Related topics</span></span>

[<span data-ttu-id="ed541-126">Advanced eDiscovery (クラシック)</span><span class="sxs-lookup"><span data-stu-id="ed541-126">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="ed541-127">結果のエクスポート </span><span class="sxs-lookup"><span data-stu-id="ed541-127">Exporting results </span></span>](export-results-in-advanced-ediscovery.md)

[<span data-ttu-id="ed541-128">レポート フィールドのエクスポート</span><span class="sxs-lookup"><span data-stu-id="ed541-128">Export report fields</span></span>](export-report-fields-in-advanced-ediscovery.md)

