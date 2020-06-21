---
title: Microsoft Threat Protection の前提条件
description: Microsoft Threat Protection のライセンス、ハードウェアとソフトウェアの要件、およびその他の構成設定について学習する
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
ms.openlocfilehash: f63c59403e84e79d1a4a5cf2b8a5544f5646781c
ms.sourcegitcommit: 51e47ca4b355436a2ad3deb154060eb1927428e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/17/2020
ms.locfileid: "44773853"
---
# <a name="microsoft-threat-protection-prerequisites"></a><span data-ttu-id="d5a3c-104">Microsoft Threat Protection の前提条件</span><span class="sxs-lookup"><span data-stu-id="d5a3c-104">Microsoft Threat Protection prerequisites</span></span>

<span data-ttu-id="d5a3c-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="d5a3c-105">**Applies to:**</span></span>
- <span data-ttu-id="d5a3c-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="d5a3c-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="d5a3c-107">プロビジョニングおよび[Microsoft の脅威保護](microsoft-threat-protection.md)の使用に関するライセンスおよびその他の要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="d5a3c-107">Learn about licensing and other requirements for provisioning and using [Microsoft Threat Protection](microsoft-threat-protection.md).</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="d5a3c-108">ライセンスの要件</span><span class="sxs-lookup"><span data-stu-id="d5a3c-108">Licensing requirements</span></span>
<span data-ttu-id="d5a3c-109">これらのライセンスのいずれかを使用すると、追加のコストを必要とせずに Microsoft 365 セキュリティセンターの Microsoft の脅威保護機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="d5a3c-109">Any of these licenses gives you access to Microsoft Threat Protection features in Microsoft 365 security center without additional cost:</span></span>

- <span data-ttu-id="d5a3c-110">Microsoft 365 E5 または A5</span><span class="sxs-lookup"><span data-stu-id="d5a3c-110">Microsoft 365 E5 or A5</span></span>
- <span data-ttu-id="d5a3c-111">Microsoft 365 E5 セキュリティまたは A5 セキュリティ</span><span class="sxs-lookup"><span data-stu-id="d5a3c-111">Microsoft 365 E5 Security or A5 Security</span></span>
- <span data-ttu-id="d5a3c-112">Windows 10 Enterprise E5 または A5</span><span class="sxs-lookup"><span data-stu-id="d5a3c-112">Windows 10 Enterprise E5 or A5</span></span>
- <span data-ttu-id="d5a3c-113">Enterprise Mobility + Security (EMS) E5 または A5</span><span class="sxs-lookup"><span data-stu-id="d5a3c-113">Enterprise Mobility + Security (EMS) E5 or A5</span></span> 
- <span data-ttu-id="d5a3c-114">Office 365 E5 または A5</span><span class="sxs-lookup"><span data-stu-id="d5a3c-114">Office 365 E5 or A5</span></span>
- <span data-ttu-id="d5a3c-115">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="d5a3c-115">Microsoft Defender Advanced Threat Protection</span></span>
- <span data-ttu-id="d5a3c-116">Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="d5a3c-116">Azure Advanced Threat Protection</span></span> 
- <span data-ttu-id="d5a3c-117">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="d5a3c-117">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="d5a3c-118">Office 365 Advanced Threat Protection (プラン 2)</span><span class="sxs-lookup"><span data-stu-id="d5a3c-118">Office 365 Advanced Threat Protection (Plan 2)</span></span>

> [!NOTE]
> <span data-ttu-id="d5a3c-119">Office 365 の試用版ライセンスは現在、Microsoft の脅威保護へのアクセスを提供していません。</span><span class="sxs-lookup"><span data-stu-id="d5a3c-119">Trial licenses for Office 365 currently do not provide access to Microsoft Threat Protection.</span></span>

