---
title: Microsoft Defender ATP プレビュー機能
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
ms.openlocfilehash: 4a91fa3c8ff55f46619c7b49eaf973ad94f60bfe
ms.sourcegitcommit: 72ae1b49e7a3d3199272fcb4c39f5daec0d66f1a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "51698192"
---
# <a name="microsoft-defender-for-endpoint-preview-features"></a><span data-ttu-id="fc40d-104">Microsoft Defender for Endpoint プレビュー機能</span><span class="sxs-lookup"><span data-stu-id="fc40d-104">Microsoft Defender for Endpoint preview features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

>[!IMPORTANT]
><span data-ttu-id="fc40d-105">プレビュー バージョンはサービス レベル契約なしで提供され、実稼働ワークロードには推奨されません。</span><span class="sxs-lookup"><span data-stu-id="fc40d-105">The preview versions are provided without a service level agreement, and it's not recommended for production workloads.</span></span> <span data-ttu-id="fc40d-106">一部の機能はサポートされていないか、制限された機能を持っている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fc40d-106">Certain features might not be supported or might have constrained capabilities.</span></span>

<span data-ttu-id="fc40d-107">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="fc40d-107">**Applies to:**</span></span>
- [<span data-ttu-id="fc40d-108">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="fc40d-108">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="fc40d-109">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fc40d-109">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="fc40d-110">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="fc40d-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="fc40d-111">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="fc40d-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="fc40d-112">Defender for Endpoint サービスは常に更新され、新機能の強化と機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="fc40d-112">The Defender for Endpoint service is constantly being updated to include new feature enhancements and capabilities.</span></span>

<span data-ttu-id="fc40d-113">Defender for Endpoint プレビュー リリースの新機能について説明し、プレビュー エクスペリエンスをオンにして、今後の機能を最初に試してみてください。</span><span class="sxs-lookup"><span data-stu-id="fc40d-113">Learn about new features in the Defender for Endpoint preview release and be among the first to try upcoming features by turning on the preview experience.</span></span>

>[!TIP]
><span data-ttu-id="fc40d-114">次の URL をフィード リーダーにコピーして貼り付け、このページが更新された場合に通知を受け取ります。 `https://docs.microsoft.com/api/search/rss?search=%22Microsoft+Defender+ATP+preview+features%22&locale=en-us`</span><span class="sxs-lookup"><span data-stu-id="fc40d-114">Get notified when this page is updated by copying and pasting the following URL into your feed reader: `https://docs.microsoft.com/api/search/rss?search=%22Microsoft+Defender+ATP+preview+features%22&locale=en-us`</span></span>

<span data-ttu-id="fc40d-115">一般に利用可能な新機能の詳細については、「Defender for Endpoint の新機能 [」を参照してください](whats-new-in-microsoft-defender-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="fc40d-115">For more information on new capabilities that are generally available, see [What's new in Defender for Endpoint](whats-new-in-microsoft-defender-atp.md).</span></span>

## <a name="turn-on-preview-features"></a><span data-ttu-id="fc40d-116">プレビュー機能を有効にする</span><span class="sxs-lookup"><span data-stu-id="fc40d-116">Turn on preview features</span></span>

<span data-ttu-id="fc40d-117">今後の機能にアクセスしてフィードバックを提供し、機能が一般提供される前に全体的なエクスペリエンスを向上させるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="fc40d-117">You'll have access to upcoming features that you can provide feedback on to help improve the overall experience before features are generally available.</span></span>

<span data-ttu-id="fc40d-118">プレビュー機能設定をオンにして、今後の機能をいち早く試します。</span><span class="sxs-lookup"><span data-stu-id="fc40d-118">Turn on the preview experience setting to be among the first to try upcoming features.</span></span>

1. <span data-ttu-id="fc40d-119">ナビゲーション ウィンドウで、[設定] [高度 **な**  >  **機能] [**  >  **プレビュー機能] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="fc40d-119">In the navigation pane, select **Settings** > **Advanced features** > **Preview features**.</span></span>

2. <span data-ttu-id="fc40d-120">[オン] と [オフ]**の間で設定を\*\*\*\*切り替え**、[基本設定の保存]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="fc40d-120">Toggle the setting between **On** and **Off** and select **Save preferences**.</span></span>

## <a name="preview-features"></a><span data-ttu-id="fc40d-121">プレビュー機能</span><span class="sxs-lookup"><span data-stu-id="fc40d-121">Preview features</span></span>

<span data-ttu-id="fc40d-122">以下の機能がプレビュー リリースに含まれています。</span><span class="sxs-lookup"><span data-stu-id="fc40d-122">The following features are included in the preview release:</span></span>

- [<span data-ttu-id="fc40d-123">デバイスの検出</span><span class="sxs-lookup"><span data-stu-id="fc40d-123">Device discovery</span></span>](device-discovery.md) <br> <span data-ttu-id="fc40d-124">追加のアプライアンスや面倒なプロセス変更を必要とせずに、企業ネットワークに接続されている管理されていないデバイスを見つけるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="fc40d-124">Helps you find unmanaged devices connected to your corporate network without the need for extra appliances or cumbersome process changes.</span></span> <span data-ttu-id="fc40d-125">オンボード デバイスを使用すると、ネットワーク内の管理されていないデバイスを見つけて、脆弱性とリスクを評価できます。</span><span class="sxs-lookup"><span data-stu-id="fc40d-125">Using onboarded devices, you can find unmanaged devices in your network and assess vulnerabilities and risks.</span></span> <span data-ttu-id="fc40d-126">その後、検出されたデバイスをオンボードして、ネットワークに管理されていないエンドポイントを持つことに関連するリスクを軽減できます。</span><span class="sxs-lookup"><span data-stu-id="fc40d-126">You can then onboard discovered devices to reduce risks associated with having unmanaged endpoints in your network.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="fc40d-127">標準検出は、2021 年 5 月 10 日からすべてのプレビューユーザーの既定のモードになります。</span><span class="sxs-lookup"><span data-stu-id="fc40d-127">Standard discovery will be the default mode for all preview customers starting May 10, 2021.</span></span> <span data-ttu-id="fc40d-128">基本モードは、[設定] ページで保持できます。</span><span class="sxs-lookup"><span data-stu-id="fc40d-128">You can choose to retain the basic mode through the settings page.</span></span> 


- [<span data-ttu-id="fc40d-129">Web コンテンツ フィルター</span><span class="sxs-lookup"><span data-stu-id="fc40d-129">Web Content Filtering</span></span>](web-content-filtering.md) <br> <span data-ttu-id="fc40d-130">Web コンテンツ フィルターは、Microsoft Defender for Endpoint の Web 保護機能の一部です。</span><span class="sxs-lookup"><span data-stu-id="fc40d-130">Web content filtering is part of web protection capabilities in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="fc40d-131">これにより、組織はコンテンツ カテゴリに基づいて Web サイトへのアクセスを追跡および規制できます。</span><span class="sxs-lookup"><span data-stu-id="fc40d-131">It enables your organization to track and regulate access to websites based on their content categories.</span></span> <span data-ttu-id="fc40d-132">これらの Web サイトの多くは悪意のあるものではないが、コンプライアンス規制、帯域幅の使用、その他の懸念により問題になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fc40d-132">Many of these websites, while not malicious, might be problematic because of compliance regulations, bandwidth usage, or other concerns.</span></span>

- [<span data-ttu-id="fc40d-133">デバイスの正常性とコンプライアンス レポート</span><span class="sxs-lookup"><span data-stu-id="fc40d-133">Device health and compliance report</span></span>](machine-reports.md) <br/> <span data-ttu-id="fc40d-134">デバイスの正常性とコンプライアンス レポートは、組織内のデバイスに関する高レベルの情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="fc40d-134">The device health and compliance report provides high-level information about the devices in your organization.</span></span>

> [!TIP] 
> <span data-ttu-id="fc40d-135">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="fc40d-135">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="fc40d-136">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="fc40d-136">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-preview-belowfoldlink)  
