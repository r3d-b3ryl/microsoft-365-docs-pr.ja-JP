---
title: Microsoft 365 Defender のプレビュー機能
description: Microsoft 365 セキュリティの新機能について学ぶ
keywords: プレビュー、新規、m365 セキュリティ、セキュリティ、365、機能
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
ms.openlocfilehash: 4c731869d1ec1740f8c9173705f9af72b0e2fe53
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844754"
---
# <a name="microsoft-365-defender-preview-features"></a><span data-ttu-id="cae14-104">Microsoft 365 Defender プレビュー機能</span><span class="sxs-lookup"><span data-stu-id="cae14-104">Microsoft 365 Defender preview features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

>[!IMPORTANT]
><span data-ttu-id="cae14-105">プレビューバージョンはサービスレベル契約なしで提供されるので、運用ワークロードにはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="cae14-105">The preview versions are provided without a service level agreement, and it's not recommended for production workloads.</span></span> <span data-ttu-id="cae14-106">一部の機能はサポートされていない場合や、制限された機能を備えている場合があります。</span><span class="sxs-lookup"><span data-stu-id="cae14-106">Certain features might not be supported or might have constrained capabilities.</span></span>

<span data-ttu-id="cae14-107">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="cae14-107">**Applies to:**</span></span>
- <span data-ttu-id="cae14-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cae14-108">Microsoft 365 Defender</span></span>

<span data-ttu-id="cae14-109">Microsoft 365 Defender service は、新しい機能の拡張と機能を含むように常に更新されています。</span><span class="sxs-lookup"><span data-stu-id="cae14-109">The Microsoft 365 Defender service is constantly being updated to include new feature enhancements and capabilities.</span></span>

<span data-ttu-id="cae14-110">Microsoft 365 Defender プレビューリリースの新機能について説明し、プレビューの操作をオンにして、最初の機能を試すことができます。</span><span class="sxs-lookup"><span data-stu-id="cae14-110">Learn about new features in the Microsoft 365 Defender preview release and be among the first to try upcoming features by turning on the preview experience.</span></span>

<span data-ttu-id="cae14-111">一般的に使用できる新機能の詳細については、「 [Microsoft の新機能 (365 Defender](whats-new.md))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cae14-111">For more information on new capabilities that are generally available, see [What's new in Microsoft 365 Defender](whats-new.md).</span></span>

## <a name="turn-on-preview-features"></a><span data-ttu-id="cae14-112">プレビュー機能を有効にする</span><span class="sxs-lookup"><span data-stu-id="cae14-112">Turn on preview features</span></span>
<span data-ttu-id="cae14-113">機能が一般に利用可能になるまでの全体的な操作を改善するためにフィードバックできる、今後提供される機能にアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="cae14-113">You'll have access to upcoming features that you can provide feedback on to help improve the overall experience before features are generally available.</span></span>

<span data-ttu-id="cae14-114">プレビュー機能設定をオンにして、今後の機能をいち早く試します。</span><span class="sxs-lookup"><span data-stu-id="cae14-114">Turn on the preview experience setting to be among the first to try upcoming features.</span></span>

1. <span data-ttu-id="cae14-115">ナビゲーション ウィンドウで、 **[設定]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="cae14-115">In the navigation pane, select **Settings**.</span></span>

2. <span data-ttu-id="cae14-116">[ **Microsoft 365 Defender** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cae14-116">Select **Microsoft 365 Defender**.</span></span>


3. <span data-ttu-id="cae14-117">**[プレビュー機能]** > **を選択し、プレビュー機能をオンにします** 。</span><span class="sxs-lookup"><span data-stu-id="cae14-117">Select **Preview features** > **Turn on preview features**.</span></span> 

3. <span data-ttu-id="cae14-118">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cae14-118">Select **Save**.</span></span>

<span data-ttu-id="cae14-119">**[プレビュー機能をオンにする]** チェックボックスが選択されていると、プレビュー機能がオンになっていることがわかります。</span><span class="sxs-lookup"><span data-stu-id="cae14-119">You'll know you have preview features turned on when you see that the **Turn on preview features** check box is selected.</span></span> 

## <a name="preview-features"></a><span data-ttu-id="cae14-120">プレビュー機能</span><span class="sxs-lookup"><span data-stu-id="cae14-120">Preview features</span></span>
<span data-ttu-id="cae14-121">現在、次の機能と拡張機能がプレビューで利用できます:</span><span class="sxs-lookup"><span data-stu-id="cae14-121">The following features and enhancements are currently available on preview:</span></span>

- <span data-ttu-id="cae14-122">**[Microsoft 365 Defender api](api-overview.md)** -lop レベルの Microsoft 365 Defender api を使用すると、共有インシデントと高度な検索テーブルに基づいてワークフローを自動化することができます。</span><span class="sxs-lookup"><span data-stu-id="cae14-122">**[Microsoft 365 Defender APIs](api-overview.md)** - The lop-level Microsoft 365 Defender APIs will enable you to automate workflows based on the shared incident and advanced hunting tables.</span></span> 
- <span data-ttu-id="cae14-123">**[高度な検索でアクションを実行](advanced-hunting-take-action.md)** する: [高度な](advanced-hunting-overview.md)検索によって検出された脅威または侵害された資産への対処をすばやく行うことができます。</span><span class="sxs-lookup"><span data-stu-id="cae14-123">**[Take action in advanced hunting](advanced-hunting-take-action.md)** —Quickly contain threats or address compromised assets that you find in [advanced hunting](advanced-hunting-overview.md).</span></span>
- <span data-ttu-id="cae14-124">**[ポータル内スキーマリファレンス](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** : セキュリティセンターで、高度な検索スキーマテーブルに関する情報を直接取得します。</span><span class="sxs-lookup"><span data-stu-id="cae14-124">**[In-portal schema reference](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** —Get information about advanced hunting schema tables directly in the security center.</span></span> <span data-ttu-id="cae14-125">このリファレンスには、テーブルと列の説明に加えて、サポートされているイベントの種類 ( `ActionType` 値) とサンプルクエリが含まれています。</span><span class="sxs-lookup"><span data-stu-id="cae14-125">In addition to table and column descriptions, this reference includes supported event types (`ActionType` values) and sample queries.</span></span>