<span data-ttu-id="d5a3c-120">詳細については、 [Microsoft 365 Enterprise service プランを参照して](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise)ください。</span><span class="sxs-lookup"><span data-stu-id="d5a3c-120">For more information, [view the Microsoft 365 Enterprise service plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span></span>

> <span data-ttu-id="d5a3c-121">まだライセンスを持っていませんか?</span><span class="sxs-lookup"><span data-stu-id="d5a3c-121">Don't have license yet?</span></span> [<span data-ttu-id="d5a3c-122">Microsoft 365 サブスクリプションを試用する/購入する</span><span class="sxs-lookup"><span data-stu-id="d5a3c-122">Try or buy a Microsoft 365 subscription</span></span>](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a><span data-ttu-id="d5a3c-123">既存のライセンスを確認する</span><span class="sxs-lookup"><span data-stu-id="d5a3c-123">Check your existing  licenses</span></span>
<span data-ttu-id="d5a3c-124">Microsoft 365 管理センター ([admin.microsoft.com](https://admin.microsoft.com/)) に移動して、既存のライセンスを表示します。</span><span class="sxs-lookup"><span data-stu-id="d5a3c-124">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="d5a3c-125">管理センターで、[**課金**]  >  [**ライセンス**] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="d5a3c-125">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="d5a3c-126">ライセンス情報を表示するには、 [AZURE AD の](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)**課金管理者**または**グローバル閲覧**者の役割のいずれかが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5a3c-126">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="d5a3c-127">アクセスの問題が発生した場合は、グローバル管理者に連絡してください。</span><span class="sxs-lookup"><span data-stu-id="d5a3c-127">If you encounter access problems, contact a global admin.</span></span>

## <a name="required-permissions"></a><span data-ttu-id="d5a3c-128">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="d5a3c-128">Required permissions</span></span>
<span data-ttu-id="d5a3c-129">必要な役割の一覧と、データへのアクセスを規制する方法については、「 [Microsoft の脅威保護へのアクセスの管理](mtp-permissions.md)について」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5a3c-129">For the list of required roles and how access to data is regulated, read about [managing access to Microsoft Threat Protection](mtp-permissions.md).</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="d5a3c-130">ブラウザー要件</span><span class="sxs-lookup"><span data-stu-id="d5a3c-130">Browser requirements</span></span>
<span data-ttu-id="d5a3c-131">Microsoft Edge、Internet Explorer 11、または任意の HTML 5 準拠の web ブラウザーを使用して、microsoft 365 セキュリティセンターの Microsoft 脅威保護にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="d5a3c-131">Access Microsoft Threat Protection in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a><span data-ttu-id="d5a3c-132">米国 GCC、GCC 高、その他の米国政府機関向けの可用性</span><span class="sxs-lookup"><span data-stu-id="d5a3c-132">Availability to US GCC, GCC High, and other US government institutions</span></span>
<span data-ttu-id="d5a3c-133">現時点では、Microsoft の脅威保護は次の場合には使用でき*ません*。</span><span class="sxs-lookup"><span data-stu-id="d5a3c-133">Currently, Microsoft Threat Protection is *not* available to:</span></span>
- <span data-ttu-id="d5a3c-134">米国政府機関向けコミュニティクラウド (GCC)</span><span class="sxs-lookup"><span data-stu-id="d5a3c-134">US Government Community Cloud (GCC)</span></span>
- <span data-ttu-id="d5a3c-135">米国政府機関向けコミュニティクラウド高 (GCC 高)</span><span class="sxs-lookup"><span data-stu-id="d5a3c-135">US Government Community Cloud High (GCC High)</span></span>
- <span data-ttu-id="d5a3c-136">米国国防総省</span><span class="sxs-lookup"><span data-stu-id="d5a3c-136">US Department of Defense</span></span>
- <span data-ttu-id="d5a3c-137">市販のライセンスを持つ米国の全行政機関</span><span class="sxs-lookup"><span data-stu-id="d5a3c-137">All US government institutions with commercial licenses</span></span>

## <a name="related-topics"></a><span data-ttu-id="d5a3c-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="d5a3c-138">Related topics</span></span>
- [<span data-ttu-id="d5a3c-139">Microsoft Threat Protection の概要</span><span class="sxs-lookup"><span data-stu-id="d5a3c-139">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="d5a3c-140">Microsoft Threat Protection を有効にする</span><span class="sxs-lookup"><span data-stu-id="d5a3c-140">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)
- [<span data-ttu-id="d5a3c-141">アクセスとアクセス許可を管理する</span><span class="sxs-lookup"><span data-stu-id="d5a3c-141">Manage access and permissions</span></span>](mtp-permissions.md)
