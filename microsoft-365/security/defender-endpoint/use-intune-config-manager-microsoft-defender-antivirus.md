---
title: サーバーをMicrosoft Defender ウイルス対策構成Microsoft エンドポイント マネージャー
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
ms.date: 05/24/2021
ms.reviewer: phuijbr, oogunrinde
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.openlocfilehash: ab77f3ab5ac9385d1ce049061730d2192e3bcb0c
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683753"
---
# <a name="use-microsoft-endpoint-manager-to-configure-and-manage-microsoft-defender-antivirus"></a><span data-ttu-id="095f0-104">[Microsoft エンドポイント マネージャーを使用して、構成および管理Microsoft Defender ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="095f0-104">Use Microsoft Endpoint Manager to configure and manage Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="095f0-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="095f0-105">**Applies to:**</span></span>

- [<span data-ttu-id="095f0-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="095f0-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="095f0-107">このオプションを使用[Microsoft エンドポイント マネージャー](/mem/endpoint-manager-overview)スキャンをMicrosoft Defender ウイルス対策できます。</span><span class="sxs-lookup"><span data-stu-id="095f0-107">You can use [Microsoft Endpoint Manager](/mem/endpoint-manager-overview) to configure Microsoft Defender Antivirus scans.</span></span> <span data-ttu-id="095f0-108">[Microsoft Intune](/mem/intune/fundamentals/what-is-intune)[構成マネージャーは](/mem/configmgr/core/understand/introduction)、このページの一部エンドポイント マネージャー。</span><span class="sxs-lookup"><span data-stu-id="095f0-108">[Microsoft Intune](/mem/intune/fundamentals/what-is-intune) and [Configuration Manager](/mem/configmgr/core/understand/introduction) are now part of Endpoint Manager.</span></span>  

## <a name="configure-microsoft-defender-antivirus-scans-in-endpoint-manager"></a><span data-ttu-id="095f0-109">コンピューター Microsoft Defender ウイルス対策スキャンを構成エンドポイント マネージャー</span><span class="sxs-lookup"><span data-stu-id="095f0-109">Configure Microsoft Defender Antivirus scans in Endpoint Manager</span></span>

1. <span data-ttu-id="095f0-110">管理センター ( ) Microsoft エンドポイント マネージャーに [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 移動し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="095f0-110">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), and sign in.</span></span>

2. <span data-ttu-id="095f0-111">[エンドポイント セキュリティ **] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="095f0-111">Navigate to **Endpoint Security**.</span></span>

3. <span data-ttu-id="095f0-112">[管理 **] で**、[ウイルス対策] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="095f0-112">Under **Manage**, choose **Antivirus**.</span></span>

4. <span data-ttu-id="095f0-113">ポリシーをMicrosoft Defender ウイルス対策します。</span><span class="sxs-lookup"><span data-stu-id="095f0-113">Select your Microsoft Defender Antivirus policy.</span></span> 

5. <span data-ttu-id="095f0-114">[**管理**] で [**プロパティ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="095f0-114">Under **Manage**, choose **Properties**.</span></span>

6. <span data-ttu-id="095f0-115">**[構成の設定]** の横にある **[編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="095f0-115">Next to **Configuration settings**, choose **Edit**.</span></span>

7. <span data-ttu-id="095f0-116">[スキャン] **セクションを** 展開し、スキャン設定を確認または編集します。</span><span class="sxs-lookup"><span data-stu-id="095f0-116">Expand the **Scan** section, and review or edit your scanning settings.</span></span>

8. <span data-ttu-id="095f0-117">[レビュー **] + [保存] の選択**</span><span class="sxs-lookup"><span data-stu-id="095f0-117">Choose **Review + save**</span></span>


> [!TIP]
> <span data-ttu-id="095f0-118">サポートが必要な場合</span><span class="sxs-lookup"><span data-stu-id="095f0-118">Need help?</span></span> <span data-ttu-id="095f0-119">「Manage [endpoint security in Microsoft Intune」 を参照してください](/mem/intune/protect/endpoint-security)。</span><span class="sxs-lookup"><span data-stu-id="095f0-119">See [Manage endpoint security in Microsoft Intune](/mem/intune/protect/endpoint-security).</span></span>


## <a name="related-articles"></a><span data-ttu-id="095f0-120">関連資料</span><span class="sxs-lookup"><span data-stu-id="095f0-120">Related articles</span></span>

- [<span data-ttu-id="095f0-121">管理および構成ツールの参照記事</span><span class="sxs-lookup"><span data-stu-id="095f0-121">Reference articles for management and configuration tools</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="095f0-122">Microsoft Defender ウイルス対策 (Windows 10)</span><span class="sxs-lookup"><span data-stu-id="095f0-122">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)