---
title: Microsoft 365 Defender と Microsoft Sentinel の統合
description: Microsoft Sentinel を SIEM として使用して、Microsoft 365 Defenderイベントに使用します。
keywords: インシデント、アラート、調査、調査、分析、応答、相関関係、攻撃、コンピューター、デバイス、ユーザー、ID、ID、メールボックス、電子メール、365、microsoft、m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
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
ms.openlocfilehash: 75aea706cdcb65752b673d32ccff968209ba74b7
ms.sourcegitcommit: 3b8e009ea1ce928505b8fc3b8926021fb91155f3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2022
ms.locfileid: "64499465"
---
# <a name="microsoft-365-defender-integration-with-microsoft-sentinel"></a>Microsoft 365 Defender と Microsoft Sentinel の統合

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**
- Microsoft 365 Defender

Microsoft Sentinel (プレビュー) の Microsoft 365 Defender コネクタは、Microsoft Sentinel にすべての Microsoft 365 Defender インシデントと通知情報を送信し、インシデントの同期を維持します。 

コネクタを追加すると、Microsoft 365 Defender&mdash; インシデントが含まれます。Microsoft Defender for Endpoint、Microsoft Defender for Identity、Microsoft Defender for Office 365、Microsoft Defender for Cloud Apps&mdash; から受信するすべての関連アラート、エンティティ、および関連情報が含まれます。は、セキュリティ情報およびイベント管理 (SIEM) データとして Microsoft Sentinel にストリーミングされ、Microsoft Sentinel でトリアージおよびインシデント対応を実行するためのコンテキストを提供します。 

Microsoft Sentinel では、インシデントは Microsoft 365 Defender と双方向に同期されたままであり、インシデントの調査と対応のために Azure ポータルの Microsoft 365 Defender ポータルと Microsoft Sentinel の両方の利点を活用できます。

Microsoft Sentinel と Microsoft Sentinel の統合の概要 (Microsoft 365 Defender 4 分) をご覧ください。

<br>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWFIRo]


動作方法を次に示します。

:::image type="content" source="../../media/microsoft-365-defender-integration-with-azure-sentinel/microsoft-365-defender-integration-with-azure-sentinel.png" alt-text="ネットワーク ポータルと Microsoft Sentinel ポータルのインシデント Microsoft 365 Defenderのフローと共有" lightbox="../../media/microsoft-365-defender-integration-with-azure-sentinel/microsoft-365-defender-integration-with-azure-sentinel.png":::

## <a name="next-steps"></a>次の手順

1. [Microsoft Sentinel](/azure/sentinel/microsoft-365-defender-sentinel-integration) との統合Microsoft 365 Defender理解を深める。
2. [Connectから Microsoft Sentinel Microsoft 365 Defenderデータを取得します](/azure/sentinel/connect-microsoft-365-defender)。

## <a name="see-also"></a>関連項目

- [グループ内のインシデントのMicrosoft 365 Defender](incidents-overview.md)
- [Microsoft Sentinel でインシデントを調査する](/azure/sentinel/tutorial-investigate-cases)
