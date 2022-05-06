---
title: Microsoft 365 Defender と Microsoft Sentinel の統合
description: インシデントとイベントをMicrosoft 365 Defenderする SIEM として Microsoft Sentinel を使用します。
keywords: インシデント, アラート, 調査, 分析, 応答, 相関関係, 攻撃, マシン, デバイス, ユーザー, ID, ID, メールボックス, 電子メール, 365, Microsoft, m365
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

Microsoft Sentinel のMicrosoft 365 Defender コネクタ (プレビュー) は、すべてのMicrosoft 365 Defenderインシデントとアラート情報を Microsoft Sentinel に送信し、インシデントを同期し続けます。 

コネクタを追加すると、Microsoft 365 Defenderインシデント&mdash;に関連するすべてのアラート、エンティティ、およびMicrosoft Defender for Endpoint、Microsoft Defender for Identity、Microsoft Defender for Office 365とMicrosoft Defender for Cloud Apps&mdash;セキュリティ情報とイベント管理 (SIEM) データとして Microsoft Sentinel にストリーミングされ、Microsoft Sentinel でトリアージとインシデント対応を実行するためのコンテキストが提供されます。 

Microsoft Sentinel では、インシデントはMicrosoft 365 Defenderと双方向に同期され続け、インシデントの調査と対応のためにAzure portalのMicrosoft 365 Defender ポータルと Microsoft Sentinel の両方の利点を利用できます。

Microsoft Sentinel と Microsoft 365 Defender (4 分) の統合の概要をご覧ください。

<br>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWFIRo]


動作方法を次に示します。

:::image type="content" source="../../media/microsoft-365-defender-integration-with-azure-sentinel/microsoft-365-defender-integration-with-azure-sentinel.png" alt-text="Microsoft 365 Defenderポータルと Microsoft Sentinel ポータルのインシデント データのフローと共有" lightbox="../../media/microsoft-365-defender-integration-with-azure-sentinel/microsoft-365-defender-integration-with-azure-sentinel.png":::

## <a name="next-steps"></a>次の手順

1. [Microsoft Sentinel とのMicrosoft 365 Defender統合](/azure/sentinel/microsoft-365-defender-sentinel-integration)について詳しく理解します。
2. [Microsoft 365 Defenderから Microsoft Sentinel にデータをConnect](/azure/sentinel/connect-microsoft-365-defender)します。

## <a name="see-also"></a>関連項目

- [Microsoft 365 Defenderのインシデントの概要](incidents-overview.md)
- [Microsoft Sentinel でインシデントを調査する](/azure/sentinel/tutorial-investigate-cases)
