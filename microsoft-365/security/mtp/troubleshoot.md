---
title: Microsoft Threat Protection サービスに関する問題のトラブルシューティング
description: 既知の Microsoft Threat Protection の問題の解決策と対処方法を見つける
keywords: Microsoft Threat Protection のトラブルシューティング、トラブルシューティング、問題
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
ms.openlocfilehash: 4c32f815e262abbe5d901f5c29323f83ef1b71d8
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2019
ms.locfileid: "39911360"
---
# <a name="troubleshoot-microsoft-threat-protection-service-issues"></a><span data-ttu-id="34184-104">Microsoft Threat Protection サービスに関する問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="34184-104">Troubleshoot Microsoft Threat Protection service issues</span></span>

<span data-ttu-id="34184-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="34184-105">**Applies to:**</span></span>
- <span data-ttu-id="34184-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="34184-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="34184-107">このセクションでは、Microsoft Threat Protection サービスを使用するときに発生する可能性のある問題に対処します。</span><span class="sxs-lookup"><span data-stu-id="34184-107">This section addresses issues that might arise as you use the Microsoft Threat Protection service.</span></span>


## <a name="not-seeing-microsoft-threat-protection-content"></a><span data-ttu-id="34184-108">Microsoft Threat Protection コンテンツが表示されない</span><span class="sxs-lookup"><span data-stu-id="34184-108">Not seeing Microsoft Threat Protection content</span></span>
<span data-ttu-id="34184-109">インシデント、アクションセンター、ポータルでの検索などの機能がナビゲーション ウィンドウに表示されない場合は、テナントに適切なライセンスがあることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34184-109">If you don't see capabilities on the navigation page such as the Incidents, Action Center, or Hunting in your portal you'll need to verify that your tenant has the appropriate license.</span></span> 

<span data-ttu-id="34184-110">詳細については、「[前提条件](prerequisites.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="34184-110">For more information, see [Prerequisites](prerequisites.md).</span></span>

## <a name="azure-atp-alerts-are-not-showing-up-in-the-microsoft-threat-protection-incidents"></a><span data-ttu-id="34184-111">Microsoft Threat Protection インシデントに Azure ATP アラートが表示されない</span><span class="sxs-lookup"><span data-stu-id="34184-111">Azure ATP alerts are not showing up in the Microsoft Threat Protection incidents</span></span>
<span data-ttu-id="34184-112">環境に Azure ATP が展開されていても、Microsoft Threat Protection インシデントの一部として Azure ATP アラートが表示されない場合は、Microsoft Cloud App Security および Azure ATP 統合が有効であることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34184-112">If you have Azure ATP deployed in your environment but you're not seeing Azure ATP alerts as part of Microsoft Threat Protection incidents, you'll need to ensure that the Microsoft Cloud App Security and Azure ATP integration is enabled.</span></span> 

<span data-ttu-id="34184-113">詳細については、「[Azure ATP 統合](https://docs.microsoft.com/cloud-app-security/aatp-integration)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34184-113">For more information, see [Azure ATP integration](https://docs.microsoft.com/cloud-app-security/aatp-integration).</span></span>

## <a name="is-microsoft-threat-protection-available-for-us-government-community-cloud-gcc-or-gcc-high"></a><span data-ttu-id="34184-114">Microsoft Threat Protection は、米国政府機関向けコミュニティ クラウド (GCC) または GCC High で使用できますか?</span><span class="sxs-lookup"><span data-stu-id="34184-114">Is Microsoft Threat Protection available for US Government Community Cloud (GCC) or GCC High?</span></span>
<span data-ttu-id="34184-115">現時点では、使用できません。</span><span class="sxs-lookup"><span data-stu-id="34184-115">At the moment, it is not available.</span></span> 


