---
title: Microsoft 365 Defender と Microsoft Sentinel の統合
description: インシデントとイベントをMicrosoft 365 Defenderする SIEM として Microsoft Sentinel を使用します。
keywords: インシデント、アラート、調査、分析、応答、相関、攻撃、マシン、デバイス、ユーザー、複数の ID、ID、メールボックス、メール、365、Microsoft、M365
search.product: eADQiWindows 10XVcnh
ms.service: microsoft-365-security
ms.subservice: m365d
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
ms.openlocfilehash: 3ddf2e863b764cbf2109acda7a6318a98882f901
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67480758"
---
# <a name="microsoft-365-defender-integration-with-microsoft-sentinel"></a>Microsoft 365 Defender と Microsoft Sentinel の統合

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**
- Microsoft 365 Defender

Microsoft Sentinel のMicrosoft 365 Defender コネクタ (プレビュー) は、すべてのMicrosoft 365 Defenderインシデントとアラート情報を Microsoft Sentinel に送信し、インシデントを同期し続けます。 

コネクタを追加すると、Microsoft Defender for Endpoint、Microsoft Defender for Identityから受信したすべての関連するアラート、エンティティ、関連情報を含むインシデント&mdash;がMicrosoft 365 Defenderされます。Microsoft Defender for Office 365とMicrosoft Defender for Cloud Apps&mdash;セキュリティ情報とイベント管理 (SIEM) データとして Microsoft Sentinel にストリーミングされ、Microsoft Sentinel でトリアージとインシデント対応を実行するためのコンテキストが提供されます。 

Microsoft Sentinel では、インシデントはMicrosoft 365 Defenderと双方向に同期され続け、インシデントの調査と対応のためにAzure portalのMicrosoft 365 Defender ポータルと Microsoft Sentinel の両方の利点を利用できます。

Microsoft Sentinel と Microsoft 365 Defender (4 分) の統合の概要をご覧ください。

<br>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWFIRo]


動作方法を次に示します。

:::image type="content" source="../../media/microsoft-365-defender-integration-with-azure-sentinel/microsoft-365-defender-integration-with-azure-sentinel.png" alt-text="Microsoft 365 Defenderポータルと Microsoft Sentinel ポータルのインシデント データのフローと共有" lightbox="../../media/microsoft-365-defender-integration-with-azure-sentinel/microsoft-365-defender-integration-with-azure-sentinel.png":::

## <a name="next-steps"></a>次の手順

1. [Microsoft Sentinel とのMicrosoft 365 Defender統合](/azure/sentinel/microsoft-365-defender-sentinel-integration)について詳しく理解します。
2. [Microsoft 365 Defenderから Microsoft Sentinel にデータを接続します](/azure/sentinel/connect-microsoft-365-defender)。

## <a name="see-also"></a>関連項目

- [Microsoft 365 Defenderのインシデントの概要](incidents-overview.md)
- [Microsoft Sentinel でインシデントを調査する](/azure/sentinel/tutorial-investigate-cases)
