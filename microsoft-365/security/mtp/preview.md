---
title: Microsoft 365 Defender のプレビュー機能
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 1636b1deb5f35d8286b33238a8f4bbfff0b33521
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288127"
---
# <a name="microsoft-365-defender-preview-features"></a><span data-ttu-id="7f9d4-104">Microsoft 365 Defender プレビュー機能</span><span class="sxs-lookup"><span data-stu-id="7f9d4-104">Microsoft 365 Defender preview features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> [!IMPORTANT]
> <span data-ttu-id="7f9d4-105">プレビュー バージョンはサービス レベルアグリーメントなしで提供され、実稼働ワークロードにはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="7f9d4-105">The preview versions are provided without a service level agreement, and it's not recommended for production workloads.</span></span> <span data-ttu-id="7f9d4-106">一部の機能がサポートされていないか、機能が制限されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7f9d4-106">Certain features might not be supported or might have constrained capabilities.</span></span>

<span data-ttu-id="7f9d4-107">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="7f9d4-107">**Applies to:**</span></span>
- <span data-ttu-id="7f9d4-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7f9d4-108">Microsoft 365 Defender</span></span>

<span data-ttu-id="7f9d4-109">Microsoft 365 Defender サービスは常に更新され、新しい機能拡張と機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="7f9d4-109">The Microsoft 365 Defender service is constantly being updated to include new feature enhancements and capabilities.</span></span>

<span data-ttu-id="7f9d4-110">Microsoft 365 Defender プレビュー リリースの新機能について説明し、プレビュー エクスペリエンスをオンにして今後の機能を最初に試してみてください。</span><span class="sxs-lookup"><span data-stu-id="7f9d4-110">Learn about new features in the Microsoft 365 Defender preview release and be among the first to try upcoming features by turning on the preview experience.</span></span>

