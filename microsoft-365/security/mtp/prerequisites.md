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
ms.openlocfilehash: 3e18759387525ec600c24f74c96d6cddf206fc82
ms.sourcegitcommit: cc3b64a91e16ccdaa9c338b9a9056dbe3963ba9e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/10/2020
ms.locfileid: "42569047"
---
# <a name="microsoft-threat-protection-prerequisites"></a><span data-ttu-id="4fdd6-104">Microsoft Threat Protection の前提条件</span><span class="sxs-lookup"><span data-stu-id="4fdd6-104">Microsoft Threat Protection prerequisites</span></span>

<span data-ttu-id="4fdd6-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="4fdd6-105">**Applies to:**</span></span>
- <span data-ttu-id="4fdd6-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="4fdd6-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="4fdd6-107">Microsoft の脅威保護をプロビジョニングおよび使用するためのライセンス、ハードウェア要件、ソフトウェア要件、およびその他の構成設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="4fdd6-107">Learn about the licensing, hardware and software requirements, and other configuration settings to provision and use Microsoft Threat Protection.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="4fdd6-108">ライセンス要件</span><span class="sxs-lookup"><span data-stu-id="4fdd6-108">Licensing requirements</span></span>
<span data-ttu-id="4fdd6-109">Microsoft の脅威保護を使用するには、次の*いずれか*のライセンスまたはライセンスの組み合わせが必要です。</span><span class="sxs-lookup"><span data-stu-id="4fdd6-109">To use Microsoft Threat Protection, you need *one* of the following licenses or combination of licenses:</span></span>

- <span data-ttu-id="4fdd6-110">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="4fdd6-110">Microsoft 365 E5</span></span>
- <span data-ttu-id="4fdd6-111">Microsoft 365 E5 Security</span><span class="sxs-lookup"><span data-stu-id="4fdd6-111">Microsoft 365 E5 Security</span></span>
- <span data-ttu-id="4fdd6-112">Office 365 E5 および "Enterprise Mobility + Security E5 (EMS E5)" および Windows E5</span><span class="sxs-lookup"><span data-stu-id="4fdd6-112">Office 365 E5 and "Enterprise Mobility + Security E5 (EMS E5)" and Windows E5</span></span>
- <span data-ttu-id="4fdd6-113">Microsoft 365 A5</span><span class="sxs-lookup"><span data-stu-id="4fdd6-113">Microsoft 365 A5</span></span>

<span data-ttu-id="4fdd6-114">詳細については、 [Microsoft 365 Enterprise service プランを参照して](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise)ください。</span><span class="sxs-lookup"><span data-stu-id="4fdd6-114">For more information, [view the Microsoft 365 Enterprise service plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span></span>

> <span data-ttu-id="4fdd6-115">まだライセンスを持っていませんか?</span><span class="sxs-lookup"><span data-stu-id="4fdd6-115">Don't have license yet?</span></span> [<span data-ttu-id="4fdd6-116">Microsoft 365 サブスクリプションを試用または購入する</span><span class="sxs-lookup"><span data-stu-id="4fdd6-116">Try or buy a Microsoft 365 subscription</span></span>](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a><span data-ttu-id="4fdd6-117">既存のライセンスを確認する</span><span class="sxs-lookup"><span data-stu-id="4fdd6-117">Check your existing  licenses</span></span>
<span data-ttu-id="4fdd6-118">Microsoft 365 管理センター ([admin.microsoft.com](https://admin.microsoft.com/)) に移動して、既存のライセンスを表示します。</span><span class="sxs-lookup"><span data-stu-id="4fdd6-118">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="4fdd6-119">管理センターで、[**課金**]  >  [**ライセンス**] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="4fdd6-119">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="4fdd6-120">ライセンス情報を表示するには、 [AZURE AD の](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)**課金管理者**または**グローバル閲覧**者の役割のいずれかが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4fdd6-120">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="4fdd6-121">アクセスの問題が発生した場合は、グローバル管理者に連絡してください。</span><span class="sxs-lookup"><span data-stu-id="4fdd6-121">If you encounter access problems, contact a global admin.</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="4fdd6-122">ブラウザー要件</span><span class="sxs-lookup"><span data-stu-id="4fdd6-122">Browser requirements</span></span>
<span data-ttu-id="4fdd6-123">Microsoft Edge、Internet Explorer 11、または任意の HTML 5 準拠の web ブラウザーを使用して、microsoft 365 セキュリティセンターの Microsoft 脅威保護にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="4fdd6-123">Access Microsoft Threat Protection in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4fdd6-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="4fdd6-124">Related topics</span></span>
- [<span data-ttu-id="4fdd6-125">Microsoft Threat Protection の概要</span><span class="sxs-lookup"><span data-stu-id="4fdd6-125">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="4fdd6-126">Microsoft Threat Protection を有効にする</span><span class="sxs-lookup"><span data-stu-id="4fdd6-126">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)
