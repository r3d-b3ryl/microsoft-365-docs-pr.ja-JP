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
ms.openlocfilehash: 66b3f7e446416b6252050e6f41a2b22d99d25767
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209237"
---
# <a name="microsoft-threat-protection-prerequisites"></a><span data-ttu-id="2af5c-104">Microsoft Threat Protection の前提条件</span><span class="sxs-lookup"><span data-stu-id="2af5c-104">Microsoft Threat Protection prerequisites</span></span>

<span data-ttu-id="2af5c-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="2af5c-105">**Applies to:**</span></span>
- <span data-ttu-id="2af5c-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="2af5c-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="2af5c-107">Microsoft の脅威保護をプロビジョニングおよび使用するためのライセンス、ハードウェア要件、ソフトウェア要件、およびその他の構成設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="2af5c-107">Learn about the licensing, hardware and software requirements, and other configuration settings to provision and use Microsoft Threat Protection.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="2af5c-108">ライセンス要件</span><span class="sxs-lookup"><span data-stu-id="2af5c-108">Licensing requirements</span></span>

>[!IMPORTANT]
><span data-ttu-id="2af5c-109">2020年5月12日から、Microsoft は、ライセンス要件に関して最適化された新しいエクスペリエンスを徐々にロールアウトし、 [microsoft の脅威保護を有効に](mtp-enable.md)します。</span><span class="sxs-lookup"><span data-stu-id="2af5c-109">Starting May 12, 2020, Microsoft will gradually roll out new, optimized experiences around licensing requirements and [turning on Microsoft Threat Protection](mtp-enable.md).</span></span> <span data-ttu-id="2af5c-110">この期間中、一部のお客様は、ポータルエクスペリエンスへの変更を確認し始めます。</span><span class="sxs-lookup"><span data-stu-id="2af5c-110">For several weeks during this period, some customers will start to see changes to their portal experiences.</span></span> <span data-ttu-id="2af5c-111">この記事では、新しいエクスペリエンスに関する情報を**新しいエクスペリエンス**としてマークしています。</span><span class="sxs-lookup"><span data-stu-id="2af5c-111">Information about the new experiences are marked **New experience** in this article.</span></span>

<span data-ttu-id="2af5c-112">Microsoft の脅威保護を使用するには、1つのライセンスまたはライセンスの組み合わせが必要です。</span><span class="sxs-lookup"><span data-stu-id="2af5c-112">To use Microsoft Threat Protection, you need either a single license or a combination of licenses.</span></span> <span data-ttu-id="2af5c-113">これらのライセンスまたはライセンスの組み合わせによって、追加のコストを必要とせずに Microsoft の脅威保護機能にアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="2af5c-113">These licenses or license combinations give you access to Microsoft Threat Protection features without additional cost.</span></span>

### <a name="single-license"></a><span data-ttu-id="2af5c-114">単一のライセンス</span><span class="sxs-lookup"><span data-stu-id="2af5c-114">Single license</span></span>
<span data-ttu-id="2af5c-115">次の*いずれか*のライセンスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="2af5c-115">You can use *one* of the following licenses:</span></span>

- <span data-ttu-id="2af5c-116">Microsoft 365 E5 または A5</span><span class="sxs-lookup"><span data-stu-id="2af5c-116">Microsoft 365 E5 or A5</span></span>
- <span data-ttu-id="2af5c-117">Microsoft 365 E5 セキュリティまたは A5 セキュリティ</span><span class="sxs-lookup"><span data-stu-id="2af5c-117">Microsoft 365 E5 Security or A5 Security</span></span>

### <a name="combination-of-licenses"></a><span data-ttu-id="2af5c-118">ライセンスの組み合わせ</span><span class="sxs-lookup"><span data-stu-id="2af5c-118">Combination of licenses</span></span>
<span data-ttu-id="2af5c-119">また、Office 365、 *Enterprise Mobility + Security (EMS)*、および Windows に対して、E5 または A5 サブスクリプションのライセンスを組み合わせて使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="2af5c-119">You can also use a combination of licenses for E5 or A5 subscriptions to Office 365, *Enterprise Mobility + Security (EMS)*, and Windows.</span></span> <span data-ttu-id="2af5c-120">ライセンスの組み合わせには、これらのライセンスの*すべて*が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2af5c-120">The license combination must include *all* of these licenses:</span></span>

- <span data-ttu-id="2af5c-121">Office 365 E5 または A5</span><span class="sxs-lookup"><span data-stu-id="2af5c-121">Office 365 E5 or A5</span></span>
- <span data-ttu-id="2af5c-122">*Enterprise Mobility + Security (EMS)* E5 または A5</span><span class="sxs-lookup"><span data-stu-id="2af5c-122">*Enterprise Mobility + Security (EMS)* E5 or A5</span></span>
- <span data-ttu-id="2af5c-123">Windows 10 Enterprise E5 または A5</span><span class="sxs-lookup"><span data-stu-id="2af5c-123">Windows 10 Enterprise E5 or A5</span></span>

