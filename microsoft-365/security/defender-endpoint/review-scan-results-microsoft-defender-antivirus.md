---
title: スキャンの結果をMicrosoft Defender ウイルス対策する
description: アプリ、アプリ、またはアプリを使用Microsoft Endpoint Configuration Manager、Microsoft Intuneスキャンの結果Windows セキュリティする
keywords: スキャン結果、修復、フル スキャン、クイック スキャン
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 10/18/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.collection: M365-security-compliance
ms.openlocfilehash: 8727baa9bb1935a1186907ca5f3d9d4f82dad6d4
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64473653"
---
# <a name="review-microsoft-defender-antivirus-scan-results"></a>スキャンMicrosoft Defender ウイルス対策確認する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

オンデマンドスキャンMicrosoft Defender ウイルス対策スケジュールされたスキャンの場合でも、スキャンが完了すると[](run-scan-microsoft-defender-antivirus.md)、結果が記録[](scheduled-catch-up-scans-microsoft-defender-antivirus.md)され、結果を表示できます。 


## <a name="use-configuration-manager-to-review-scan-results"></a>Configuration Manager を使用してスキャン結果を確認する

詳細については[、「ユーザーの状態をEndpoint Protectionする」を参照してください](/configmgr/protect/deploy-use/monitor-endpoint-protection)。

## <a name="use-powershell-cmdlets-to-review-scan-results"></a>PowerShell コマンドレットを使用してスキャン結果を確認する

次のコマンドレットは、エンドポイント上の各検出を返します。 同じ脅威の複数の検出がある場合、各検出は、各検出の時間に基づいて個別に一覧表示されます。

```PowerShell
Get-MpThreatDetection
```

:::image type="content" source="../../media/wdav-get-mpthreatdetection.png" alt-text="PowerShell のコマンドレットと出力" lightbox="../../media/wdav-get-mpthreatdetection.png":::

特定の脅威 `-ThreatID` に対する検出のみを表示する出力を制限する場合に指定できます。

脅威検出を一覧表示するが、同じ脅威の検出を 1 つのアイテムに結合する場合は、次のコマンドレットを使用できます。

```PowerShell
Get-MpThreat
```

:::image type="content" source="../../media/wdav-get-mpthreat.png" alt-text="PowerShell コード" lightbox="../../media/wdav-get-mpthreat.png":::

[PowerShell コマンドレットを](use-powershell-cmdlets-microsoft-defender-antivirus.md)構成して実行する方法の詳細については、「powerShell コマンドレットを構成して実行する Microsoft Defender ウイルス対策」および「[Defender Antivirus コマンドレット](/powershell/module/defender/)」を参照Microsoft Defender ウイルス対策。

## <a name="use-windows-management-instruction-wmi-to-review-scan-results"></a>[Windows管理命令 (WMI) を使用してスキャン結果を確認する

クラスおよび [**クラス** の Get **メソッド** MSFT_MpThreat使用](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)MSFT_MpThreatDetectionします。


## <a name="related-articles"></a>関連記事

- [スキャンと修復の結果をカスタマイズ、開始Microsoft Defender ウイルス対策確認する](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender ウイルス対策 (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)
