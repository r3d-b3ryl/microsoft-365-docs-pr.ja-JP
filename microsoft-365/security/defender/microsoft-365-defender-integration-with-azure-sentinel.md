---
title: Microsoft 365 Defender と Azure Sentinel との統合
description: Azure Sentinel を SIEM として使用して、Microsoft 365 Defenderイベントを実行します。
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
ms.openlocfilehash: adb65c82713464da2df4d473d2fd7a055e0dbeb3
ms.sourcegitcommit: 4046c2c390851dffcdb430e1ba38c4df23fe2e69
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/13/2021
ms.locfileid: "53415580"
---
# <a name="microsoft-365-defender-integration-with-azure-sentinel"></a><span data-ttu-id="91f0f-104">Microsoft 365 Defender と Azure Sentinel との統合</span><span class="sxs-lookup"><span data-stu-id="91f0f-104">Microsoft 365 Defender integration with Azure Sentinel</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="91f0f-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="91f0f-105">**Applies to:**</span></span>
- <span data-ttu-id="91f0f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="91f0f-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="91f0f-107">Azure Sentinel (プレビュー) の Microsoft 365 Defender コネクタは、すべての Microsoft 365 Defender インシデントとアラート情報を Azure Sentinel に送信し、インシデントの同期を維持します。</span><span class="sxs-lookup"><span data-stu-id="91f0f-107">The Microsoft 365 Defender connector for Azure Sentinel (preview) sends all Microsoft 365 Defender incidents and alerts information to Azure Sentinel and keeps the incidents synchronized.</span></span> 

<span data-ttu-id="91f0f-108">コネクタを追加すると &mdash; 、Microsoft Defender for Endpoint、Microsoft Defender for Identity、Microsoft Defender for Office 365、および Microsoft Cloud App Security から受信した関連するすべてのアラート、エンティティ、関連情報を含む Microsoft 365 Defender インシデントがセキュリティ情報およびイベント管理 (SIEM) データとして Azure Sentinel にストリーミングされ、Azure Sentinel でトリアージとインシデント対応を実行するためのコンテキストが提供されます。 &mdash;</span><span class="sxs-lookup"><span data-stu-id="91f0f-108">Once you add the connector, Microsoft 365 Defender incidents&mdash;which include all associated alerts, entities, and relevant information received from Microsoft Defender for Endpoint, Microsoft Defender for Identity, Microsoft Defender for Office 365, and Microsoft Cloud App Security&mdash;are streamed to Azure Sentinel as security information and event management (SIEM) data, providing you with context to perform triage and incident response with Azure Sentinel.</span></span> 

<span data-ttu-id="91f0f-109">Azure Sentinel では、インシデントは Microsoft 365 Defender と双方向に同期されたままであり、インシデントの調査と対応のために Azure ポータルの Microsoft 365 Defender ポータルと Azure Sentinel の両方の利点を利用できます。</span><span class="sxs-lookup"><span data-stu-id="91f0f-109">Once in Azure Sentinel, incidents remain bi-directionally synchronized with Microsoft 365 Defender, allowing you to take advantage of the benefits of both the Microsoft 365 Defender portal and Azure Sentinel in the Azure portal for incident investigation and response.</span></span>

<span data-ttu-id="91f0f-110">Azure Sentinel と Azure Sentinel の統合の概要 (Microsoft 365 Defender 4 分) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="91f0f-110">Watch this short overview of Azure Sentinel integration with Microsoft 365 Defender (4 minutes).</span></span>

<br>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWFIRo]


<span data-ttu-id="91f0f-111">動作方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="91f0f-111">Here's how it works.</span></span>

:::image type="content" source="../../media/microsoft-365-defender-integration-with-azure-sentinel/microsoft-365-defender-integration-with-azure-sentinel.png" alt-text="インシデント データのフローと共有は、Microsoft 365 Defenderと Azure Sentinel の間で行います。":::

## <a name="next-steps"></a><span data-ttu-id="91f0f-113">次の手順</span><span class="sxs-lookup"><span data-stu-id="91f0f-113">Next steps</span></span>

1. <span data-ttu-id="91f0f-114">Azure Sentinel との統合に[関するMicrosoft 365 Defender理解を深める](/azure/sentinel/microsoft-365-defender-sentinel-integration)。</span><span class="sxs-lookup"><span data-stu-id="91f0f-114">Get a deeper understanding of [Microsoft 365 Defender integration with Azure Sentinel](/azure/sentinel/microsoft-365-defender-sentinel-integration).</span></span>
2. <span data-ttu-id="91f0f-115">[Connectから Azure Sentinel Microsoft 365 Defenderデータを取得します](/azure/sentinel/connect-microsoft-365-defender)。</span><span class="sxs-lookup"><span data-stu-id="91f0f-115">[Connect data from Microsoft 365 Defender to Azure Sentinel](/azure/sentinel/connect-microsoft-365-defender).</span></span>

## <a name="see-also"></a><span data-ttu-id="91f0f-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="91f0f-116">See also</span></span>

- [<span data-ttu-id="91f0f-117">インシデントのMicrosoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="91f0f-117">Overview of incidents in Microsoft 365 Defender</span></span>](incidents-overview.md)
- [<span data-ttu-id="91f0f-118">Azure Sentinel でインシデントを調査する</span><span class="sxs-lookup"><span data-stu-id="91f0f-118">Investigate incidents with Azure Sentinel</span></span>](/azure/sentinel/tutorial-investigate-cases)
