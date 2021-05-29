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
# <a name="microsoft-365-defender-integration-with-azure-sentinel"></a>Microsoft 365Defender と Azure Sentinel の統合

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**
- Microsoft 365 Defender

Azure Sentinel の Microsoft 365 Defender コネクタ (プレビュー) は、すべての Microsoft 365 Defender インシデントとアラート情報を Azure Sentinel に送信し、インシデントの同期を維持します。 

コネクタを追加すると、Microsoft Defender for Endpoint、Microsoft Defender for Identity、Microsoft Defender for Office 365、および Microsoft Cloud App Security から受信した関連するすべてのアラート、エンティティ、関連情報を含む Microsoft 365 Defender インシデントがセキュリティ情報およびイベント管理 (SIEM) データとして Azure Sentinel にストリーミングされ &mdash; 、Azure Sentinel でトリアージとインシデント応答を実行するためのコンテキストが提供されます。 &mdash; 

Azure Sentinel では、インシデントは Microsoft 365 Defender と双方向に同期されたままであり、インシデントの調査と対応のために Azure ポータルの Microsoft 365 セキュリティ センターと Azure Sentinel の両方の利点を利用できます。

動作方法を次に示します。

:::image type="content" source="../../media/microsoft-365-defender-integration-with-azure-sentinel/microsoft-365-defender-integration-with-azure-sentinel.png" alt-text="Defender と Azure Sentinel の間のインシデント Microsoft 365のフローと共有":::

## <a name="next-steps"></a>次の手順

1. Defender と[Azure Sentinel との統合Microsoft 365理解を深める](/azure/sentinel/microsoft-365-defender-sentinel-integration)。
2. [Connect Defender から Azure Sentinel Microsoft 365データを取得します](/azure/sentinel/connect-microsoft-365-defender)。

## <a name="see-also"></a>関連項目

- [Defender でのインシデントMicrosoft 365概要](incidents-overview.md)
- [Azure Sentinel でインシデントを調査する](/azure/sentinel/tutorial-investigate-cases)
