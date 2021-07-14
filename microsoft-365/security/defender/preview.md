---
title: プレビュー機能のMicrosoft 365 Defender
description: Microsoft 365 セキュリティの新機能について学ぶ
keywords: プレビュー、新規、m365 セキュリティ、セキュリティ、365、機能
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 088dbd16c3667331843ff934c80f85aa8d3a837f
ms.sourcegitcommit: 997a21b83795789cda0a6b4a77f9985a3233d0c0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2021
ms.locfileid: "53430818"
---
# <a name="microsoft-365-defender-preview-features"></a><span data-ttu-id="b4dbd-104">Microsoft 365 Defenderプレビュー機能</span><span class="sxs-lookup"><span data-stu-id="b4dbd-104">Microsoft 365 Defender preview features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="b4dbd-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="b4dbd-105">**Applies to:**</span></span>
- <span data-ttu-id="b4dbd-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b4dbd-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="b4dbd-107">新Microsoft 365 Defender機能を含むサービスが常に更新されています。</span><span class="sxs-lookup"><span data-stu-id="b4dbd-107">The Microsoft 365 Defender service is constantly being updated to include new feature enhancements and capabilities.</span></span>

<span data-ttu-id="b4dbd-108">プレビュー リリースの新機能Microsoft 365 Defender、プレビュー エクスペリエンスをオンにして、今後の機能を最初に試してみてください。</span><span class="sxs-lookup"><span data-stu-id="b4dbd-108">Learn about new features in the Microsoft 365 Defender preview release and be among the first to try upcoming features by turning on the preview experience.</span></span>