<span data-ttu-id="2af5c-124">詳細については、 [Microsoft 365 Enterprise service プランを参照して](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise)ください。</span><span class="sxs-lookup"><span data-stu-id="2af5c-124">For more information, [view the Microsoft 365 Enterprise service plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span></span>

> <span data-ttu-id="2af5c-125">まだライセンスを持っていませんか?</span><span class="sxs-lookup"><span data-stu-id="2af5c-125">Don't have license yet?</span></span> [<span data-ttu-id="2af5c-126">Microsoft 365 サブスクリプションを試用または購入する</span><span class="sxs-lookup"><span data-stu-id="2af5c-126">Try or buy a Microsoft 365 subscription</span></span>](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)


<span data-ttu-id="2af5c-127">**新しい作業:** 2020年5月12日から、ユーザーはこの操作に対する変更を段階的に受け取ります。</span><span class="sxs-lookup"><span data-stu-id="2af5c-127">**New experience:** Starting May 12, 2020, customers will gradually receive changes to this experience.</span></span> <span data-ttu-id="2af5c-128">新機能を使用する場合は、次のいずれかのライセンスを持つ*すべて*のお客様が Microsoft の脅威保護を有効にするオプションを利用できます。</span><span class="sxs-lookup"><span data-stu-id="2af5c-128">For those with the new experience, the option to turn on Microsoft Threat Protection will be available to *all* customers with any of the following licenses:</span></span>

- <span data-ttu-id="2af5c-129">Microsoft 365 E5 または A5</span><span class="sxs-lookup"><span data-stu-id="2af5c-129">Microsoft 365 E5 or A5</span></span>
- <span data-ttu-id="2af5c-130">Microsoft 365 E5 セキュリティまたは A5 セキュリティ</span><span class="sxs-lookup"><span data-stu-id="2af5c-130">Microsoft 365 E5 Security or A5 Security</span></span>
- <span data-ttu-id="2af5c-131">Windows 10 Enterprise E5 または A5</span><span class="sxs-lookup"><span data-stu-id="2af5c-131">Windows 10 Enterprise E5 or A5</span></span>
- <span data-ttu-id="2af5c-132">Enterprise Mobility + Security (EMS) E5 または A5</span><span class="sxs-lookup"><span data-stu-id="2af5c-132">Enterprise Mobility + Security (EMS) E5 or A5</span></span> 
- <span data-ttu-id="2af5c-133">Office 365 E5 または A5</span><span class="sxs-lookup"><span data-stu-id="2af5c-133">Office 365 E5 or A5</span></span>
- <span data-ttu-id="2af5c-134">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="2af5c-134">Microsoft Defender Advanced Threat Protection</span></span> 
- <span data-ttu-id="2af5c-135">Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="2af5c-135">Azure Advanced Threat Protection</span></span> 
- <span data-ttu-id="2af5c-136">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="2af5c-136">Microsoft Cloud App Security</span></span> 
- <span data-ttu-id="2af5c-137">Office 365 Advanced Threat Protection (プラン 2)</span><span class="sxs-lookup"><span data-stu-id="2af5c-137">Office 365 Advanced Threat Protection (Plan 2)</span></span> 

### <a name="check-your-existing--licenses"></a><span data-ttu-id="2af5c-138">既存のライセンスを確認する</span><span class="sxs-lookup"><span data-stu-id="2af5c-138">Check your existing  licenses</span></span>
<span data-ttu-id="2af5c-139">Microsoft 365 管理センター ([admin.microsoft.com](https://admin.microsoft.com/)) に移動して、既存のライセンスを表示します。</span><span class="sxs-lookup"><span data-stu-id="2af5c-139">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="2af5c-140">管理センターで、[**課金**]  >  [**ライセンス**] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="2af5c-140">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="2af5c-141">ライセンス情報を表示するには、 [AZURE AD の](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)**課金管理者**または**グローバル閲覧**者の役割のいずれかが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2af5c-141">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="2af5c-142">アクセスの問題が発生した場合は、グローバル管理者に連絡してください。</span><span class="sxs-lookup"><span data-stu-id="2af5c-142">If you encounter access problems, contact a global admin.</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="2af5c-143">ブラウザー要件</span><span class="sxs-lookup"><span data-stu-id="2af5c-143">Browser requirements</span></span>
<span data-ttu-id="2af5c-144">Microsoft Edge、Internet Explorer 11、または任意の HTML 5 準拠の web ブラウザーを使用して、microsoft 365 セキュリティセンターの Microsoft 脅威保護にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="2af5c-144">Access Microsoft Threat Protection in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="us-gcc-and-gcc-high-availability"></a><span data-ttu-id="2af5c-145">US GCC および GCC 高可用性</span><span class="sxs-lookup"><span data-stu-id="2af5c-145">US GCC and GCC High availability</span></span>
<span data-ttu-id="2af5c-146">現時点では、Microsoft の脅威保護は米国政府機関向けの Community Cloud (GCC) および Government Community Cloud High (GCC High) のお客様にはご利用いただけません。</span><span class="sxs-lookup"><span data-stu-id="2af5c-146">Currently, Microsoft Threat Protection is not available to US Government Community Cloud (GCC) and Government Community Cloud High (GCC High) customers.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="2af5c-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="2af5c-147">Related topics</span></span>
- [<span data-ttu-id="2af5c-148">Microsoft Threat Protection の概要</span><span class="sxs-lookup"><span data-stu-id="2af5c-148">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="2af5c-149">Microsoft Threat Protection を有効にする</span><span class="sxs-lookup"><span data-stu-id="2af5c-149">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)
