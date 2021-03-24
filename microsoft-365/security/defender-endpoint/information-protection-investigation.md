---
title: インシデント対応に優先順位を付ける場合は、感度ラベルを使用する
description: インシデントの優先順位付けと調査に感度ラベルを使用する方法について学習する
keywords: 情報、保護、データ、損失、防止、ラベル、dlp、インシデント、調査、調査
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d0c27ab2c6af8706e5e06a3c87b44e49c9185766
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065812"
---
# <a name="use-sensitivity-labels-to-prioritize-incident-response"></a><span data-ttu-id="b4090-104">インシデント対応に優先順位を付ける場合は、感度ラベルを使用する</span><span class="sxs-lookup"><span data-stu-id="b4090-104">Use sensitivity labels to prioritize incident response</span></span>  

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b4090-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="b4090-105">**Applies to:**</span></span>
- [<span data-ttu-id="b4090-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="b4090-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="b4090-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b4090-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="b4090-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="b4090-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b4090-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="b4090-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


<span data-ttu-id="b4090-110">一般的な高度な永続的な脅威ライフサイクルには、データの取り込みが含まれる。</span><span class="sxs-lookup"><span data-stu-id="b4090-110">A typical advanced persistent threat lifecycle involves data exfiltration.</span></span> <span data-ttu-id="b4090-111">セキュリティ インシデントでは、機密ファイルが危険にさらされる可能性がある調査に優先順位を付け、企業のデータと情報を保護することが重要です。</span><span class="sxs-lookup"><span data-stu-id="b4090-111">In a security incident, it's important to have the ability to prioritize investigations where sensitive files may be jeopardy so that corporate data and information are protected.</span></span>

<span data-ttu-id="b4090-112">Defender for Endpoint は、セキュリティ インシデントの事前設定を、感度ラベルを使用して、はるかに簡単に行うのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b4090-112">Defender for Endpoint helps to make the prioritization of security incidents much simpler with the use of sensitivity labels.</span></span> <span data-ttu-id="b4090-113">機密ラベルは、機密情報などの機密情報を持つデバイスに関連する可能性のあるインシデントをすばやく識別します。</span><span class="sxs-lookup"><span data-stu-id="b4090-113">Sensitivity labels quickly identify incidents that may involve devices with sensitive information such as confidential information.</span></span> 

## <a name="investigate-incidents-that-involve-sensitive-data"></a><span data-ttu-id="b4090-114">機密データを含むインシデントを調査する</span><span class="sxs-lookup"><span data-stu-id="b4090-114">Investigate incidents that involve sensitive data</span></span>
<span data-ttu-id="b4090-115">データの感度ラベルを使用してインシデント調査の優先順位を設定する方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="b4090-115">Learn how to use data sensitivity labels to prioritize incident investigation.</span></span>

>[!NOTE]
><span data-ttu-id="b4090-116">ラベルは、Windows 10 バージョン 1809 以降で検出されます。</span><span class="sxs-lookup"><span data-stu-id="b4090-116">Labels are detected for Windows 10, version 1809 or later.</span></span>

1. <span data-ttu-id="b4090-117">Microsoft Defender セキュリティ センターで、[インシデント] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b4090-117">In Microsoft Defender Security Center, select **Incidents**.</span></span> 

2. <span data-ttu-id="b4090-118">右にスクロールすると、[データの感度 **] 列が表示** されます。</span><span class="sxs-lookup"><span data-stu-id="b4090-118">Scroll to the right to see the **Data sensitivity** column.</span></span> <span data-ttu-id="b4090-119">この列は、インシデントに関連するデバイスで観察された機密ラベルを反映し、機密ファイルがインシデントの影響を受ける可能性があるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="b4090-119">This column reflects sensitivity labels that have been observed on devices related to the incidents providing an indication of whether sensitive files may be impacted by the incident.</span></span>

    ![[データの感度] 列の画像](images/data-sensitivity-column.png)

    <span data-ttu-id="b4090-121">また、データの感度に基 **づいてフィルター処理を実行できます。**</span><span class="sxs-lookup"><span data-stu-id="b4090-121">You can also filter based on **Data sensitivity**</span></span> 

    ![データの感度フィルターの画像](images/data-sensitivity-filter.png)

3. <span data-ttu-id="b4090-123">インシデント ページを開き、さらに調査します。</span><span class="sxs-lookup"><span data-stu-id="b4090-123">Open the incident page to further investigate.</span></span>

    ![インシデント ページの詳細の画像](images/incident-page.png)

4. <span data-ttu-id="b4090-125">[デバイス] **タブを** 選択して、感度ラベル付きファイルを格納するデバイスを識別します。</span><span class="sxs-lookup"><span data-stu-id="b4090-125">Select the **Devices** tab to identify devices storing files with sensitivity labels.</span></span>

    ![[デバイス] タブのイメージ](images/investigate-devices-tab.png)
   

5. <span data-ttu-id="b4090-127">機密データを格納するデバイスを選択し、タイムラインを検索して、影響を受ける可能性のあるファイルを特定し、データが保護される適切なアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="b4090-127">Select the devices that store sensitive data and search through the timeline to identify which files may be impacted then take appropriate action to ensure that data is protected.</span></span> 

   <span data-ttu-id="b4090-128">デバイスのタイムラインに表示されるイベントを絞り込むには、データの感度ラベルを検索します。</span><span class="sxs-lookup"><span data-stu-id="b4090-128">You can narrow down the events shown on the device timeline by searching for data sensitivity labels.</span></span> <span data-ttu-id="b4090-129">これにより、ラベル名が指定されたファイルに関連付けられたイベントだけが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b4090-129">Doing this will show only events associated with files that have said label name.</span></span>

    ![ラベルに基づいて検索結果を絞り込むデバイスタイムラインの画像](images/machine-timeline-labels.png)


>[!TIP]
><span data-ttu-id="b4090-131">これらのデータ ポイントは、高度な検索で 'DeviceFileEvents' を通じて公開され、高度なクエリとスケジュール検出で、感度ラベルとファイル保護の状態を考慮に入れることができるようになりました。</span><span class="sxs-lookup"><span data-stu-id="b4090-131">These data points are also exposed through the ‘DeviceFileEvents’ in advanced hunting, allowing advanced queries and schedule detection to take into account sensitivity labels and file protection status.</span></span> 