<span data-ttu-id="b4dbd-109">一般に利用可能な新機能の詳細については、「新機能」を参照[Microsoft 365 Defender。](whats-new.md)</span><span class="sxs-lookup"><span data-stu-id="b4dbd-109">For more information on new capabilities that are generally available, see [What's new in Microsoft 365 Defender](whats-new.md).</span></span>

 ## <a name="what-you-need-to-know"></a><span data-ttu-id="b4dbd-110">知る必要があるもの</span><span class="sxs-lookup"><span data-stu-id="b4dbd-110">What you need to know</span></span>

<span data-ttu-id="b4dbd-111">パブリック プレビューで機能を操作する場合は、次の機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="b4dbd-111">When working with features in public preview, these features:</span></span>

- <span data-ttu-id="b4dbd-112">機能が制限または制限されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b4dbd-112">May have restricted or limited functionality.</span></span> <span data-ttu-id="b4dbd-113">たとえば、この機能は 1 つのプラットフォームにのみ適用できます。</span><span class="sxs-lookup"><span data-stu-id="b4dbd-113">For example, the feature may only apply to one platform.</span></span>
- <span data-ttu-id="b4dbd-114">通常、機能の変更は、一般に利用できる (GA) 前に行います。</span><span class="sxs-lookup"><span data-stu-id="b4dbd-114">Typically go through feature changes before they're generally available (GA).</span></span>
- <span data-ttu-id="b4dbd-115">Microsoft で完全にサポートされています。</span><span class="sxs-lookup"><span data-stu-id="b4dbd-115">Are fully supported by Microsoft.</span></span>
- <span data-ttu-id="b4dbd-116">選択した地域またはクラウド環境でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="b4dbd-116">May only be available in selected geographic regions or cloud environments.</span></span> <span data-ttu-id="b4dbd-117">たとえば、この機能が政府機関のクラウドに存在しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b4dbd-117">For example, the feature may not exist in the government cloud.</span></span>
- <span data-ttu-id="b4dbd-118">プレビューの個々の機能には、使用およびサポートの制限が多い場合があります。</span><span class="sxs-lookup"><span data-stu-id="b4dbd-118">Individual features in preview may have more usage and support restrictions.</span></span> <span data-ttu-id="b4dbd-119">その場合、この情報は通常、機能のドキュメントに示されています。</span><span class="sxs-lookup"><span data-stu-id="b4dbd-119">If so, this information is typically noted in the feature documentation.</span></span>
- <span data-ttu-id="b4dbd-120">プレビュー バージョンは標準のサポート レベルで提供され、実稼働環境で使用できます。</span><span class="sxs-lookup"><span data-stu-id="b4dbd-120">The preview versions are provided with a standard support level, and can be used for production environments.</span></span> 



## <a name="required-permissions"></a><span data-ttu-id="b4dbd-121">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="b4dbd-121">Required permissions</span></span>

<span data-ttu-id="b4dbd-122">次のロール (Azure Azure Active Directory) AD割り当てられたアカウントは、プレビュー機能Microsoft 365 Defender有効にできます。</span><span class="sxs-lookup"><span data-stu-id="b4dbd-122">Accounts assigned the following Azure Active Directory (Azure AD) roles can turn on Microsoft 365 Defender Preview features:</span></span>

- <span data-ttu-id="b4dbd-123">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="b4dbd-123">Global administrator</span></span>
- <span data-ttu-id="b4dbd-124">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="b4dbd-124">Security administrator</span></span>
- <span data-ttu-id="b4dbd-125">セキュリティ オペレーター</span><span class="sxs-lookup"><span data-stu-id="b4dbd-125">Security Operator</span></span>

## <a name="turn-on-preview-features"></a><span data-ttu-id="b4dbd-126">プレビュー機能を有効にする</span><span class="sxs-lookup"><span data-stu-id="b4dbd-126">Turn on preview features</span></span>

<span data-ttu-id="b4dbd-127">今後の機能にアクセスしてフィードバックを提供し、機能が一般提供される前に全体的なエクスペリエンスを向上させるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b4dbd-127">You'll have access to upcoming features that you can provide feedback on to help improve the overall experience before features are generally available.</span></span>

<span data-ttu-id="b4dbd-128">プレビュー機能設定をオンにして、今後の機能をいち早く試します。</span><span class="sxs-lookup"><span data-stu-id="b4dbd-128">Turn on the preview experience setting to be among the first to try upcoming features.</span></span>

1. <span data-ttu-id="b4dbd-129">ナビゲーション ウィンドウで、**[設定]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="b4dbd-129">In the navigation pane, select **Settings**.</span></span>
2. <span data-ttu-id="b4dbd-130">[Microsoft 365 Defender]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b4dbd-130">Select **Microsoft 365 Defender**.</span></span>
3. <span data-ttu-id="b4dbd-131">**[プレビュー機能]** > **を選択し、プレビュー機能をオンにします**。</span><span class="sxs-lookup"><span data-stu-id="b4dbd-131">Select **Preview features** > **Turn on preview features**.</span></span> 
4. <span data-ttu-id="b4dbd-132">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b4dbd-132">Select **Save**.</span></span>

<span data-ttu-id="b4dbd-133">**[プレビュー機能をオンにする]** チェックボックスが選択されていると、プレビュー機能がオンになっていることがわかります。</span><span class="sxs-lookup"><span data-stu-id="b4dbd-133">You'll know you have preview features turned on when you see that the **Turn on preview features** check box is selected.</span></span> 

## <a name="preview-features"></a><span data-ttu-id="b4dbd-134">プレビュー機能</span><span class="sxs-lookup"><span data-stu-id="b4dbd-134">Preview features</span></span>

<span data-ttu-id="b4dbd-135">現在、次の機能と拡張機能がプレビューで利用できます:</span><span class="sxs-lookup"><span data-stu-id="b4dbd-135">The following features and enhancements are currently available on preview:</span></span>

- <span data-ttu-id="b4dbd-136">**[脅威タグごとにレポートを表示](threat-analytics.md#view-reports-per-threat-tags)** する - 脅威タグは、特定の脅威カテゴリに焦点を当て、最も関連性の高いレポートを確認するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b4dbd-136">**[View reports per threat tags](threat-analytics.md#view-reports-per-threat-tags)** - Threat tags help you focus on specific threat categories and review the most relevant reports.</span></span>
- <span data-ttu-id="b4dbd-137">**[ストリーミング API](../defender-endpoint/raw-data-export.md)** - Microsoft 365 Defender高度なハンティングを通じて利用可能なすべてのイベントをイベント ハブや Azure ストレージ アカウントにストリーミングできます。</span><span class="sxs-lookup"><span data-stu-id="b4dbd-137">**[Streaming API](../defender-endpoint/raw-data-export.md)** - Microsoft 365 Defender supports streaming all the events available through Advanced Hunting to an Event Hubs and/or Azure storage account.</span></span>
- <span data-ttu-id="b4dbd-138">**[Microsoft 365 Defender API](api-overview.md)** - トップ レベルの Microsoft 365 Defender API を使用すると、共有インシデントテーブルと高度なハンティング テーブルに基づいてワークフローを自動化できます。</span><span class="sxs-lookup"><span data-stu-id="b4dbd-138">**[Microsoft 365 Defender APIs](api-overview.md)** - The top-level Microsoft 365 Defender APIs will enable you to automate workflows based on the shared incident and advanced hunting tables.</span></span> 
- <span data-ttu-id="b4dbd-139">**[高度な狩猟でアクションを](advanced-hunting-take-action.md)** 実行する - 高度な狩猟で見つけた脅威を迅速に含むか、侵害された資産 [に対処します](advanced-hunting-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="b4dbd-139">**[Take action in advanced hunting](advanced-hunting-take-action.md)** - Quickly contain threats or address compromised assets that you find in [advanced hunting](advanced-hunting-overview.md).</span></span>
- <span data-ttu-id="b4dbd-140">**[ポータル内スキーマ参照](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** - セキュリティ センターで高度な検索スキーマ テーブルに関する情報を直接取得します。</span><span class="sxs-lookup"><span data-stu-id="b4dbd-140">**[In-portal schema reference](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** - Get information about advanced hunting schema tables directly in the security center.</span></span> <span data-ttu-id="b4dbd-141">テーブルと列の説明に加えて、この参照には、サポートされているイベントの種類 ( `ActionType` 値) とサンプル クエリが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b4dbd-141">In addition to table and column descriptions, this reference includes supported event types (`ActionType` values) and sample queries.</span></span>
- <span data-ttu-id="b4dbd-142">**[DeviceFromIP() 関数](advanced-hunting-devicefromip-function.md)** - 特定の時間範囲で特定の IP アドレスまたはアドレスが割り当てられているデバイスに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="b4dbd-142">**[DeviceFromIP() function](advanced-hunting-devicefromip-function.md)** - Get information about which devices have been assigned a specific IP address or addresses at a given time range.</span></span>
