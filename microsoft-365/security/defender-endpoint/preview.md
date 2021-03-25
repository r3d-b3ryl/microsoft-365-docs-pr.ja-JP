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
ms.openlocfilehash: 9400d448b2b133f7478ef8ceb01f605c17f36bc9
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064948"
---
# <a name="microsoft-defender-for-endpoint-preview-features"></a><span data-ttu-id="01e36-104">Microsoft Defender for Endpoint プレビュー機能</span><span class="sxs-lookup"><span data-stu-id="01e36-104">Microsoft Defender for Endpoint preview features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

>[!IMPORTANT]
><span data-ttu-id="01e36-105">プレビュー バージョンはサービス レベル契約なしで提供され、実稼働ワークロードには推奨されません。</span><span class="sxs-lookup"><span data-stu-id="01e36-105">The preview versions are provided without a service level agreement, and it's not recommended for production workloads.</span></span> <span data-ttu-id="01e36-106">一部の機能はサポートされていないか、制限された機能を持っている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="01e36-106">Certain features might not be supported or might have constrained capabilities.</span></span>

<span data-ttu-id="01e36-107">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="01e36-107">**Applies to:**</span></span>
- [<span data-ttu-id="01e36-108">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="01e36-108">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="01e36-109">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="01e36-109">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="01e36-110">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="01e36-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="01e36-111">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="01e36-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="01e36-112">Defender for Endpoint サービスは常に更新され、新機能の強化と機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="01e36-112">The Defender for Endpoint service is constantly being updated to include new feature enhancements and capabilities.</span></span>

> [!TIP]
> <span data-ttu-id="01e36-113">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="01e36-113">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="01e36-114">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="01e36-114">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-preview-abovefoldlink)

<span data-ttu-id="01e36-115">Defender for Endpoint プレビュー リリースの新機能について説明し、プレビュー エクスペリエンスをオンにして、今後の機能を最初に試してみてください。</span><span class="sxs-lookup"><span data-stu-id="01e36-115">Learn about new features in the Defender for Endpoint preview release and be among the first to try upcoming features by turning on the preview experience.</span></span>

>[!TIP]
><span data-ttu-id="01e36-116">次の URL をフィード リーダーにコピーして貼り付け、このページが更新された場合に通知を受け取ります。 `https://docs.microsoft.com/api/search/rss?search=%22Microsoft+Defender+ATP+preview+features%22&locale=en-us`</span><span class="sxs-lookup"><span data-stu-id="01e36-116">Get notified when this page is updated by copying and pasting the following URL into your feed reader: `https://docs.microsoft.com/api/search/rss?search=%22Microsoft+Defender+ATP+preview+features%22&locale=en-us`</span></span>

