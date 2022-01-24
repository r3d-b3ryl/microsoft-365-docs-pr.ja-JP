---
title: Microsoft 365 Defender と Microsoft Sentinel の統合
description: Microsoft Sentinel を SIEM として使用して、Microsoft 365 Defenderイベントを実行します。
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
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 0c00ecdde6f94d7737cb4dc8d503b83469821fb5
ms.sourcegitcommit: 6f3bc00a5cf25c48c61eb3835ac069e9f41dc4db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2022
ms.locfileid: "62171895"
---
# <a name="microsoft-365-defender-integration-with-microsoft-sentinel"></a>Microsoft 365 Defender と Microsoft Sentinel の統合

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**
- Microsoft 365 Defender

Microsoft Sentinel (プレビュー) の Microsoft 365 Defender コネクタは、すべてのインシデントと通知Microsoft 365 Defender Microsoft Sentinel に送信し、インシデントの同期を維持します。 

コネクタを追加すると、Microsoft &mdash; Defender for Endpoint、Microsoft Defender for Identity、Microsoft Defender for Office 365、Microsoft Defender for Cloud Apps &mdash; から受信するすべての関連アラート、エンティティ、関連情報を含む Microsoft 365 Defender インシデントが発生します。は、セキュリティ情報およびイベント管理 (SIEM) データとして Microsoft Sentinel にストリーミングされ、Microsoft Sentinel でトリアージおよびインシデント対応を実行するためのコンテキストを提供します。 

Microsoft Sentinel では、インシデントは Microsoft 365 Defender と双方向に同期されたままで、インシデントの調査と対応のために Azure ポータルの Microsoft 365 Defender ポータルと Microsoft Sentinel の両方の利点を利用できます。

Microsoft Sentinel と Microsoft Sentinel の統合の概要 (Microsoft 365 Defender 4 分) をご覧ください。

<br>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWFIRo]


動作方法を次に示します。

:::image type="content" source="../../media/microsoft-365-defender-integration-with-azure-sentinel/microsoft-365-defender-integration-with-azure-sentinel.png" alt-text="インシデント データのフローと共有は、Microsoft 365 Defenderと Microsoft Sentinel の間で行います。":::

## <a name="next-steps"></a>次の手順

1. Microsoft Sentinel との統合に[関するMicrosoft 365 Defender理解を深める](/azure/sentinel/microsoft-365-defender-sentinel-integration)。
2. [Connectから Microsoft Sentinel Microsoft 365 Defenderデータを取得します](/azure/sentinel/connect-microsoft-365-defender)。

## <a name="see-also"></a>関連項目

- [インシデントのMicrosoft 365 Defender](incidents-overview.md)
- [Microsoft Sentinel でインシデントを調査する](/azure/sentinel/tutorial-investigate-cases)
