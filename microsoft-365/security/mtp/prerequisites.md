---
title: Microsoft Threat Protection の前提条件
description: Microsoft Threat Protection のライセンス、ハードウェアとソフトウェアの要件、およびその他の構成設定について学習する
keywords: 要件、前提条件、ハードウェア、ソフトウェア、ブラウザー、MTP、M365、ライセンス
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
ms.openlocfilehash: 7498f7a15578979a24a1524e94f307067eeeb893
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42083606"
---
# <a name="microsoft-threat-protection-prerequisites"></a><span data-ttu-id="dbe3f-104">Microsoft Threat Protection の前提条件</span><span class="sxs-lookup"><span data-stu-id="dbe3f-104">Microsoft Threat Protection prerequisites</span></span>

<span data-ttu-id="dbe3f-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="dbe3f-105">**Applies to:**</span></span>
- <span data-ttu-id="dbe3f-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="dbe3f-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="dbe3f-107">Microsoft の脅威保護をプロビジョニングおよび使用するためのライセンス、ハードウェア要件、ソフトウェア要件、およびその他の構成設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="dbe3f-107">Learn about the licensing, hardware and software requirements, and other configuration settings to provision and use Microsoft Threat Protection.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="dbe3f-108">ライセンス要件</span><span class="sxs-lookup"><span data-stu-id="dbe3f-108">Licensing requirements</span></span>
<span data-ttu-id="dbe3f-109">Microsoft の脅威保護を使用するには、次のいずれかのライセンスまたはライセンスの組み合わせが必要です。</span><span class="sxs-lookup"><span data-stu-id="dbe3f-109">To use Microsoft Threat Protection, you need one of the following licenses or combination of licenses:</span></span>

- <span data-ttu-id="dbe3f-110">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="dbe3f-110">Microsoft 365 E5</span></span>
- <span data-ttu-id="dbe3f-111">Microsoft 365 E5 Security</span><span class="sxs-lookup"><span data-stu-id="dbe3f-111">Microsoft 365 E5 Security</span></span>
- <span data-ttu-id="dbe3f-112">Office 365 E5、Enterprise Mobility + Security E5、および Windows E5</span><span class="sxs-lookup"><span data-stu-id="dbe3f-112">Office 365 E5, Enterprise Mobility + Security E5, and Windows E5</span></span>

[<span data-ttu-id="dbe3f-113">Microsoft 365 Enterprise service プランを表示する</span><span class="sxs-lookup"><span data-stu-id="dbe3f-113">View Microsoft 365 Enterprise service plans</span></span>](https://www.microsoft.com/en-us/licensing/product-licensing/microsoft-365-enterprise)

### <a name="check-your-existing--licenses"></a><span data-ttu-id="dbe3f-114">既存のライセンスを確認する</span><span class="sxs-lookup"><span data-stu-id="dbe3f-114">Check your existing  licenses</span></span>
<span data-ttu-id="dbe3f-115">Microsoft 365 管理センター ([admin.microsoft.com](https://admin.microsoft.com/)) に移動して、既存のライセンスを表示します。</span><span class="sxs-lookup"><span data-stu-id="dbe3f-115">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="dbe3f-116">管理センターで、[**課金**]  >  [**ライセンス**] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="dbe3f-116">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="dbe3f-117">ライセンス情報を表示するには、 [AZURE AD の](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)**課金管理者**または**グローバル閲覧**者の役割のいずれかが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbe3f-117">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="dbe3f-118">アクセスの問題が発生した場合は、グローバル管理者に連絡してください。</span><span class="sxs-lookup"><span data-stu-id="dbe3f-118">If you encounter access problems, contact a global admin.</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="dbe3f-119">ブラウザー要件</span><span class="sxs-lookup"><span data-stu-id="dbe3f-119">Browser requirements</span></span>
<span data-ttu-id="dbe3f-120">Microsoft Edge、Internet Explorer 11、または任意の HTML 5 準拠の web ブラウザーを使用して、microsoft 365 セキュリティセンターの Microsoft 脅威保護にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="dbe3f-120">Access Microsoft Threat Protection in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="related-topics"></a><span data-ttu-id="dbe3f-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="dbe3f-121">Related topics</span></span>
- [<span data-ttu-id="dbe3f-122">Microsoft Threat Protection の概要</span><span class="sxs-lookup"><span data-stu-id="dbe3f-122">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="dbe3f-123">Microsoft Threat Protection を有効にする</span><span class="sxs-lookup"><span data-stu-id="dbe3f-123">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)
