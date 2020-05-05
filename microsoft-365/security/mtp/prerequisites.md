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
ms.openlocfilehash: 12e68cd8fcd7c784b1d0b4c70c5c25370cbbb409
ms.sourcegitcommit: 997f6227f33c3683ade9672e881d09216df22ee9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2020
ms.locfileid: "44016004"
---
# <a name="microsoft-threat-protection-prerequisites"></a><span data-ttu-id="cc913-104">Microsoft Threat Protection の前提条件</span><span class="sxs-lookup"><span data-stu-id="cc913-104">Microsoft Threat Protection prerequisites</span></span>

<span data-ttu-id="cc913-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="cc913-105">**Applies to:**</span></span>
- <span data-ttu-id="cc913-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="cc913-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="cc913-107">Microsoft の脅威保護をプロビジョニングおよび使用するためのライセンス、ハードウェア要件、ソフトウェア要件、およびその他の構成設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="cc913-107">Learn about the licensing, hardware and software requirements, and other configuration settings to provision and use Microsoft Threat Protection.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="cc913-108">ライセンス要件</span><span class="sxs-lookup"><span data-stu-id="cc913-108">Licensing requirements</span></span>

<span data-ttu-id="cc913-109">Microsoft の脅威保護を使用するには、1つのライセンスまたはライセンスの組み合わせが必要です。</span><span class="sxs-lookup"><span data-stu-id="cc913-109">To use Microsoft Threat Protection, you need either a single license or a combination of licenses.</span></span> <span data-ttu-id="cc913-110">これらのライセンスまたはライセンスの組み合わせによって、追加のコストを必要とせずに Microsoft の脅威保護機能にアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="cc913-110">These licenses or license combinations give you access to Microsoft Threat Protection features without additional cost.</span></span>

### <a name="single-license"></a><span data-ttu-id="cc913-111">単一のライセンス</span><span class="sxs-lookup"><span data-stu-id="cc913-111">Single license</span></span>
<span data-ttu-id="cc913-112">次の*いずれか*のライセンスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="cc913-112">You can use *one* of the following licenses:</span></span>

- <span data-ttu-id="cc913-113">Microsoft 365 E5 または A5</span><span class="sxs-lookup"><span data-stu-id="cc913-113">Microsoft 365 E5 or A5</span></span>
- <span data-ttu-id="cc913-114">Microsoft 365 E5 セキュリティまたは A5 セキュリティ</span><span class="sxs-lookup"><span data-stu-id="cc913-114">Microsoft 365 E5 Security or A5 Security</span></span>

### <a name="combination-of-licenses"></a><span data-ttu-id="cc913-115">ライセンスの組み合わせ</span><span class="sxs-lookup"><span data-stu-id="cc913-115">Combination of licenses</span></span>
<span data-ttu-id="cc913-116">また、Office 365、 *Enterprise Mobility + Security (EMS)*、および Windows に対して、E5 または A5 サブスクリプションのライセンスを組み合わせて使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="cc913-116">You can also use a combination of licenses for E5 or A5 subscriptions to Office 365, *Enterprise Mobility + Security (EMS)*, and Windows.</span></span> <span data-ttu-id="cc913-117">ライセンスの組み合わせには、これらのライセンスの*すべて*が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="cc913-117">The license combination must include *all* of these licenses:</span></span>

- <span data-ttu-id="cc913-118">Office 365 E5 または A5</span><span class="sxs-lookup"><span data-stu-id="cc913-118">Office 365 E5 or A5</span></span>
- <span data-ttu-id="cc913-119">*Enterprise Mobility + Security (EMS)* E5 または A5</span><span class="sxs-lookup"><span data-stu-id="cc913-119">*Enterprise Mobility + Security (EMS)* E5 or A5</span></span>
- <span data-ttu-id="cc913-120">Windows 10 Enterprise E5 または A5</span><span class="sxs-lookup"><span data-stu-id="cc913-120">Windows 10 Enterprise E5 or A5</span></span>

<span data-ttu-id="cc913-121">詳細については、 [Microsoft 365 Enterprise service プランを参照して](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise)ください。</span><span class="sxs-lookup"><span data-stu-id="cc913-121">For more information, [view the Microsoft 365 Enterprise service plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span></span>

> <span data-ttu-id="cc913-122">まだライセンスを持っていませんか?</span><span class="sxs-lookup"><span data-stu-id="cc913-122">Don't have license yet?</span></span> [<span data-ttu-id="cc913-123">Microsoft 365 サブスクリプションを試用または購入する</span><span class="sxs-lookup"><span data-stu-id="cc913-123">Try or buy a Microsoft 365 subscription</span></span>](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a><span data-ttu-id="cc913-124">既存のライセンスを確認する</span><span class="sxs-lookup"><span data-stu-id="cc913-124">Check your existing  licenses</span></span>
<span data-ttu-id="cc913-125">Microsoft 365 管理センター ([admin.microsoft.com](https://admin.microsoft.com/)) に移動して、既存のライセンスを表示します。</span><span class="sxs-lookup"><span data-stu-id="cc913-125">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="cc913-126">管理センターで、[**課金**]  >  [**ライセンス**] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="cc913-126">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="cc913-127">ライセンス情報を表示するには、 [AZURE AD の](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)**課金管理者**または**グローバル閲覧**者の役割のいずれかが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="cc913-127">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="cc913-128">アクセスの問題が発生した場合は、グローバル管理者に連絡してください。</span><span class="sxs-lookup"><span data-stu-id="cc913-128">If you encounter access problems, contact a global admin.</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="cc913-129">ブラウザー要件</span><span class="sxs-lookup"><span data-stu-id="cc913-129">Browser requirements</span></span>
<span data-ttu-id="cc913-130">Microsoft Edge、Internet Explorer 11、または任意の HTML 5 準拠の web ブラウザーを使用して、microsoft 365 セキュリティセンターの Microsoft 脅威保護にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="cc913-130">Access Microsoft Threat Protection in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="microsoft-threat-protection-for-us-government-community-cloud-and-us-government-community-cloud-high-gcc-high-customers"></a><span data-ttu-id="cc913-131">米国政府機関向けの Microsoft の脅威保護コミュニティクラウドおよび米国政府機関向けコミュニティクラウド高 (GCC 高) お客様</span><span class="sxs-lookup"><span data-stu-id="cc913-131">Microsoft Threat Protection for US Government Community Cloud and US Government Community Cloud High (GCC High) customers</span></span>
<span data-ttu-id="cc913-132">現時点では、マイクロソフトの脅威保護は、アメリカ GCC および GCC 高のお客様は利用できません。</span><span class="sxs-lookup"><span data-stu-id="cc913-132">Currently, Microsoft Threat Protection is not available to US GCC and GCC High customers.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="cc913-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="cc913-133">Related topics</span></span>
- [<span data-ttu-id="cc913-134">Microsoft Threat Protection の概要</span><span class="sxs-lookup"><span data-stu-id="cc913-134">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="cc913-135">Microsoft Threat Protection を有効にする</span><span class="sxs-lookup"><span data-stu-id="cc913-135">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)
