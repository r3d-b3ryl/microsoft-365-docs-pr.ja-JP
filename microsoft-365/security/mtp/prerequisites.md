---
title: Microsoft 365 Defender の前提条件
description: Microsoft 365 Defender のライセンス、ハードウェアおよびソフトウェアの要件、およびその他の構成設定について説明します。
keywords: 要件、前提条件、ハードウェア、ソフトウェア、ブラウザー、MTP、M365、license、E5、A5、EMS、購入
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
ms.openlocfilehash: 415cdb79a6aa9371ee2f07de579cfb2f873f1acb
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844778"
---
# <a name="microsoft-365-defender-prerequisites"></a><span data-ttu-id="5cc2e-104">Microsoft 365 Defender の前提条件</span><span class="sxs-lookup"><span data-stu-id="5cc2e-104">Microsoft 365 Defender prerequisites</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="5cc2e-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="5cc2e-105">**Applies to:**</span></span>
- <span data-ttu-id="5cc2e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5cc2e-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="5cc2e-107">[Microsoft 365 Defender](microsoft-threat-protection.md)をプロビジョニングおよび使用するためのライセンスおよびその他の要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="5cc2e-107">Learn about licensing and other requirements for provisioning and using [Microsoft 365 Defender](microsoft-threat-protection.md).</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="5cc2e-108">ライセンスの要件</span><span class="sxs-lookup"><span data-stu-id="5cc2e-108">Licensing requirements</span></span>
<span data-ttu-id="5cc2e-109">これらのライセンスのいずれかを使用すると、追加のコストを必要とせずに microsoft 365 セキュリティセンターの Microsoft 365 Defender の機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="5cc2e-109">Any of these licenses gives you access to Microsoft 365 Defender features in Microsoft 365 security center without additional cost:</span></span>

- <span data-ttu-id="5cc2e-110">Microsoft 365 E5 または A5</span><span class="sxs-lookup"><span data-stu-id="5cc2e-110">Microsoft 365 E5 or A5</span></span>
- <span data-ttu-id="5cc2e-111">Microsoft 365 E5 セキュリティまたは A5 セキュリティ</span><span class="sxs-lookup"><span data-stu-id="5cc2e-111">Microsoft 365 E5 Security or A5 Security</span></span>
- <span data-ttu-id="5cc2e-112">Windows 10 Enterprise E5 または A5</span><span class="sxs-lookup"><span data-stu-id="5cc2e-112">Windows 10 Enterprise E5 or A5</span></span>
- <span data-ttu-id="5cc2e-113">Enterprise Mobility + Security (EMS) E5 または A5</span><span class="sxs-lookup"><span data-stu-id="5cc2e-113">Enterprise Mobility + Security (EMS) E5 or A5</span></span> 
- <span data-ttu-id="5cc2e-114">Office 365 E5 または A5</span><span class="sxs-lookup"><span data-stu-id="5cc2e-114">Office 365 E5 or A5</span></span>
- <span data-ttu-id="5cc2e-115">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="5cc2e-115">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="5cc2e-116">Id の Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="5cc2e-116">Microsoft Defender for Identity</span></span> 
- <span data-ttu-id="5cc2e-117">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="5cc2e-117">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="5cc2e-118">Office 365 の Defender (プラン 2)</span><span class="sxs-lookup"><span data-stu-id="5cc2e-118">Defender for Office 365 (Plan 2)</span></span>

> [!NOTE]
> <span data-ttu-id="5cc2e-119">Office 365 の試用版ライセンスは現在、Microsoft 365 Defender へのアクセスを提供していません。</span><span class="sxs-lookup"><span data-stu-id="5cc2e-119">Trial licenses for Office 365 currently do not provide access to Microsoft 365 Defender.</span></span>