<span data-ttu-id="7f9d4-111">一般に利用可能な新機能について詳しくは [、Microsoft 365 Defender の新機能に関するページをご覧ください](whats-new.md)。</span><span class="sxs-lookup"><span data-stu-id="7f9d4-111">For more information on new capabilities that are generally available, see [What's new in Microsoft 365 Defender](whats-new.md).</span></span>

## <a name="required-permissions"></a><span data-ttu-id="7f9d4-112">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="7f9d4-112">Required permissions</span></span>

<span data-ttu-id="7f9d4-113">次の Azure Active Directory (Azure AD) ロールが割り当てられているアカウントは、Microsoft 365 Defender Preview 機能を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="7f9d4-113">Accounts assigned the following Azure Active Directory (Azure AD) roles can turn on Microsoft 365 Defender Preview features:</span></span>

- <span data-ttu-id="7f9d4-114">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="7f9d4-114">Global administrator</span></span>
- <span data-ttu-id="7f9d4-115">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="7f9d4-115">Security administrator</span></span>
- <span data-ttu-id="7f9d4-116">セキュリティ オペレーター</span><span class="sxs-lookup"><span data-stu-id="7f9d4-116">Security Operator</span></span>

## <a name="turn-on-preview-features"></a><span data-ttu-id="7f9d4-117">プレビュー機能を有効にする</span><span class="sxs-lookup"><span data-stu-id="7f9d4-117">Turn on preview features</span></span>

<span data-ttu-id="7f9d4-118">機能が一般提供される前に、全体的なエクスペリエンスを向上させるためにフィードバックを提供できる今後の機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="7f9d4-118">You'll have access to upcoming features that you can provide feedback on to help improve the overall experience before features are generally available.</span></span>

<span data-ttu-id="7f9d4-119">プレビュー機能設定をオンにして、今後の機能をいち早く試します。</span><span class="sxs-lookup"><span data-stu-id="7f9d4-119">Turn on the preview experience setting to be among the first to try upcoming features.</span></span>

1. <span data-ttu-id="7f9d4-120">ナビゲーション ウィンドウで、**[設定]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="7f9d4-120">In the navigation pane, select **Settings**.</span></span>
2. <span data-ttu-id="7f9d4-121">**Microsoft 365 Defender を選択します**。</span><span class="sxs-lookup"><span data-stu-id="7f9d4-121">Select **Microsoft 365 Defender**.</span></span>
3. <span data-ttu-id="7f9d4-122">**[プレビュー機能]** > **を選択し、プレビュー機能をオンにします**。</span><span class="sxs-lookup"><span data-stu-id="7f9d4-122">Select **Preview features** > **Turn on preview features**.</span></span> 
4. <span data-ttu-id="7f9d4-123">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7f9d4-123">Select **Save**.</span></span>

<span data-ttu-id="7f9d4-124">**[プレビュー機能をオンにする]** チェックボックスが選択されていると、プレビュー機能がオンになっていることがわかります。</span><span class="sxs-lookup"><span data-stu-id="7f9d4-124">You'll know you have preview features turned on when you see that the **Turn on preview features** check box is selected.</span></span> 

## <a name="preview-features"></a><span data-ttu-id="7f9d4-125">プレビュー機能</span><span class="sxs-lookup"><span data-stu-id="7f9d4-125">Preview features</span></span>

<span data-ttu-id="7f9d4-126">現在、次の機能と拡張機能がプレビューで利用できます:</span><span class="sxs-lookup"><span data-stu-id="7f9d4-126">The following features and enhancements are currently available on preview:</span></span>

### <a name="improved-microsoft-365-security-center"></a><span data-ttu-id="7f9d4-127">Microsoft 365 セキュリティ センターの強化</span><span class="sxs-lookup"><span data-stu-id="7f9d4-127">Improved Microsoft 365 security center</span></span>
<span data-ttu-id="7f9d4-128">改善された [Microsoft 365 セキュリティ センター](https://security.microsoft.com)がパブリック プレビューで利用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="7f9d4-128">The improved [Microsoft 365 security center](https://security.microsoft.com) is now available in public preview.</span></span> <span data-ttu-id="7f9d4-129">この新しいエクスペリエンスにより、Defender for Endpoint、Defender for Office 365、Microsoft 365 Defender、その他が Microsoft 365 セキュリティ センターに追加されます。</span><span class="sxs-lookup"><span data-stu-id="7f9d4-129">This new experience brings Defender for Endpoint, Defender for Office 365, Microsoft 365 Defender, and more into the Microsoft 365 security center.</span></span> <span data-ttu-id="7f9d4-130">これは、セキュリティ制御を管理するための新しいホームです。</span><span class="sxs-lookup"><span data-stu-id="7f9d4-130">This is the new home to manage your security controls.</span></span> <span data-ttu-id="7f9d4-131">[新機能について説明します](https://docs.microsoft.com/microsoft-365/security/mtp/overview-security-center)。</span><span class="sxs-lookup"><span data-stu-id="7f9d4-131">[Learn what's new](https://docs.microsoft.com/microsoft-365/security/mtp/overview-security-center).</span></span>

- <span data-ttu-id="7f9d4-132">**[Microsoft 365 Defender 脅威分析](threat-analytics.md)** レポート - 脅威分析は、アクティブな攻撃への対応と影響の最小化に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="7f9d4-132">**[Microsoft 365 Defender threat analytics report](threat-analytics.md)** - Threat analytics helps you respond to and minimize the impact of active attacks.</span></span> <span data-ttu-id="7f9d4-133">また、Microsoft 365 Defender ソリューションによってブロックされる攻撃の試みについて学習し、さらなる露出のリスクを軽減し、回復性を高める予防的なアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="7f9d4-133">You can also learn about attack attempts blocked by Microsoft 365 Defender solutions and take preventive actions that mitigate the risk of further exposure and increase resiliency.</span></span> <span data-ttu-id="7f9d4-134">統合されたセキュリティ エクスペリエンスの一環として、Microsoft Defender for Endpoint および Microsoft Defender for Office E5 ライセンス所有者向け脅威分析が利用できます。</span><span class="sxs-lookup"><span data-stu-id="7f9d4-134">As part of the unified security experience, threat analytics is now available for Microsoft Defender for Endpoint and Microsoft Defender for Office E5 license holders.</span></span>
- <span data-ttu-id="7f9d4-135">**[Microsoft 365 Defender API](api-overview.md)** - Microsoft 365 Defender のトップ レベル API を使用すると、共有インシデントと高度な検索テーブルに基づいてワークフローを自動化できます。</span><span class="sxs-lookup"><span data-stu-id="7f9d4-135">**[Microsoft 365 Defender APIs](api-overview.md)** - The top-level Microsoft 365 Defender APIs will enable you to automate workflows based on the shared incident and advanced hunting tables.</span></span> 
- <span data-ttu-id="7f9d4-136">**[高度な検索でアクションを実行](advanced-hunting-take-action.md)** する — 高度な検索で見つけた脅威を迅速に含むか、侵害された資産 [に対処します](advanced-hunting-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="7f9d4-136">**[Take action in advanced hunting](advanced-hunting-take-action.md)**—Quickly contain threats or address compromised assets that you find in [advanced hunting](advanced-hunting-overview.md).</span></span>
- <span data-ttu-id="7f9d4-137">**[ポータル内スキーマ リファレンス](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)**— 高度な検索スキーマ テーブルに関する情報をセキュリティ センターで直接取得します。</span><span class="sxs-lookup"><span data-stu-id="7f9d4-137">**[In-portal schema reference](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)**—Get information about advanced hunting schema tables directly in the security center.</span></span> <span data-ttu-id="7f9d4-138">このリファレンスには、テーブルと列の説明に加えて、サポートされているイベントの種類 ( `ActionType` 値) とサンプル クエリが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7f9d4-138">In addition to table and column descriptions, this reference includes supported event types (`ActionType` values) and sample queries.</span></span>
- <span data-ttu-id="7f9d4-139">**[DeviceFromIP() 関数](advanced-hunting-devicefromip-function.md)**—特定の時間範囲で特定の IP アドレスが割り当てられているデバイスに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="7f9d4-139">**[DeviceFromIP() function](advanced-hunting-devicefromip-function.md)**—Get information about which devices have been assigned a specific IP address or addresses at a given time range.</span></span>
