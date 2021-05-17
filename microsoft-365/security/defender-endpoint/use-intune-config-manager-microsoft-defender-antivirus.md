---
title: Configuration Manager Microsoft Defender ウイルス対策 Intune で構成する
description: Microsoft Defender AV Microsoft エンドポイント マネージャー Microsoft Intuneを構成するには、Microsoft Defender AV と Microsoft Defender AV を構成するEndpoint Protection
keywords: scep、intune、エンドポイント保護、構成
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 10/26/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.openlocfilehash: b62344945efc0bdfc495a4fc4196cea6ddcb1874
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275326"
---
# <a name="use-microsoft-endpoint-manager-and-microsoft-intune-to-configure-and-manage-microsoft-defender-antivirus"></a><span data-ttu-id="29ade-104">[Microsoft エンドポイント マネージャーとMicrosoft Intuneを使用して、構成および管理Microsoft Defender ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="29ade-104">Use Microsoft Endpoint Manager and Microsoft Intune to configure and manage Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="29ade-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="29ade-105">**Applies to:**</span></span>

- [<span data-ttu-id="29ade-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="29ade-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="29ade-107">ネットワーク上のエンドポイントMicrosoft エンドポイント マネージャーまたは Microsoft Intuneを使用していた場合は、Microsoft エンドポイント マネージャーを使用してMicrosoft Defender ウイルス対策できます。</span><span class="sxs-lookup"><span data-stu-id="29ade-107">If you were using Microsoft Endpoint Manager or Microsoft Intune to manage the endpoints on your network, you can now use Microsoft Endpoint Manager to manage Microsoft Defender Antivirus scans.</span></span>

1. <span data-ttu-id="29ade-108">[管理Microsoft エンドポイント マネージャー () で [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 、[エンドポイント セキュリティ]**に移動します**。</span><span class="sxs-lookup"><span data-stu-id="29ade-108">In the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), navigate to **Endpoint Security**.</span></span>

2. <span data-ttu-id="29ade-109">[管理 **] で**、[ウイルス対策] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="29ade-109">Under **Manage**, choose **Antivirus**.</span></span>

3. <span data-ttu-id="29ade-110">ポリシーをMicrosoft Defender ウイルス対策します。</span><span class="sxs-lookup"><span data-stu-id="29ade-110">Select your Microsoft Defender Antivirus policy.</span></span> 

4. <span data-ttu-id="29ade-111">[**管理**] で [**プロパティ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="29ade-111">Under **Manage**, choose **Properties**.</span></span>

5. <span data-ttu-id="29ade-112">**[構成の設定]** の横にある **[編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="29ade-112">Next to **Configuration settings**, choose **Edit**.</span></span>

6. <span data-ttu-id="29ade-113">[スキャン] **セクションを** 展開し、スキャン設定を確認または編集します。</span><span class="sxs-lookup"><span data-stu-id="29ade-113">Expand the **Scan** section, and review or edit your scanning settings.</span></span>

7. <span data-ttu-id="29ade-114">[レビュー **] + [保存] の選択**</span><span class="sxs-lookup"><span data-stu-id="29ade-114">Choose **Review + save**</span></span>

<span data-ttu-id="29ade-115">サポートが必要な場合</span><span class="sxs-lookup"><span data-stu-id="29ade-115">Need help?</span></span> <span data-ttu-id="29ade-116">「Manage [endpoint security in Microsoft Intune」 を参照してください](/mem/intune/protect/endpoint-security)。</span><span class="sxs-lookup"><span data-stu-id="29ade-116">See [Manage endpoint security in Microsoft Intune](/mem/intune/protect/endpoint-security).</span></span>


## <a name="related-articles"></a><span data-ttu-id="29ade-117">関連記事</span><span class="sxs-lookup"><span data-stu-id="29ade-117">Related articles</span></span>

- [<span data-ttu-id="29ade-118">管理および構成ツールのリファレンス トピック</span><span class="sxs-lookup"><span data-stu-id="29ade-118">Reference topics for management and configuration tools</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="29ade-119">Microsoft Defender ウイルス対策 (Windows 10)</span><span class="sxs-lookup"><span data-stu-id="29ade-119">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)