<span data-ttu-id="5cc2e-120">詳細については、 [Microsoft 365 Enterprise service プランを参照して](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise)ください。</span><span class="sxs-lookup"><span data-stu-id="5cc2e-120">For more information, [view the Microsoft 365 Enterprise service plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span></span>

> <span data-ttu-id="5cc2e-121">まだライセンスを持っていませんか?</span><span class="sxs-lookup"><span data-stu-id="5cc2e-121">Don't have license yet?</span></span> [<span data-ttu-id="5cc2e-122">Microsoft 365 サブスクリプションを試用する/購入する</span><span class="sxs-lookup"><span data-stu-id="5cc2e-122">Try or buy a Microsoft 365 subscription</span></span>](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a><span data-ttu-id="5cc2e-123">既存のライセンスを確認する</span><span class="sxs-lookup"><span data-stu-id="5cc2e-123">Check your existing  licenses</span></span>
<span data-ttu-id="5cc2e-124">Microsoft 365 管理センター ([admin.microsoft.com](https://admin.microsoft.com/)) に移動して、既存のライセンスを表示します。</span><span class="sxs-lookup"><span data-stu-id="5cc2e-124">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="5cc2e-125">管理センターで、[ **課金** ]  >  [ **ライセンス** ] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="5cc2e-125">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="5cc2e-126">ライセンス情報を表示するには、 [AZURE AD の](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)**課金管理者** または **グローバル閲覧** 者の役割のいずれかが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5cc2e-126">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="5cc2e-127">アクセスの問題が発生した場合は、グローバル管理者に連絡してください。</span><span class="sxs-lookup"><span data-stu-id="5cc2e-127">If you encounter access problems, contact a global admin.</span></span>

## <a name="required-permissions"></a><span data-ttu-id="5cc2e-128">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="5cc2e-128">Required permissions</span></span>
<span data-ttu-id="5cc2e-129">Microsoft 365 Defender を有効にするには、Azure Active Directory の **グローバル管理者** または **セキュリティ管理者** である必要があります。</span><span class="sxs-lookup"><span data-stu-id="5cc2e-129">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft 365 Defender.</span></span> <span data-ttu-id="5cc2e-130">Microsoft 365 Defender を使用するために必要な役割の一覧と、データへのアクセスを規制する方法については、「 [microsoft 365 Defender へのアクセスの管理](mtp-permissions.md)について」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5cc2e-130">For the list of roles required to use Microsoft 365 Defender and information on how access to data is regulated, read about [managing access to Microsoft 365 Defender](mtp-permissions.md).</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="5cc2e-131">ブラウザー要件</span><span class="sxs-lookup"><span data-stu-id="5cc2e-131">Browser requirements</span></span>
<span data-ttu-id="5cc2e-132">Microsoft Edge、Internet Explorer 11、または任意の HTML 5 準拠の web ブラウザーを使用して、microsoft 365 セキュリティセンターの Microsoft 365 Defender にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="5cc2e-132">Access Microsoft 365 Defender in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a><span data-ttu-id="5cc2e-133">米国 GCC、GCC 高、その他の米国政府機関向けの可用性</span><span class="sxs-lookup"><span data-stu-id="5cc2e-133">Availability to US GCC, GCC High, and other US government institutions</span></span>
<span data-ttu-id="5cc2e-134">現時点では、Microsoft 365 Defender を使用することはでき *ません* 。</span><span class="sxs-lookup"><span data-stu-id="5cc2e-134">Currently, Microsoft 365 Defender is *not* available to:</span></span>
- <span data-ttu-id="5cc2e-135">米国政府機関向けコミュニティクラウド (GCC)</span><span class="sxs-lookup"><span data-stu-id="5cc2e-135">US Government Community Cloud (GCC)</span></span>
- <span data-ttu-id="5cc2e-136">米国政府機関向けコミュニティクラウド高 (GCC 高)</span><span class="sxs-lookup"><span data-stu-id="5cc2e-136">US Government Community Cloud High (GCC High)</span></span>
- <span data-ttu-id="5cc2e-137">米国国防総省</span><span class="sxs-lookup"><span data-stu-id="5cc2e-137">US Department of Defense</span></span>
- <span data-ttu-id="5cc2e-138">市販のライセンスを持つ米国の全行政機関</span><span class="sxs-lookup"><span data-stu-id="5cc2e-138">All US government institutions with commercial licenses</span></span>

## <a name="related-topics"></a><span data-ttu-id="5cc2e-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="5cc2e-139">Related topics</span></span>
- [<span data-ttu-id="5cc2e-140">Microsoft 365 Defender の概要</span><span class="sxs-lookup"><span data-stu-id="5cc2e-140">Microsoft 365 Defender overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="5cc2e-141">Microsoft 365 Defender をオンにする</span><span class="sxs-lookup"><span data-stu-id="5cc2e-141">Turn on Microsoft 365 Defender</span></span>](mtp-enable.md)
- [<span data-ttu-id="5cc2e-142">アクセスとアクセス許可を管理する</span><span class="sxs-lookup"><span data-stu-id="5cc2e-142">Manage access and permissions</span></span>](mtp-permissions.md)
