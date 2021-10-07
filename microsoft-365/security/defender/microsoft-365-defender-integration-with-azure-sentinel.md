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
ms.localizationpriority: medium
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
ms.openlocfilehash: 0520b5dde6cd2cd1d3b59fe05ce32df6412bb7fd
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60210581"
---
# <a name="microsoft-365-defender-integration-with-azure-sentinel"></a>Microsoft 365 Defender と Azure Sentinel との統合

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**
- Microsoft 365 Defender

Azure Sentinel (プレビュー) の Microsoft 365 Defender コネクタは、すべての Microsoft 365 Defender インシデントとアラート情報を Azure Sentinel に送信し、インシデントの同期を維持します。 

コネクタを追加すると &mdash; 、Microsoft Defender for Endpoint、Microsoft Defender for Identity、Microsoft Defender for Office 365、および Microsoft Cloud App Security から受信した関連するすべてのアラート、エンティティ、関連情報を含む Microsoft 365 Defender インシデントが Azure Sentinel にストリーミングされます。 &mdash;セキュリティ情報およびイベント管理 (SIEM) データとして、Azure Sentinel でトリアージおよびインシデント対応を実行するためのコンテキストを提供します。 

Azure Sentinel では、インシデントは Microsoft 365 Defender と双方向に同期されたままであり、インシデントの調査と対応のために Azure ポータルの Microsoft 365 Defender ポータルと Azure Sentinel の両方の利点を利用できます。

Azure Sentinel と Azure Sentinel の統合の概要 (Microsoft 365 Defender 4 分) をご覧ください。

<br>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWFIRo]


動作方法を次に示します。

:::image type="content" source="../../media/microsoft-365-defender-integration-with-azure-sentinel/microsoft-365-defender-integration-with-azure-sentinel.png" alt-text="インシデント データのフローと共有は、Microsoft 365 Defenderと Azure Sentinel の間で行います。":::

## <a name="next-steps"></a>次の手順

1. Azure Sentinel との統合に[関するMicrosoft 365 Defender理解を深める](/azure/sentinel/microsoft-365-defender-sentinel-integration)。
2. [Connectから Azure Sentinel Microsoft 365 Defenderデータを取得します](/azure/sentinel/connect-microsoft-365-defender)。

## <a name="see-also"></a>関連項目

- [インシデントのMicrosoft 365 Defender](incidents-overview.md)
- [Azure Sentinel でインシデントを調査する](/azure/sentinel/tutorial-investigate-cases)
