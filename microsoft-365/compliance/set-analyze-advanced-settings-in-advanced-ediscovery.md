---
title: 高度な電子情報開示の高度な設定を分析する設定を行う
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
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
ms.assetid: a797682f-ad85-4c08-a354-3850ba2237ee
description: 詳細な電子情報開示の分析プロセスについて、ほぼ重複、電子メールスレッド、テーマを含む高度な設定を構成する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 39d99609cfff92dcd6e6d2f4483076b8bfe808be
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936754"
---
# <a name="set-analyze-advanced-settings-in-advanced-ediscovery"></a><span data-ttu-id="f591b-103">高度な電子情報開示の高度な設定を分析する設定を行う</span><span class="sxs-lookup"><span data-stu-id="f591b-103">Set Analyze advanced settings in Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="f591b-104">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization.</span><span class="sxs-lookup"><span data-stu-id="f591b-104">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization.</span></span> <span data-ttu-id="f591b-105">If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="f591b-105">If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="f591b-106">Advanced eDiscovery は、モジュール設定を分析するための既定の高度なパラメーターを提供します。</span><span class="sxs-lookup"><span data-stu-id="f591b-106">Advanced eDiscovery provides default advanced parameters for Analyze module settings.</span></span> <span data-ttu-id="f591b-107">次の手順では、指定可能な設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="f591b-107">The following procedure describes settings that can be specified.</span></span>
  
1. <span data-ttu-id="f591b-108">[Analyze の設定の準備] タブで、[**詳細設定**] (ページの下部) をクリックします。 \*\* \> \> \*\*</span><span class="sxs-lookup"><span data-stu-id="f591b-108">In the **Prepare \> Analyze \> Setup** tab, click **Advanced settings** (at the bottom of the page).</span></span> <span data-ttu-id="f591b-109">次のパネルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f591b-109">The following panel is displayed.</span></span> 
    
    ![分析設定の拡張設定](../media/c9ea3017-e19a-456b-a742-c3d07121a3f6.png)
  
2. <span data-ttu-id="f591b-111">[**ほぼ重複] および [電子メールスレッド] パラメーター**で、必要に応じて次の値を選択します。</span><span class="sxs-lookup"><span data-stu-id="f591b-111">In **Near-duplicates and Email threads parameters**, select values for the following as necessary:</span></span>
    
  - <span data-ttu-id="f591b-112">**少なく**とも1つの単語の最小数: ファイルがほぼ重複した分析のために送信されません。</span><span class="sxs-lookup"><span data-stu-id="f591b-112">**Minimum number of words**: Minimum number for words, below which a file is not submitted for Near-duplicate analysis.</span></span> 
    
  - <span data-ttu-id="f591b-113">**単語の**最大数: 単語の最大数。これは、ほぼ重複した分析のためにファイルが送信されません。</span><span class="sxs-lookup"><span data-stu-id="f591b-113">**Maximum number of words**: Maximum number for words, above which a file is not submitted for Near-duplicate analysis.</span></span>
    
  - <span data-ttu-id="f591b-114">**電子メールの類似性**: 2 通の電子メールについては、resemblance の最低限のレベルで類似したものと見なされます。</span><span class="sxs-lookup"><span data-stu-id="f591b-114">**Email similarity**: Minimal level of resemblance for two emails to be considered similar.</span></span> <span data-ttu-id="f591b-115">値は常に等しいか、ドキュメントの類似性よりも大きい値です。</span><span class="sxs-lookup"><span data-stu-id="f591b-115">Value is always equal to, or larger than document similarity.</span></span> <span data-ttu-id="f591b-116">既定値は90% です。</span><span class="sxs-lookup"><span data-stu-id="f591b-116">Default is 90%.</span></span>
    
3. <span data-ttu-id="f591b-117">[テーマの**パラメーター**] で、[**テーマの分析に数字を含める**] チェックボックスをオンにして、分析中のテーマの処理に番号を含めます。</span><span class="sxs-lookup"><span data-stu-id="f591b-117">In **Themes parameters**, select the **Include numbers in theme analysis** check box to include numbers in the processing of Themes during Analyze.</span></span> 
    
4. <span data-ttu-id="f591b-118">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f591b-118">Click **Save**.</span></span> 
    
## <a name="related-topics"></a><span data-ttu-id="f591b-119">関連トピック</span><span class="sxs-lookup"><span data-stu-id="f591b-119">Related topics</span></span>

[<span data-ttu-id="f591b-120">Advanced eDiscovery (クラシック)</span><span class="sxs-lookup"><span data-stu-id="f591b-120">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="f591b-121">ドキュメントの類似点について</span><span class="sxs-lookup"><span data-stu-id="f591b-121">Understanding document similarity</span></span>](understand-document-similarity-in-advanced-ediscovery.md)
  
[<span data-ttu-id="f591b-122">分析オプションの設定</span><span class="sxs-lookup"><span data-stu-id="f591b-122">Setting Analyze options</span></span>](set-analyze-options-in-advanced-ediscovery.md)
  
[<span data-ttu-id="f591b-123">無視するテキストの設定</span><span class="sxs-lookup"><span data-stu-id="f591b-123">Setting ignore text</span></span>](set-ignore-text-in-advanced-ediscovery.md)
  
[<span data-ttu-id="f591b-124">分析結果の表示</span><span class="sxs-lookup"><span data-stu-id="f591b-124">Viewing Analyze results</span></span>](view-analyze-results-in-advanced-ediscovery.md)

