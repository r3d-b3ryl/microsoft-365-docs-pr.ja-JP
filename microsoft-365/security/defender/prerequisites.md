---
title: Microsoft 365 Defender の前提条件
description: Microsoft 365 Defender のライセンス、ハードウェアとソフトウェアの要件、その他の構成設定について説明します。
keywords: 要件、前提条件、ハードウェア、ソフトウェア、ブラウザー、Microsoft 365 Defender、M365、ライセンス、E5、A5、EMS、購入
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
ms.openlocfilehash: 930a3de078d6d003241bb6fcd5df71bc9f301962
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935607"
---
# <a name="microsoft-365-defender-prerequisites"></a><span data-ttu-id="cfdaa-104">Microsoft 365 Defender の前提条件</span><span class="sxs-lookup"><span data-stu-id="cfdaa-104">Microsoft 365 Defender prerequisites</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="cfdaa-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="cfdaa-105">**Applies to:**</span></span>
- <span data-ttu-id="cfdaa-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cfdaa-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="cfdaa-107">[Microsoft 365 Defender](microsoft-365-defender.md)のプロビジョニングと使用に関するライセンスその他の要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="cfdaa-107">Learn about licensing and other requirements for provisioning and using [Microsoft 365 Defender](microsoft-365-defender.md).</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="cfdaa-108">ライセンスの要件</span><span class="sxs-lookup"><span data-stu-id="cfdaa-108">Licensing requirements</span></span>
<span data-ttu-id="cfdaa-109">これらのライセンスは、追加コストなしで Microsoft 365 セキュリティ センターの Microsoft 365 Defender 機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="cfdaa-109">Any of these licenses gives you access to Microsoft 365 Defender features in Microsoft 365 security center without additional cost:</span></span>

- <span data-ttu-id="cfdaa-110">Microsoft 365 E5 または A5</span><span class="sxs-lookup"><span data-stu-id="cfdaa-110">Microsoft 365 E5 or A5</span></span>
- <span data-ttu-id="cfdaa-111">Microsoft 365 E5 Security または A5 Security</span><span class="sxs-lookup"><span data-stu-id="cfdaa-111">Microsoft 365 E5 Security or A5 Security</span></span>
- <span data-ttu-id="cfdaa-112">Windows 10 Enterprise E5 または A5</span><span class="sxs-lookup"><span data-stu-id="cfdaa-112">Windows 10 Enterprise E5 or A5</span></span>
- <span data-ttu-id="cfdaa-113">Enterprise Mobility + Security (EMS) E5 または A5</span><span class="sxs-lookup"><span data-stu-id="cfdaa-113">Enterprise Mobility + Security (EMS) E5 or A5</span></span> 
- <span data-ttu-id="cfdaa-114">Office 365 E5 または A5</span><span class="sxs-lookup"><span data-stu-id="cfdaa-114">Office 365 E5 or A5</span></span>
- <span data-ttu-id="cfdaa-115">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="cfdaa-115">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="cfdaa-116">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="cfdaa-116">Microsoft Defender for Identity</span></span> 
- <span data-ttu-id="cfdaa-117">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="cfdaa-117">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="cfdaa-118">Defender for Office 365 (プラン 2)</span><span class="sxs-lookup"><span data-stu-id="cfdaa-118">Defender for Office 365 (Plan 2)</span></span>