<span data-ttu-id="01e36-117">一般に利用可能な新機能の詳細については、「Defender for Endpoint の新機能 [」を参照してください](whats-new-in-microsoft-defender-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="01e36-117">For more information on new capabilities that are generally available, see [What's new in Defender for Endpoint](whats-new-in-microsoft-defender-atp.md).</span></span>

## <a name="turn-on-preview-features"></a><span data-ttu-id="01e36-118">プレビュー機能を有効にする</span><span class="sxs-lookup"><span data-stu-id="01e36-118">Turn on preview features</span></span>

<span data-ttu-id="01e36-119">今後の機能にアクセスしてフィードバックを提供し、機能が一般提供される前に全体的なエクスペリエンスを向上させるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="01e36-119">You'll have access to upcoming features that you can provide feedback on to help improve the overall experience before features are generally available.</span></span>

<span data-ttu-id="01e36-120">プレビュー機能設定をオンにして、今後の機能をいち早く試します。</span><span class="sxs-lookup"><span data-stu-id="01e36-120">Turn on the preview experience setting to be among the first to try upcoming features.</span></span>

1. <span data-ttu-id="01e36-121">ナビゲーション ウィンドウで、[設定] [高度 **な**  >  **機能] [**  >  **プレビュー機能] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="01e36-121">In the navigation pane, select **Settings** > **Advanced features** > **Preview features**.</span></span>

2. <span data-ttu-id="01e36-122">[オン] と [オフ]**の間で設定を\*\*\*\*切り替え**、[基本設定の保存]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="01e36-122">Toggle the setting between **On** and **Off** and select **Save preferences**.</span></span>

## <a name="preview-features"></a><span data-ttu-id="01e36-123">プレビュー機能</span><span class="sxs-lookup"><span data-stu-id="01e36-123">Preview features</span></span>

<span data-ttu-id="01e36-124">以下の機能がプレビュー リリースに含まれています。</span><span class="sxs-lookup"><span data-stu-id="01e36-124">The following features are included in the preview release:</span></span>

- [<span data-ttu-id="01e36-125">Web コンテンツ フィルター</span><span class="sxs-lookup"><span data-stu-id="01e36-125">Web Content Filtering</span></span>](web-content-filtering.md) <br> <span data-ttu-id="01e36-126">Web コンテンツ フィルターは、Microsoft Defender for Endpoint の Web 保護機能の一部です。</span><span class="sxs-lookup"><span data-stu-id="01e36-126">Web content filtering is part of web protection capabilities in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="01e36-127">これにより、組織はコンテンツ カテゴリに基づいて Web サイトへのアクセスを追跡および規制できます。</span><span class="sxs-lookup"><span data-stu-id="01e36-127">It enables your organization to track and regulate access to websites based on their content categories.</span></span> <span data-ttu-id="01e36-128">これらの Web サイトの多くは悪意のあるものではないが、コンプライアンス規制、帯域幅の使用、その他の懸念により問題になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="01e36-128">Many of these websites, while not malicious, might be problematic because of compliance regulations, bandwidth usage, or other concerns.</span></span>

- [<span data-ttu-id="01e36-129">デバイスの正常性とコンプライアンス レポート</span><span class="sxs-lookup"><span data-stu-id="01e36-129">Device health and compliance report</span></span>](machine-reports.md) <br/> <span data-ttu-id="01e36-130">デバイスの正常性とコンプライアンス レポートは、組織内のデバイスに関する高レベルの情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="01e36-130">The device health and compliance report provides high-level information about the devices in your organization.</span></span>

- [<span data-ttu-id="01e36-131">情報保護</span><span class="sxs-lookup"><span data-stu-id="01e36-131">Information protection</span></span>](information-protection-in-windows-overview.md)<BR>
<span data-ttu-id="01e36-132">情報保護は、Microsoft 365 Enterprise スイートの不可欠な部分で、機密性の高いデータを安全に保ちながら、職場での生産性を実現するためのインテリジェントな保護を提供します。</span><span class="sxs-lookup"><span data-stu-id="01e36-132">Information protection is an integral part of Microsoft 365 Enterprise suite, providing intelligent protection to keep sensitive data secure while enabling productivity in the workplace.</span></span> <span data-ttu-id="01e36-133">Microsoft Defender for Endpoint は Microsoft Threat Protection にシームレスに統合され、Windows デバイスに完全かつ包括的なデータ損失防止 (DLP) ソリューションを提供します。</span><span class="sxs-lookup"><span data-stu-id="01e36-133">Microsoft Defender for Endpoint is seamlessly integrated in Microsoft Threat Protection to provide a complete and comprehensive data loss prevention (DLP) solution for Windows devices.</span></span>

    >[!NOTE]
    ><span data-ttu-id="01e36-134">部分的に Windows 10 バージョン 1809 から利用できます。</span><span class="sxs-lookup"><span data-stu-id="01e36-134">Partially available from Windows 10, version 1809.</span></span>

- [<span data-ttu-id="01e36-135">オンボード Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="01e36-135">Onboard Windows Server 2019</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-server-endpoints#windows-server-version-1803-and-windows-server-2019) <BR> <span data-ttu-id="01e36-136">Microsoft Defender for Endpoint では、Windows Server 2019 のサポートが追加されました。</span><span class="sxs-lookup"><span data-stu-id="01e36-136">Microsoft Defender for Endpoint now adds support for Windows Server 2019.</span></span> <span data-ttu-id="01e36-137">Windows 10 クライアント デバイスで使用できるのと同じ方法で、Windows Server 2019 をオンボードできます。</span><span class="sxs-lookup"><span data-stu-id="01e36-137">You'll be able to onboard Windows Server 2019 in the same method available for Windows 10 client devices.</span></span>


> [!TIP] 
> <span data-ttu-id="01e36-138">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="01e36-138">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="01e36-139">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="01e36-139">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-preview-belowfoldlink)  
