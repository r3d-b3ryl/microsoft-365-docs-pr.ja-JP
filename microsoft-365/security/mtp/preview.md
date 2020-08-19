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
ms.openlocfilehash: ff610cee46b2b48815af82fa86d0b30aa99f4b5c
ms.sourcegitcommit: 445b249a6f0420b32e49742fd7744006c7090b2b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/18/2020
ms.locfileid: "46798236"
---
# <a name="microsoft-threat-protection-preview-features"></a><span data-ttu-id="0ddbc-104">Microsoft Threat Protection のプレビュー機能</span><span class="sxs-lookup"><span data-stu-id="0ddbc-104">Microsoft Threat Protection preview features</span></span>

<span data-ttu-id="0ddbc-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="0ddbc-105">**Applies to:**</span></span>
- <span data-ttu-id="0ddbc-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="0ddbc-106">Microsoft Threat Protection</span></span>


<span data-ttu-id="0ddbc-107">Microsoft Threat Protection サービスは、新しい機能の拡張と機能を含むように、絶えず更新されています。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-107">The Microsoft Threat Protection service is constantly being updated to include new feature enhancements and capabilities.</span></span>

<span data-ttu-id="0ddbc-108">Microsoft Threat Protection プレビューリリースの新機能について説明し、プレビューの操作をオンにして、最初に予定されている機能を試すことができます。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-108">Learn about new features in the Microsoft Threat Protection preview release and be among the first to try upcoming features by turning on the preview experience.</span></span>

<span data-ttu-id="0ddbc-109">一般的に利用可能な新機能の詳細については、「[Microsoft Threat Protection の新機能](whats-new.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-109">For more information on new capabilities that are generally available, see [What's new in Microsoft Threat Protection](whats-new.md).</span></span>

## <a name="turn-on-preview-features"></a><span data-ttu-id="0ddbc-110">プレビュー機能を有効にする</span><span class="sxs-lookup"><span data-stu-id="0ddbc-110">Turn on preview features</span></span>
<span data-ttu-id="0ddbc-111">機能が一般に利用可能になるまでの全体的な操作を改善するためにフィードバックできる、今後提供される機能にアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-111">You'll have access to upcoming features which you can provide feedback on to help improve the overall experience before features are generally available.</span></span>

<span data-ttu-id="0ddbc-112">[プレビュー環境] 設定をオンにして、最初の機能を試すことができます。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-112">Turn on the preview experience setting to be among the first to try upcoming features.</span></span>

1. <span data-ttu-id="0ddbc-113">ナビゲーションウィンドウで、[ **設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-113">In the navigation pane, select **Settings**.</span></span>

2. <span data-ttu-id="0ddbc-114">[ **Microsoft Threat Protection**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-114">Select **Microsoft Threat Protection**.</span></span>


3. <span data-ttu-id="0ddbc-115">[**プレビュー機能の選択]**  >  **プレビュー機能を有効に**します。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-115">Select **Preview features** > **Turn on preview features**.</span></span> 

3. <span data-ttu-id="0ddbc-116">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-116">Select **Save**.</span></span>

<span data-ttu-id="0ddbc-117">[ **プレビュー機能を有効に** する] チェックボックスがオンになっている場合は、プレビュー機能が有効になっていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-117">You'll know you have preview features turned on when you see that the **Turn on preview features** check box is selected.</span></span> 

## <a name="preview-features"></a><span data-ttu-id="0ddbc-118">プレビュー機能</span><span class="sxs-lookup"><span data-stu-id="0ddbc-118">Preview features</span></span>
<span data-ttu-id="0ddbc-119">現在、次の機能と拡張機能をプレビューで利用できます。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-119">The following features and enhancements are currently available on preview:</span></span>

- <span data-ttu-id="0ddbc-120">**[高度な検索の](advanced-hunting-identitydirectoryevents-table.md)** 場合は、Active DIRECTORY (AD) を実行しているオンプレミスのドメインコントローラーを含むイベントを検索します。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-120">**[IdentityDirectoryEvents table in advanced hunting](advanced-hunting-identitydirectoryevents-table.md)** — Find events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="0ddbc-121">この表では、ドメインコントローラーの id 関連イベントの範囲とシステムイベントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-121">This table covers a range of identity-related events as well as system events on the domain controller.</span></span>
- <span data-ttu-id="0ddbc-122">**[AssignedIPAddresses () 関数](advanced-hunting-assignedipaddresses-function.md)** -高度な検索でこの関数を使用して、デバイスに割り当てられている最新の ip アドレス、または指定した時点からの最新の ip アドレスをすばやく取得します。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-122">**[AssignedIPAddresses() function](advanced-hunting-assignedipaddresses-function.md)** — Use this function in advanced hunting to quickly obtain the latest IP addresses that have been assigned to a device or the most recent IP addresses from a specified point in time.</span></span>
- <span data-ttu-id="0ddbc-123">**[高度な検索でアクションを実行](advanced-hunting-take-action.md)** する: [高度な](advanced-hunting-overview.md)検索によって検出された脅威または侵害された資産への対処をすばやく行うことができます。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-123">**[Take action in advanced hunting](advanced-hunting-take-action.md)** — Quickly contain threats or address compromised assets that you find in [advanced hunting](advanced-hunting-overview.md).</span></span>
- <span data-ttu-id="0ddbc-124">**[ポータル内スキーマリファレンス](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** : セキュリティセンターで、高度な検索スキーマテーブルに関する情報を直接取得します。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-124">**[In-portal schema reference](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** — Get information about advanced hunting schema tables directly in the security center.</span></span> <span data-ttu-id="0ddbc-125">この便利なリファレンスでは、テーブルと列の説明に加えて、サポートされているイベントの種類 (値) とサンプルクエリに関する情報を提供して `ActionType` います。</span><span class="sxs-lookup"><span data-stu-id="0ddbc-125">In addition to table and column descriptions, this convenient reference provides information about supported event types (`ActionType` values) and sample queries.</span></span>

