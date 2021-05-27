---
title: Microsoft 365Defender の前提条件
description: Defender のライセンス、ハードウェアとソフトウェアの要件、その他の構成設定Microsoft 365する
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
ms.openlocfilehash: f3fd597181d73c1768057ea7740ab111e5af2068
ms.sourcegitcommit: 82a4d74020cd93ba444006317cfecc178c6d41dc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689159"
---
# <a name="microsoft-365-defender-prerequisites"></a><span data-ttu-id="a0596-104">Microsoft 365Defender の前提条件</span><span class="sxs-lookup"><span data-stu-id="a0596-104">Microsoft 365 Defender prerequisites</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="a0596-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="a0596-105">**Applies to:**</span></span>
- <span data-ttu-id="a0596-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a0596-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="a0596-107">Defender のプロビジョニングと使用に関するライセンスその他の[要件Microsoft 365します](microsoft-365-defender.md)。</span><span class="sxs-lookup"><span data-stu-id="a0596-107">Learn about licensing and other requirements for provisioning and using [Microsoft 365 Defender](microsoft-365-defender.md).</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="a0596-108">ライセンスの要件</span><span class="sxs-lookup"><span data-stu-id="a0596-108">Licensing requirements</span></span>
<span data-ttu-id="a0596-109">これらのライセンスを使用すると、セキュリティ センター Microsoft 365 Defender 機能Microsoft 365追加コストなしでアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="a0596-109">Any of these licenses gives you access to Microsoft 365 Defender features in Microsoft 365 security center without additional cost:</span></span>

- <span data-ttu-id="a0596-110">Microsoft 365 E5 または A5</span><span class="sxs-lookup"><span data-stu-id="a0596-110">Microsoft 365 E5 or A5</span></span>
- <span data-ttu-id="a0596-111">Microsoft 365 E3アドオンMicrosoft 365 E5 Securityを使用する</span><span class="sxs-lookup"><span data-stu-id="a0596-111">Microsoft 365 E3 with the Microsoft 365 E5 Security add-on</span></span>
- <span data-ttu-id="a0596-112">Microsoft 365A5 セキュリティ アドオンMicrosoft 365 A3</span><span class="sxs-lookup"><span data-stu-id="a0596-112">Microsoft 365 A3 with the Microsoft 365 A5 Security add-on</span></span>
- <span data-ttu-id="a0596-113">Windows 10 Enterprise E5 または A5</span><span class="sxs-lookup"><span data-stu-id="a0596-113">Windows 10 Enterprise E5 or A5</span></span>
- <span data-ttu-id="a0596-114">Enterprise Mobility + Security (EMS) E5 または A5</span><span class="sxs-lookup"><span data-stu-id="a0596-114">Enterprise Mobility + Security (EMS) E5 or A5</span></span> 
- <span data-ttu-id="a0596-115">Office 365 E5 または A5</span><span class="sxs-lookup"><span data-stu-id="a0596-115">Office 365 E5 or A5</span></span>
- <span data-ttu-id="a0596-116">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="a0596-116">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="a0596-117">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="a0596-117">Microsoft Defender for Identity</span></span> 
- <span data-ttu-id="a0596-118">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="a0596-118">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="a0596-119">Defender for Office 365 (プラン 2)</span><span class="sxs-lookup"><span data-stu-id="a0596-119">Defender for Office 365 (Plan 2)</span></span>

