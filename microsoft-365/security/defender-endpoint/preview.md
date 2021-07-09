---
title: Microsoft Defender for Endpoint プレビュー機能
description: Microsoft Defender for Endpoint プレビュー機能にアクセスする方法について説明します。
keywords: プレビュー、プレビュー エクスペリエンス、Microsoft Defender for Endpoint、機能、更新プログラム
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 0b6edbdcda61eaf402275ae0b6dc9a38c5fe19f7
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339492"
---
# <a name="microsoft-defender-for-endpoint-preview-features"></a><span data-ttu-id="ecd4f-104">Microsoft Defender for Endpoint プレビュー機能</span><span class="sxs-lookup"><span data-stu-id="ecd4f-104">Microsoft Defender for Endpoint preview features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ecd4f-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="ecd4f-105">**Applies to:**</span></span>
- [<span data-ttu-id="ecd4f-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="ecd4f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ecd4f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ecd4f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="ecd4f-108">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="ecd4f-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ecd4f-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="ecd4f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="ecd4f-110">Defender for Endpoint サービスは常に更新され、新機能の強化と機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ecd4f-110">The Defender for Endpoint service is constantly being updated to include new feature enhancements and capabilities.</span></span>

<span data-ttu-id="ecd4f-111">Defender for Endpoint プレビュー リリースの新機能について説明し、プレビュー エクスペリエンスをオンにして、今後の機能を最初に試してみてください。</span><span class="sxs-lookup"><span data-stu-id="ecd4f-111">Learn about new features in the Defender for Endpoint preview release and be among the first to try upcoming features by turning on the preview experience.</span></span>

>[!TIP]
><span data-ttu-id="ecd4f-112">次の URL をフィード リーダーにコピーして貼り付け、このページが更新された場合に通知を受け取ります。 `/api/search/rss?search=%22In+the+navigation+pane%2C+select+Settings+%3E+Advanced+features+%3E+Preview+features.%22&locale=en-us&facet=`</span><span class="sxs-lookup"><span data-stu-id="ecd4f-112">Get notified when this page is updated by copying and pasting the following URL into your feed reader: `/api/search/rss?search=%22In+the+navigation+pane%2C+select+Settings+%3E+Advanced+features+%3E+Preview+features.%22&locale=en-us&facet=`</span></span>

<span data-ttu-id="ecd4f-113">一般に利用可能な新機能の詳細については、「Defender for Endpoint の新機能 [」を参照してください](whats-new-in-microsoft-defender-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="ecd4f-113">For more information on new capabilities that are generally available, see [What's new in Defender for Endpoint](whats-new-in-microsoft-defender-atp.md).</span></span>

 ## <a name="what-you-need-to-know"></a><span data-ttu-id="ecd4f-114">知る必要があるもの</span><span class="sxs-lookup"><span data-stu-id="ecd4f-114">What you need to know</span></span>

<span data-ttu-id="ecd4f-115">パブリック プレビューで機能を操作する場合は、次の機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="ecd4f-115">When working with features in public preview, these features:</span></span>

- <span data-ttu-id="ecd4f-116">機能が制限または制限されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ecd4f-116">May have restricted or limited functionality.</span></span> <span data-ttu-id="ecd4f-117">たとえば、この機能は 1 つのプラットフォームにのみ適用できます。</span><span class="sxs-lookup"><span data-stu-id="ecd4f-117">For example, the feature may only apply to one platform.</span></span>
- <span data-ttu-id="ecd4f-118">通常、機能の変更は、一般に利用できる (GA) 前に行います。</span><span class="sxs-lookup"><span data-stu-id="ecd4f-118">Typically go through feature changes before they're generally available (GA).</span></span>
- <span data-ttu-id="ecd4f-119">Microsoft で完全にサポートされています。</span><span class="sxs-lookup"><span data-stu-id="ecd4f-119">Are fully supported by Microsoft.</span></span>
- <span data-ttu-id="ecd4f-120">選択した地域またはクラウド環境でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="ecd4f-120">May only be available in selected geographic regions or cloud environments.</span></span> <span data-ttu-id="ecd4f-121">たとえば、この機能が政府機関のクラウドに存在しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ecd4f-121">For example, the feature may not exist in the government cloud.</span></span>
- <span data-ttu-id="ecd4f-122">プレビューの個々の機能には、使用およびサポートの制限が多い場合があります。</span><span class="sxs-lookup"><span data-stu-id="ecd4f-122">Individual features in preview may have more usage and support restrictions.</span></span> <span data-ttu-id="ecd4f-123">その場合、この情報は通常、機能のドキュメントに示されています。</span><span class="sxs-lookup"><span data-stu-id="ecd4f-123">If so, this information is typically noted in the feature documentation.</span></span>
- <span data-ttu-id="ecd4f-124">プレビュー バージョンは標準のサポート レベルで提供され、実稼働環境で使用できます。</span><span class="sxs-lookup"><span data-stu-id="ecd4f-124">The preview versions are provided with a standard support level, and can be used for production environments.</span></span> 



## <a name="turn-on-preview-features"></a><span data-ttu-id="ecd4f-125">プレビュー機能を有効にする</span><span class="sxs-lookup"><span data-stu-id="ecd4f-125">Turn on preview features</span></span>

<span data-ttu-id="ecd4f-126">今後の機能にアクセスしてフィードバックを提供し、機能が一般提供される前に全体的なエクスペリエンスを向上させるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ecd4f-126">You'll have access to upcoming features that you can provide feedback on to help improve the overall experience before features are generally available.</span></span>

<span data-ttu-id="ecd4f-127">プレビュー機能設定をオンにして、今後の機能をいち早く試します。</span><span class="sxs-lookup"><span data-stu-id="ecd4f-127">Turn on the preview experience setting to be among the first to try upcoming features.</span></span>

1. <span data-ttu-id="ecd4f-128">ナビゲーション ウィンドウで、[高度な **機能設定**  >  **プレビュー機能]**  >  **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ecd4f-128">In the navigation pane, select **Settings** > **Advanced features** > **Preview features**.</span></span>

2. <span data-ttu-id="ecd4f-129">[オン] と [オフ]**の間で設定を\*\*\*\*切り替え**、[基本設定の保存]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ecd4f-129">Toggle the setting between **On** and **Off** and select **Save preferences**.</span></span>

## <a name="preview-features"></a><span data-ttu-id="ecd4f-130">プレビュー機能</span><span class="sxs-lookup"><span data-stu-id="ecd4f-130">Preview features</span></span>

<span data-ttu-id="ecd4f-131">以下の機能がプレビュー リリースに含まれています。</span><span class="sxs-lookup"><span data-stu-id="ecd4f-131">The following features are included in the preview release:</span></span>

- [<span data-ttu-id="ecd4f-132">Web コンテンツ フィルター</span><span class="sxs-lookup"><span data-stu-id="ecd4f-132">Web Content Filtering</span></span>](web-content-filtering.md) <br> <span data-ttu-id="ecd4f-133">Web コンテンツ フィルターは、Microsoft Defender for Endpoint の Web 保護機能の一部です。</span><span class="sxs-lookup"><span data-stu-id="ecd4f-133">Web content filtering is part of web protection capabilities in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="ecd4f-134">これにより、組織はコンテンツ カテゴリに基づいて Web サイトへのアクセスを追跡および規制できます。</span><span class="sxs-lookup"><span data-stu-id="ecd4f-134">It enables your organization to track and regulate access to websites based on their content categories.</span></span> <span data-ttu-id="ecd4f-135">これらの Web サイトの多くは悪意のあるものではないが、コンプライアンス規制、帯域幅の使用、その他の懸念により問題になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ecd4f-135">Many of these websites, while not malicious, might be problematic because of compliance regulations, bandwidth usage, or other concerns.</span></span>

- [<span data-ttu-id="ecd4f-136">デバイスの正常性とコンプライアンスのレポート</span><span class="sxs-lookup"><span data-stu-id="ecd4f-136">Device health and compliance report</span></span>](machine-reports.md) <br/> <span data-ttu-id="ecd4f-137">デバイスの正常性とコンプライアンス レポートは、組織内のデバイスに関する高レベルの情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="ecd4f-137">The device health and compliance report provides high-level information about the devices in your organization.</span></span>

> [!TIP] 
> <span data-ttu-id="ecd4f-138">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="ecd4f-138">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ecd4f-139">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="ecd4f-139">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-preview-belowfoldlink)  