<span data-ttu-id="cfdaa-119">詳細については [、Microsoft 365 Enterprise サービス プランを参照してください](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise)。</span><span class="sxs-lookup"><span data-stu-id="cfdaa-119">For more information, [view the Microsoft 365 Enterprise service plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span></span>

> <span data-ttu-id="cfdaa-120">まだライセンスがありませんか?</span><span class="sxs-lookup"><span data-stu-id="cfdaa-120">Don't have license yet?</span></span> [<span data-ttu-id="cfdaa-121">Microsoft 365 サブスクリプションを試用する/購入する</span><span class="sxs-lookup"><span data-stu-id="cfdaa-121">Try or buy a Microsoft 365 subscription</span></span>](../../commerce/try-or-buy-microsoft-365.md?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a><span data-ttu-id="cfdaa-122">既存のライセンスを確認する</span><span class="sxs-lookup"><span data-stu-id="cfdaa-122">Check your existing  licenses</span></span>
<span data-ttu-id="cfdaa-123">既存のライセンスを表示するには、Microsoft 365 管理センター[(admin.microsoft.com](https://admin.microsoft.com/)) に移動します。</span><span class="sxs-lookup"><span data-stu-id="cfdaa-123">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="cfdaa-124">管理センターで、[**課金**]  >  [**ライセンス**] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="cfdaa-124">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="cfdaa-125">ライセンス情報を表示するには[、Azure](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)サーバーで課金管理者またはグローバル リーダー AD割り当てる必要があります。 </span><span class="sxs-lookup"><span data-stu-id="cfdaa-125">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="cfdaa-126">アクセスの問題が発生した場合は、グローバル管理者に連絡してください。</span><span class="sxs-lookup"><span data-stu-id="cfdaa-126">If you encounter access problems, contact a global admin.</span></span>

## <a name="required-permissions"></a><span data-ttu-id="cfdaa-127">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="cfdaa-127">Required permissions</span></span>
<span data-ttu-id="cfdaa-128">Microsoft 365 Defenderを有効 **にするには**、Azure Active Directory のグローバル管理者またはセキュリティ管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="cfdaa-128">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft 365 Defender.</span></span> <span data-ttu-id="cfdaa-129">Microsoft 365 Defender の使用に必要な役割の一覧と、データへのアクセスが規制される方法に関する情報については [、「Microsoft 365 Defender](m365d-permissions.md)へのアクセスの管理」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cfdaa-129">For the list of roles required to use Microsoft 365 Defender and information on how access to data is regulated, read about [managing access to Microsoft 365 Defender](m365d-permissions.md).</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="cfdaa-130">ブラウザー要件</span><span class="sxs-lookup"><span data-stu-id="cfdaa-130">Browser requirements</span></span>
<span data-ttu-id="cfdaa-131">Microsoft Edge、Internet Explorer 11、または HTML 5 準拠の Web ブラウザーを使用して、Microsoft 365 セキュリティ センターの Microsoft 365 Defender にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="cfdaa-131">Access Microsoft 365 Defender in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a><span data-ttu-id="cfdaa-132">米国の GCC、GCC High、その他の米国政府機関への可用性</span><span class="sxs-lookup"><span data-stu-id="cfdaa-132">Availability to US GCC, GCC High, and other US government institutions</span></span>
<span data-ttu-id="cfdaa-133">現在、Microsoft 365 Defender は *次の機能を* 使用できません。</span><span class="sxs-lookup"><span data-stu-id="cfdaa-133">Currently, Microsoft 365 Defender is *not* available to:</span></span>
- <span data-ttu-id="cfdaa-134">米国政府機関コミュニティ クラウド (GCC)</span><span class="sxs-lookup"><span data-stu-id="cfdaa-134">US Government Community Cloud (GCC)</span></span>
- <span data-ttu-id="cfdaa-135">US Government Community Cloud High (GCC High)</span><span class="sxs-lookup"><span data-stu-id="cfdaa-135">US Government Community Cloud High (GCC High)</span></span>
- <span data-ttu-id="cfdaa-136">米国国防総省</span><span class="sxs-lookup"><span data-stu-id="cfdaa-136">US Department of Defense</span></span>
- <span data-ttu-id="cfdaa-137">商用ライセンスを持つすべての米国政府機関</span><span class="sxs-lookup"><span data-stu-id="cfdaa-137">All US government institutions with commercial licenses</span></span>

## <a name="related-topics"></a><span data-ttu-id="cfdaa-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="cfdaa-138">Related topics</span></span>
- [<span data-ttu-id="cfdaa-139">Microsoft 365 Defender の概要</span><span class="sxs-lookup"><span data-stu-id="cfdaa-139">Microsoft 365 Defender overview</span></span>](microsoft-365-defender.md)
- [<span data-ttu-id="cfdaa-140">Microsoft 365 Defender を有効にする</span><span class="sxs-lookup"><span data-stu-id="cfdaa-140">Turn on Microsoft 365 Defender</span></span>](m365d-enable.md)
- [<span data-ttu-id="cfdaa-141">アクセスとアクセス許可の管理</span><span class="sxs-lookup"><span data-stu-id="cfdaa-141">Manage access and permissions</span></span>](m365d-permissions.md)
