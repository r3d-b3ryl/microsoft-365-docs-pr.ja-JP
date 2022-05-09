---
title: Microsoft Defender for Endpoint サービスのオフボード デバイス
description: Microsoft Defender for Endpoint サービスからWindows デバイス、サーバー、非Windows デバイスをオンボードする
keywords: オフボード、Microsoft Defender for Endpointオフボード、オフボード
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
ms.openlocfilehash: c2ec837ebc9fef0aabd2810dbd22db24597c52da
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63322605"
---
# <a name="offboard-devices-from-the-microsoft-defender-for-endpoint-service"></a>Microsoft Defender for Endpoint サービスのオフボード デバイス

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**プラットフォーム**
- macOS
- Linux
- Windows Server 2012 R2
- Windows Server 2016

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-offboarddevices-abovefoldlink)

推奨されるデプロイ方法に応じて、対応する手順に従います。

> [!NOTE]
> デバイスの状態は、オフボードの 7 日後に [非アクティブ](fix-unhealthy-sensors.md#inactive-devices) に切り替えられます。
>
> オフボードされたデバイスのデータ (タイムライン、アラート、脆弱性など) は、構成された [保持期間](data-storage-privacy.md#how-long-will-microsoft-store-my-data-what-is-microsofts-data-retention-policy) の有効期限が切れるまでポータルに残ります。
>
> デバイスのプロファイル (データなし) は、180 日以内に [デバイス一覧](machines-view-overview.md) に残ります。
>
> さらに、過去 30 日間にアクティブになっていないデバイスは、組織の脅威と脆弱性の管理[公開スコア](tvm-exposure-score.md)と Microsoft Secure Score for Devices を反映したデータには考慮されません。
>
> アクティブなデバイスのみを表示するには、 [センサーの正常性状態](machines-view-overview.md#use-filters-to-customize-the-device-inventory-views)、 [デバイス タグ](machine-tags.md) 、または [マシン グループ](machine-groups.md)でフィルター処理できます。

## <a name="offboard-windows-devices"></a>オフボード Windows デバイス

- [ローカル スクリプトを使用してデバイスをオフボードする](configure-endpoints-script.md#offboard-devices-using-a-local-script)
- [グループ ポリシーを使用してデバイスをオフボードする](configure-endpoints-gp.md#offboard-devices-using-group-policy)
- [モバイル デバイス管理ツールを使用してデバイスをオフボードする](configure-endpoints-mdm.md#offboard-and-monitor-devices-using-mobile-device-management-tools)

## <a name="offboard-servers"></a>オフボード サーバー

- [オフボード サーバー](configure-server-endpoints.md#offboard-windows-servers)

## <a name="offboard-non-windows-devices"></a>オフボード非Windows デバイス

- [オフボード非Windows デバイス](configure-endpoints-non-windows.md#offboard-non-windows-devices)
