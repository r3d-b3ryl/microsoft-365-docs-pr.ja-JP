---
title: Microsoft 365 Defender と Microsoft Sentinel の統合
description: Microsoft 365 Defender インシデントおよびイベントの SIEM として Microsoft Sentinel を使用します。
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
ms.openlocfilehash: d0add9fe000966cdeb2ffc5ce23e4ba0690bbadb
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63320285"
---
# <a name="microsoft-365-defender-integration-with-microsoft-sentinel"></a>Microsoft 365 Defender と Microsoft Sentinel の統合

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**
- Microsoft 365 Defender

Microsoft Sentinel 用 Microsoft 365 Defender コネクタ (プレビュー) は、Microsoft 365 Defender のすべてのインシデントとアラート情報を Microsoft Sentinel に送信し、インシデントの同期を維持します。 

コネクタを追加すると、Microsoft 365 Defender&mdash; インシデントが含まれます。Microsoft Defender for Endpoint、Microsoft Defender for Identity、Microsoft Defender for Office 365、Microsoft Defender for&mdash; Cloud Apps から受信した関連情報はすべて、セキュリティ情報およびイベント管理 (SIEM) データとして Microsoft Sentinel にストリーミングされ、Microsoft Sentinel でトリアージとインシデント対応を実行するためのコンテキストが提供されます。 

Microsoft Sentinel では、インシデントは Microsoft 365 Defender と双方向に同期されたままであり、インシデントの調査と対応のために Azure ポータルの Microsoft 365 Defender ポータルと Microsoft Sentinel の両方の利点を活用できます。

Microsoft Sentinel と Microsoft 365 Defender との統合の概要 (4 分) をご覧ください。

<br>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWFIRo]


動作方法を次に示します。

:::image type="content" source="../../media/microsoft-365-defender-integration-with-azure-sentinel/microsoft-365-defender-integration-with-azure-sentinel.png" alt-text="Microsoft 365 Defender と Microsoft Sentinel のインシデント データのフローと共有。":::

## <a name="next-steps"></a>次の手順

1. [Microsoft 365 Defender と Microsoft Sentinel](/azure/sentinel/microsoft-365-defender-sentinel-integration) との統合について、より深く理解してください。
2. [Microsoft 365 Defender から Microsoft Sentinel にデータを接続します](/azure/sentinel/connect-microsoft-365-defender)。

## <a name="see-also"></a>関連項目

- [Microsoft 365 Defender でのインシデントの概要](incidents-overview.md)
- [Microsoft Sentinel でインシデントを調査する](/azure/sentinel/tutorial-investigate-cases)