<span data-ttu-id="a0596-120">詳細については、サービス[プランのMicrosoft 365 Enterpriseしてください](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise)。</span><span class="sxs-lookup"><span data-stu-id="a0596-120">For more information, [view the Microsoft 365 Enterprise service plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span></span>

> <span data-ttu-id="a0596-121">まだライセンスがありませんか?</span><span class="sxs-lookup"><span data-stu-id="a0596-121">Don't have license yet?</span></span> [<span data-ttu-id="a0596-122">Microsoft 365 サブスクリプションを試用する/購入する</span><span class="sxs-lookup"><span data-stu-id="a0596-122">Try or buy a Microsoft 365 subscription</span></span>](../../commerce/try-or-buy-microsoft-365.md)

### <a name="check-your-existing--licenses"></a><span data-ttu-id="a0596-123">既存のライセンスを確認する</span><span class="sxs-lookup"><span data-stu-id="a0596-123">Check your existing  licenses</span></span>
<span data-ttu-id="a0596-124">既存のMicrosoft 365を表示するには、admin.microsoft.com[管理センター](https://admin.microsoft.com/)( admin.microsoft.com ) に移動します。</span><span class="sxs-lookup"><span data-stu-id="a0596-124">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="a0596-125">管理センターで、[**課金**]  >  [**ライセンス**] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="a0596-125">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="a0596-126">ライセンス情報を表示するには[、Azure](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)サーバーで課金管理者またはグローバル リーダー AD割り当てる必要があります。 </span><span class="sxs-lookup"><span data-stu-id="a0596-126">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="a0596-127">アクセスの問題が発生した場合は、グローバル管理者に連絡してください。</span><span class="sxs-lookup"><span data-stu-id="a0596-127">If you encounter access problems, contact a global admin.</span></span>

## <a name="required-permissions"></a><span data-ttu-id="a0596-128">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="a0596-128">Required permissions</span></span>
<span data-ttu-id="a0596-129">Defender を有効に **するには、** グローバル管理者またはセキュリティAzure Active Directory管理者Microsoft 365があります。</span><span class="sxs-lookup"><span data-stu-id="a0596-129">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft 365 Defender.</span></span> <span data-ttu-id="a0596-130">Microsoft 365 Defender を使用するために必要な役割の一覧と、データへのアクセスが規制される方法に関する情報については、「Defender へのアクセスの管理」[をMicrosoft 365してください](m365d-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="a0596-130">For the list of roles required to use Microsoft 365 Defender and information on how access to data is regulated, read about [managing access to Microsoft 365 Defender](m365d-permissions.md).</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="a0596-131">ブラウザー要件</span><span class="sxs-lookup"><span data-stu-id="a0596-131">Browser requirements</span></span>
<span data-ttu-id="a0596-132">Microsoft 365、Microsoft 365 11、または HTML 5 準拠の web ブラウザーを使用Microsoft Edgeセキュリティ センター Internet Explorer Defender にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="a0596-132">Access Microsoft 365 Defender in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a><span data-ttu-id="a0596-133">米国の政府機関GCC、GCC、その他の米国政府機関への可用性</span><span class="sxs-lookup"><span data-stu-id="a0596-133">Availability to US GCC, GCC High, and other US government institutions</span></span>
<span data-ttu-id="a0596-134">現時点では、Microsoft 365 Defender *を使用* できません。</span><span class="sxs-lookup"><span data-stu-id="a0596-134">Currently, Microsoft 365 Defender is *not* available to:</span></span>
- <span data-ttu-id="a0596-135">US Government Community Cloud (GCC)</span><span class="sxs-lookup"><span data-stu-id="a0596-135">US Government Community Cloud (GCC)</span></span>
- <span data-ttu-id="a0596-136">米国 Government Community Cloud高 (GCC高)</span><span class="sxs-lookup"><span data-stu-id="a0596-136">US Government Community Cloud High (GCC High)</span></span>
- <span data-ttu-id="a0596-137">米国国防総省</span><span class="sxs-lookup"><span data-stu-id="a0596-137">US Department of Defense</span></span>
- <span data-ttu-id="a0596-138">商用ライセンスを持つすべての米国政府機関</span><span class="sxs-lookup"><span data-stu-id="a0596-138">All US government institutions with commercial licenses</span></span>


<span data-ttu-id="a0596-139">現時点では、Microsoft Defender for Office 365統合された Defender 機能Microsoft 365統合は、データセンターの次の場所Office 365使用できません。</span><span class="sxs-lookup"><span data-stu-id="a0596-139">Currently, the Microsoft Defender for Office 365 integration into the unified Microsoft 365 Defender features are not available to customers in the following Office 365 datacenter locations:</span></span>

- <span data-ttu-id="a0596-140">ブラジル</span><span class="sxs-lookup"><span data-stu-id="a0596-140">Brazil</span></span> 
- <span data-ttu-id="a0596-141">ドイツ</span><span class="sxs-lookup"><span data-stu-id="a0596-141">Germany</span></span> 
- <span data-ttu-id="a0596-142">ノルウェー</span><span class="sxs-lookup"><span data-stu-id="a0596-142">Norway</span></span> 
- <span data-ttu-id="a0596-143">シンガポール</span><span class="sxs-lookup"><span data-stu-id="a0596-143">Singapore</span></span> 
- <span data-ttu-id="a0596-144">南アフリカ</span><span class="sxs-lookup"><span data-stu-id="a0596-144">South Africa</span></span>
- <span data-ttu-id="a0596-145">スイス</span><span class="sxs-lookup"><span data-stu-id="a0596-145">Switzerland</span></span> 
- <span data-ttu-id="a0596-146">アラブ首長国連邦</span><span class="sxs-lookup"><span data-stu-id="a0596-146">United Arab Emirates</span></span> 


## <a name="related-topics"></a><span data-ttu-id="a0596-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="a0596-147">Related topics</span></span>
- [<span data-ttu-id="a0596-148">Microsoft 365Defender の概要</span><span class="sxs-lookup"><span data-stu-id="a0596-148">Microsoft 365 Defender overview</span></span>](microsoft-365-defender.md)
- [<span data-ttu-id="a0596-149">Microsoft 365 Defender を有効にする</span><span class="sxs-lookup"><span data-stu-id="a0596-149">Turn on Microsoft 365 Defender</span></span>](m365d-enable.md)
- [<span data-ttu-id="a0596-150">アクセスとアクセス許可の管理</span><span class="sxs-lookup"><span data-stu-id="a0596-150">Manage access and permissions</span></span>](m365d-permissions.md)
