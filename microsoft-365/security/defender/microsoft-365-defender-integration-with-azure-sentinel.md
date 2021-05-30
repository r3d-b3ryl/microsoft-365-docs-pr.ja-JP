---
title: Microsoft 365Defender と Azure Sentinel の統合
description: Defender のインシデントとイベントに対する SIEM Microsoft 365 Azure Sentinel を使用します。
keywords: インシデント、アラート、調査、調査、分析、応答、相関関係、攻撃、コンピューター、デバイス、ユーザー、ID、ID、メールボックス、電子メール、365、microsoft、m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: b5a53131733d1c7c539676c1d45abe7eabbe2de7
ms.sourcegitcommit: 76c91e7b0d3172de57988eb4576d2b91c2f9ce18
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2021
ms.locfileid: "52707339"
---
# <a name="microsoft-365-defender-integration-with-azure-sentinel"></a><span data-ttu-id="bf487-104">Microsoft 365Defender と Azure Sentinel の統合</span><span class="sxs-lookup"><span data-stu-id="bf487-104">Microsoft 365 Defender integration with Azure Sentinel</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="bf487-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="bf487-105">**Applies to:**</span></span>
- <span data-ttu-id="bf487-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bf487-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="bf487-107">Azure Sentinel の Microsoft 365 Defender コネクタ (プレビュー) は、すべての Microsoft 365 Defender インシデントとアラート情報を Azure Sentinel に送信し、インシデントの同期を維持します。</span><span class="sxs-lookup"><span data-stu-id="bf487-107">The Microsoft 365 Defender connector for Azure Sentinel (preview) sends all Microsoft 365 Defender incidents and alerts information to Azure Sentinel and keeps the incidents synchronized.</span></span> 

<span data-ttu-id="bf487-108">コネクタを追加すると、Microsoft Defender for Endpoint、Microsoft Defender for Identity、Microsoft Defender for Office 365、および Microsoft Cloud App Security から受信した関連するすべてのアラート、エンティティ、関連情報を含む Microsoft 365 Defender インシデントがセキュリティ情報およびイベント管理 (SIEM) データとして Azure Sentinel にストリーミングされ &mdash; 、Azure Sentinel でトリアージとインシデント応答を実行するためのコンテキストが提供されます。 &mdash;</span><span class="sxs-lookup"><span data-stu-id="bf487-108">Once you add the connector, Microsoft 365 Defender incidents&mdash;which include all associated alerts, entities, and relevant information received from Microsoft Defender for Endpoint, Microsoft Defender for Identity, Microsoft Defender for Office 365, and Microsoft Cloud App Security&mdash;are streamed to Azure Sentinel as security information and event management (SIEM) data, providing you with context to perform triage and incident response with Azure Sentinel.</span></span> 

<span data-ttu-id="bf487-109">Azure Sentinel では、インシデントは Microsoft 365 Defender と双方向に同期されたままであり、インシデントの調査と対応のために Azure ポータルの Microsoft 365 セキュリティ センターと Azure Sentinel の両方の利点を利用できます。</span><span class="sxs-lookup"><span data-stu-id="bf487-109">Once in Azure Sentinel, incidents remain bi-directionally synchronized with Microsoft 365 Defender, allowing you to take advantage of the benefits of both the Microsoft 365 security center and Azure Sentinel in the Azure portal for incident investigation and response.</span></span>

<span data-ttu-id="bf487-110">動作方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="bf487-110">Here's how it works.</span></span>

:::image type="content" source="../../media/microsoft-365-defender-integration-with-azure-sentinel/microsoft-365-defender-integration-with-azure-sentinel.png" alt-text="Defender と Azure Sentinel の間のインシデント Microsoft 365のフローと共有":::

## <a name="next-steps"></a><span data-ttu-id="bf487-112">次の手順</span><span class="sxs-lookup"><span data-stu-id="bf487-112">Next steps</span></span>

1. <span data-ttu-id="bf487-113">Defender と[Azure Sentinel との統合Microsoft 365理解を深める](/azure/sentinel/microsoft-365-defender-sentinel-integration)。</span><span class="sxs-lookup"><span data-stu-id="bf487-113">Get a better understanding of [Microsoft 365 Defender integration with Azure Sentinel](/azure/sentinel/microsoft-365-defender-sentinel-integration).</span></span>
2. <span data-ttu-id="bf487-114">[Connect Defender から Azure Sentinel Microsoft 365データを取得します](/azure/sentinel/connect-microsoft-365-defender)。</span><span class="sxs-lookup"><span data-stu-id="bf487-114">[Connect data from Microsoft 365 Defender to Azure Sentinel](/azure/sentinel/connect-microsoft-365-defender).</span></span>

## <a name="see-also"></a><span data-ttu-id="bf487-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="bf487-115">See also</span></span>

- [<span data-ttu-id="bf487-116">Defender でのインシデントMicrosoft 365概要</span><span class="sxs-lookup"><span data-stu-id="bf487-116">Overview of incidents in Microsoft 365 Defender</span></span>](incidents-overview.md)
- [<span data-ttu-id="bf487-117">Azure Sentinel でインシデントを調査する</span><span class="sxs-lookup"><span data-stu-id="bf487-117">Investigate incidents with Azure Sentinel</span></span>](/azure/sentinel/tutorial-investigate-cases)
