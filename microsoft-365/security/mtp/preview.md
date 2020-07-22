---
title: Microsoft の脅威保護のプレビュー機能
description: Microsoft 365 セキュリティの新機能について説明します。
keywords: preview、new、m365 security、security、365、capabilities
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 4dde4d1b30fe5bcbe4d3bc63c4d998c804b0ce69
ms.sourcegitcommit: b4119682bd3c036289e851fff56fde869c816479
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/22/2020
ms.locfileid: "45204829"
---
# <a name="microsoft-threat-protection-preview-features"></a><span data-ttu-id="67026-104">Microsoft Threat Protection のプレビュー機能</span><span class="sxs-lookup"><span data-stu-id="67026-104">Microsoft Threat Protection preview features</span></span>

<span data-ttu-id="67026-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="67026-105">**Applies to:**</span></span>
- <span data-ttu-id="67026-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="67026-106">Microsoft Threat Protection</span></span>


<span data-ttu-id="67026-107">Microsoft Threat Protection サービスは、新しい機能の拡張と機能を含むように、絶えず更新されています。</span><span class="sxs-lookup"><span data-stu-id="67026-107">The Microsoft Threat Protection service is constantly being updated to include new feature enhancements and capabilities.</span></span>

<span data-ttu-id="67026-108">Microsoft Threat Protection プレビューリリースの新機能について説明し、プレビューの操作をオンにして、最初に予定されている機能を試すことができます。</span><span class="sxs-lookup"><span data-stu-id="67026-108">Learn about new features in the Microsoft Threat Protection preview release and be among the first to try upcoming features by turning on the preview experience.</span></span>

<span data-ttu-id="67026-109">一般的に利用可能な新機能の詳細については、「[Microsoft Threat Protection の新機能](whats-new.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67026-109">For more information on new capabilities that are generally available, see [What's new in Microsoft Threat Protection](whats-new.md).</span></span>

## <a name="turn-on-preview-features"></a><span data-ttu-id="67026-110">プレビュー機能を有効にする</span><span class="sxs-lookup"><span data-stu-id="67026-110">Turn on preview features</span></span>
<span data-ttu-id="67026-111">機能が一般に利用可能になるまでの全体的な操作を改善するためにフィードバックできる、今後提供される機能にアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="67026-111">You'll have access to upcoming features which you can provide feedback on to help improve the overall experience before features are generally available.</span></span>

<span data-ttu-id="67026-112">[プレビュー環境] 設定をオンにして、最初の機能を試すことができます。</span><span class="sxs-lookup"><span data-stu-id="67026-112">Turn on the preview experience setting to be among the first to try upcoming features.</span></span>

1. <span data-ttu-id="67026-113">ナビゲーションウィンドウで、[**設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="67026-113">In the navigation pane, select **Settings**.</span></span>

2. <span data-ttu-id="67026-114">[ **Microsoft Threat Protection**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="67026-114">Select **Microsoft Threat Protection**.</span></span>


3. <span data-ttu-id="67026-115">[**プレビュー機能の選択]**  >  **プレビュー機能を有効に**します。</span><span class="sxs-lookup"><span data-stu-id="67026-115">Select **Preview features** > **Turn on preview features**.</span></span> 

3. <span data-ttu-id="67026-116">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="67026-116">Select **Save**.</span></span>

<span data-ttu-id="67026-117">[**プレビュー機能を有効に**する] チェックボックスがオンになっている場合は、プレビュー機能が有効になっていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="67026-117">You'll know you have preview features turned on when you see that the **Turn on preview features** check box is selected.</span></span> 

## <a name="preview-features"></a><span data-ttu-id="67026-118">プレビュー機能</span><span class="sxs-lookup"><span data-stu-id="67026-118">Preview features</span></span>
<span data-ttu-id="67026-119">現在、次の機能と拡張機能をプレビューで利用できます。</span><span class="sxs-lookup"><span data-stu-id="67026-119">The following features and enhancements are currently available on preview:</span></span>

- <span data-ttu-id="67026-120">**[ポータル内スキーマリファレンス](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)**: セキュリティセンターで直接使用できるスキーマテーブルに関する情報。</span><span class="sxs-lookup"><span data-stu-id="67026-120">**[In-portal schema reference](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** — information about schema tables available directly in the security center.</span></span> <span data-ttu-id="67026-121">このリファレンスでは、テーブルと列の説明に加えて、サポートされているイベントの種類 ( `ActionType` 値) とサンプルクエリに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="67026-121">In addition to table and column descriptions, this reference provides information about supported event types (`ActionType` values) and sample queries.</span></span>  

- <span data-ttu-id="67026-122">**[ハントの移動](advanced-hunting-go-hunt.md)**—クエリベースの[高度な](advanced-hunting-overview.md)検索機能を使用して、特定のイベント、ユーザー、デバイス、またはその他のエンティティの種類を調査するために、インシデントの調査からすばやくピボットします。</span><span class="sxs-lookup"><span data-stu-id="67026-122">**[Go hunt](advanced-hunting-go-hunt.md)** — quickly pivot from investigating an incident to inspecting a specific event, a user, a device, or other entity types using query-based [advanced hunting](advanced-hunting-overview.md) capabilities.</span></span>
