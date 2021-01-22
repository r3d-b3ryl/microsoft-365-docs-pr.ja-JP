---
title: Microsoft 365 Defender の前提条件
description: Microsoft 365 Defender のライセンス、ハードウェアとソフトウェアの要件、その他の構成設定について説明します。
keywords: 要件, 前提条件, ハードウェア, ソフトウェア, ブラウザー, MTP, M365, ライセンス, E5, A5, EMS, 購入
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
ms.openlocfilehash: ee1777debdb91a6ac73737db2db48e434ed3e2e2
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930092"
---
# <a name="microsoft-365-defender-prerequisites"></a><span data-ttu-id="2a5ca-104">Microsoft 365 Defender の前提条件</span><span class="sxs-lookup"><span data-stu-id="2a5ca-104">Microsoft 365 Defender prerequisites</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="2a5ca-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="2a5ca-105">**Applies to:**</span></span>
- <span data-ttu-id="2a5ca-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2a5ca-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="2a5ca-107">[ライセンスと、Microsoft 365 Defender](microsoft-threat-protection.md)のプロビジョニングと使用に関するその他の要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="2a5ca-107">Learn about licensing and other requirements for provisioning and using [Microsoft 365 Defender](microsoft-threat-protection.md).</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="2a5ca-108">ライセンスの要件</span><span class="sxs-lookup"><span data-stu-id="2a5ca-108">Licensing requirements</span></span>
<span data-ttu-id="2a5ca-109">これらのライセンスは、追加コストなしで Microsoft 365 セキュリティ センターの Microsoft 365 Defender 機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="2a5ca-109">Any of these licenses gives you access to Microsoft 365 Defender features in Microsoft 365 security center without additional cost:</span></span>

- <span data-ttu-id="2a5ca-110">Microsoft 365 E5 または A5</span><span class="sxs-lookup"><span data-stu-id="2a5ca-110">Microsoft 365 E5 or A5</span></span>
- <span data-ttu-id="2a5ca-111">Microsoft 365 E5 セキュリティまたは A5 セキュリティ</span><span class="sxs-lookup"><span data-stu-id="2a5ca-111">Microsoft 365 E5 Security or A5 Security</span></span>
- <span data-ttu-id="2a5ca-112">Windows 10 Enterprise E5 または A5</span><span class="sxs-lookup"><span data-stu-id="2a5ca-112">Windows 10 Enterprise E5 or A5</span></span>
- <span data-ttu-id="2a5ca-113">Enterprise Mobility + Security (EMS) E5 または A5</span><span class="sxs-lookup"><span data-stu-id="2a5ca-113">Enterprise Mobility + Security (EMS) E5 or A5</span></span> 
- <span data-ttu-id="2a5ca-114">Office 365 E5 または A5</span><span class="sxs-lookup"><span data-stu-id="2a5ca-114">Office 365 E5 or A5</span></span>
- <span data-ttu-id="2a5ca-115">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="2a5ca-115">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="2a5ca-116">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="2a5ca-116">Microsoft Defender for Identity</span></span> 
- <span data-ttu-id="2a5ca-117">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="2a5ca-117">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="2a5ca-118">Defender for Office 365 (プラン 2)</span><span class="sxs-lookup"><span data-stu-id="2a5ca-118">Defender for Office 365 (Plan 2)</span></span>

> [!NOTE]
> <span data-ttu-id="2a5ca-119">現在、Office 365 の試用版ライセンスは、Microsoft 365 Defender へのアクセスを提供しません。</span><span class="sxs-lookup"><span data-stu-id="2a5ca-119">Trial licenses for Office 365 currently do not provide access to Microsoft 365 Defender.</span></span>

