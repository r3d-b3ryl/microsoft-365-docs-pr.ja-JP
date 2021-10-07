---
title: Microsoft Defender for Endpoint サービスのオフボード デバイス
description: オンボード Windows、サーバー、Microsoft Defender for Endpoint サービスWindowsデバイス以外のデバイス
keywords: offboarding, Microsoft Defender for Endpoint offboarding, offboarding
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 8a84885f26273a731bbda72f81c51502aa137b21
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60168220"
---
# <a name="offboard-devices-from-the-microsoft-defender-for-endpoint-service"></a>Microsoft Defender for Endpoint サービスのオフボード デバイス

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**プラットフォーム**
- macOS
- Linux
- Windows Server 2012 R2
- Windows Server 2016

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-offboarddevices-abovefoldlink)

使用する展開方法に応じて、対応する手順に従います。

> [!NOTE]
> オフボード後、デバイスの状態 [は非アクティブ](fix-unhealthy-sensors.md#inactive-devices) 7 日に切り替えられます。
>
> オフボードされたデバイスのデータ (タイムライン、アラート、脆弱性など) は、構成された保持期間が経過するまでポータル [に](data-storage-privacy.md#how-long-will-microsoft-store-my-data-what-is-microsofts-data-retention-policy) 残ります。
>
> デバイスのプロファイル (データなし) は、デバイス[](machines-view-overview.md)リストに 180 日間以上残ります。
>
> また、過去 30 日間にアクティブではないデバイスは、組織の 脅威と脆弱性の管理 露出スコアと Microsoft Secure Score for Devices[](tvm-exposure-score.md)を反映するデータには考慮されません。
>
> アクティブなデバイスのみを表示するには、正常性状態、[](machines-view-overview.md#health-state)デバイス タグ、または[コンピューター グループで](machine-tags.md)[フィルター処理できます](machine-groups.md)。

## <a name="offboard-windows-devices"></a>オフボード Windows デバイス

- [ローカル スクリプトを使用してデバイスをオフボードする](configure-endpoints-script.md#offboard-devices-using-a-local-script)
- [グループ ポリシーを使用してデバイスをオフボードする](configure-endpoints-gp.md#offboard-devices-using-group-policy)
- [モバイル デバイス管理ツールを使用してデバイスをオフボードする](configure-endpoints-mdm.md#offboard-and-monitor-devices-using-mobile-device-management-tools)

## <a name="offboard-servers"></a>オフボード サーバー

- [オフボード サーバー](configure-server-endpoints.md#offboard-windows-servers)

## <a name="offboard-non-windows-devices"></a>オフボードの非Windowsデバイス

- [オフボードの非Windowsデバイス](configure-endpoints-non-windows.md#offboard-non-windows-devices)
