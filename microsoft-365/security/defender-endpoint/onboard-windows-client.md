---
title: Windows クライアントのオンボードを行う Defender for Endpoint
description: Windows クライアントをオンボードします。
keywords: オンボード, Microsoft Defender for Endpointオンボード, sccm, グループ ポリシー, mdm, ローカル スクリプト, 検出テスト
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365-initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 60b7e78902dff29278e3fe960e016e38c10cf296
ms.sourcegitcommit: 5e5c2c1f7c321b5eb1c5b932c03bdd510005de13
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2022
ms.locfileid: "66822168"
---
# <a name="defender-for-endpoint-onboarding-windows-client"></a>Windows クライアントのオンボードを行う Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [エンドポイントのデータ損失防止](/microsoft-365/compliance/endpoint-dlp-learn-about)
- [インサイダー リスク管理](/microsoft-365/compliance/insider-risk-management)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https:%2F%2Faka.ms%2FMDEp2OpenTrial)

サポートされているデバイスのいずれかをオンボードするには、Defender for Endpoint ポータルのオンボード セクションを確認する必要があります。 デバイスに応じて、適切な手順と、デバイスに適した管理および展開ツールのオプションが提供されます。

Defender for Endpoint サービスがセンサー データを取得できるように、組織内のデバイスを構成する必要があります。 組織内のデバイスを構成するために使用できるさまざまな方法と展開ツールがあります。

一般に、オンボードしているクライアントを特定し、デバイスまたは環境に適した対応するツールに従います。

:::image type="content" source="images/onboarddevices.png" alt-text="デバイスのオンボード" lightbox="images/onboarddevices.png":::

## <a name="related-topics"></a>関連項目
- [Microsoft Intuneを使用して Windows デバイスをオンボードする](configure-endpoints-mdm.md)
- [グループ ポリシーを使用してデバイスをオンボードする](configure-endpoints-gp.md)
- [ローカル スクリプトを使用した Windows デバイスのオンボード](configure-endpoints-script.md)
- [非永続的な仮想デスクトップ インフラストラクチャ (VDI) デバイスのオンボード](configure-endpoints-vdi.md)