<span data-ttu-id="2a5ca-120">詳細については [、Microsoft 365 Enterprise サービス プランを参照してください](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise)。</span><span class="sxs-lookup"><span data-stu-id="2a5ca-120">For more information, [view the Microsoft 365 Enterprise service plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span></span>

> <span data-ttu-id="2a5ca-121">まだライセンスを持っていない場合</span><span class="sxs-lookup"><span data-stu-id="2a5ca-121">Don't have license yet?</span></span> [<span data-ttu-id="2a5ca-122">Microsoft 365 サブスクリプションを試用する/購入する</span><span class="sxs-lookup"><span data-stu-id="2a5ca-122">Try or buy a Microsoft 365 subscription</span></span>](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a><span data-ttu-id="2a5ca-123">既存のライセンスを確認する</span><span class="sxs-lookup"><span data-stu-id="2a5ca-123">Check your existing  licenses</span></span>
<span data-ttu-id="2a5ca-124">既存のライセンスを表示するには、Microsoft 365 管理センター[(admin.microsoft.com](https://admin.microsoft.com/)) に移動します。</span><span class="sxs-lookup"><span data-stu-id="2a5ca-124">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="2a5ca-125">管理センターで、[**課金**]  >  [**ライセンス**] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="2a5ca-125">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="2a5ca-126">ライセンス情報を表示するには[、Azure](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) ADの課金管理者またはグローバル 閲覧者ロールが割り当てられている必要があります。 </span><span class="sxs-lookup"><span data-stu-id="2a5ca-126">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="2a5ca-127">アクセスの問題が発生した場合は、グローバル管理者に連絡してください。</span><span class="sxs-lookup"><span data-stu-id="2a5ca-127">If you encounter access problems, contact a global admin.</span></span>

## <a name="required-permissions"></a><span data-ttu-id="2a5ca-128">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="2a5ca-128">Required permissions</span></span>
<span data-ttu-id="2a5ca-129">Microsoft 365 Defenderを **有効** にする場合は、Azure Active Directory のグローバル管理者またはセキュリティ管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a5ca-129">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft 365 Defender.</span></span> <span data-ttu-id="2a5ca-130">Microsoft 365 Defender の使用に必要な役割の一覧と、データへのアクセスが規制される方法に関する情報については [、Microsoft 365 Defender](mtp-permissions.md)へのアクセスの管理に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2a5ca-130">For the list of roles required to use Microsoft 365 Defender and information on how access to data is regulated, read about [managing access to Microsoft 365 Defender](mtp-permissions.md).</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="2a5ca-131">ブラウザー要件</span><span class="sxs-lookup"><span data-stu-id="2a5ca-131">Browser requirements</span></span>
<span data-ttu-id="2a5ca-132">Microsoft Edge、Internet Explorer 11、または HTML 5 準拠の Web ブラウザーを使用して、Microsoft 365 セキュリティ センターで Microsoft 365 Defender にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="2a5ca-132">Access Microsoft 365 Defender in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a><span data-ttu-id="2a5ca-133">米国の GCC、GCC High、その他の米国政府機関の利用可能性</span><span class="sxs-lookup"><span data-stu-id="2a5ca-133">Availability to US GCC, GCC High, and other US government institutions</span></span>
<span data-ttu-id="2a5ca-134">現在、Microsoft 365 Defender は *次の機能を* 利用できません。</span><span class="sxs-lookup"><span data-stu-id="2a5ca-134">Currently, Microsoft 365 Defender is *not* available to:</span></span>
- <span data-ttu-id="2a5ca-135">米国政府機関コミュニティ クラウド (GCC)</span><span class="sxs-lookup"><span data-stu-id="2a5ca-135">US Government Community Cloud (GCC)</span></span>
- <span data-ttu-id="2a5ca-136">US Government Community Cloud High (GCC High)</span><span class="sxs-lookup"><span data-stu-id="2a5ca-136">US Government Community Cloud High (GCC High)</span></span>
- <span data-ttu-id="2a5ca-137">米国国防総省</span><span class="sxs-lookup"><span data-stu-id="2a5ca-137">US Department of Defense</span></span>
- <span data-ttu-id="2a5ca-138">商用ライセンスを持つすべての米国政府機関</span><span class="sxs-lookup"><span data-stu-id="2a5ca-138">All US government institutions with commercial licenses</span></span>

## <a name="related-topics"></a><span data-ttu-id="2a5ca-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="2a5ca-139">Related topics</span></span>
- [<span data-ttu-id="2a5ca-140">Microsoft 365 Defender の概要</span><span class="sxs-lookup"><span data-stu-id="2a5ca-140">Microsoft 365 Defender overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="2a5ca-141">Microsoft 365 Defender を有効にする</span><span class="sxs-lookup"><span data-stu-id="2a5ca-141">Turn on Microsoft 365 Defender</span></span>](mtp-enable.md)
- [<span data-ttu-id="2a5ca-142">アクセスとアクセス許可を管理する</span><span class="sxs-lookup"><span data-stu-id="2a5ca-142">Manage access and permissions</span></span>](mtp-permissions.md)
