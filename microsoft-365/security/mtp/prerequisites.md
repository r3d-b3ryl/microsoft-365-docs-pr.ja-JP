---
title: Microsoft Threat Protection の前提条件
description: Microsoft Threat Protection のライセンス、ハードウェアとソフトウェアの要件、およびその他の構成設定について学習する
keywords: 要件、前提条件、ハードウェア、ソフトウェア、ブラウザー、MTP、M365、ライセンス
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
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
ms.openlocfilehash: 2175ca328678e271056ae75d1bcbb7dc70a2198d
ms.sourcegitcommit: 5b0a2e11c86c00e6e6b534f8b0a19962d1bb2805
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/27/2019
ms.locfileid: "40881968"
---
# <a name="microsoft-threat-protection-prerequisites"></a><span data-ttu-id="d746e-104">Microsoft Threat Protection の前提条件</span><span class="sxs-lookup"><span data-stu-id="d746e-104">Microsoft Threat Protection prerequisites</span></span>

<span data-ttu-id="d746e-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="d746e-105">**Applies to:**</span></span>
- <span data-ttu-id="d746e-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="d746e-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="d746e-107">Microsoft 365 セキュリティを実行および使用するライセンス、ハードウェアとソフトウェアの要件、およびその他の構成設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="d746e-107">Learn about the licensing, hardware and software requirements, and other configuration settings to run and use the Microsoft 365 security.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="d746e-108">ライセンス要件</span><span class="sxs-lookup"><span data-stu-id="d746e-108">Licensing requirements</span></span>
<span data-ttu-id="d746e-109">Microsoft 365 セキュリティには、次のいずれかのライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="d746e-109">Microsoft 365 security requires one of the following licenses:</span></span>

- <span data-ttu-id="d746e-110">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="d746e-110">Microsoft 365 E5</span></span> 
- <span data-ttu-id="d746e-111">Office 365 E5、Enterprise Mobility + Security E5、および Windows E5</span><span class="sxs-lookup"><span data-stu-id="d746e-111">Office 365 E5, Enterprise Mobility + Security E5, and Windows E5</span></span>

<span data-ttu-id="d746e-112">これらのライセンスは、[Microsoft 365 Enterprise ページ](https://www.microsoft.com/en-us/microsoft-365/enterprise)から取得できます。</span><span class="sxs-lookup"><span data-stu-id="d746e-112">You can acquire these licenses from the [Microsoft 365 enterprise page](https://www.microsoft.com/en-us/microsoft-365/enterprise).</span></span>

### <a name="check-your-existing--licenses"></a><span data-ttu-id="d746e-113">既存のライセンスを確認する</span><span class="sxs-lookup"><span data-stu-id="d746e-113">Check your existing  licenses</span></span>
<span data-ttu-id="d746e-114">[admin.microsoft.com](https://admin.microsoft.com/) の Microsoft 365 管理センターに移動し、既存のライセンスを表示します。</span><span class="sxs-lookup"><span data-stu-id="d746e-114">Go to Microsoft 365 admin center at [admin.microsoft.com](https://admin.microsoft.com/) to view your existing licenses.</span></span> <span data-ttu-id="d746e-115">管理センターで、[**課金**]  >  [**ライセンス**] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="d746e-115">In the admin center, go to **Billing** > **Licenses**.</span></span>

<span data-ttu-id="d746e-116">ライセンス情報を確認するには、[**課金管理者**] または [**グローバルな閲覧者**] の[役割を Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) で割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="d746e-116">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see licensing information.</span></span> <span data-ttu-id="d746e-117">アクセスの問題が発生した場合は、グローバル管理者に連絡してください。</span><span class="sxs-lookup"><span data-stu-id="d746e-117">If you encounter access problems, contact a global admin.</span></span>  

## <a name="browser-requirements"></a><span data-ttu-id="d746e-118">ブラウザー要件</span><span class="sxs-lookup"><span data-stu-id="d746e-118">Browser requirements</span></span>
<span data-ttu-id="d746e-119">Microsoft 365 セキュリティ センターへのアクセスはブラウザーで行います。</span><span class="sxs-lookup"><span data-stu-id="d746e-119">Access to Microsoft 365 security center is done through a browser.</span></span> <span data-ttu-id="d746e-120">Internet Explorer と Microsoft Edge がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="d746e-120">Internet Explorer and Microsoft Edge is supported.</span></span> <span data-ttu-id="d746e-121">HTML5 に準拠したブラウザーもサポートされています。</span><span class="sxs-lookup"><span data-stu-id="d746e-121">Any HTML5 compliant browsers are also supported.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d746e-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="d746e-122">Related topics</span></span>
- [<span data-ttu-id="d746e-123">Microsoft Threat Protection の概要</span><span class="sxs-lookup"><span data-stu-id="d746e-123">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="d746e-124">Microsoft Threat Protection を有効にする</span><span class="sxs-lookup"><span data-stu-id="d746e-124">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)