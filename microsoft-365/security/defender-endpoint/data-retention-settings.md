---
title: データストレージの場所を確認し、データ保持設定を更新する
description: Microsoft Defender for Endpoint のデータストレージの場所を確認し、データ保持設定を更新する
keywords: データ、ストレージ、設定、保持、更新
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
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: b83e6682ce0c11d076e0bbef60fdef365c9be564
ms.sourcegitcommit: d4604e333507c6f57d5bf327531a241b649052de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/31/2021
ms.locfileid: "51471103"
---
# <a name="verify-data-storage-location-and-update-data-retention-settings-for-microsoft-defender-for-endpoint"></a><span data-ttu-id="c3df2-104">Microsoft Defender for Endpoint のデータストレージの場所を確認し、データ保持設定を更新する</span><span class="sxs-lookup"><span data-stu-id="c3df2-104">Verify data storage location and update data retention settings for Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="c3df2-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="c3df2-105">**Applies to:**</span></span>
- [<span data-ttu-id="c3df2-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="c3df2-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c3df2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c3df2-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="c3df2-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="c3df2-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c3df2-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="c3df2-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-gensettings-abovefoldlink)

<span data-ttu-id="c3df2-110">オンボーディング プロセス中に、ウィザードによって Defender for Endpoint のデータストレージと保持設定が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c3df2-110">During the onboarding process, a wizard takes you through the data storage and retention settings of Defender for Endpoint.</span></span> 

<span data-ttu-id="c3df2-111">オンボーディングが完了すると、[データ保持設定] ページで選択内容を確認できます。</span><span class="sxs-lookup"><span data-stu-id="c3df2-111">After completing the onboarding, you can verify your selection in the data retention settings page.</span></span>

## <a name="verify-data-storage-location"></a><span data-ttu-id="c3df2-112">データストレージの場所を確認する</span><span class="sxs-lookup"><span data-stu-id="c3df2-112">Verify data storage location</span></span>
<span data-ttu-id="c3df2-113">セットアップ フェーズ [中に](production-deployment.md)、データを保存する場所を選択したとします。</span><span class="sxs-lookup"><span data-stu-id="c3df2-113">During the [Set up phase](production-deployment.md), you would have selected the location to store your data.</span></span> 

<span data-ttu-id="c3df2-114">[設定データの保持] に移動すると、データの **場所**  >  **を確認できます**。</span><span class="sxs-lookup"><span data-stu-id="c3df2-114">You can verify the data location by navigating to **Settings** > **Data retention**.</span></span>

## <a name="update-data-retention-settings"></a><span data-ttu-id="c3df2-115">データ保持設定の更新</span><span class="sxs-lookup"><span data-stu-id="c3df2-115">Update data retention settings</span></span>

<span data-ttu-id="c3df2-116">データ保持設定を更新できます。</span><span class="sxs-lookup"><span data-stu-id="c3df2-116">You can update the data retention settings.</span></span> <span data-ttu-id="c3df2-117">既定では、保持期間は 180 日です。</span><span class="sxs-lookup"><span data-stu-id="c3df2-117">By default, the retention period is 180 days.</span></span> 

1. <span data-ttu-id="c3df2-118">ナビゲーション ウィンドウで、[設定データ保持 **]**  >  **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c3df2-118">In the navigation pane, select **Settings** > **Data retention**.</span></span>

2. <span data-ttu-id="c3df2-119">ドロップダウン リストからデータ保持期間を選択します。</span><span class="sxs-lookup"><span data-stu-id="c3df2-119">Select the data retention duration from the drop-down list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c3df2-120">その他の設定は編集できません。</span><span class="sxs-lookup"><span data-stu-id="c3df2-120">Other settings are not editable.</span></span>

3. <span data-ttu-id="c3df2-121">[設定 **の保存] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="c3df2-121">Click **Save preferences**.</span></span>


## <a name="related-topics"></a><span data-ttu-id="c3df2-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="c3df2-122">Related topics</span></span>
- [<span data-ttu-id="c3df2-123">データ保持設定の更新</span><span class="sxs-lookup"><span data-stu-id="c3df2-123">Update data retention settings</span></span>](data-retention-settings.md)
- [<span data-ttu-id="c3df2-124">Defender for Endpoint でアラート通知を構成する</span><span class="sxs-lookup"><span data-stu-id="c3df2-124">Configure alert notifications in Defender for Endpoint</span></span>](configure-email-notifications.md)
- [<span data-ttu-id="c3df2-125">高度な機能を構成する</span><span class="sxs-lookup"><span data-stu-id="c3df2-125">Configure advanced features</span></span>](advanced-features.md)
